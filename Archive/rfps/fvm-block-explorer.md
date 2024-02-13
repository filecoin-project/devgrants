# RFP: Block Explorer with FVM / FEVM support

## Project Description

Decentralized systems consist of a complex network of nodes that must agree or come to “consensus” on the current state of the broader system. Whether as a storage provider, storage client, developer, token holder or another type of user, it is essential that Filecoin network participants have visibility and observability over the state and the activity of the network and the chain, both real-time and historical.

The Filecoin ecosystem currently has several block explorers including:

* [Filfox.io](https://Filfox.io)
* [Filscan.io](https://Filscan.io)

Additionally it has several public chain analytics and chain data tools including:

* [Spacegap](https://spacegap.github.io)
* [Starboard](https://dashboard.starboard.ventures/dashboard)
* [Filecoin Green](https://filecoin.energy/)
* [Filecoin CID Checker](https://filecoin.tools/)
* [File.app](https://file.app/)

 &nbsp; 
 
Up to now Filecoin has had a basic VM with a limited set of hard-coded, built-in actors only, and this is what the above tooling supports. (Note: actor = smart contract in Filecoin.)

With user programmability arriving to the Filecoin Virtual Machine early next year ([FEVM / FVM roadmap](https://fvm.filecoin.io/#roadmap-4)) we are seeking proposals from talented teams that can build **a new or updated public block explorer to showcase activity and interactions involving user-defined actors (native and EVM smart contracts).** One new key persona that upcoming block explorers should cater to are **developers** building custom actors on Filecoin and the users of their dapps. This will include EVM-compatible actors.

Preference be given to teams that build fully open source explorers so that it is extensible (although we encourage all teams to apply). Aspects we value include (in no particular order): functionality and feature set, usability, ease of use, design, information architecture, linkability, code structure/quality, navigation latency, multi-network support. 


### Data to Display

In addition to what current block explorers support, new functional requirements we would like to see are as follows. (This is a non-comprehensive list, submitters should propose their own.)

* Actor Introspection Tooling for both EVM and native FVM:

  * Actor ABI view (Solidity and native ABIs, standard upcoming)
  * Actor code view: Wasm bytecode, EVM bytecode, and high-level code (verifiable builds necessary)
  * [4byte](https://www.4byte.directory/) integration for function signatures (EVM)
  * Internal transactions (and decoding those)
  * *Note: a technical guide to interpreting FEVM messages and state will be provided by the FVM team soon and linked from this RFP.*


* Transaction data

  * Interpreting and decoding token transfers, internal transactions

* Transaction metadata (function name, message type, value, etc.)

  * Parsing of passed parameters and return values ([example](https://filfox.info/en/message/bafy2bzaceanrw4o6cr4pi7ao77csk2eoq7v2dtujavte2wrnialnxupvkta5i))
  * Support for both EVM and Filecoin addresses (f0, f1, f2, f3, f4)
  * Gas information
  * Logs emitted

* Support for all address classes

  * Displaying all addresses associated with an actor
  * [Including F4 address class](https://github.com/filecoin-project/FIPs/discussions/459) (decomposing the address)
  * Displaying Ethereum address equivalents

* Support for abstract accounts and delegated transactions

  * [Account abstraction](https://github.com/filecoin-project/FIPs/discussions/388) 
     * e.g. Ethereum-style addresses will be supported by the FEVM and translated to Filecoin addresses \
	
* Block explorer

  * High-level network statistics and chain data with the ability to drill down to rich detail 
  * (for a list of potential features see the [original block explorer RFP](https://github.com/filecoin-project/devgrants/blob/d96a38813f99acfb14246d3b84a8833aa42122b2/rfps/rfp-block-explorer.md#data-to-display))
  * Support for information on key actors

* Search

  * Include a universal search bar that allows users to search by address and CID: block height, block hash, transaction message CID, code CID, etc.

* Indexing

  * Show transactions by receiver, sender, etc.

&nbsp;

Additional features that can be implemented with **_future_** FVM updates:

* Use of FVM built-in actor Public API

  * The Filecoin team will be providing a [Public API to all built-in Filecoin actors](https://github.com/filecoin-project/FIPs/discussions/401) that other custom actors can leverage. This is scheduled for initial development in Oct 2022.

* Use of FVM Interface Definition Language

  * The FVM team will provide an interface definition language leveraging codegen for parsing native actor state and method inputs and outputs. See [#fvm-idl](https://filecoinproject.slack.com/archives/C03US7U3800) in Filecoin Slack for current discussions. This will likely be started after FEVM is shipped.

&nbsp;

Other nice to have features to support developers might include:

* Contract source code verification
    * Also see the [Verifiable Builds RFP](https://github.com/filecoin-project/devgrants/blob/master/rfps/fvm-rfp-ideas.md#reproducible--verifiable-builds-for-native-fvm)
    * See Etherscan for a reference
* Contract interactions for developer testing
    * Read-only methods based on ABI first, then
    * Write methods based on ABI
    * See Etherscan for a reference
* Public API other developers can use
    * See [https://eips.ethereum.org/EIPS/eip-3091](https://eips.ethereum.org/EIPS/eip-3091) for standardizing block explorer API routes for wallets
* Token tracker

&nbsp;

NOTE: These are suggestions. We would like teams to be very thoughtful about the work they are doing, and will prefer teams that are thoughtfully choosing what to include in their product as opposed to doing just what we suggest.
.
### Note about Backend Infrastructure

**Relaxed historical scope.** As this may be a new generation explorer the initial goal here is to support FEVM deployment and onwards. It is acceptable for teams to focus on new data ingest at first and start backfilling processes for historical chain data later on. In this interim, deep links to existing explorers could also be used for prior transactions.

There are several existing backends that have performed Filecoin chain ETL since genesis:

- [Lily](https://lilium.sh/) - a TimeScale DB maintained by the Sentinel team at PL but is also intended for network-wide analysis.
- [Filecoin Chain DB](https://docs.zondax.ch/) - also a TimeScale DB maintained by the Filecoin ecosystem collaborator, Zondax. They will be releasing a public self-serve API soon.

While we are open to proposals for improved backend infrastructure from expert teams, re-use of existing infrastructure is recommended to reduce costs and accelerate your project's development timeline. Please talk to us about the above potential options.


&nbsp;

## Deliverables

* Fully functional block explorer website, hosted/maintained/managed by your team. Publicly accessible via a `https://` site.
    * Must also work on mobile and be mobile-friendly
    * Real-time updates based on changes in the network
    * Fast to load
    * Good UX and visual design
* Open-sourced repo for block explorer codebase, dual-licensed under [LICENSE-MIT](https://github.com/filecoin-project/devgrants/blob/master/LICENSE-MIT) and [LICENSE-APACHE](https://github.com/filecoin-project/devgrants/blob/master/LICENSE-APACHE) (see this [License section](https://github.com/filecoin-project/devgrants#license) for how it can look)
* Well-documented codebase so anyone can learn from your application development process
* User-facing documentation for anyone to spin up your block explorer locally

&nbsp;

## Milestones & Funding

Please propose a budget in your proposal. 

(Teams can also share their budgets privately with the FVM team by emailing eva [at] protocol.ai).

Example:

<table>
  <tr>
   <td><strong>Milestone No.</strong>
   </td>
   <td><strong>Milestone Description</strong>
   </td>
   <td><strong>Funding</strong>
   </td>
   <td><strong>Estimated Timeframe</strong>
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>High-fidelity design mockups, running staging site with some UI elements implemented
   </td>
   <td>TBD
   </td>
   <td>3 weeks
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td>Initial implementation of block explorer
   </td>
   <td>TBD
   </td>
   <td>6 weeks
   </td>
  </tr>
  <tr>
   <td>3
   </td>
   <td>Project deliverables are open sourced and made public (live website, documentation, codebase)
   </td>
   <td>TBD
   </td>
   <td>2 weeks
   </td>
  </tr>
  <tr>
   <td>4
   </td>
   <td>Iterative improvements with plans for native FVM updates next year
   </td>
   <td>TBD
   </td>
   <td>4 weeks
   </td>
  </tr>
  <tr>
   <td>5
   </td>
   <td>Ongoing maintenance updates
   </td>
   <td>TBD
   </td>
   <td>Ongoing
   </td>
  </tr>
</table>


Total Funding Amount: TBD

&nbsp;

## Recommended Team

Please provide links to your team members' Githubs or LinkedIn profiles.

* A team with strong design and web development skills (please show evidence of this in your proposal) and experience creating production blockchain applications
* Experience extracting metadata from a blockchain or a complex tech back-end
* Solid knowledge of Filecoin chain data structures

&nbsp;

## Resources

* [Filecoin brand card](https://www.figma.com/file/SujAdL1z8HBPHUuQTxExbv/Filecoin-brand-sheet-public?node-id=0%3A1)
* [FVM website](https://fvm.filecoin.io)
* Technical guide to interpreting FEVM messages and state *(coming soon)*

&nbsp;

## How to apply

To submit a grant proposal, please open a <a href="https://github.com/filecoin-project/devgrants/issues/new?assignees=realChainLife&labels=RFP&template=rfp-application.md&title=RFP+Application">new RFP issue</a> in the `filecoin-project/devgrants` repo.
For questions or to submit a private proposal you can also email eva [at] protocol.ai.

You can also contact us via [Filecoin Slack](https://filecoin.io/slack) via the [#fvm channel](https://filecoinproject.slack.com/archives/C029MT4PQB1) or DM @eshon.

&nbsp;

*This RFP was published on Sep 30, 2022. We will begin reviewing applications starting 2 weeks from the publish date, i.e., October 17, 2022.*
