# FVM Project Ideas

We are seeking proposals for the following RFPs for the Filecoin VM.

#### About the FVM

The Filecoin Virtual Machine is a new and exciting addition to the Filecoin protocol to support user-programmable smart contracts with both EVM-compatible as well as native capabilities. ***It is currently in active development.***

For the current roadmap and timeline, visit [https://fvm.filecoin.io/#roadmap-4](https://fvm.filecoin.io/#roadmap-4)

 &nbsp; 👾 &nbsp; In late Nov. 2022, a preview **Buildernet** testnet with the Filecoin EVM runtime is slated to go live.
 - The community is invited to participate in heavy functional, technical, and security testing.
 - Incentives and bounties may be available for developers and security researchers.

-----

Have a question about an RFP? Ask in [Filecoin Slack](https://filecoin.io/slack) in the `#fvm` channel and flag the technical sponsors.

Interested in applying for an RFP below or have a project idea not listed here? See the [FVM Open Tooling & Infrastructure RFP](fvm-open-tools-infra.md) for guidelines on submitting a proposal.

-----

## *FVM Project Ideas*

- [Reproducible / Verifiable Builds for Native FVM](#reproducible--verifiable-builds-for-native-fvm)
- [Collections / Libraries of common example actors for Native FVM](#collections--libraries-of-common-example-actors-for-native-fvm)
- [Tool for applying test vectors from Ethereum on FEVM](https://github.com/filecoin-project/devgrants/blob/master/rfps/fvm-ethereum-test-vectors.md)
- [Block Explorer with FVM / FEVM support](https://github.com/filecoin-project/devgrants/blob/master/rfps/fvm-block-explorer.md)

*Stay tuned! More RFPs will be posted soon:*

- Local Simulated Filecoin Network Sandbox (RFP coming soon)
- FVM Native developer toolbox (RFP coming soon)
- FVM Actor Interface Definition Language (RFP coming soon)

&nbsp;
-----
&nbsp;

### Reproducible / Verifiable Builds for Native FVM

**Category:** `devtools-libraries`

#### Overview

A tool to verify that, given the source of an actor (Filecoin smart contract) and its build configuration, the Wasm bytecode on chain matches.

**Priority**: P0

#### Description

Given an actor on chain and code CID, it is not possible to verify the source code of that actor. We therefore need a path for:

1. Devs to publish source code for an actor to a repo, and for
2. Users to perform a build using the exact configuration that led to the Wasm bytecode that went on chain when the code was deployed (i.e. reproducible build).

A match between the locally-built Wasm bytecode and what’s on chain will enable users to trust that the code they’re viewing corresponds to the code on-chain.

For Solidity EVM contracts [Sourcify.eth](https://sourcify.dev/) provides this kind of functionality.

The Solana ecosystem’s native Anchor dev tool has a **verify** command for this. In Solana, because building the same native program on different machines may embed machine-specific code into the resulting binary, their tool can verify that the on-chain bytecode matches locally compiled artifacts. The Solana ecosystem also has an online registry for publishing verified builds at [https://anchor.so/programs](https://anchor.so/programs).

We would like to see a similar native verification tool for the Filecoin VM that takes an actor and a set of build params as input to verify some byte code. A Rust actor alone is insufficient to verify a build, since the specific compiler used and build flags used (such as compression levels and optimizations) are required to reproduce the build and verify the bytecode.

For Rust, this could be prototyped using [Filecoin’s built-in actors](https://github.com/filecoin-project/builtin-actors). Using an existing actor that’s already been deployed, a prototype of this tool would take the actor and a specific set of build flags, produce Wasm bytecode, then verify the bytecode’s code CID matches a specific code CID provided as input for verification.

As a start, Rust’s cargo toolchain could be used with a cargo subcommand that might look as follows:

> $ cargo filecoin verify local <codeCID>

Locally, the output is a Wasm bytecode that, after going through the content addressing process, produces a code CID. This command then verifies that the local code CID produced matches the one given as input.

As a second component, the tool could accept any actor on chain from a code CID or a composite for any Filecoin address such as an f2 address (which are reserved for actors) for verification:

> $ cargo filecoin verify chain <codeCID or f2 address>

This command then verifies that the on-chain bytecode for those matches the locally compiled  bytecode’s code CID.

Because FVM will offer a multi-SDK experience, it is likely that actors written in different languages will differ in some ways. For Rust, everything needed for this tool to be written currently exists.

Similar to Anchor, ultimately this tool could also be folded into an umbrella developer tool for the FVM (see the [[WIP] FVM Native developer toolbox spec](https://docs.google.com/document/d/1vCk3Uh5nGoApFcCBxHExrBliBOric_eOp08bkHsiZRc/edit#bookmark=id.oerodtn885fw) RFP for more info).

#### Technical Sponsors

@raulk

#### References

Solana’s Anchor Verify and Registry
- [https://book.anchor-lang.com/anchor_references/cli.html?#verify](https://book.anchor-lang.com/anchor_references/cli.html?highlight=verify#verify)
- [https://book.anchor-lang.com/anchor_references/anchor-toml_reference.html?#registry](https://book.anchor-lang.com/anchor_references/anchor-toml_reference.html?#registry)
- [https://anchor.so/programs](https://anchor.so/programs)

Filecoin Built-in Actors
- [https://github.com/filecoin-project/builtin-actors](https://github.com/filecoin-project/builtin-actors)

&nbsp;
-----
&nbsp;
  
### Collections / Libraries of common example actors for Native FVM

**Category:**

#### Overview
  
Similar to [OpenZeppelin Contracts](https://github.com/OpenZeppelin/openzeppelin-contracts) for EVM, a modular library of reusable foundational native actors for standards implementations such as ERCs, common utilities and access control patterns. This library can be well-audited so that developers can build more advanced actors using secure primitives and not have to reinvent the wheel.
  
**Priority**: P1

#### Description
  
This standard library for FVM could include standards implementations such as ERC20, ERC721, utilities for signature verifications and basic merkle proof verifications, safe math, upgradable actors, etc., access control and ownership patterns and any other secure building blocks that might be useful to the Filecoin actor building community.

We may reasonably expect that whoever takes this on will also initiate discussion and post proposals around standardizing the interfaces of these native actors through **Filecoin Standard Interfaces [TODO - references?].** For example, prototypes of 10 standard interfaces could be submitted along with the proposed suite of actors.

Some example actors in this library might include:

(Inspired by OpenZeppelin Contracts:)

- [Access control](https://docs.openzeppelin.com/contracts/4.x/api/access) actor and standard interface

- Fungible token actor - existing resources:

  - [ERC20 example actor by @raulk](https://github.com/filecoin-project/ref-fvm/pull/290)

  - [Fungible token standard discussion by @anorth](https://github.com/filecoin-project/FIPs/discussions/277)

  - [Helix’s fungible token implementation](https://github.com/helix-onchain/filecoin/tree/main/fil_fungible_token)
  
  - [Zondax's ERC 20 token example for their AssemblyScript SDK](https://github.com/Zondax/fil-erc20-actor-as)

  - Potentially add [ERC777](https://docs.openzeppelin.com/contracts/4.x/erc777) functionality

- Multi-token standard [ERC1155](https://docs.openzeppelin.com/contracts/4.x/erc1155)

- Security primitives

- [Pull payment](https://docs.openzeppelin.com/contracts/4.x/api/security#PullPayment) pattern

- [Reentrancy](https://docs.openzeppelin.com/contracts/4.x/api/security#ReentrancyGuard) guard

- [Pausable](https://docs.openzeppelin.com/contracts/4.x/api/security#Pausable) contracts

(Other possibilities:)

- Name registry actor (ENS?)

- Events actor

- [Governance](https://docs.openzeppelin.com/contracts/4.x/api/governance)

We seek an initial set of actors for this native library. As it gains wider adoption additional actors can be added by the FVM community.

Developers of this library are also encouraged to explore how native Rust communities (like Solana) currently approach this kind of library, in addition to the EVM ecosystem.

Proposal submitters are encouraged to add other ideas to this list, to structure delivery in a progressive manner through several small phases, and to propose actions to promote developer engagement and to socialise their work.

#### Technical Sponsors
  
@raulk

#### References
  
OpenZeppelin Contracts
- [https://github.com/OpenZeppelin/openzeppelin-contracts](https://github.com/OpenZeppelin/openzeppelin-contracts)

&nbsp;
-----
&nbsp;

<!--

### RFP Idea title

**Category:**

#### Overview

#### Description

#### Technical Sponsors

#### References

&nbsp;
-----
&nbsp;

-->
