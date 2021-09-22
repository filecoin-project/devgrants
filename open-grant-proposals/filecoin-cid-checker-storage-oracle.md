# Open Grant Proposal: `Filecoin CID Checker and Storage Oracle`

**Name of Project: Filecoin CID Checker and Storage Oracle**

**Proposal Category: `app-dev`**

**Proposer: `bradleymd`**

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?: "Yes"** 

# Project Description

We will implement a website and API service that is listed as a high priority for FileCoin project. It can list all CIDs along with their current status in the latest state tree.

The page could also support queries by CID or miner. One option would be to build 1 long table that shows each miner x sectors they are storing x state as a colored indicator:

green - good grey - capacity red - failing

## Value

This site and API could be used as an oracle of storage status that anyone can run alongside a full node.

For retrieval miners, this indexes from which storage miners they can retrieve requested CIDs.

For storage miners, this indexes redundant copies being stored with other storage miners, in case they need to retrieve data cheaply due to data corruption or loss.

Risk are low as there are no such tools to interact with FileCoin.
 
## Deliverables

- Website
- API
- Documentation

## Development Roadmap

### Milestone 1: Project Design
* Goals:
    * Project specification documentation 
        * project manager and lead developer
        * 4 days 
    * UI/UX Design.
        * 6 days 
        * 1 designer
        
* Cost: 3000 $
* Time: 2 weeks

### Milestone 2: Infrastructure
* Goals:
    * Lotus node configuration
        * Infrastructure engineer
        * 5 days 
    * Lotus node syncing, monitoring and backup configuration
        * Architect and Infrastructure engineer
        * 5 days

* Cost: 5000 $
* Time: 2 weeks

### Milestone 3: Development
* Goals:
    * Complete file upload from front end to filecoin backend.
        * frontend and backend engineer
        * 9 days
    * File management on the frontend including file list.
        * frontend engineer
        * 1 day
    * Implement storage Oracle
        * frontend and backend engineer
        * 1 days 
    * Implement File CID Checker
        * frontend and backend engineer
        * 12 days

* Cost: 10000 $
* Time: 3 weeks

### Milestone 4: Deployment
* Goals:
    * User documentation
        * frontend developer and project manager
        * 2 days
    * Developer documentation
        * infrastructure engineer and project manager 
        * 2 days
    * Stress testing
        * infrastructure engineer
        * 2 days 
    * Production deployment 
        * infrastructure engineer
        * 3 days
    * QA with bug fixes

* Cost: 2000 $
* Time: 2 weeks

## Total Budget Requested

$20,000.

## Maintenance and Upgrade Plans

The team will maintain the package long-term. We should have a version before the mainnet launch of FileCoin, and we will release future versions with new FileCoin release.

# Team

## Team Members

Bradley Fish: https://github.com/bradleymd
Jinwen Long: https://github.com/8696
Alex Oliveira: https://github.com/alexoliveira21

## Relevant Experience

I have participated in the FileStorm project that utilizes IPFS for storage
The website:
https://github.com/MOACChain/FileStorm/tree/master/filestorm-info-web
The SDK:
https://github.com/filestorm-fst/js-fstorm-http-client

## Team code repositories

https://github.com/filestorm-fst/go-stormchain
