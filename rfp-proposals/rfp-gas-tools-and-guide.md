# RFP Proposal: `Filecoin Gas Tool and Guide`

**Name of Project:**  FILGas

**Link to RFP:**  [Gas tool and guide](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-mining-tools-rfps.md#gas-tool-and-guide)

**RFP Category:**  app-dev

**Proposer:**  [P2P.ORG - P2P Validator](https://p2p.org/)

**Do you agree to open source all work you do on behalf of this RFP and dual-licenses under MIT and APACHE2 licenses?:**
 "Yes"

# Project Description

Our team works on connecting Filecoin and Polkadot ecosystems together ([grant proposal](https://github.com/filecoin-project/devgrants/pull/122)). We've built our own data extraction and indexing solution for Filecoin blockchain using lotus API to extract data from chain, PostgreSQL database to store it and Kafka to connect our extractor written in go with other possible consumers of collected data. This prroject will be open sourced soon.

To demonstrate possible use-cases of our solution while providing real value for Filecoin ecosystem we decided to participate in this grant and build service that will explain users how gas in Filecoin works and help them estimate it better.

# Deliverables

As result of our work we will deliver redash dashbord with read-only access. This approach combines great UI with ease of development and maintenance. Every widget on dashbord (except plain text) is configured by writing plain SQL query and configuring it's visualisation that can be chosen from a lot of built-in options directly from redash UI.

## Displayed data

The list below represents widgets that we want to include into our dashbord. Feel free to add or remove something if you think that it will add value to final product.

- An article on how gas in Filecoin works with some useful links.
- Chart with gas fees changes for each tipset
- Table of all messages stored with variables that are used in gas fees calculation (`gasPremium`, `gasLimit`, `gasUsed`, `baseFee`, `gasFeeCap`) as well as gas fees paid for each message
- Tables of tipsets and blocks with total gas fees paid and averages of variables needed to calculate them
- Charts that show average gas fees for message types
- General statistics

Currently we are working on MPool data extraction and we are looking forward to add MPool data statistics (i.e. average time spent by message type in MPool by gasPremium) when it will be implemented.

# Milestones & Funding

Total Funding Amount: $1000

We don't see a point in dividing such small grant into several small milestones, we think one milestone with estimated timeframe of 5-6 weeks is enough. It includes implementation of functionality described above, development of configuration and deploy scripts and writing documentation.

# Our Team

## People involved into project

- Vasily Shapovalov : CTO of p2p validator (https://github.com/vshvsh)
- Dmitry Mandrika : Filecoin Team Lead (https://github.com/x88)
- Egor Miloserdov : Go developer (https://github.com/Jopoleon)
- Martynenko Lev : Go developer (https://github.com/martelev)

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
[Lido.fi](https://github.com/lidofinance)




 