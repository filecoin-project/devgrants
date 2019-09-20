# RFP Proposal: `ars-js-filecoin-explorer`

**Name of Project:** js-filecoin-explorer

**Link to RFP:** [rfp-block-explorer](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-block-explorer.md)

**RFP Category:** `app-dev`

**Proposer:** [@waynewyang](https://github.com/waynewyang)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes



# Project Description

The main purpose of js-filecoin-explorer is to give clearly views and general search functions for users of filecoin network, including clients, developers, miners, and investors. They can deeply know about filecoin network through js-filecoin-explorer.

In order to meet needs of different users, we divide the filecoin blockchain explorer into four functional dimensions, 

- Blockchain
  - Including  Tipset, Block, Message, Actor.
- Token
  - Transaction history
  - Token History
    - Plan block rewards
    - Real block rewards
    - Liquid token 
    - Collateral token
    - Account that held token
- Storage Market
  - Storage miner 
  - Storage client
  - Storage ask
  - Storage miners history
  - Storage clients history
  - Storage deals history
- Retrieval Market
  - Retrieval miner 
  - Retrieval client
  - Retrieval ask
  - Retrieval miners history
  - Retrieval clients history
  - Retrieval deals history

## Deliverables

Firstly, We'll meet the RFP requirements,
- [rfp-deliverables](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-block-explorer.md#deliverables)

And our implementation will including the functions that the history implementation and the Requirements of the RFP, as below .

- [Filecoin Network Stats Dashboard](https://stats.kittyhawk.wtf/)
- [Block explorer](http://user.kittyhawk.wtf:8000/)
- [Detailed Requirements & Constraints](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-block-explorer.md#detailed-requirements--constraints)
  - [User Flows](#https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-block-explorer.md#user-flows)
  - [Data to Display](#https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-block-explorer.md#data-to-display)

Besides, We will provide more  functions in our implementation, for example,

- 1 Global 
  - General search function,you can search by block height or a CID etc., perherps the CID is a miner address, an account, a message, an actor,or an ask etc.

- 2 Overview
  - Best tipset,avg…，etc
  - blockchain growing in real time
  - Trend chart of storage miners
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart: 
        - total power
        - total collateral
      - histogram:  total counts of active storage miner
  - Trend chart of storage deals
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart:  dealed price (min,max,avg,start,end)
      - histogram:  
        - duration active clients counts
        - duration dealed capacity
  - Trend chart of retrieval miners
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart: total retrieval capacity
      - histogram:  total counts of retrieva miner
  - Trend chart of retrieval deals
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart:  dealed price (min,max,avg,start,end)
      - histogram:  
        - duration active clients counts
        - duration dealed capacity
  - Trend chart of  transfer
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart:  
        - duration active  transfer amount
      - histogram:  
        - duration active account counts

- 3 Block Chain
  - Chain
  - Actor



- 4 StorageMarket
  - Trend chart of storage miners ，power&collateral
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart: 
        - total power
        - total collateral
      - histogram:  total counts of active storage miner
  - Trend chart of storage miners counts
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart:
        -  counts of total miners 
        - counts of active miners 
      - histogram:  
        - duration counts of new miners 
  - Trend chart of storage clients counts
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart: counts of total clients 
      - histogram:  
        - duration counts of new clients 
  - Trend chart of storage deals
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart:  dealed price (min,max,avg,start,end)
      - histogram:  
        - duration active clients counts
        - duration dealed capacity
        - duration dealed counts
        - duration dealed time cost
  - Storage deal Size Distribution
    - The pie chart
  - Trend chart of storage ask
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart:  ask price (min,max,avg,start,end)
      - histogram:  
        - duration active miners counts
        - duration dealed capacity
- 5 RetrievalMarket
  - Trend chart of retrieval miners ，power&collateral
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart: 
        - total retrieval capacity
      - histogram:  total counts of active retrieval miner
  - Trend chart of retrieval miners counts
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart:
        -  counts of total miners 
        - counts of active miners 
      - histogram:  
        - duration counts of new miners 
  - Trend chart of retrieval clients counts
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart: counts of total clients 
      - histogram:  
        - duration counts of new clients 
  - Trend chart of retrieval deals
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart:  dealed price (min,max,avg,start,end)
      - histogram:  
        - duration active clients counts
        - duration dealed capacity
        - duration dealed counts
        - duration dealed time cost
  - Retrieval deal Size Distribution
    - The pie chart
  - Trend chart of retrieval ask
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart:  ask price (min,max,avg,start,end)
      - histogram:  
        - duration active clients counts
        - duration dealed capacity
- 6 Token
  - Trend chart of  transfer
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart:  
        - duration active  transfer amount (min,max,avg,start,end)
      - histogram:  
        - duration active account counts
  - Trend chart of  token
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart:  
        - total  liquid
        - total collateral
        - total account that held token
      - histogram:  
        - duration new liquid
        - duration new collateral
        - duration new account that held token
  - Trend chart of  block reward
    - abscissa: Time(24hour,Day,Week,Month,Year)
    - ordinate:
      - The line chart:  
        - Planed total block rewards
        - Real total block rewards
      - histogram:  
        - Planed duration new block rewards
        - Real duration new block rewards



**Domain and server**

- Domain
- norton https
- AWS, AWS allowing you to quickly scale capacity, both up and down. And Cloud security at AWS is the highest priority. Using  CDN will establish and maintain secure connections closer to the requestor

**Now, We've already do some pre work**,

- The draft DB design of the back-end design.
- Draft of UE/UI design.
- Demo of our project.



## Development Roadmap

**Total Funding Amount:$25,000** 

**Milestones:** 

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | 1)Low-fidelity design mockups.<br />Visual design and animation design, produce clickable high fidelity mockups.<br />2)running staging site with some UI elements implemented. 3) DB design. | $10,000 | 4 weeks |
| 2 | Completed implementation of block explorer | $7,500 | 6 weeks |
| 3 | All project deliverables are completed and added to the [Filecoin Shipyard](https://github.com/filecoin-shipyard) (website, documentation, codebase) | $2,500 | 2 weeks |
| 4 | Maintenance and Upgrade | $5,000 |1 year|



**M1（2019.10.8 -2019.11.8）:**

- **Total Funding Amount:20,000**

| No. | Software Functionality | Team Member | Funding Required |
| --- | --- | --- | --- |
| 1                 | Low-fidelity design mockups.<br />Visual design and animation design, produce clickable high fidelity mockups. | [@fengyuxilu](https://github.com/fengyuxilu)<br />[@Frank-design](https://github.com/Frank-design)<br /> | $3,750 |
| 2 | Front-end component desgin,  finish staging site with some UI elements implemented. | [@maxi-zhang](https://github.com/maxi-zhang)<br /> | $2,500 |
| 3 | Arch design, filecoin explorer DB, and api Design. |  [@waynewyang](https://github.com/waynewyang) | $3,750 |



**M2（2019.11.11-2019.12.20）:**

- **Total Funding Amount:15,000**

| No. | Software Functionality | Team Member | Funding Required |
| --- | --- | --- | --- |
| 1 | Finish front-end develop. | [@maxi-zhang](https://github.com/maxi-zhang) | $3,750 |
| 2 | Finish Back-end develop. |  [@waynewyang](https://github.com/waynewyang) | $3,750 |



**M3（2019.12.23-2020.01.10）:**

- **Total Funding Amount:$5,000**

| No. | Software Functionality | Team Member | Funding Required |
| --- | --- | --- | --- |
| 1    | All project deliverables are completed and added to the [Filecoin Shipyard](https://github.com/filecoin-shipyard) (website, documentation, codebase),Pre-delivery testing | [@maxi-zhang](https://github.com/maxi-zhang)<br /> [@waynewyang](https://github.com/waynewyang) | $2,500 |



**M4（2020.01.12-2020.12.31）:**

- **Total Funding Amount:$10,000**

| No.  | Software Functionality  | Team Member      | Funding Required |
| ---- | ----------------------- | ----------- | ----------------- |
| 1    | Maintenance and Upgrade | Arsyun team | $5,000          |



## Total Budget Requested

| Milestones | Funding Amount |
| --- | --- |
| M1 | $10,000 |
| M2 | $7,500 |
| M3 | $2,500 |
| M4 | $5,000 |
| **Total** | **$25,000** |



## Maintenance and Upgrade Plans

- Interesting on long term maintenance and upgrade plan

  

# Team

## Team Members
- [@fengyuxilu](https://github.com/fengyuxilu): pm/ue
- [@Frank-design](https://github.com/Frank-design): ui
- [@maxi-zhang](https://github.com/maxi-zhang) : front-end
- [@waynewyang](https://github.com/waynewyang) : arch/back-end

## Team Member LinkedIn Profiles

- [waynewyang](https://www.linkedin.com/in/waynewyang/?locale=en_US)


## Team Website

- https://www.arsyun.com
- https://github.com/arsyun

## Relevant Experience

- ARS team has rich experience in distributed cloud storage and has deployed practical products. And provides cloud service base on IPFS and filecoin.
  - [Essential-Thinking-of-Blockchain](https://github.com/arsyun/Essential-Thinking-of-Blockchain)
  - [Product:pServer](https://www.arsyun.com/web/index.html)
-  [@waynewyang](https://github.com/waynewyang) is the [Contributor](https://github.com/filecoin-project/go-filecoin/graphs/contributors) of go-filecoin, we can deeply understand the work flow about file coin.
- ARS Team has been attended IPFS camp in berlin and Barcelona, We're very interesting in IPFS and filecoin, and plan to do some application based on IPFS & filecoin.

## Team code repositories

- https://github.com/arsyun.
- https://github.com/arsyun/js-filecoin-explorer

# Additional Information

**Now, We've alreay do some pre work**,

- [Demo code of ars-js-filecoin-explorer](https://github.com/arsyun/js-filecoin-explorer)
  - Front-end: React
  - Back-end: Nodejs
- [ Backend db design of ars-js-filecoin-explorer ](https://github.com/arsyun/js-filecoin-explorer/tree/master/db)
  - Mongodb, Read > Write.
- [Ue draft of ars-js-filecoin-explorer ]( https://wbhnrp.axshare.com )


**The Funding  does not include server rental**