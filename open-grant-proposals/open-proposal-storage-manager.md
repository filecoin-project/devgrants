# Open Grant Proposal: `Storage Manager`

**Name of Project:** Storage Manager

**Proposal Category:** `app-dev`

**Proposer:** `edisinovcic`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

We are building GUI tool that will make it easy for the end-users to interact with filecoin.
We are going to build a React frontend that will show interaction with storage functionality in a friendly way.
On the backend, we will be running a full filecoin node and express API. API will convert API calls to cli calls for filecoin node for importing, storing, retrieving and checking all important data about current deals and miners. We will make use of the [lotus-jsonrpc-engine](https://github.com/openworklabs/lotus-jsonrpc-engine) package where it will be needed.

## Value

- Our project will provide better user experience for general audience and help widespread   Filecoin project
- Risks are low because currently there are no such tools and users have to use cli tools to interact with filecoin, only risk is that they pay for storage via our node (they use our running filecoin node) and are not paying for storage themselves and that means that we are in control of the data. Currently there is no better solution for this, but in the future integration with wallets, signing etc. would be a possibility to fix this. 
- We need a stable testnet for this to work. On our end we could run multiple nodes so if one goes down, we have backups

## Deliverables

* Frontend (react)
* Storing data
    * Multiple file upload to frontend
    * Listing uploaded files
    * List all miners available for storing data
    * List requirement of specific miner 
    * Store data CID with a miner
    * Check the status of the deal
    * Show Deal CID
* Retrieving data
    * Find by Data CID
    * Retrieve by Data CID
* Lotus stats
    * Lotus sync status
    * Showing the head tipset
* Backend (node.js/express)
We will have an express app that uses lotus-jsonrpc-engine for connecting and making calls to full node.
App will be written in typescript.
It will support all API calls that need to be converted to cli commands.
Websocket connection would be open between frontend and backend so users can have a real-time output of the cli
Lotus (one node in the first version, more in the future).

This way where users use our wallets in lotus is the only proper solution for testnet. For mainnet their wallets need to be used and that will be integrated in the next phase.

## Development Roadmap

### Milestone 1:
* Goals:
    * Specification document 
        * 2 members (project manager and lead developer)
        * 3 days 
        * 2400 $
    * Finish UI/UX design for frontend
        * 5 days 
        * 1 designer
        * 1600 $
* Cost: 4000 $
* Time: 10 days

### Milestone 2:
* Goals:
    * Setup lotus node
        * 1 Infrastructure engineer
        * 2 days 
        * 800 $
    * Setup express API
        * 1 backend engineer
        * 2 days
        * 800 $
    * Setup a basic react app
        * 2 days 
        * 1 frontend engineer
        * 800 $
    * Lotus sync status, head tipset on the frontend 
        * 1 days
        * 1 frontend engineer
        * 400 $

* Cost: 2800 $
* Time: 10 days (react will be setup after express and lotus node)

### Milestone 3:
* Goals:
    * Multiple file upload to frontend and sending them to backend and storing in filesystem on the backend so the path can be sent to filecoin
        * 9 days
        * 1 frontend, 1 backend engineer
        * 7200 $
    * Listing all uploaded files on frontend
        * 1 day
        * 1 frontend engineer
        * 400 $
    * List all miner available for storing data and list requirements of a specific miner
        * 1 days 
        * 1 frontend engineer, 1 backend engineer
        * 800 $
    * Store data CID with a miner, show deal CID, check the status of the deal, find by data CID, Retrieve by Data CID
        * 8 days
        * 1 frontend
        * 3200 $ 
        * 3 days
        * 1 backend engineers
        * 1200 $

* Cost: 12800 $
* Time: 20 days


### Milestone 4:
* Goals:
    * User documentation
        * 2 days
        * 1 frontend developer, 1 project manager
        * 1280 $
    * Developer documentation
        * 2 days
        * 1 infrastructure engineer, 1 project manager 
        * 1280 $
    * Stress testing
        * 2 days 
        * 1 infrastructure engineer
        * 800 $
    * Production deployment 
        * 3 days
        * 1 infrastructure engineer
        * 1200 $
    * QA with bug fixes


* Cost: 4560 $
* Time: 11 days

Milestone 1 - 4000$
Milestone 2 - 2800$
Milestone 3 - 12800$
Milestone 4 - 4560$

| Role 		          | Rate / hour |
| -------------------------- | ------  |
| Designer                  | 40 $  |
| Lead developer        | 70 $ |
| Backend developer  | 50 $ |
| Frontend developer  | 50 $ |
| Project manager       | 30 $ |
| Infrastructure engineer | 50 $ |


Total: 24160 $

## Maintenance and Upgrade Plans

This is a first version that is only meant to be used for testnet or local devnet. In the future we will have multiple nodes running as a backup, so we can have almost 100% uptime and we will customize it for mainnet once it’s live. Also service will be running on kubernetes once we reach production version (integration with mainnet). Once the mainnet is connected we would like to integrate the wallet with our solution so users can sign transactions with their own keys and not ours (lotus running instances).
# Team

## Team Members

- Edi Sinovcic
- Darko Macesic
- Jakov Buratovic
- Igor Lide

## Team Member LinkedIn Profiles

- [Edi](https://www.linkedin.com/in/edi-sinovcic/)
- [Darko](https://www.linkedin.com/in/darko-macesic/)

## Team Website

#### [shardlabs.io](https://shardlabs.io/)

## Relevant Experience

We are a team of four with expertise in providing different full-stack blockchain solutions. We are working part time on projects for Ethereum Foundation and ZoKrates as external contributors and have also done grants for Web3 Foundation. We have closely cooperated with Remix, Solidity teams and are pushing towards more enterprise approach for tools like ipfs and similar. We believe that decentralization is the key and that it needs to be integrated into standard web2 tools and services and that it will bring more transparency, security and trustworthiness to those systems by forcing collectors of the data to be responsible to the end users.

## Team code repositories
[source-verify](https://github.com/ethereum/source-verify) - utility to check integrity of deployed smart contracts on Ethereum blockchain
[ZoKrates](https://github.com/Zokrates/ZoKrates) - a toolbox for zkSNARKs on Ethereum
[ink-remix-plugin](https://github.com/blockchain-it-hr/ink-remix-plugin) - plugin for Remix IDE used for creating and building ink polkadot smart contracts straight from browser. It uses a websocket connection to the backend and controls ink cli while showing real time updates in the plugin.
[zokrates-remix-plugin](https://github.com/blockchain-it-hr/zokrates-remix-plugin) - frontend implementation of ZoKrates
[remixd](https://github.com/blockchain-it-hr/remixd) - service for Remix IDE that allows file manager access to local storage

# Additional Information

We’ve already tested quite a bit of your platform and have decided to contribute to it by giving you and your users even better UX. Building on ipfs is one of the most interesting areas that we explore now and platforms like filecoin feel like a great match for us.
