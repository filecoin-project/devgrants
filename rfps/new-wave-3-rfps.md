<p align="center">
  <img src="https://github.com/filecoin-project/devgrants/blob/master/img/triangles.png" width="80px">
</p>


# New RFP Ideas for Wave 3

As Filecoin gets ready for mainnet launch in a [few months](https://filecoin.io/blog/roadmap-update-february-2020/) ([gantt chart](https://app.instagantt.com/shared/s/1152992274307505/latest)), we are seeking proposals for the following RFPs for Wave 3 of the Dev Grant program.

Deadline for Wave 3 proposals: **April 15th, 2020 23:59 PDT**

## RFP Ideas

- High Priority
  - [Storage client application with erasure coding and basic PGP](#storage-client-application-with-erasure-coding-and-basic-pgp)
  - [Simple Storage webapps](#simple-storage-webapps)
  - [Filecoin CID Checker and Storage Oracle](#filecoin-cid-checker-and-storage-oracle)
  - [Filecoin Chain State Explorer](#filecoin-chain-state-explorer)
  - [Resumable Data Uploads with GraphSync](#resumable-data-uploads-with-graphsync)

- Other Ideas
  - [Diagram the Filecoin Blockchain](#diagram-the-filecoin-blockchain)
  - [Storage and Retrieval Market Order Books](#storage-and-retrieval-market-order-books) *
  - [Web archiving browser extension or Twitter bot](#web-archiving-browser-extension-or-twitter-bot)
  - [SDKs in various mainstream programming languages](#sdks-in-various-mainstream-programming-languages)
  - [S3 (Glacier) API for Filecoin](#s3-glacier-api-for-filecoin) *
  - [Proxy re-encryption library and service](#proxy-re-encryption-library-and-service)
  - [FLOPy AWS Snowball-like hard drive service](#flopy-aws-snowball-like-hard-drive-service)
  - [Ganache-like UI or improved tooling for running a FIlecoin Devnet](#ganache-like-ui-or-improved-tooling-for-running-a-filecoin-devnet)
  - [GraphQL API for lotus-chainwatch](#graphql-api-for-lotus-chainwatch)
  - [Storage Workflow User Research](#storage-workflow-user-research)
  - [Snarks as a Service](#snarks-as-a-service) *
  - [Cross chain integrations](#cross-chain-integrations)
  - [VM research - verifiable subsets of WASM-able languages](#vm-research---verifiable-subsets-of-wasm-able-languages)
  - [VM research - Improving state tries](#vm-research---improving-state-tries)
  - [Expert use of large data archives](#expert-use-of-large-data-archives)

still open *

We also accept **Open Grant Proposals** where you can suggest your own Filecoin project idea.

See our [Proposal Guidelines](#proposal-guidelines) below about how to apply.

*Have a question about any of these RFPs? Email devgrants@filecoin.org*


&nbsp;

------


## *High priority RFP ideas*

&nbsp;

### Storage client application with erasure coding and basic PGP

**Project Description**

A storage client application with an easy-to-understand interface and nice UX that has support for basic file encryption and erasure coding to suggest an ideal number of redundant storage deals. The application should allow users to encrypt data, enter into storage deals with several miners, retrieve and decrypt the data.

**Proposed Features**

- encrypts and decrypts a file using basic PGP (e.g. [Keybase example](https://keybase.io/encrypt) or with MetaMask keys or other options)
- calculates recommended redundancy using a good erasure coding library (e.g. [zfec](https://github.com/tahoe-lafs/zfec)) and can reconstruct data if a copy cannot be retrieved
- enters into a recommended number of storage deals
- can range from a simple single-page webapp with a simple drag n’ drop interface to a desktop application
- decentralized application or dapp although it can assume public hosted Filecoin node JSON RPC API endpoints exist
- optionally can also split larger files into smaller pieces
- optionally can also use [this Filecoin signing tools library](https://github.com/zondax/filecoin-rs) or [the Filecoin JS API](https://github.com/filecoin-shipyard/js-lotus-client) (both are currently WIP)

Your proposal should provide examples of applications and user interfaces your team has built and links to their code repositories.

&nbsp;

### Simple Storage webapps

**Project Description**

Single page apps that demonstrate using Filecoin to store and retrieve files. Example workflow: drag + drop a file, pay to store it, retrieve it. Show miner info, CIDs.

One version could eli5 (explain-it-like-I'm-5) to new users as a tutorial or tour.

Your proposal should provide examples of applications and interfaces your team has built and links to their code repos.

Also see [Filecoin community resources](https://github.com/filecoin-project/docs/wiki) for an initial list of Filecoin developer tools.

&nbsp;

### Filecoin CID Checker and Storage Oracle

**Project Description**

A website and API service that can list all CIDs along with their current status in the latest state tree.

The page could also support queries by CID or miner. One option would be to build 1 long table that shows each miner x sectors they are storing x state as a colored indicator:

green - good
grey - capacity
red - failing

Benefits:
- This site and API could be used as an oracle of storage status that anyone can run alongside a full node.
- For retrieval miners, this indexes from which storage miners they can retrieve requested CIDs.
- For storage miners, this indexes redundant copies being stored with other storage miners, in case they need to retrieve data cheaply due to data corruption or loss.
- Also see this [Slack discussion](https://filecoinproject.slack.com/archives/CEHHJNJS3/p1585159620012300).

&nbsp;

### Filecoin Chain State Explorer

**Project Description**

An interactive visual tool to dive into the Filecoin state trie would help protocol developers and researchers do in-depth analysis. The 1st level could be an interpretation of the actual tree and include key Actors, a map of the HAMT data structure, etc. Currently a latest trie snapshot is ~10GB.

Also see the RFP for Diagram the Filecoin blockchain

Existing tools:
- The lotus node implementation of Filecoin has a Postgres database tool called chainwatch on top of which a visual chain explorer has been built.
- Several block explorers for Filecoin (filscan.io, filscout.io, filplorer.com) have been developed
- Filecoin’s state trie is unique but this [Ethereum state trie diagram](https://i.stack.imgur.com/s6yKz.png) provides an example of what may be involved

Preferred applicants should be able to work independently and learn how the Filecoin state trie is structured using the [Filecoin Specification](https://filecoin-project.github.io/specs/) and the various Filecoin node implementations.

&nbsp;

### Resumable Data Uploads with GraphSync

**Project Description**

When a storage client sends data to a miner, interruptible data transfer and resume can provide end-to-end convenience for all users, particularly for larger files. Code around GraphSync could make this available to users. An example tool for resumable uploads is [tus.io](tus.io), although the goal of this project is to build something using IPFS data structures as a foundation.

GraphSync is a protocol for synchronizing IPLD graphs among peers. (For more information, see the [GraphSync spec](https://github.com/ipld/specs/blob/master/block-layer/graphsync/graphsync.md) and [go implementation](https://github.com/ipfs/go-graphsync).

Preferred applicants should have a solid understanding of underlying IPFS data structures and should invest time in learning about GraphySync and how Graphsync currently works in Filecoin.

&nbsp;

-------

## *Additional RFP Ideas*

&nbsp;

### Diagram the Filecoin Blockchain

**Project Description**

Diagrams of the Filecoin blockchain at the level of detail and visual quality of Lee Thomas’ [diagram of the Ethereum Yellow paper](https://i.stack.imgur.com/afWDt.jpg) and [state trie](https://i.stack.imgur.com/s6yKz.png) [[Source](https://ethereum.stackexchange.com/questions/268/ethereum-block-architecture)].

Preferred applicants should be able to work independently and learn how the Filecoin blockchain is structured using the [Filecoin Specification](https://filecoin-project.github.io/specs/) and the various Filecoin node implementations.

&nbsp;

### Storage and Retrieval Market Order Books

**Project Description**

Although storage deals are on chain, storage market asks in which miners create price offers for their storage are off chain in Filecoin. Order books could aggregate storage and retrieval asks as a convenience to storage clients seeking to make deals and improve global awareness of pricing. 

Order books may be decentralized protocols or single-operator services.
To learn more see https://filecoin-project.github.io/specs/#discovery.

&nbsp;


### Web archiving browser extension or Twitter bot

**Project Description**

A browser extension that allows users to archive websites to IPFS and backup to Filecoin. This extension could also provide a Filecoin wallet so that users can pay for archival and as a way to keep track of what they have saved. 

In the future this could be expanded to ways to collaborate on and share archived bookmarks in online communities or as bookmarking services (e.g. [Pinboard](https://pinboard.in), Pinterest, etc.)

A Twitter bot such as the former [Link Archiver](https://twitter.com/LinkArchiver) could automatically archive websites from tweeted links.

This project would need to explore the required infrastructure for these services.

&nbsp;

### SDKs in various mainstream programming languages

**Project Description**

SDKs can make it easier for developers more familiar with other languages to use Filecoin and abstract things for developers less familiar with cryptography, blockchain, etc. 

Currently a [Filecoin JS API](https://github.com/filecoin-shipyard/js-lotus-client) that works with the [lotus JSON RPC API](https://lotu.sh/en+api) is being developed.

A [Filecoin signing tools library](https://github.com/zondax/filecoin-rs) that supports signing Filecoin transactions outside of a full node is also being developed and supports many languages via FFI and WASM.

Proposals should clearly define target users, their use cases and environments and contexts and what additional features and benefits your SDK would offer to developers. For example, an SDK targeting miners comfortable with GoLang could include a variety of tools to help manage miners. An SDK targeting application developers of .NET could support developers building Unity games with storage client services.

Proposals that will also provide useful sample applications built with the SDK are also preferred so that the SDK’s utility is verified by at least one user and use case right away.

Applicants should have open source examples of SDKs and APIs they have created that are very well documented, easy to understand and well-used by developers.

&nbsp;

### S3 (Glacier) API for Filecoin

**Project Description**

So that current users of S3 (e.g. Glacier) can easily port their existing archive and retrieve workflows to Filecoin and IPFS.

Proposals should include an initial analysis of the most common and logical API calls to support. Exploration of interesting features that have great analogies in Filecoin such as [Requester Pays Buckets](https://arxiv.org/help/bulk_data_s3) are sought. Proposals that port an existing S3 workflow or UI (e.g. [freezeapp](https://www.freezeapp.net/)) and can dogfood the API in a demo application right away are also desired. One potential interesting demo application is an S3 to Filecoin and IPFS migration tool targeting 500 GB or less as a convenience.

Applicants should demonstrate prior experience using the S3 (Glacier) API in an application and have open source examples of SDKs or APIs they have created that are very well documented, easy to understand and used by other developers as well as understanding of IPFS data structures.

&nbsp;

### Proxy re-encryption library and service

**Project Description**

To support data forwarding with encryption, proxy re-encryption allows a user to delegate access to others using a semi-trusted proxy service that does not have to decrypt the data and can re-encrypt with new public keys and share.

To learn more see https://en.wikipedia.org/wiki/Proxy_re-encryption

This project would explore building a set of tools and demo service.

Use cases:

- A proxy service
- Groups and orgs sharing access
- Advanced storage clients

&nbsp;

### FLOPy AWS Snowball-like hard drive service

**Project Description**

End-to-end proof-of-concept of a white glove full service that extracts large volumes of data to external hard drives that are physically shipped to miners using offline deals.

In scientific and archival data communities, it is often more efficient to physically ship datasets via hard drives than send it over the Internet. [AWS Snowball](https://aws.amazon.com/snowball/) is an example service. In Filecoin offline deals are possible, where drives are shipped to miners via prior arrangement in an appropriate format and imported upon physical receipt as a new storage deal.

One option is that a Shopify-like storefront for data on drives could be made to make it easy for interested storage miners to find datasets and clients that need hosting. Miners could initially pay logistics costs to ship (e.g. using a service like [Shippo](https://goshippo.com/)) so they can earn rewards later on the Filecoin network.

Proposals for this project will have 2 phases:

1. The 1st phase is to propose an architecture and design specification of how the service would work and look to potential storage clients and miners. Ideally at this time your team has found a specific data provider and dataset as well as candidate storage miners to understand their user workflows.

2. In the 2nd phase top specifications from the 1st phase will receive funding to actually implement a proof-of-concept service.

A team with UX researchers + data specialists + developers could explore a workflow with a large public dataset (e.g. scientific data at a science lab) and miners.

We are especially interested in collaborating with University student groups and University archival groups and scientific labs with large datasets that need backup. 

&nbsp;

### Ganache-like UI or improved tooling for running a FIlecoin Devnet

**Project Description**

So that developers new to Filecoin can easily run a local Filecoin devnet for prototyping and learn what's important to know about the Filecoin network when building dapps. Examples: [Truffle Framework's Ganache](https://www.trufflesuite.com/ganache) and [Lightning Network's Polar](https://lightningpolar.com/)

&nbsp;

### GraphQL API for lotus-chainwatch

**Project Description**

Allows dapp developers to use a GraphQL API interface to explore Filecoin chain data.

The Filecoin lotus client offers a Postgres database chain data import tool called lotus chainwatch. This database schema could be improved and a GraphQL API could be added to this.

Optionally subgraphs could also be created for specific dapps and deals like [TheGraph](https://thegraph.com/explorer/) or related dapp smart-contract and transaction monitoring tools such as [VulcanizeDB](https://github.com/vulcanize/vulcanizedb) and [Quickblocks](https://quickblocks.io/docs/introduction.html#architecture).

&nbsp;


### Expert Postgres tuning of lotus-chainwatch

**Project Description**

We are interested in tuning of the Postgres chain database that the Filecoin lotus client offers called lotus chainwatch to improve its efficiency, flexibility and speed.

Preferred aplicants should have experience tuning blockchain databases and understand the various use cases for how these databases may be used.

&nbsp;

### Storage Workflow User Research

**Project Description**

Do you know of an organization, community or individuals with interesting archival storage use cases? We’re interested in learning more about their user needs and workflows and how Filecoin can support them. 

Deliverables should produce well-written UX briefs including user journey maps synthesizing user interview transcripts, screenshots of their current tools and workflow diagrams and a write-up of recommendations for tools and infrastructure support.

Applicants should demonstrate knowledge of user research best practices and confirm collaboration from the use case partner.

&nbsp;

### Cross chain integrations

**Project Description**

User-defined smart contracts will not be available in Filecoin at mainnet launch but are on the Filecoin roadmap. We are generally interested in proposals for cross chain integrations that can make Filecoin programmatically usable from other popular blockchains.

To be considered, proposals should provide as much detail as possible about what type of integration is possible and reasonable to build in the near-term on the Filecoin side.

Applicants should have a good understanding of protocol-level integrations and be willing to do some early exploration of how the Filecoin protocol is designed.

&nbsp;

### Snarks as a Service

**Project Description**

Filecoin has two core proofs of storage, Proof of Replication and the election-based Proof of Spacetime (PoRep and ePoSt). Each also involve compression using SNARKs into succinct proofs for the chain. SNARKs are generally best processed by GPUs so that these proofs can be submitted within a block time epoch window. Miners not elected to produce proofs in an epoch may also have GPU cycles to spare.

We are seeking proposals for an efficient way to provide Snarks as a Service as a market offering to miners who wish to be less reliant on GPUs.

Preferred applicants should have a good understanding of Filecoin's core proofs, familiarity with SNARKs and OpenCL and evidence of being able to build computation-bound services at scale.

<sub>* *Note that the Filecoin proofs will be updated shortly. Waiting for these updates to be published before starting research on this is recommended. Also proofs like PoRep are likely to be updated in the future to ensure network security, for efficiency improvements, and to add features.*</sub>

&nbsp;

### VM research - verifiable subsets of WASM-able languages

**Project Description**

Explore what subset of a WASMable language can be formally verified to help with future smart contract VM recommendations.
 
User-defined smart contracts in Filecoin are a roadmap item for post-mainnet.
 

&nbsp;

### VM research - Improving state tries

**Project Description**

Improving execution of VMs on chain with space-saving enhancements to state tries.

A number of space-saving enhancements to state tries have been proposed in the blockchain research community. We are interested in research proposals that could lead to a viable VM space savings.

&nbsp;

### Expert use of large data archives

**Project Description**

We invite data analysts and experts from different domains (public health, GIS, etc.) to produce tutorials and visualizations that demonstrate how to work with large data archives that can be stored on Filecoin and various open source tools to produce analysis.

Help showcase important human use cases of large data archives and why saving certain datasets is so important.


&nbsp;

----

## Proposal Guidelines

We generally fund projects that can be built in a 2-3 month time frame and evaluate proposals based on:

- The quality of the proposal and near-term value to the Filecoin ecosystem
- Your team’s technical experience, open source contributions and interest in diving into how Filecoin works
- Likelihood that your team will continue to support the Filecoin ecosystem long-term and commitment to maintaining your project for one year

Note that all proposals must be open sourced via MIT and Apache2 licenses.


**Proposal Requirements**

Proposals should include a value proposition about how it will benefit the Filecoin ecosystem, a good amount of technical detail about what your team intends to build and evidence your team is capable of creating good, re-usable open source code and compelling product demos and great documentation, and a reasonable technical development plan broken down into milestones.

Proposals should include the following sections:

1. Project Description
   - Value to the Filecoin ecosystem
   - An explanation of your technical solution and architecture
       - Imagine that experienced software developers and project managers will evaluate your proposal.
2. Deliverables
3. Milestones & Funding
4. Team
   - Roles and Experience
       - Teams with a history of high-quality open source code repos and live applications and products are preferred.

We also accept **Open Grant Proposals** where you can suggest your own Filecoin project idea. [More info](https://github.com/filecoin-project/devgrants/blob/master/open-grant-proposals/open-proposal-template.md)

To submit a proposal, fork and make [a PR](https://github.com/filecoin-project/devgrants/pulls) to this repo by April 15th 23:59 PDT.

&nbsp;

---

*Have a question about any of these RFPs? Email devgrants@filecoin.org*
