
# RFP Proposal: `FilMarket`

**Name of Project:** FilMarket

**Link to RFP:** [NEAR x Filecoin](https://github.com/filecoin-project/devgrants/blob/master/rfps/near-and-filecoin.md)

**RFP Category:** app-dev

**Proposer:** arctic-ash (CrossChainLabs)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Filecoin facilitates open markets for storing and retrieving files that anyone can participate in. As a result the available storage and pricing is not controlled by any single company. Which makes it a bit difficult for users to get a clear overview on the price that they have to pay to store a TB of date per year, which storage provider should they choose, what storage power does it has, what is the difference compared to the average storage price per geographical region and also what is the evolution of the price per TB of storage over a period of a year. 

The solution that the CrossChain Labs presents is going to address all the uncertainties described above and offer clarity on the storage pricing, helping the user take the right decision for its storage requirements. For making this process transparent all the essential information is going to be kept into a NEAR smart contract, which cuts the need of having a traditional backend connected to a database. As a conclusion the use of the NEAR smart contract will provide clarity and a verifiable proof of all the price data points used by the FilMarket app.

## Value

There are many benefits of getting the FilMarket project up and running:
 - offer a clear overview on storage pricing, easily accesible by having all the required data on a nicely designed dashboard
 - increase the user's apettite for storing data into the Filecoin network fueled by seeing how cheap is to store
 - the implemented API can be easily integrated in other apps
 
The risks are low since since the architecture has a robust structure that doesn't include the usage of a traditional backend with a database, data is stored in the NEAR smart contract.
CrossChain Labs team is experienced enough to accomplish this project and to maintain it during the new releases of Lotus updates.

## Deliverables

### Dashboard Overview
![image](https://github.com/CrossChainLabs/devgrants/blob/3c196deef27028874538a96ad66fa0ce31ce33a9/rfp-proposals/filMarketDashboard.png)
---
- FilMarket Dashboard that will include:
  - average storage price of 1 TB per year
  - evolution of the FIL price on the last 24hours
  - network power increase compared to last month
  - average storage price chart per 1 TB of data per year, for different geographical regions: North America, Europe, Asis and others
  - pie chart with the number of active storage providers per geographical regions
  - list of storage providers that contains: miner ID, region, power, USD price, FIL Price

- FilMarket Bot that will serve to get all the required data from Lotus node and interact with NEAR smart contract.

- Filmarket Smart Contract based on NEAR protocol.

## Development Roadmap

**Milestone 1**

FilMarket bot and Filmarket smart contract based on NEAR protocol are being implemented as following:

- FilMarket smart contract:
  - receives active storage providers list with the current storage prices for each storage provider
  - calculate averages per region and global average

- FilMarket Bot:
  - every 24 hours updates the list with active storage providers
  - request the price for each storage provider using a lotus node
  - send the list with the current storage prices for each storage provider to NEAR smart contract

Members:
- Andreea - Full Stack Developer (JavaScript, Rust, dev-ops)
- Cristina - Full Stack Developer (JavaScript, React)

Completed By: 15th of December, 2021

Budgetary Needs: This milestone will last 4 weeks = $14,000

**Milestone 2**

Create the frontend and integrate it with FilMarket smart contract:
- FilMarket Dashboard
  - average storage price of 1 TB per year
  - evolution of the FIL price on the last 24hours
  - network power increase compared to last month
  - average storage price chart per 1 TB of data per year, for different geographical regions: North America, Europe, Asis and others
  - pie chart with the number of active storage providers per geographical regions
  - list of storage providers that contains: miner ID, region, power, USD price, FIL Price

Members:
- Andreea - Full Stack Developer (JavaScript, Rust, dev-ops)
- Cristina - Full Stack Developer (JavaScript, React)
- Florin - UI/UX Designer (Sketch, Figma)

Completed By: 1st of February, 2022

Budgetary Needs: This milestone will last 6 weeks = $25,000

**Milestone 3**

Make the final adjustments and release the product:
  - create the production infrastructure
  - move the smart contract on mainnet
  - deploy filmarket.io Dapp 
  - run the final tests
  - public release

Members:
- Andreea - Full Stack Developer (JavaScript, Rust, dev-ops)
- Cristina - Full Stack Developer (JavaScript, React)

Completed By: 15th of February, 2022

Budgetary Needs: This milestone will last 2 weeks = $11,000

## Total Budget Requested

We're requesting a total funding of $50,000 to complete all the above milestones, and the fund will be split into:

- Research and Development
- UX
- Infrastructure

| Milestone  | Duration| Cost    |
|------------|---------|---------|
|   #1       | 4 weeks | $14,000 |
|   #2       | 6 weeks | $25,000 |
|   #3       | 2 weeks | $11,000 |
|            |         |         |
| **Total**  | 12 weeks| $50,000 |

> NOTE: The cost of Milestone 3 includes NEAR transactions fees and cloud infrastructure cost estimated $4,000.

## Maintenance and Upgrade Plans

This is an open source project and we are committed in maintaining it by upgrading to comply with newest Lotus and NEAR SDK releases, doing bug fixes and adding new features based on the community feedback. 

# Team

## Contact Info
We thank you for your interest in FilMarket project. If you have and questions don't hesitate to contact Andreea at andreea.stefan@crosschainlabs.tech 

## Team Members

- Andreea - Full Stack Developer (JavaScript, Rust, Go, dev-ops, C++)
- Cristina - Full Stack Developer (JavaScript, React)
- Florin - UI/UX Designer (Sketch, Figma)

## Team Member LinkedIn Profiles

- [Andreea Stefan](https://www.linkedin.com/in/andreea-stefan-66740b20/)
- [Cristina Varteniuc](https://www.linkedin.com/in/cristina-varteniuc-6b3121224/)
- [Florin Gradinaru](https://ro.linkedin.com/in/florin-gradinaru-73891bb)

## Team Website

https://github.com/CrossChainLabs

## Relevant Experience

We are a team of developers with experience in blockchain technologies. Some of the latest dev-grants were for projects from NEAR protocol (NEAR registrar, Audit Registry, near.link) with tech stack: IPFS, rust, react, go and javascript.
- Andreea Stefan - is an ex Consensys employee and the co-founder of Crosschain Labs. Has a work experience as a software developer of 14 years and her main focus for the last several years is blockchain development
- Cristina Varteniuc - accomplished numerous courses of software development, participated to multiple hackatons and her focus is in blockchain-related products development
- Florin Gradinaru - is an experienced artist and graphic designer with 18 years of work experience and a strong passion for UI/UX

## Team code repositories

- https://github.com/CrossChainLabs
- https://filmarket.io (coming soon)

