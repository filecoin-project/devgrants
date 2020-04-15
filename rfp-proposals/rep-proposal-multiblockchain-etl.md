# RFP Proposal: `Multiblockchain ETL`

**Name of Project:** Blockchain-agnostic ETL for Polkadot and Filecoin

**Link to RFP:** [new-wave-3-rfps.md](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#graphql-api-for-lotus-chainwatch)

**RFP Category:** `devtools-libraries`

**Proposer:** [P2P.ORG - P2P Validator](https://p2p.org/)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description
Taken to the extreme, we envision interoperability-first blockchain data warehouse across all the blockchains we validate, complete with event subscriptions and useful aggregate functions. With it people have easier time building wallets, dashboards, explorers and apps that interact with multiple blockchains connected through interchain communication protocols. In the interconnected blockchain network applications will need to be able to follow events across chains. Imagine, for example, moving a chain A asset through bridge B to parachain X to open a CDP, then using received stablecoin to long a synthetic asset from parachain D on a margin trade chain E. The closest analog to what we want to eventually make is dfuse, but for the forest of blockchains.

Main points:
- many blockchains lack good public and/or ready-made private APIs to build apps on
- with interblockchain communication proliferation, a walled garden-like APIs won't cut it: good apps will require a single request to analyze multiple blockchains (simplest example is a wallet querying multiple balances but it's going to be much more complex than that eventually)
- multi-network validators are uniquely positioned to implement such an API: on one hand, they already bear a good part of blockchain API costs: node management.

On the other, they are already trusted to validate blockchain network and have their skin in the game, making them more trustworthy as a source of blockchain data
That’s a long way into the future: for a first step, we can make an adaptable ETL solution for both Polkadot and Filecoin + GraphQL API for the collected data. It is a comparatively small deliverable that still makes us closer to our grand vision and can be continued with data enrichment pipelines and ETL and APIs for notable applications and additional blockchains.

NB: This is a proposal for combined grant initiative for both Web3 Foundation and Filecoin. Sorry that it's not completely conforming to Filecoin proposal standard because we had to make it work for both foundation.

## Value to the Filecoin ecosystem

A good ETL solution will make building apps and analytics over the platform easier. Multiblockchain ETL with a single GraphQL API gateway will help with cross-chain applications, like dapps on Polkadot using Filecoin as a storage layer.

## A bit more details about the implementation
We want to make an adaptable framework that consist of extraction adapters, transformation framework and storage adapter. Extraction adapter should handle specific blockchains and push extracted data - transaction and block data for most blockchains  - into a message queue to be picked up by transformation framework. 

Transformations (logic to make sense of raw transaction data) are the central piece of the project and will be put front and center. Ideally people writing transformation logic won't even need to touch the extraction or storage part or understand how it works. 

For a storage adapter we'll implement a PostgreSQL backend. 

On top of that we'll set up a GraphQL endpoint for the extracted data, along with similar endpoint for a native ETL in the Lotus node.


## Deliverables

Described in the Development Roadmap below.


## Development Roadmap

Before the development starts we need to take the big decision of what stack to use. Main options are industry standards (Apache Spark/Beam pipelines) or making an extension for the Graph Protocol open-source code. We’ve reached out to them and they would be happy to help with the latter and upstream it - it’s more or less the direction they want to take with their already pretty great software. 
We provide estimations in a separate sheet. 

### Milestone 1 — ETL Stack and Architecture Drafts — 2 weeks
- We will explore and compare options to make the extensible and easy to use Extraction toolkit for Substrate-based blockchains. We'll compare industrial standard stacks (e.g. Apache Spark, Apache Beam) and successful related blockchain-specific projects (e.g. EthereumETL, VulcanizeDB, Graph Protocol)
- We will reach out to experts in the field, including Graph Protocol team, to ensure that the architecture allows for reusable code and logic.
- We will deliver a specification for stack and architecture we will use

Milestone 2 — GraphQL API over built-in Filecoin Lotus node ETL — 2 weeks (in parallel with architecture drafts)
- We will develop GraphQL API endpoint over built-in Lotus node ETL based on Hasura
- We will provide deployment scripts, documentation and tutorials on configuring and running GraphQL endpoint

Milestone 3 — Extraction and Load framework — 1 month
- We will develop the framework to extract and store raw tx/block data from Polkadot Relay chain and Filecoin, suitable both for blockchains with finality gadgets and reorganizable chains
- We will develop a reference implementation of the said pipeline for Filecoin and Polkadot 
- We will provide documentation and tutorials on running the extraction pipelines and making a custom extraction pipeline

Milestone 4 — Enrichment, API endpoints, Documentation — 1 month
- We will create enrichment transformations for the blockchain chain data, including specialized structured data warehouses for transfers, staking, governance on Polkadot and actors and messages on Filecoin
- We will create a GraphQL API over raw and enriched data extracted from the chain
- We will provide documentation and tutorials on running the pipelines we made, hosting an API, using the API and developing your own pipelines and APIs for other blockchains.
- We will provide a docker-compose setup for easy deployment of the ETL and API solution

Milestone 5 — Miner’s Dashboard for Filecoin — 1 month
- We will create a dashboard that tracks filecoin miner’s activity and historical data using the GraphQL API we made and prometheus exporter
- We will provide documentation and tutorials on running the dashboard 


People Involved:
1 Engineering Manager, 2 Senior Engineers, 2 Backend Engineers, 1 Frontend Engineer, 1 DevOps Engineer 

## Maintenance and Upgrade Plans

The team will maintain the software and upgrade them according to Filecoin and Polkadot upgrade.

# Team

## Contact Info
Vasiliy Shapovalov: vs@p2p@org

## Team Members
* Vasiliy Shapovalov, 11 years in software development. Mostly infosec-related projects, including compiler engineering, network security, formal verification.
* Andrey Zavgorodniy: senior blockchain developer. Ex-SONM, Ex-Lazada.
* Michael Mozhaev: golang developer
* Pavel Klyibik: golang/c++ developer
* Mikhail Semenkin: solidity & full stack NodeJS developer
* Vladimir Matveev: devops engineer


## Team Member GitHub Profiles
* Vasiliy Shapovalov https://github.com/vshvsh
* Andrey Zavgorodniy https://github.com/oopcode
* Michael Mozhaev http://github.com/programmer10110
* Pavel Klyibik https://github.com/PashaKlybik
* Mikhail Semenkin https://github.com/krogla
* Vladimir Matveev https://github.com/ponchik69

## Relevant Experience
Blockchain team received Interchain Foundation funding for [Arcade](https://github.com/corestario/tendermint) - Tendermint hack with built-in BLS random beacon.
A few of the most interesting files to check out:
https://github.com/corestario/tendermint/blob/develop/docs/arcade/arcade.md
https://github.com/corestario/dkglib/blob/master/lib/dealer/dkg_dealer.go
https://github.com/corestario/tendermint/blob/develop/node/bls/bls_node.go
We've developed ETL pipeline and an API for Cosmos data, it's closed source so far but you can see how it works on our website.
The cool thing about our pipeline is that we extract data paid rewards on delegation and redelegation that no single block explorer so far can show (you can see the examples in our (article)[https://economy.dev-p2p.org/lost-in-cosmos-explorers/]) and we can work with all three upgrades of Cosmos Hub at once.
We've developed an API for Cosmos staking referral program, where you can check out our documentation-fu:
https://docs.defiapi.com/cosmos-staking-api/


## Team code repositories
[P2P.ORG](https://github.com/p2p-org)
