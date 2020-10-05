To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Elastos Hive++ and Filecoin Service`

**Name of Project:** Elastos Hive++ FIL Service

**Proposal Category:** `app-dev`

**Proposer:** `ClarenceL`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** YES

# Project Description

The Elastos network is a complete platform for dApp development including an EVM compatible sidechain, W3C DID (Decentralized Identifier) services and an Elastos Hive++ storage API that wraps IPFS as well as traditional storage services. All of these features are built on top of a strong AuxPoW layer that is the Elastos mainchain and its ELA token, which has over 50% of BTC's hashrate. However Elastos' Hive++ storage solution is still in its early stages and currently lacks a way to pay and ensure IPFS files are pinned such as what Filecoin has.

The goal for this project is to build a semi-centralized open source service that allows anyone to run a node which exposes the Elastos Hive++ storage API but uses Filecoin and FIL to renew the pinning of IPFS files. To make the integration seamless ideally the long-term goal would be to allow cross-chain swaps of ELA for FIL, so that users on Elastos can directly pay in ELA. But given the lack of bridging right now (which other RFPs are working on), and that user-defined smart contracts are a roadmap feature in Filecoin, we will first deploy a listener type service on top of Powergate.

This service would be a docker compose running a web UI and gRPC API, where Elastos users can escrow ELA to be used to pay for pinning of files through Filecoin that are accessible through a locally running Elastos Hive++ API.

## Value

Elastos Hive++ is still in development and also uses IPFS, in this I believe our goals are aligned in creating more data on IPFS. Elastos Hive++ has been tackling the data access performance issue for dApps and focusing on structured, semi-structured and key-value pair data access in a decentralized manner. Elastos is also an open-source non-profit project, therefore if Filecoin (FIL) becomes the globally accepted token of payment for storage pinning and mining we believe there is mutual benefit in sharing technology. 

Elastos has ample funding which is passed through to the community led project CR Regions which I run and we won't be requesting funding for development, so I believe the risk is low.

Also Elastos is partners with StorSwift, a leading Chinese Filecoin mining entity as well as supporting FIL through its Elaphant Wallet app - https://cyberrepublic.press/elaphant-wallet-and-filecoin-agreement-proposal. We believe successful integration will boost both our communities.


## Deliverables

- Web UI - interface allows connecting Metamask (linked to Elastos network) or ElaMask (Elastos clone of Metamask) to escrow ELA in a secure non-upgradeable smart contract to fund pinning of files via FIL,
	list the files they have pinned and manage renewal settings on each cid
- Elastos Hive FIL Service - this process will wrap Powergate gRPC calls and allow the operator of the node to provide a nominal FIL liquidity pool to support the Elastos (ELA) escrow contracts, and a gRPC 	API that underpins the Web UI and provides the same functionality through RPC calls

## Development Roadmap

ALL DEVELOPMENT IS ON TESTNET FOR NOW

1. **ELA Escrow Contracts - Oct 19, 2021**

	We'll need a set of smart contracts to allow nodes to stake ELA as a collateral in case they do 	not perform their pinning obligations, and also to gate access to being a node. Smart contracts 	are also needed for	users to deposit ELA to be used as an escrow so that the node can spend its 	FIL to renew the pinning. 
	
2. **FIL CID Checker Oracle - Oct 31, 2020**

	For on-chain verification that pinning is successful we will use our Chainlink oracles to query 	the CID checker tools provide this data to the escrow smart contracts. This will complete the 
	smart contract milestones and verified with complete test suites.

3. **Elastos Hive++ FIL Service - Nov 16, 2020**

	This is a running process that wraps both Powergate and Elastos Hive++ API and coordinates all 	the main functions.
	
	- **File Upload** - Example flow: user escrows ELA on Elastos EVM chain, user calls smart contract with a file hash, oracle whitelist and renewal request, user uploads matching file, service will lock the escrow and sign the renewal request, service will pin the file using its own FIL balance, service will issue an oracle data request, service will request payment from the escrow address by submitting proof from CID checker to the smart contract.
	- **Withdraw Escrow** - user decides they no longer want to pin a file, this signed request will 	have the service release its lock.
	- **Failure Function** - if the service fails to renew a pin or is down during a critical renewal period the escrow lock automatically releases funds back to the user and the node's stake is slashed/rewarded to all users using that node.

4. **Front-End Web UI and Co-Marketing - Nov 30, 2020**

	We will only request a minimal budget for co-marketing the service in both Elastos and Filecoin 	communities. However if this is outside the scope of the dev-grant we will indeed be happy to 	develop this service regardless as long as we have the permission to publicize the service. 
	
	The Web UI is self-explanatory, basically a Metamask linked interface to list and 	manage your pinned files linked to your smart contract.
	
	- Optional Budget: 2,500 USD - to co-market the service in crypto PR outlets.

## Total Budget Requested

Ideally but optionally 2,500 USD for co-marketing expenses on successful completion, 0 cost otherwise.

## Maintenance and Upgrade Plans

CR Regions is funded with two high performance AWS servers which will run an official node of this service, but our hope is that our community will also contribute and run additional nodes.

# Team

## Team Members

- Clarence Liu - CR Regions Lead - primary developer
- Harry Liu - Elastos ETH Task Force Lead - dev-ops and assistant

## Team Member LinkedIn Profiles

- Clarence Liu - https://www.linkedin.com/in/clarencehlliu
- Harry Liu - https://www.linkedin.com/in/harry-liu-a3957095/

## Team Website

https://crregions.com/#/eth

## Relevant Experience

My name is Clarence Liu and I'm a prominent executive at Elastos as well as the lead of the community run CR Regions entity that handles external integration efforts. If given the green light I will be handling most of this project myself on an on-going basis with some of my earmarked Elastos development time.

## Team code repositories

https://github.com/elastosjs/elastosj

# Additional Information

Please include any additional information that you think would be useful in helping us to evaluate your proposal.