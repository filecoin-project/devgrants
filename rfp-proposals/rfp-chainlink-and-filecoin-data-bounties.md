# RFP Proposal: `chainlink and filecoin Data Bounties`

**Name of Project:**

**Link to RFP:**  [chainlink-and-filecoin](https://github.com/filecoin-project/devgrants/blob/master/rfps/chainlink-and-filecoin.md)


**RFP Category:** `core-dev`

**Proposer:** `flyworker`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:**   Yes

# Project Description

This project is aiming at providing Smart contracts can pool together funds for the storage of a particular piece of data, as characterized by its unique content identifier (CID). The payment is triggered once the proof that it has been stored on the Filecoin Network is relayed from Chainlink oracles.

## Deliverables
* UI upload to IPFS
* User deposit fund (collateral with storage fee)  to the smart contract
* Tools backup the file to Filecoin network 
* Smart contract by DAO holders for sign the storage deal active proof
* Trigger service for make payment from smart contract to storage provider and client

## Development Roadmap

### Milestone 1
**Timeline: 3 weeks**
- User upload File to ipfs 
- User get the cid and select the storage provider 
- User deposit fund to polygon with the cid and target provider address 
- User Collateral File storage Fee Waiting for file backup to Filecoin network 
- Multiple Filecoin Chainlink Oracle holders update the ChainLink contract state 
- After Chainlink oracle prove the storage deal is online, anyone can trigger the release lock pay to the storage provider 
- The reward is paid to the storage provider and collateral refund to user 

### Milestone 2
**Timeline: 3 weeks**
- Build the Chainlink DAO
- UI improvement
- Metamask integration
- Load testing
- Eth, BSC and other blockchain integration 

In this project, we need :
- 1 project manager: Design the entire roadmap and scope.
- 1 smart contract developer:  Oralce Chainlink
- 2 IPFS/Filecoin Developers: Uploading, trunk/ merger file and batch file to filecoin network
- 1 Blockchain developer: metamask, UI and system integration

Milestone 1 tasks about 3 weeks and milestone 3 
Some pre-work can be found here: https://www.youtube.com/watch?v=c4Dvidz3plU


## Total Budget Requested

* Milestone 1: $20,000

* Milestone 2: $15,000

* Smart contract auditiong: $5000

Total: $30,000
.

## Maintenance and Upgrade Plans

We have a dedicated team in Montreal with 10 developer team, since this product has very close relationship with the Storage market project Swan we are building we will keep a code upgrade at weekly bases. Future upgrade can be add S3 compatible file importer service, enhancement of key management, connect to swan project. Etc. 

# Team

## Team Members

- Charles Cao   Development Manager
- Baoyuan Sun 	Project Manager
- Yiming Liu	Smart Contract Developer
- Rick Zhao	    Blockchain Developer
- Boqian Zhang  Filecoin Developer 
- Guohao Ma	    Filecoin Developer

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/charles-cao-09a79526/
- https://www.linkedin.com/in/boqian-wang-6b0955171/

## Team Website

https://filswan.com

## Relevant Experience

We - FilSwan Canada participated in SR1, SR2, and cooperation with starling and pinata project. In slingshot 2 we processed over 10,000 deals and over 500 offline deals, talked to 100 miners and actively working data transfer service between Asia and North American users.
Prior to working on Filecoin project, we were working on a decentrilized AI computing platform which using smart contract for data/task transmission to different AI workers, we have in hand experience of handling encryption and data pipeline.

We build the following product

- https://nbai.io GPU cloud computing 
- https://nbfspool.com One of the largest Filecoin mining node in North America
- Https://filswan.com A storage market for price decovering and offline trasfer

The team get the following reward and honor.

- The Natural Science and Engineering Research Council of Canada (NSERC) special fund supports research on the direction of video coding.
- Canadian government high-tech research and development grant
- Natural Science Foundation of Canada (NSERC) Blockchain to AI Cloud Computing Research Grant
- Canadian Information Technology and Integrated Systems Mathematical Organization (Mitacs) AI medical identification project grants
- Canadian tax support for scientific research and experimental development
- Quebec e-commerce innovation enterprise support
- CENGN (Canadian Center of Excellence for Next Generation Networks) Research Support Project
- Canadian D3 incubator Hosted Startup support
- Microsoft Entrepreneurship Support Program (BizSpark) Support
- HP Enterprise Supplier Partner, Dell Enterprise Supplier Partner, ASUS Enterprise Service Partner, Amazon Enterprise Partner, NVIDIA Canadian Cloud Computing Supplier


Charles Cao, Founder of Filecoin node NBFS Canada, CEO of Nebule AI inc, previous working for IBM, Autodesk, Exepida and Paysafe. NBFS Canada is working on building an edge cloud computing platform (Project Swan) integrated with Filecoin decentralized storage solution. Project Swan integrates computing, online/offline deal management and storage price discovering in one platform to bring enterprise applications closer to where the data located.

## Team code repositories

https://github.com/filswan/payment-bridge

# Additional Information

HackFS participant

