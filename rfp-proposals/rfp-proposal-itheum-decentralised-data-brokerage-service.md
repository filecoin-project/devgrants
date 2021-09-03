# RFP Proposal: Itheum Decentralised Data Brokerage Service

**Name of Project:** Decentralised Data Brokerage Service powered by Hedera and Filecoin

**Link to RFP:** [Hedera x Filecoin RFP](https://github.com/filecoin-project/devgrants/blob/master/rfps/hedera-and-filecoin.md)

**RFP Category:** `app-dev`

**Proposer:** `Itheum`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `yes`

# Project Description
![Itheum Data DEX](https://raw.githubusercontent.com/Itheum/data-dex/dev/itheum-dex-hero.png)

Today; your personal data is bought and sold in hidden data markets. The data brokerage market is worth more than $200 billion per year. And yet you (the person who produced this data) has no idea this is happening or can partake in this data economy or share in these earnings.

Itheum is the world's 1st "Decentralised Data Brokerage". We reduce the monopoly and dominance these data brokers have over your life. We believe in a future of personal data sovereignty and the role it plays in society. The Itheum platform follows the principle of "progressive decentralisation" to ensure we provide a platform that has real world use-cases today and yet enables the systematic removal of centralised intermediaries (traditional intermediaries like Data Brokers). 

Our main product is a `Decentralised Data DEX`: This cross-chain data DEX allows you to unlock your personal data for the greater social good and earn revenue for sharing your data assets. We provide some revolutionary new features like:
- Peer-to-Peer sale of personal data
- Data NFTs - wrap data as an NFT to gain features like limited availability, royalties and to trade in secondary markets like OpenSea and Decentraland
- Data Coalitions - sell data in bulk via a DAO managed entity
- Personal Data Proofs - For 3rd Party Smart Contract access to data
- Data Adaptors - For on-chain/off-chain personal data importers
- Data Vaults - For access to highly sensitive personal data
- Data Streams - For longitudinal personal data streams
- Trusted Computation Framework - For privacy-preserving computation on personal data


Itheum also provides a web2 solution called the "data collection and analytics platform". Anyone can use this toolkit to build user data collection tools with built in outcome-oriented analytics. This product is already in the market and powers products like OKPulse (https://okpulse.life). The aim of this web2 solution is to democratise data collection and analytics technology and to increase the quantity of high quality, outcome oriented personal data.

Reason we are submitting this RFP:
1. Our current DApp runs on EVM compatible chains and have been deployed to Ethereum, Polygon and BSC testnets. But we are finding that these traditional chains and their probabilistic consensus models + highly variable gas fees are probably not a right fit for our use case of high frequency data trading - so we are keen to explore **Hedera's Hashgraph** consensus blockchain (the uniformity of this option in terms of TX speed and cost, will probably also make Itheum more attractive for our enterprise data sharing use-cases).** 

2. Our project also has many requirements for decentralised data storage (both to store the actual encrypted personal data itself and other metadata file storage for our solutions like Data NFTs, Data Coalitions and Data Streams). Our `Trusted Computation Framework` which enables privacy preserving computation on sensitive workloads will also benefit from having distributed computing close to storage. For these reason we are very very keen to build on the **Filecoin Network**

In summary; we feel that Filecoin and Hedera will make a perfect unified platform for our goal to be a decentralised data brokerage service.

## Deliverables
Itheum is a large project and has many features to facilitate the infrastructure needed for data brokerage. To make the RFP more focused; we'd like to limit the scope to the following 2 deliverables (we already have built these in EVM chains + IPFS so we know the architecture and should be able to move this to Hedera + Filecoin without much difficult as part of this RFP):

- `Deliverable 1: "Peer-to-Peer" data sale feature` - Allow users to upload their personal data or link to the core Itheum platform's apps (OKPulse, Red Heart Challenge etc). Data gets uploaded to FileCoin network along with the `Personal Data Proof` (think of this as the evidence of the provenance, veracity and lineage of the personal data)
- `Deliverable 2: Data NFT marketplace` - Allows users to upload their personal data and wrap it as an NFT (to gain benefits of limited availability, royalties, harberger tax etc). Raw data + Personal Data Proof as well as the NFT Metadata will be on FileCoin network
- `Stretch Goal` - we'd like to explore potential for our Trusted Computation Framework use-case to also utilise the FileCoin network (i.e. leverage the distributed compute of the network)

## Development Roadmap

** `Deliverable 1: "Peer-to-Peer" data sale feature`**
- DApp for user to login using a DID / Wallet
- Once logged in; a UI for user to upload their personal data (a JSON file will be the requirement to keep it simple)
- User can set meta-data around the data sale. i.e. the price, terms of sale, preview of data etc (to be stored in the meta-data file)
- User will click on "upload and sell as raw data"
- The raw file is stored on FileCoin
- The file location and hash is linked to the meta-data file and also stored in FileCoin
- The raw file hash, location, meta data file hash and location is published on-chain under the user's identity 
- A "advertised data" page where a on-chain lookup will show all the data the user has advertised for sale
- The Dapp will be deployed to a public URL (we will use a deployment method that's recommended for Hedera DApps)

Estimate:
`2 Itheum Core Devs will work on this. It will take 4 weeks build time and we estimate it will cost 30k` 

You can get an idea of what the UI will look like by watching this video of our existing DApp: https://youtu.be/63BE4plzDzw


** `Deliverable 2: "Data NFT marketplace`**
- We will leverage the same DApp as the above and extend
- As in `Deliverable 1`, the user can upload new data and advertise for sale. But instead of a regular data file we will wrap it into a NFT standard token
- User can set meta-data around the data sale. i.e. the price, terms of sale, preview of data etc (to be stored in the meta-data file)
- User can click on "upload and sell as NFT"
- The raw file is stored on FileCoin
- The hash of the data will be used to to create a generative art that will form the "outward art" layer of the NFT
- The file location and hash is linked to the meta-data file and also stored in FileCoin
- The raw file hash, location, meta data file hash and location is published on-chain under the user's identity
- We will have a new section called Data NFT Marketplace that will show all the user's Data NFT Tokens

Estimate:
`2 Itheum Core Devs will work on this. It will take 2 weeks build time and we estimate it will cost 20k` 

You can get an idea of what the UI will look like by watching this video of our existing DApp: https://youtu.be/f5FtZl6XGSY


## Total Budget Requested
$50,000

## Maintenance and Upgrade Plans
- Once we deploy our solution; we will support with it the same SLAs as all our other opensource blockchain software. Our goal is to demonstrate the Filecoin + Hedera stack as the more suitable stack for our web3 application.

# Team

## Contact Info

- We will email your our personal email addresses on devgrants@filecoin.org shortly and link it to this RFP
- You can reach us on Twitter at - https://twitter.com/itheum
- Speak to us directly on Discord at - https://discord.gg/y77P9gKF27

## Team Members

- Mark Paul (Blockchain Lead)
- Mridul Khanal (Cryptography Lead)
- Dineish Nathan (Data Security Lead)

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/markpaulweb/
- https://www.linkedin.com/in/mkhanal/
- https://www.linkedin.com/in/dineish/

## Team Website
https://itheum.com

## Relevant Experience
As a team we each have over 20 years experience in the software engineering, technology, data and security industry and have worked for the some of the largest global corporates (spanning Government, Banking, Consulting, Media etc). We are now moving into the blockchain tech space to solve the "public/social goods" issue around data governance, data sharing and personal data sovereignty.

## Team code repositories
- https://github.com/Itheum/data-dex
- https://github.com/Itheum/itheumcore

# Additional Information

- We'd like some help from the FileCoin dev team to help us expand on our use-cases beyond just storage. Privacy Preserving Computation using the distributed compute (near storage) nodes is of particular interest to us as we are now exploring a multiparty computation use case (i.e. how can we share data across enterprises to get shared insights without exposing the origin source). We have data from multiple companies who are running the OKPulse Employee Wellness app so its a perfect use case to demonstrate this technology.
- We'd like some help from the Hedera team on how we can best use their frameworks and tools to expand our data brokerage solution to include an enterprise tier for organisations to share data amounst themselves. This would be our enterprise offering that will help support funding to keep our public good offering free for everyone.
