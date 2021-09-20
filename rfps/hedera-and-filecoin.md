NOTE (09/20/2021): The following RFP has now been closed. 
If you wish to apply for a Grant to fund your work, please apply instead under the [Filecoin Grant Program](https://github.com/filecoin-project/devgrants). There are a variety of grants to fulfil the development stage you are at. 



# Hedera x Filecoin

This is a Request for Proposals for projects that combine Hedera’s efficient, flexible public ledger technology with Filecoin’s large-scale verifiable storage capabilities.

[Hedera](https://hedera.com/) is a decentralized public ledger designed for efficient, low-cost transactions, such as supply chain, verifiable proofs for data, payments, advertising, tokenization of assets, and more. However, it is not optimized for persistent storage of large files or object data.

[Filecoin](https://filecoin.io/) is a decentralized peer-to-peer storage network, allowing anyone to store and validate large-scale data as part of a global, 6-exabyte (and growing) network. Under the hood, all Filecoin nodes use the InterPlanetary File System (IPFS), a content-addressed protocol for storing and sharing data.

Together, there are many possibilities to maximize trust for in-game assets, art, music, supply chain, financial applications, and more. The Hadera HTS demo (https://github.com/hashgraph/hedera-hts-demo/) shows how HTS metadata can be stored on the IPFS and Filecoin networks, via the NFT.storage API.

To encourage new projects that make creative use of these possibilities, Hedera and Filecoin are jointly offering **up to USD $200,000** in grant funding for projects in the following areas:

## 1. **Decentralized Storage SDK for Hedera & Demo Application**
We want to make it easy for builders using Filecoin Storage and Hedera Token Service to integrate the two into their applications. This grant will be awarded for an SDK that seamlessly integrates existing Hedera and Filecoin toolchains. It should enable non-fungible tokenization and allow storage of larger files associated with Hedera Token Service tokens (such as digital art, music, JSON metadata, etc.) on the Filecoin network.

The accompanying demo application must use this SDK to build an open source end-to-end NFT marketplace demo application to 1) Showcase the functionality of the Decentralized Storage SDK and 2) Be used by other developers in the community as a reference architecture. The demo application should include:
1. NFTs created on Hedera.
2. Multimedia associated with the NFT stored on Filecoin.
3. [JSON metadata schema](https://github.com/hashgraph/hedera-improvement-proposal/blob/master/HIP/hip-10.md) associated with those NFTs on Filecoin.
4. Accepting HBAR and FIL (at a minimum) for payment of NFTs.

[Prize: $75,000]

## 2. **Real-world Applications**
These grants will be awarded to proposals for real-world applications that utilize both [Hedera Token Service (HTS)](http://hedera.com/token-service) and Filecoin decentralized storage. Developers can be as creative as they’d like — there are no strict requirements as to the type of application or use case, but it must utilize both Hedera HTS and Filecoin.

[First prize: $50,000; Second prize: $40,000; Third prize: $20,000; Fourth prize: $10,000; Fifth prize: $5,000]

---

#### Additional Notes

* Proposals may build on Hedera and Filecoin directly, or use libraries or services that provide abstractions to simplify such as [Estuary](https://estuary.tech/), [Fleek Space Daemon](https://github.com/FleekHQ/space-daemon), [NFT.storage](https://nft.storage/), [Textile Powergate.](https://github.com/textileio/powergate/), et cetera.
* Projects outside these listed areas are welcome and encouraged to apply for grant funding via the [Filecoin Dev Grants](https://github.com/filecoin-project/devgrants/) program.

#### Proposal Guidelines

We generally fund projects that can be built in a 6-week to 3-month timeframe. Proposals are evaluated based on:
* The quality of the proposal and near-term value to the Filecoin and Hedera ecosystems
* Your team’s technical experience, prior open source contributions and interest in diving into how Filecoin works
* Likelihood that your team will continue to commit to maintaining your project for one year or longer

All work funded via these grants must be open sourced via the MIT license.

#### Proposal Requirements

Proposals should include a value proposition about how it will benefit the Filecoin ecosystem, technical detail about what your team intends to build and evidence your team is capable of creating good, re-usable open source code, compelling product demos and great documentation, and a reasonable technical development plan broken down into milestones. Here's a good sample proposal.

Proposals should include:

* Project Description
* Brief description
* Value to the Filecoin and Hedera ecosystems
* Deliverables
* An explanation of your technical solution and architecture
* Imagine that an experienced software developer will evaluate your proposal
* Milestones & Funding requested (most projects have 2-4 milestones)
* Budget and estimated timeframe for each milestone
* Team
* Roles and Experience

Teams with a history of high-quality open source software, with live applications and products, are preferred.

To submit a proposal, follow the steps to [submit a proposal for an RFP](https://github.com/filecoin-project/devgrants/#submit-a-proposal-for-an-rfp) by August 30, 2021 for priority consideration. We will evaluate later proposals submitted after the deadline as capacity allows.
