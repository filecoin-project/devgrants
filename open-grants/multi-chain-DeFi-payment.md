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

With our defi payment solution, it can help the ecosystem projects easily integrated multi-coin payment to their system.
Projects can use metamask pay eth, USDT, matic or other token for their storage cost. If the project cannot implemented
properly, it will delay the process of lots of ecosystem projects integrated with other blockchain.

The risks of make executing on this project difficult are:

* Smart contracts. There are so many token in the world, we need to create lots of smart contracts, they all needed to
  be audited for preventing fatal bugs
* User adaption. After implementation there are huge effort needed for marketing and user training.

## Deliverables
A typical payment scenario is as following:
* User query the price of a file storage on Filecoin
* He sent his token to swan-payment gateway for the target file
* FIle is paid and backup to the storage network
* if backup failed the payment will be refund, he can also claim refund if the storage is not qualified.

The delivered product contains the following component:
* A GUI for user testing uploading file
* A smart contract for user query and make payment, first version is EVM contract
* DAO holders maintain the wrapped token hub and in charge of the claim issue

## Development Roadmap

### Milestone 1 Project setup with scope and architecture
* define the goals and scope of the project
* define the acceptance criteria
* define the user scenario
* define the components and specs 
* document the design and workflow

### Milestone 2 Meta mask based token payment
* user pay to a smart contract for a file in metamask
* The price is defined in Defi Module

### Milestone 3 Payment DAO for the token fund maintenance
* Define root key holders
* Init members sign keys
* define the policy of adding and remove member from the board
### Milestone 4. Payment frontend UI/Backend
* User can connect to his metamask wallet from UI
* He can choose a file to pay for backup to filecoin network
* His fund is locked until the storage is online, then it will be released to the client
### Milestone 5. SDKs for project integration
* Devs can use golang sdk for making payment
* JS will be in Phase 2, since we believe this will be a multi phases project
### Milestone 6.  Release document and marketing
* Testing in alpha group
* Document creation
* Workshop and marketing
## Total Budget Requested

| Milestone | Description | Time | Budget | 
| :--- | :------ | :--- | :--- |
| #1| Project setup with scope and architecture    | 1 Weeks    |   5,000  
| #2| Meta mask based token payment    |  2 Weeks    |   20,000  
| #3| Payment DAO for the token fund maintenance |  2 Weeks    |   20,000  
| #4| Payment frontend UI/Backend    |  4 Weeks    |   30,000  
| #5| SDKs for project integration    |  3 Weeks    |   10,000  
| #6| Release document and marketing    |  2 Weeks    |   15,000  

Total: $100,000

## Maintenance and Upgrade Plans

We have a dedicated team in Montreal with 10 developer team, since this product has very close relationship with the
Storage market project Swan we are building we will keep a code upgrade at weekly bases. Future upgrade can be add S3
compatible file importer service, enhancement of key management, connect to swan project. Etc.

# Team

## Team Members

- Charles Cao | Development Manager (worked previously in Filecoin grant 6,7,8,9)
- Baoyuan Sun |  Project Manager (worked previously in Filecoin grant 6,7,8,9)
- Yiming Liu | Smart Contract Developer
- Rick Zhao | Blockchain Developer (worked previously in Filecoin grant 7)
- Dora Chen | Backend Developer
- Boqian Zhang | Filecoin Developer(worked previously in Filecoin grant 6,7,8,9)
- Guohao Ma | Filecoin Developer (worked previously in Filecoin grant 6,7)

## Team Member LinkedIn Profiles

- [Charles Cao](https://www.linkedin.com/in/charles-cao-09a79526/)
- [Boqian Wang](https://www.linkedin.com/in/boqian-wang-6b0955171/)
- [Baoyuan Sun](https://www.linkedin.com/in/sun-baoyuan-50026637/)
- [Yiming Liu](https://www.linkedin.com/in/yiming-liu-0aa1a516/)
- [Guohao Ma](https://www.linkedin.com/in/guohaoma/)
- [Zhiqiang Zhao](https://www.linkedin.com/in/zhiqiang-zhao-9ba555199/)

## Team Website

https://filswan.com

## Relevant Experience

We - FilSwan Canada participated in SR1, SR2, and cooperation with starling and pinata project. In slingshot 2 we
processed over 10,000 deals and over 500 offline deals, talked to 100 miners and actively working data transfer service
between Asia and North American users. Prior to working on Filecoin project, we were working on a decentrilized AI
computing platform which using smart contract for data/task transmission to different AI workers, we have in hand
experience of handling encryption and data pipeline.

We build the following product

- https://nbai.io GPU cloud computing
- https://nbfspool.com One of the largest Filecoin mining node in North America
- Https://filswan.com A storage market for price decovering and offline trasfer

The team get the following reward and honor.

- The Natural Science and Engineering Research Council of Canada (NSERC) special fund supports research on the direction
  of video coding.
- Canadian government high-tech research and development grant
- Natural Science Foundation of Canada (NSERC) Blockchain to AI Cloud Computing Research Grant
- Canadian Information Technology and Integrated Systems Mathematical Organization (Mitacs) AI medical identification
  project grants
- Canadian tax support for scientific research and experimental development
- Quebec e-commerce innovation enterprise support
- CENGN (Canadian Center of Excellence for Next Generation Networks) Research Support Project
- Canadian D3 incubator Hosted Startup support
- Microsoft Entrepreneurship Support Program (BizSpark) Support
- HP Enterprise Supplier Partner, Dell Enterprise Supplier Partner, ASUS Enterprise Service Partner, Amazon Enterprise
  Partner, NVIDIA Canadian Cloud Computing Supplier

Charles Cao, Founder of Filecoin node NBFS Canada, CEO of Nebule AI inc, previous working for IBM, Autodesk, Exepida and
Paysafe. NBFS Canada is working on building an edge cloud computing platform (Project Swan) integrated with Filecoin
decentralized storage solution. Project Swan integrates computing, online/offline deal management and storage price
discovering in one platform to bring enterprise applications closer to where the data located.

## Team code repositories

https://github.com/filswan/payment-bridge

# Additional Information

- HackFS participant
- Chainlink HackFS chainlink pool Grant award