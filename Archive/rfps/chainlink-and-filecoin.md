NOTE (12/18/2021): The following RFP has now been closed. If you wish to apply for a grant to fund your work, please apply instead via the [Filecoin Dev Grants Program](https://github.com/filecoin-project/devgrants).

# Chainlink x Filecoin

This is a Request for Proposals for projects that accelerate development of [hybrid smart contracts](https://blog.chain.link/hybrid-smart-contracts-explained/) combining Chainlink’s decentralized oracles and Filecoin’s decentralized storage within a single application.

Hybrid smart contacts leverage code running on the blockchain (on-chain) with data and computation from outside the blockchain (off-chain). By bringing together Filecoin and Chainlink, developers can build end-to-end decentralized applications that have cost-efficient and immutable storage capabilities along with a universal and secure connection to external resources. As part of a prior collaboration, Chainlink and Filecoin have already been working on [Chainlink External Adapters](https://filecoin.io/blog/posts/filecoin-and-chainlink-integration/) to facilitate bi-directional communication between the two projects. 

[Chainlink](https://chain.link/) is a decentralized oracle network that expands capabilities of smart contracts by enabling access to real-world data and off-chain computation while maintaining the security and reliability guarantees.

[Filecoin](https://filecoin.io/) is a decentralized peer-to-peer storage network, allowing anyone to store and validate large-scale data as part of a global, 8-exabyte (and growing) network. Under the hood, all Filecoin nodes use the InterPlanetary File System (IPFS), a content-addressed protocol for storing and sharing data.

This RFP is looking to deepen the integrations between Chainlink and Filecoin. In essence, the co-sponsored grants are for developers who are extending the Web3.0 stack beyond on-chain computation and into decentralized off-chain computation, data, and storage. 

This joint grant initiative will support up to five teams building superior hybrid smart contract applications powered by tamper-proof file storage and universal connectivity. 

Here are a few examples of possible hybrid smart contract applications, but we encourage all proposals combining Chainlink and Filecoin to apply:

## 1. **Filecoin Miner Insurance**
Chainlink oracles can inform external smart contracts when a Filecoin miner is unreliable. If the oracles cannot retrieve data from storage or determine the miner is offline, an insurance payout can be automatically issued to policyholders on another blockchain.

## 2. **Data Bounties**
Smart contracts can pool together funds for the storage of a particular piece of data, as characterized by its unique content identifier (CID). The payment is triggered once the proof that it has been stored on the Filecoin Network is relayed from Chainlink oracles.

## 3. **Perpetual Storage**
Smart contracts on other blockchains can fund and verify storage on Filecoin thanks to the bidirectional connection of Chainlink. Contracts can be built on networks like Ethereum where anyone can deposit and fund the storage of data at specific intervals on Filecoin.

## 3. **DeFi Data**
Smart contracts can use Chainlink’s oracles to store extensive amounts of financial data on Filecoin in a tamper-proof manner, which can be delivered on-demand to smart contracts on various blockchains to create more interoperability. 

---

#### Additional Notes

* Proposals may build on Chainlink and Filecoin directly, or use libraries or services that provide abstractions to simplify. For Filecoin, you may use tools and services such [Estuary](https://estuary.tech/), [Fleek Space Daemon](https://github.com/FleekHQ/space-daemon), [NFT.storage](https://nft.storage/), [Textile Powergate.](https://github.com/textileio/powergate/), et cetera. For Chainlink, you may find the [Chainlink developer resources](https://chain.link/developer-resources) and [docs](https://docs.chain.link/) useful.
* Projects outside these listed areas are welcome and encouraged to apply for grant funding via the [Filecoin Dev Grants](https://github.com/filecoin-project/devgrants/) program.

#### Proposal Guidelines

We generally fund projects that can be built in a 6-week to 3-month timeframe. Proposals are evaluated based on:
* The quality of the proposal and near-term value to the Filecoin and Chainlink’s ecosystems
* Your team’s technical experience, prior open source contributions and interest in diving into how Filecoin works
* Likelihood that your team will continue to commit to maintaining your project for one year or longer

All work funded via these grants must be open sourced via the MIT license.

#### Proposal Requirements

Proposals should include a value proposition about how it will benefit the Filecoin ecosystem, technical detail about what your team intends to build and evidence your team is capable of creating good, re-usable open source code, compelling product demos and great documentation, and a reasonable technical development plan broken down into milestones. Here's a [good sample proposal](https://github.com/filecoin-project/devgrants/pull/254).

Proposals should include:

* Project Description
* Brief description
* Value to the Filecoin and Chainlink ecosystems
* Deliverables
* An explanation of your technical solution and architecture
* Imagine that an experienced software developer will evaluate your proposal
* Milestones & Funding requested (most projects have 2-4 milestones)
* Budget and estimated timeframe for each milestone
* Team
* Roles and Experience

Teams with a history of high-quality open source software, with live applications and products, are preferred.

To submit a proposal, follow the steps to [submit a proposal for an RFP](https://github.com/filecoin-project/devgrants/#submit-a-proposal-for-an-rfp) by **Friday December 17, 2021** for consideration. Applications will be evaluated on a rolling basis and early applications are encouraged. 
