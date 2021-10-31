To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `filecoin-near-digital-market`

**Name of Project:** `fn-digital-market`

**Proposal Category:** `app-dev`

**Proposer:** `w0xpo`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `Yes`

# Project Description

At first release it will be blockchain ticket-office for concerts, lottery, transport or any other event. Website + mobile app, that allows user to buy tickets via near protocol ans store required booking information at filecoin system. Only buyer's wallet should be eligible to use ticket, so some protection system should be implemented (in-app ticket usage or encoding with NEAR wallet key).

As tickets are protected by blockchain so for sharing ticket user should use transfer-ownership feature (in case when event implies transfer of rights). As additional feature will be allowed to import any existing ticket to protect and store them in blockchain. 

Created platform will have full potential to be easily transformed to digital assets marketplace.

## Value

Popularization of blockchain technologies such as Filecoin or NEAR could be achieved via using them in everyday life. That is why our way is introduction suitable apps which provides easy and secure access to digital assets.
- What are the benefits to getting this right?
  - Seamless transition and user confidence in the blockchain tech. Let's start from something everyday and domestic.
- What are the risks if you don't get it right?
  - Wasted time. But anyway we will get opensource codebase which could be used in similar integrations 
- What are the risks that will make executing on this project difficult?
  - Performance in case of becoming project too popular. neither NEAR nor Filecoin protocol is a bottleneck so all other issues could be solved by hiring experienced DevOps engineer for system scaling.

## Deliverables

### NEAR smart contract
Core of project is blockchain instructions for confirming deals and payment processing. At this point we also must implement security layer for digital assets ownership protection.

### Website
Marketplace and user personal area, available after connecting NEAR wallet. User can see digital assets he owns or buy available.

### Admin panel + Vendor API + Service
Website area for vendors where digital assets could be put up for sale. Firstly - manual management, in following milestones - integration with vendor API + service.

### Backend + API
Website and mobile app support.

### Mobileapp
All features in suitable form.

## Development Roadmap

### Milestone 1: Core

Expect: First step with core features of the project - smart contract for NEAR blockchain.

Roles: Blockchain dev, System architect, QA engineer

Estimated duration: 3 weeks

Budget: $14,000

### Milestone 2: Security layer, website

Expect: NEAR + Filecoin integration with security layer support. Website skeleton

Roles: Blockchain dev, System architect, Frontend dev, QA engineer, DevOps

Estimated duration: 3-4 weeks

Budget: $38,000

### Milestone 3: Website

Expect: Customers interfaces for marketplace, share and import features and wallet connection.

Roles: Backend dev \ System architect, Frontend devs, QA engineer, DevOps, Blockchain dev (partially)

Estimated duration: 8-10 weeks

Budget: $53,000

### Milestone 4: Vendor admin panel

Expect: Vendors must be able to place assets\goods information at the marketplace via this interface

Roles: Backend dev \ System architect, Frontend dev, QA engineer, DevOps

Estimated duration: 8-10 weeks

Budget: $45,000

### Milestone 5: Mobile apps (independent step)

Note: Could be implemented simultaneously with Milestone 3

Expect: Mobile apps development. Android + iOS

Roles: Backend dev \ System architect, Mobile devs, QA engineer

Estimated duration: 8-10 weeks

Budget: $36,000

### Milestone 6: Vendor API (independent step)

Note: Could be implemented simultaneously with Milestone 4

Expect: 2-side integration for Vedors. Here we're exposing API and expect some API to be implemented on vendor's side.

Roles: Backend dev \ System architect, Frontend dev, QA engineer, DevOps

Estimated duration: 8-10 weeks

Budget: $30,000

## Total Budget Requested

Total: $216,000

## Maintenance and Upgrade Plans

In our plans for couple of years:
- Website and mobile applications support and maintenance
- Integrations with vendors, service updates
- Hotfixes at any layer
- Marketing and distribution of project

# Team

## Team Members

### Roles
- Blockchain dev
- Frontend dev x 2
- Backend dev \ System architect
- Mobile dev x 2
- Designer (mobile + web)
- QA engineer x 2
- DevOps

## Relevant Experience

For now we have core team of:
- Senior backend developer with tech-lead and system architect role (.NET, NodeJS, Phyton - 10+ years)
- Senior Frontend developer (React, Vue, NodeJS - 8+ years)
- Android developer (Java 5+ years)
- Rust developer with 1 year experience in blockchain

All other staff listed in roles we plan to attract as freelancers

# Additional Information

TBD: Please include any additional information that you think would be useful in helping us to evaluate your proposal.
