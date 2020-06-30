# Open Grant Proposal: `Storage Manager`

**Name of Project:** Storage Manager

**Proposal Category:** `app-dev`

**Proposer:** `edisinovcic`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

We are building the decentralized GUI tool that will make it easy for the end-users to interact with filecoin.
We are going to build a frontend app deployed to the IPFS that will show interaction with storage functionality in a friendly way.

## Value

- Our project will provide better user experience for general audience and help widespread   Filecoin project
- Risks are low because currently there are no such tools and users have to use cli tools to interact with filecoin
- We need a stable public node for this to work

## Deliverables

* Frontend
    * Storing data
        * Wallet provider integration
        * Multiple file upload to frontend
        * Listing uploaded files
        * Encrypt files using PGP
        * List all miners available for storing data
        * List requirement of specific miner 
        * Store data CID with a miner
        * Check the status of the deal
        * Show Deal CID
    * Retrieving data
        * Find by Data CID
        * Retrieve by Data CID
        * Decrypt retrieved data
    * Public node stats
        * node sync status
        * Showing the head tipset

## Development Roadmap

### Milestone 1:
* Goals:
    * Specification document 
        * 3 days       
        * 2 members (project manager and lead developer)
        * 2400 $ 
    * Create UI/UX design for the frontend
        * 5 days 
        * 1 designer
        * 1600 $
* Cost: 4000 $
* Time: 8 days

### Milestone 2:
* Goals:
    * Initialize a frontend app
        * 2 days 
        * 1 software engineer
        * 800 $
    * Public node sync status, head tipset on the frontend 
        * 2 days
        * 1 software engineer
        * 800 $
    * Multiple file upload to frontend
        * 5 days
        * 1 software engineer
        * 2000 $

* Cost: 3600 $
* Time: 9 days

### Milestone 3:
* Goals:
    * Encryption/Decryption
        * 10 days
        * 1 software engineer
        * 4000 $
    * Listing all uploaded files on frontend
        * 2 day
        * 2 software engineer
        * 1600 $
    * List all miner available for storing data and list requirements of a specific miner
        * 2 days 
        * 2 software engineer
        * 1600 $
    * Store data CID with a miner, show deal CID, check the status of the deal, find by data CID, Retrieve by Data CID
        * 2 days
        * 2 software engineer
        * 1600 $ 

* Cost: 8800 $
* Time: 16 days


### Milestone 4:
* Goals:
    * User documentation
        * 2 days
        * 1 software engineer, 1 project manager
        * 1280 $
    * Developer documentation
        * 6 days
        * 1 infrastructure engineer, 1 project manager 
        * 1920 $
    * Production deployment 
        * 2 days
        * 1 infrastructure engineer
        * 800 $
    * QA with bug fixes
        * 10% of total price


* Cost: 4000 $
* Time: 9 days

Milestone 1 - 4000 $
Milestone 2 - 3600 $
Milestone 3 - 8800 $
Milestone 4 - 4000 $

| Role 		          | Rate / hour |
| -------------------------- | ------  |
| Designer                  | 40 $  |
| Lead developer        | 70 $ |
| Software engineer  | 50 $ |
| Project manager       | 30 $ |
| Infrastructure engineer | 50 $ |


Total (without QA): 20400 $ 
Total (with QA) 22440$

## Maintenance and Upgrade Plans

First implementation will store 3 copies of desired files without splitting. Plan is to research the erasure encoding algorithm to save resources in the future and implement it on frontend. That will provide a more precise recommendation on the number of copies. Also, we will split files larger than 32 GB in chunks in the future also. 

# Team

## Team Members

- Edi Sinovcic
- Darko Macesic
- Jakov Buratovic
- Igor Lide
- Karlo Majer
- Ana Milic-Strkalj

## Team Member LinkedIn Profiles

- [Edi](https://www.linkedin.com/in/edi-sinovcic/)
- [Darko](https://www.linkedin.com/in/darko-macesic/)
- [Jakov](https://www.linkedin.com/in/jakov-buratovic/)

## Team Website

#### [shardlabs.io](https://shardlabs.io/)

## Relevant Experience

We are a team of six with expertise in providing different full-stack blockchain solutions. We are working part time on projects for Ethereum Foundation and ZoKrates as external contributors and have also done grants for Web3 Foundation. We have closely cooperated with Remix, Solidity and ZoKrates teams and are pushing towards more enterprise approaches for tools like IPFS and similar. We believe that decentralization is the key and that it needs to be integrated into standard web2 tools and services and that it will bring more transparency, security and trustworthiness to those systems by forcing collectors of the data to be responsible to the end users.

## Team code repositories
[sourcify](https://github.com/ethereum/sourcify/pull/201) - new UI (PR in progress, images in comments)
[source-verify](https://github.com/ethereum/source-verify) - utility to check integrity of deployed smart contracts on Ethereum blockchain (same project as sourcify, just above is the UI that you can take a look from design perspective)
[ZoKrates](https://github.com/Zokrates/ZoKrates) - a toolbox for zkSNARKs on Ethereum
[ink-remix-plugin](https://github.com/blockchain-it-hr/ink-remix-plugin) - plugin for Remix IDE used for creating and building ink polkadot smart contracts straight from browser. It uses a websocket connection to the backend and controls ink cli while showing real time updates in the plugin.
[zokrates-remix-plugin](https://github.com/blockchain-it-hr/zokrates-remix-plugin) - frontend implementation of ZoKrates
[remixd](https://github.com/blockchain-it-hr/remixd) - service for Remix IDE that allows file manager access to local storage
[shardlabs](https://github.com/Shard-Labs/) - company repository
[blockchainit](https://github.com/blockchain-it-hr/) - company repository before rebranding

# Additional Information

We’ve already tested quite a bit of your platform and have decided to contribute to it by giving you and your users even better UX. Building on ipfs is one of the most interesting areas that we explore now and platforms like filecoin feel like a great match for us.
