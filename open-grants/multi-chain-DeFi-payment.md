To submit a proposal, please create a PR against this template in this repo. Please title your
file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Multi-chain DeFi payment for FIlecoin`

**Name of Project:**

**Proposal Category:** `devtools-libraries`

**Proposer:** flyworker

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:**
Yes

# Project Description

Filecoin as a storage solution leading in decentralized storage market is using by lots of famous blockchain
projects.e.g. Near,Polygon.it is also used by lots of projects in NFT, deep learning. However, Filecoin blockchain
currently only support Fil as the payment solution while lots of storage solutions like nft.storage, web3.storage
provide free storage base on verified deals, but there is no free meal in the long run. We need to have a decentralized
payment solutions for Filecoin projects.

Our solution is building a Defi based multi-chain solutions to converting major cryptocurrencies to filecoin payment.
With the defi base price it can fast response to the price changes from multi-chain and make the payment smoothly and
lowest Trading slippage.

## Value


This section should be 1-3 paragraphs long. With our defi payment solution, it can help the ecosystem projects easily
integrated to their system. Projects can use metamask pay eth, USDT, matic or other token for their storage cost.

## Deliverables

Please describe in details what your final deliverable for this project will be. Include a specification of the project
and what functionality the software will deliver when it is finished.

## Development Roadmap

* Project setup with scope and architecture
* Token swap on multiple chain
* Libs and SDKs for project integration
* Release document and marketing


## Total Budget Requested

* Milestone 1: $25,000

| Function | Description | Time | Developer | Budget | 
| :--- | :------ | :--- | :--- | :--------: | 
| Polygon payment Contact | Cross chain payment from polygoin network      |  3 Weeks    |  Yiming Liu    |   10,000         |
| UI Design and implementation| Upload,pin file to IPFS and retrieval     |  2 Weeks    |  Yiming Liu   |   5,000         |
| Backend support| browser sync and payment gateway    |  2 Weeks    |  Rick Zhang	   |   5,000         |
| File upload to IPFS/Filecoin &CID management | File management and testing |  2 Week    |  Boqian Zhang&Guohao Ma    |   5,000         


* Milestone 2: $35,000

| Function | Description | Time | Developer | Budget | 
| :--- | :------ | :--- | :--- | :--------: | 
| Chainlink DAO Contact |  Voting Dao For the data online proof      |  4 Weeks    |  Yiming Liu    |   10,000         |
| UI and wallet integration| Wallet for voting      |  2 Weeks    |  Yiming Liu    |   5,000         |
| Backend support| browser sync and payment gateway    |  3 Weeks    |  Boqian Zhang&Rick Zhao	   |   15,000         |
| Muilti chain integration | Deployed the small contract on multi-chain and testing |  1 Week    |  Baoyuan Sun    |   2,500        
| UX and testing   | Performance testing |  1 Week    |  Baoyuan Sun    |   2,500          


* Smart contract auditing: $5000

Total: $60,000


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
- HackFS participant
- Chainlink HackFS chainlink pool Grant award