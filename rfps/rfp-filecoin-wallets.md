# RFP: Filecoin Wallet & Tools

**Name of Project:** `Filecoin Wallet & Tools`

**Proposal Category:** `app-dev`, `devtools-libraries`

**Proposers:**  @eshon, @jnthnvctr

## Project Description

This RFP has 2 possible tracks:

  - [Track 1: Self-hosted Wallet](#track-1-self-hosted-wallet)
  - [Track 2: Wallet Tools and Integrations](#track-2-wallet-tools-and-integrations)
  
### Track 1: Self-hosted Wallet
--------------------------------
We are seeking proposals for an open source, self-hosted Filecoin wallet application that supports receiving, storing and sending FIL, shows when transactions are confirmed by the network and helps users safely manage their keys.

> NOTE: Nodes have wallet CLIs and APIs that will be further developed to meet the Filecoin Spec (e.g. Multisig wallets). A reference tool for signing raw transactions outside of a node will also be created by the Filecoin team.

The goals of an enhanced open source wallet are to:

- provide the community with an open source implementation that has better UX for non-technical end-users
- ensure good node API coverage for wallet functionality
- help test parts of node APIs that interact with wallets
- reveal additional architectural components of wallet infrastructure that could be open sourced
- provide a reference or re-usable library for future application developers
- provide additional features to improve usability for end-users or developers

There are many types of wallets and many features that could be included. We leave the choice of which would greatly improve usability and adoption up to you.

Possible wallet types and features:

- Web, Mobile, Desktop (or Paper)
- HD (Hierarchical Deterministic) wallets that support multiple addresses from a mnemonic seed
- Secure private key management and storage
- Wallets customized to support Mining
- 2FA or Multi-device backup
- MultiSig wallets
- Air-gapped cold wallet vs. hot wallets
- Support for BLS in addition to secp256k1
- Cross-platform integration
- Suggest additional features


### Track 2: Wallet Tools and Integrations
-------------------------------------------

We are also seeking proposals for open source tools and integrations for wallets. This can include supporting libraries or infrastructure that provide new and existing wallets with important services for integrating with the Filecoin Network or enhanced usability.

Some examples:

- Hardware wallet integration (e.g. [lotus issue #39](https://github.com/filecoin-project/lotus/issues/39))
- Browser integration or with other applications
- Wallet frameworks for app developers
- Gas estimation tools
- Privacy features
- Exchange or swap integration
- Spot pricing tools
- Specialized Wallet API providers
- Suggest additional tools and services

##  Deliverables

An open-sourced, dual-licensed (under MIT and APACHE2) implementation that:

for Track 1:

- enables users to receive and transfer FIL
- supports secure key management, backup and recovery
- shows transactions confirmed by the network
- supports any additional features listed above

for Track 2:

- provides useful features or services to wallet users and/or developers
- is easy to integrate with new and existing wallets
- would help grow adoption or improve security

for both Tracks:

- has a well-documented API
- works with a Filecoin node API (lotus and/or go-filecoin, local or remote) to perform the intended workflow
- has tutorials with demo usage
- is written in a mainstream language to ensure wider adoption, future interoperability and re-use
- has a well-documented, human-readable codebase
- is well-tested and would be convenient to security audit

> NOTE: Node Wallet API improvements and timeline may require further planning with node implementation teams. We will work with node implementers to document relevant API calls and provide coordinated opportunities for questions and feedback.

## Recommended Team

- A small team with strong design and web development skills (please show evidence of this in your proposal)
- Familiarity with creating wallets and supporting signing tools, endpoints and libraries
- Familiarity with using node APIs and a strong desire to help node implementation teams with useful feedback

## Milestones & Funding

**Total Funding Amount:** TBD. Please propose a budget in your proposal.

**Suggested Milestones:**

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Finalize scope, a list of node API endpoints to be used, workflow design, architectural design & UI mockups | TBD | 2-3 weeks |
| 2 | Implementation interoperable with a Filecoin node | TBD | 4-6 weeks |
| 3 | All project deliverables are completed and added to the [Filecoin Shipyard](https://github.com/filecoin-shipyard) (website, documentation, codebase) | TBD | 2 weeks |
| 4 | Maintenance and Upgrades during Testnet and Mainnet | TBD | 2-3 weeks |

## Acceptance Criteria

**Acceptance criteria for Finalize scope, workflow design, architecture & Design mockups:**
- This milestone's deliverables must represent the final design of the service and its intended interoperability with a Filecoin node API and functionality.
- The workflow design should address the core goals proposed in the description of this brief, with a focus on wallet user experience.

**Acceptance criteria for Implementation interoperable with a Filecoin node:**
- The service must enable the functionality specified in Milestone 1 in at least one mainstream language.
- A functioning demo of the service to be presented and testable by the PL team.

**Acceptance criteria for All project deliverables:**
- All of the criteria above have been met.
- A developer on our team can use and test the functionality of this service themselves without needing to talk to anyone.

**Acceptance criteria for Maintenance and Upgrades during Testnet:**
- The application must be usable on the Filecoin Network during Testnet and robust at Mainnet launch.

If a milestone is not satisfactorily met, we may not continue to fund your team for this project.

## Resources

Example open source wallets:
- https://github.com/gnosis/MultiSigWallet
- https://github.com/ConsenSys/eth-lightwallet
- https://github.com/paritytech/fether

[Filecoin Brand Card](https://drive.google.com/open?id=1ynWUBagoUhmIJK4G4J7JKG-G1SceYBaP)

#### Additional Notes

Please refer to the
[Filecoin Specification](https://filecoin-project.github.io/specs/) for further details on the definitions below.

- A WALLET can hold funds and is identified by an Address.

- An ADDRESS maps to one public/private key pair and can state a balance. An Address may reference a Wallet or Miner, or any Actor. An Address may be in BLS or secp256k1.

- ACTORS can hold funds and are similar to smart contracts - their code is run in the VM where transactions are processed. This may include Miners, the StorageMarket, Wallets, Actors, Payment Channels, etc.

- A MULTISIG WALLET ACTOR exists and requires a configurable number of signatures on transactions. It can be used for sharing funds, backup and can release funds over time.

Concepts specific to Mining:

- An OWNER ACCOUNT is an abstraction intended to represent an Owner of multiple Miner workers. They would likely be offline most of the time to keep their private keys secure. The Owner Account is authorized to control a Miner, and its Address is where mining rewards can be sent.

- PEER IDs (from [libp2p]([libp2p.io](https://docs.libp2p.io/concepts/peer-id/))) of nodes also have public-private keys. A Peer ID could be changed have incoming deals for a particular Miner be routed to a different machine.

----
**Questions about this RFP?**

Contact @eshon or ask in the [Filecoin DevGrants forum](https://discuss.filecoin.io/c/devgrants).
