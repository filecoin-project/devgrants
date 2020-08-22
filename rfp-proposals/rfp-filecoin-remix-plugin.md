# RFP Proposal: `Lighthouse`

**Name of Project:** Lighthouse

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-4-rfps.md#crosschain-integrations

**RFP Category:** `devtools-libraries`

**Proposer:** [@vasa-develop](https://github.com/vasa-develop)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

Inspired by the [Quasar](https://github.com/openworklabs/quasar) project, we propose "Lighthouse", a smart contract based FPS storage.

We will also provide a [Remix Plugin](https://github.com/ethereum/remix-plugin) which will act as an UI interface for Lighthouse.

### How Lighthouse Works?

Below is an overview of how Lighthouse will work:

![Lighthouse Architecture](https://i.pinimg.com/originals/1d/10/12/1d1012451e022c64133cfa5535116c5d.png)

1. VulcanizeDB indexes all the smart contracts on any given network (for eg. Ethereum Mainnet)

2. Lighthouse listens to [smart contracts](#contracts) events for the CIDs that a user wants to be stored.

3. The indexed CIDs will then be stored to IPFS+Filecoin networks using [Filecoin-backed IPFS pinning service(s) or (FPS)](https://docs.google.com/document/d/1CcNWIPp-xQr-21W2buN_ZUN7aOA4kWrPFgsUYY0cfuI/edit).

### Contracts

We will have following 4 contracts:

1. `FpsRegistryInterface.sol`: Defines basic functions that should be supported by the `FpsRegistry.sol` contract.
2. `FpsRegistry.sol`: Manages a list of `Fps.sol` contracts. In other words, you can register your FPS in `FpsRegistry.sol`
3. `FpsInterface.sol`: Defines the basic functions that should be supported by the `Fps.sol` contract.
4. `Fps.sol`: Provides functions that augument the functionality of a FPS via the smart contract functions. This includes functions like `addCID`, `listCIDs`, etc.

### Event Indexing

Lighthouse will VulcanizeDB to listen for the contract events and index the relevant inforamtion (like CIDs, FPS config, etc.) that will be used by Lighthouse to store data on the FPS.

### Data Storage

Lighthouse will use the data indexed by the VulcanizeDB to store data with desired configuration in the selected FPS. As an example, we will register a [Textile Powergate](https://docs.textile.io/powergate/) as a FPS.

Summing up, Lighthouse will consist of a Lighthouse node (preferably a Node.js or Typescript project) and infrastructure (VulcanizeDB and Powergate FPS). The Lighthouse node will expose HTTP/websocket endpoints which can be used to access by a HTTP/websocket client node module (js-lighthouse) which can be used by the front end applications (to access the Lighthouse HTTP endpoints).

We will have a Remix Plugin that will act as an UI interface for the Lighthouse node.

## Deliverables

1. Smart Contracts that are listed above.
2. VulcanizeDB infrastructure that listens and indexes the smart contract events. (Will be managed by VulcanizeDB team)
3. A FPS module that stores data from inputs from the VulcanizeDB.
4. A Lighthouse node codebase written in TypeScript/Node.js with unit tests.
5. A HTTP/Websocket client for Lighthouse node (js-lighthouse).
6. A Remix Plugin that serves as an interface for the Lighthouse node.
7. Full Documentation for Lighthouse node.
8. Full Documentation for Remix Plugin.
9. Tutorial for Lighthouse node.
10. Tutorial for Remix Plugin.
11. Demo video for using Lighthouse node.
12. Demo video for using Remix Plugin.

## Development Roadmap

| No. | Milestone                                                                                              | Funding | Estimated Timeframe |
| --- | ------------------------------------------------------------------------------------------------------ | ------- | ------------------- |
| 1   | Writing Smart contracts                                                                                | \$3,000 | 1 week              |
| 2   | Writing the core Lighthouse logic to capture and parse the events from smart contracts via VulcanizeDB | \$3,000 | 1 week              |
| 3   | Add Infura support and make Lighthouse configurable to use either Infura and/or VulcanizeDB            | \$3,000 | 1 week              |
| 4   | Connecting Lighthouse to Powergate instance                                                            | \$6,000 | 2 weeks             |
| 5   | Testing on Ethereum testnet (mainnet-like) environment                                                 | \$3,000 | 1 week              |
| 6   | Creating a Truffle Box                                                                                 | \$4,000 | 2 weeks             |
| 7   | Documentation and Demos                                                                                | \$3,000 | 1 week              |

During the course of the project, I (Vaibhav) will be the developer involved in the project. I will also act as the point of contact to the Filecoin devgrants team for updating them on the progress.

## Total Budget Requested

\$25,000

## Maintenance and Upgrade Plans

I'm ready to maintain the implementation for this year through the mainnet launch (and through any future Filecoin/Ethereum network updates)

# Team

## Contact Info

Email: [vasa@dappkit.io](mailto:vasa@dappkit.io)

## Team Members

- [Vaibhav Saini (vasa)](https://github.com/vasa-develop)

## Team Member LinkedIn Profiles

- [Vaibhav Saini (vasa)](https://www.linkedin.com/in/vasadev/)

## Team Website

[dappkit.io](https://dappkit.io)

## Relevant Experience

Vaibhav has been working in the DWeb space for 3 years. He has been running a startup ([Signy Advanced Technologies](https://signy.io)) since 2018, and multiple open-source projects involving projects like Ethereum, Quorum, Hashgraph, Stellar, IPFS, Filecoin, OrbitDB, and many more.

## Team code repositories

- [ipfs-cluster/js-cluster-client](https://github.com/ipfs-cluster/js-cluster-client): Maintainer of official Javascript client library for the IPFS Cluster HTTP API.

- [Filecoin Shipyard](https://github.com/filecoin-shipyard/): Built a few tutorials for Filecoin Docs.

  - [powergate-pinning-service](https://github.com/filecoin-shipyard/powergate-pinning-service)
  - [lotus-devnet](https://github.com/filecoin-shipyard/lotus-devnet)
  - [filecoin-network-inspector](https://github.com/filecoin-shipyard/filecoin-network-inspector)
  - [meme-marketplace](https://github.com/filecoin-shipyard/meme-marketplace)

- [Cluster Labs](https://github.com/cluster-labs): A suite of open-source projects DWeb focussed on end users, including:

  - [IPFS Cloud](https://github.com/cluster-labs/ipfscloud-web): Google drive using IPFS
  - [Quasar](https://www.youtube.com/watch?v=4HaE7QKvoZM): Search engine for IPFS
  - [IPFS Docs](https://github.com/cluster-labs/ipfscloud-web/tree/production/app/ipfsdocs): Google docs using IPFS
  - [Horizon](https://github.com/cluster-labs/horizon): Dashboard for managing IPFS cluster

- [Dappkit](https://github.com/cluster-labs): Firebase for Web 3.0. Tools, libraries, and infrastructure for Web 3.0 developers.

  - [AvionDB](https://github.com/dappkit/aviondb): A distributed, MongoDB-like database

- A lot of work related to Ethereum, Quorum, and other Blockchains, some of which is [open-sourced](https://github.com/vasa-develop?tab=repositories&q=eth&type=&language=), and some of which is proprietary.
