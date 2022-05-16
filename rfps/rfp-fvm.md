# FVM Tooling & Infrastructure

We are seeking proposals for various developer and infrastructure tooling to extend the functionality and usability of the [Filecoin Virtual Machine](https://github.com/filecoin-project/ref-fvm) (FVM).

## Overview

The Filecoin Virtual Machine (FVM) aims to combine smart contracts with co-location of storage and compute capabilities.

The FVM is a WASM-based polyglot execution environment for IPLD data. It is designed to support native Filecoin actors written in languages that compile to WASM, as well as smart contracts written for foreign runtimes including the Ethereum Virtual Machine (EVM), Secure EcmaScript (SES), and eBPF.

Refer to [FVM Website](https://fvm.filecoin.io/) for more details on the possibilities FVM will unlock, the current roadmap and links to the current [reference FVM and SDK](https://github.com/filecoin-project/ref-fvm) written in Rust.

We want to build the best tech and tooling available to help enable future developers to build the use cases they envision on the FVM easily and seamlessly.

We are therefore seeking proposals for various developer and infrastructure tooling to extend the functionality and usability of the FVM.

These projects are critical to build the set of tools that we would need to provide in order to have an end-to-end builders process for people who are deploying smart contracts on FVM.

The projects needed include (but are not limited to):

- SDK's

  - High-level Rust
  - Go
  - AssemblyScript
  - Kotlin
  - Swift
  - Others

- Native Tooling & Developer Tooling
  - Local runtime tools and developer environments (like ethereum's Hardhat)
  - Debugging & Testing tools
  - Deployment flow tooling
  - Testnets, Faucets, RPC Endpoints & local nodes
  - Smart contract playgrounds and standards (for example OpenZeppelin and Remix type applications)
  - Foreign Runtime Bridges (including EVM) & Oracles
  - Wallets and wallet integrations

## Description

The FVM is an integral and high-priority project for extending the functionality of Filecoin by bringing storage solutions to the blockchain and executing computation jobs or data pipelines on globally distributed data by pushing compute to the edges and coordinating its execution.

Examples of future ideas include: async programming via continuations/futures, capability-orientation, time-locked transactions (using external beacons), parallel execution, native primitives for cross-chain interoperability, computation correctness proofs, and more.

These projects are essential to build the minimum set of tools that we would need to provide in order to have an end-to-end builders process for people who are deploying smart contracts on FVM.

## Deliverables

Teams should provide a clear outline of the scope of the work and milestones along with a time-frame for completing these with a monetary funding amount requested for each. These can be in the form of a research project and associated reporting, a prototype project or MVP map and associated outcomes and specifications.

Example on Milestones & Funding:
**Total Funding Amount:** List the total proposed funding amount (currently in USD, eventually can be a distribution between USD/FIL)

**Milestones:** Make sure that the values in the Funding column add up to the Total Funding Amount listed above.

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| ------------- | --------------------- | ------- | ------------------- |
| 1             | Example milestone     | $X      | Y weeks             |
| 2             | Example milestone     | $X      | Y weeks             |
| 3             | Example milestone     | $X      | Y weeks             |

## Recommended Team

We are looking for teams and individuals with in-depth knowledge on blockchain infrastructure and high technical skill that want to be deeply involved in the Filecoin ecosystem.

## Acceptance Criteria

Proposal Applications for FVM Tooling and infrastructure will be overseen by a committee consisting of 3 [technical sponsors](https://github.com/filecoin-project/devgrants/blob/master/technical-sponsors.md).

- Raúl Kripalani [@raulk](https://github.com/raulk)
- Dragan Zurzin [@blocksonachain](https://github.com/BlocksOnAChain)
- Alison Haire [@developerally](https://github.com/DeveloperAlly)

### Proposal Guidelines

### Filecoin Dev Grants

We evaluate proposals based on:

- The quality of the proposal and near-term value to the Filecoin ecosystem
- Your team’s technical experience, open source contributions and interest in diving into how Filecoin works
- Likelihood that your team will continue to support the Filecoin ecosystem long-term and commitment to maintaining your project for one year

Note that all proposals must be open sourced via MIT and Apache2 licenses.

## Resources

The following resources may be helpful:

#### General FVM Resources

- [FVM Website with Roadmap](https://fvm.filecoin.io)
- [FVM Reference Implementation](https://github.com/filecoin-project/ref-fvm)
- [FVM Specification](https://github.com/filecoin-project/fvm-specs)
- [FIP Proposal](https://github.com/filecoin-project/FIPs/blob/master/FIPS/fip-0031.md#coordinated-testnets)
- [FVM Early Builders Program Information & Meeting Recordings](https://pl-strflt.notion.site/Welcome-to-the-FVM-Foundry-Early-Builders-Program-0c21aa082a3a48b5b9262d122204d141)
- [Filecoin Project FVM Slack Channel](https://filecoinproject.slack.com/archives/C029MT4PQB1)

#### Application Examples

- Example proposoal from Polyphene: [High-level Rust SDK](https://github.com/filecoin-project/devgrants/issues/562)
- Example proposal from Zondax: [AssemblyScript SDK](https://github.com/filecoin-project/devgrants/issues/582)

#### Tooling ideas

- [FVM Tooling Landscape Thoughts](https://pl-strflt.notion.site/58253a87924e405d84c225d5735db059?v=84dd5cfeb7444512b362139ab6129a11)
