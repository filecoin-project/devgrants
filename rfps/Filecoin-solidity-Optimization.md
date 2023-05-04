# Filecoin-solidity: Optimization, Improvement, Maintenance

Category: devtools-libraries for FEVM

Project priority: P0

RFP content:
- Overview and goals
- Epic: Compatibility with compiler optimizers 
- Epic: Implementing backlog items 
   * Enable read-only “view” methods for protocol accessors 
   * Propagate exit codes 
   * Unblock other backlog items 
- Epic: Developer ergonomics 
- Epic: Bytecode and gas reduction 
- Epic: Improving testing 
- Epic: Network upgrade evolution, OSS stewardship/maintenance


### Overview and goals
The purpose of this proposal is to outline additional work that should be done in order to improve and optimize the current state of our [filecoin-solidity libraries](https://github.com/Zondax/filecoin-solidity), as well as establish continued maintenance and OSS stewardship for this common good.

For context, the current version was very successful in providing low-level access to Filecoin protocol methods, actors, and state, to the initial wave of applications deployed on FEVM following its mainnet launch on March 14, 2023.

However, there are a number of core areas that can be improved, namely enabling optimizability, mirroring the ergonomics of popular Solidity libraries (e.g. OpenZeppelin), and minimising footprint. Furthermore, there’s an active backlog of smaller issues that need to be fixed as part of continued maintenance. We aim to make 

This means minimizing footprint, increasing compatibility with Solidity developer tools, and mirroring the ergonomics of writing Solidity code that is standard across the industry.

### Epic: Compatibility with compiler optimizers
There is at least one case where the [BigNumber](https://github.com/zondax/solidity-bignumber/blob/39dbb9e2dd186a549c9ad7eb1b4b204dc6705245/src/BigNumbers.sol#L880) library uses msize, which is incompatible with solc’s Yul optimizer. [See issue](https://github.com/Zondax/filecoin-solidity/issues/295).

This incompatibility fully disarms the Yul optimizer for the entire compilation, infecting other developer contracts within the same build, as well as consumed libraries (e.g. OpenZeppelin).

This results in larger contract sizes, higher deployment costs, and potentially high gas fees on execution. Because the Filecoin EVM inherits the Ethereum’s EVM 24KiB size limitation, this bloat may render contracts undeployable.

Success Criteria: The filecoin-solidity library works seamlessly with all types of optimizers, including Standard, YUL, and –via–ir optimizers. Refer to the [Optimizers](https://docs.soliditylang.org/en/v0.8.19/internals/optimizer.html) Solidity help page.

### Epic: Implementing backlog items
#### Enable read-only “view” methods for protocol accessors 
See [this issue](https://github.com/Zondax/filecoin-solidity/issues/368). The callByAddress and callByID methods in Actor.sol use delegatecall, thus obeying the requirements of the [relevant Filecoin precompiles](https://github.com/filecoin-project/builtin-actors/blob/2fa978c5a8a3da6112542b127e5db853f6be4cdf/actors/evm/src/interpreter/precompiles/fvm.rs#L130-L132). However, this signals to solc that the method can possibly mutate state, preventing functions from being declared as view (and therefore invocable through eth_call).

An example of how this can be done is shown in a different, filecoin-related project and it can be found [here](https://github.com/wadealexc/fevmate/blob/main/contracts/utils/CallNative.sol#L53).

Success Criteria: If a smart contract utilizes read-only actor methods, the public method can be labeled as view and the compiler will respect it.
#### Propagate exit codes
See [this issue](https://github.com/Zondax/filecoin-solidity/issues/363). Protocol methods convey information through exit codes. However, the library currently swallows the exit code and unconditionally reverts, making it impossible for developers to handle errors. This needs to be fixed.
#### Unblock other backlog items
Besides the above issue, view the current state of the [backlog](https://github.com/Zondax/filecoin-solidity/issues?q=is%3Aissue+is%3Aopen+sort%3Aupdated-desc) and take actions to unblock it (implement, 

### Epic: Developer ergonomics
You should assess developer ergonomics of the current library versus other popular libraries.

Some ideas to improve ergonomics include:

* Struct-wrapped params versus flat parameters (where it makes sense). In many parts of the filecoin-solidity library, additional object-based structures and Params objects are used in favor of more input parameter lists, and return types. Two examples:
* SendAPI takes a CommonTypes.FilAddress, which is ultimately just bytes. Instead of just taking a native bytes object, a developer would have to create CommonTypes.FilAddress on the stack, and then either read or write the bytes themselves.
* GetOwnerReturn object can be represented as (bytes, bytes), allowing for terser code, smaller bytecode footprint, and a more native inspection of the underlying types themselves. There are likely cases where this approach is warranted (PendingBeneficiaryChange), but there are also many cases where it is an overkill.
For most operations, using Structs for parameters or return objects should reflect usability improvements and not the standard way to interact with Filecoin APIs. Remaining structs should be logical concepts (like EpochTimeFrame), and be non-duplicative across use cases. For instance, there are some structures which have the exact same members, but are called different things. 
Newly introduced individual parameters should be properly documented in the solidity smart contract library so developers can inspect the code to know how to use them, instead of trying to find the documentation or comments for the Lotus Actor code.
* Consolidating types and callers for built-in actors in self-contained files. Right now these are split across packages, which forces the user to import multiple files just to make a call.
* More accurate and detailed documentation of Solidity methods in solidity-docgen format.
### Epic: Bytecode and gas reduction
Once the above is solved and code can be duly optimized, you should focus on bytecode size and gas optimizations. You should identify hotspots, and create a benchmark that enables you to track and measure the incremental improvements you make.

Potential areas of focus include:

* Import and dependency structure across components.
* CBOR serde.
* Data type serialization (e.g. CID hacks).
* Performance hotspots.

Success Criteria: Demonstrable, iterative improvements to both deployment and runtime gas costs.

Example benchmark: The [FilForwarder](https://github.com/lotus-web3/FilForwarder), which is a single line contract that exposes the SendAPI, is 4.36KB un-optimized, and 3KB optimized at 1,000,000 runs. This is roughly 1/6th of the contract limit size to send FIL. In comparison, a single line contract to send FIL from one eth address to another (and not relying on Filecoin.sol), is 0.492 KB, or roughly 1/8th of the size of the filecoin-solidity counterpart.
### Epic: Improving testing
The current testing approach instantiates a ref-fvm with builtin-actors to perform full integration testing. While this works great for end-to-end testing, for smaller utility functions that do not touch the protocol (e.g. data type conversions, serialization logic), this is overkill and too coarse-grained. We need to introduce Solidity unit testing, possibly facilitated by hardhat.
### Epic: Network upgrade evolution, OSS stewardship/maintenance
As a part of this project application, teams that are applying to make the development changes should also take into account and consider the maintenance aspect that they would need to provide after they are done implementing the solutions from the RFP.

Development teams that are applying should support the library in the coming months as code owners. As we continue to cycle changes in and hone the library it is important to maintain contextual continuity.

Scope:

* Monitor issues created in the filecoin-solidity repo, keep the backlog organized, and work on implementing the solutions.
* Be an excellent OSS maintainer, have a helpful attitude, and support devs in their usage of the library on GitHub, Filecoin Slack, and other support channels.
* Proactively respond and shepherd PRs to completion.
* Update the filecoin-solidity library on an ongoing basis as the interface of the built-in actors evolves, making sure that things stay backwards compatible as well.
* Consistently produce new releases with detailed changelogs.
