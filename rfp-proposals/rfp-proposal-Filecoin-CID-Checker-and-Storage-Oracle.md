**Name of Project:** Filecoin CID Checker and Storage Oracle

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#filecoin-cid-checker-and-storage-oracle

**RFP Category:** `app-dev`

**Proposer:** [@mgarciap](https://github.com/mgarciap)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

The motivation behind the proposal is to deliver a positive change to the experience of end users and developers engaged in the Filecoin network. 

As a user, if I want to check and verify the state of my files stored in the Lotus network, currently I can only do it using the Lotus CLI, which is not always convenient.

This is a proposal for one of the high priority RFP ideas listed in [New RFP Ideas for Wave 3](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#filecoin-cid-checker-and-storage-oracle), the **Filecoin CID Checker and Storage Oracle**:
> A website and API service that can list all CIDs along with their current status in the latest state tree
> The page could also support queries by CID or miner. One option would be to build 1 long table that shows each miner x sectors they are storing x state as a colored indicator:
green - good grey - capacity red - failing


## Value for the community

- The website and API can be used as an oracle of storage status that anyone can run alongside a full node.
- As a retrieval miner I can index from which storage miners I can retrieve requested CIDs.
- As  a storage miner I can index redundant copies being stored with other storage miners, in case I need to retrieve data cheaply due to data corruption or loss.


Delivering this project will enable Protofire - 30+ engineers blockchain dev shop with proven experience and reputation in the Ethereum ecosystem - to grow its skills around the Filecoin technology and to get to know the ecosystem so we can contribute more and help bootstrap developer adoption and network usage long term.


## Deliverables

- An open-sourced, dual-licensed (under MIT and APACHE2) service that will allow any network participants to access a website and an API that can be used as an oracle of storage status  which can run alongside a full node.
- Well-documented code for the service conforming to best practices.



## Development Roadmap

### Milestone 1 - Complete specifications
- Goals:
  - Finalize components deployment and low level research
  - Finalize specs and architecture
  - Validate specs with the Filecoin team
- Deliverables:
  - Detailed website and API specs
  - UI wireframes
- Outcomes:
 - Expectations, scope, effort and budget will be clear for everybody
- Duration: 1 week
- Team: Part-time Go engineer, Part-time Tech Analyst, and Part-time PM
- Budget: $2,860




### Milestone 2 - Retrieve and process data from the test-network
- Goals:
  - Retrieve and explore blocks structure 
  - Create data mappings
  - Design data querying mechanisms
- Deliverables:
 - Data structure and mapping diagrams
 - API building blocks
- Outcomes:
 - Initial data for the website is being retrieved and processed either by scripts or manually.
 - Data can be validated against other tools and the community
- Duration: 1 week
- Team: Part-time Go engineer, Part-time Tech Analyst, and Part-time PM
- Budget: $4,290

### Milestone 3 - Backend development
- Goals:
  - Automate data retrieval and processing
  - Develop API endpoints
  - Integrate with the Lotus network
 - Deliverables:
  - Backend repository
  - API endpoints code
  - Automated tests
  - Documentation
- Outcomes:
  - A user can interact with the API and retrieve data using a Rest client (eg.: curl or postman)
- Duration: 2 weeks
- Team: Part-time Go engineer, Part-time Tech Analyst, and Part-time PM
- Budget: $8,580

### Milestone 4 - UI design and development
- Goals:
  - UI implementation
- Deliverables:
    - UI Mockups
    - Frontend repository 
    - Webapp running on staging on the test-network and ready for testing
- Outcomes:
  - A user can see his/her files (data CIDs) stored in the Lotus network with details of miners, sectors, and  state as a colored indicator: green (all good), grey (capacity), red (failing)
- Duration: 1 week
- Team: Part-time UI/UX designer, Full-time Full-time Frontend developer, and Part-time PM
- Budget: $4,290

### Milestone 5 - QA and documentation
- Goals:
  - Complete automated tests
  - Bugs fixing
  - Publish the code repository
  - Finish writing documentation
- Deliverables: 
  - The code is added to the GitHub repository designated by the Filecoin team
  - Detailed `Readme.md` explaining how to run, test and deploy the application; as well as how to contribute
- Outcomes:
  - Any community member will be able to deploy a CDI checker following the instructions in the repository
- Duration: 1 week
- Team: Full-time QA engineer, Part-time Developer, Part-time Tech analyst and Part-time PM
- Budget: $1,950

### Assumptions
- We assume that the data from the state of the Lotus network doesn’t require creating an additional decryption mechanism. If it does, additional efforts might be required.
- The Filecoin team will provide a point of contact for technical questions so our development doesn’t get blocked when we have technical issues or questions impacting on delivery dates and team allocation costs.

## Milestones & Funding

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Complete specifications | $2,860 | 1 week
| 2 | Retrieve and process data from the test-network | $4,290 | 1 week
| 3 | Backend development | $8,580 | 2 weeks
| 4 | UI design and development | $4,290 | 1 week
| 5 | QA and documentation | $1,950 | 1 week

Project duration: 6 weeks
Total funding: $21,970


## Maintenance and Upgrade Plans

Bugs and feature requests will be created in the github repository. Critical bugs will be fixed for a period of up to 2 months after delivery. After this period, a scope of work with the bugs and features can be created and applied for a grant.

# Team

## Contact Info

manuel@protofire.io

## Team Members

| Role | Team member | Role Description |
|---|---|---|
| Tech Analyst / PM | Vitaliy Chernov [LinkedIn](https://www.linkedin.com/in/vitaliy-chernov-45289a14) | Project Manager is responsible for: overseeing the design & development teams; creating specs; Lotus network data analysis and mapping; user stories/scenarios elaboration; drawing workflow diagrams |
| GoLang Developer | Alexander Kochetkov [LinkedIn](https://www.linkedin.com/in/alexander-kochetkov-6273599a/) | GoLang Developer is responsible for: Filecoin dev-node setup, synchronizing with the Lotus network; Defining methods of querying the data from the state; and Backend development |
| GoLang Developer/ AWS Certified Cloud Practitioner | Ilya Patotski [LinkedIn](https://www.linkedin.com/in/ilyapatotski) | GoLang Developer is responsible for: interaction between the backend and Lotus node; integration with a user FIL account; and Backend development |
| UI/UX designer | Gabriel Rodrigues [Github](https://github.com/gabitoesmiapodo) | UI Designer is responsible for the development of a Design System which includes UI and UX |
| Full-stack JS Developer| Jorge Shirai [Github](https://github.com/unjaponeshttps) | Javascript developer is responsible for implementing visual elements that users see and interact with in a web application as well as any development on the backend|
| QA engineer |Franco Venica [Github](https://github.com/francovenica) | QA engineer is responsible for ensuring the product is bug-free and meets client requirements |

## Team Website

http://protofire.io/

## Relevant Experience

Protofire is a team of engineers that helps providers of decentralized infrastructure, protocols and developer platforms to accelerate the growth of their ecosystems. 
Our goal is to invest in building expertise with Filecoin and become a long-term contributor and partner.
Our Relevant Expertise and GitHub links can be found in [this document](https://docs.google.com/document/d/1ql7UPQ4GxwSsR1-1Jm5rBVZwb6GWilfi63ze3QSMcGo/edit?usp=sharing). 

As for our commitment to the open-source ecosystem, Protofire develops and maintains the most popular Solidity linter: [Solhint](https://github.com/protofire/solhint) (currently funded by the Ethereum Foundation) and [eth-cli](https://github.com/protofire/eth-cli) a CLI swiss army knife for Ethereum developers.

## Team code repositories

https://github.com/protofire