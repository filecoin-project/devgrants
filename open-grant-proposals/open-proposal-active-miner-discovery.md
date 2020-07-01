# Open Grant Proposal: `Active Miner Discovery `

**Active Miner discovery**

**Proposal Category:** `app-dev`

**Proposer:** [@mgarciap](https://github.com/mgarciap)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

An additional service combined with the Filecoin [CID checker and Storage Orace](https://github.com/protofire/filecoin-CID-checker).

The application will automatically ping storage miner nodes, collect responses from the _active_ miners, and aggregate their *Asks* on one screen providing the following information:

- Miner ID
- Storage volume
- Price
- Other valuable information TBD

A new **"Search by Miner ID"** mechanism will be implemented allowing for checking available free storage volumes and price of a certain Miner.

## Value

Currently there are no services enabling Users to easily find active storage miner *Asks* in one place and understand the current pricing market. 

The Miner discovery service will benefit from synergy effect with the **Filecoin CID checker** developed by Protofire, as both services have a common type of User and can be run on one Filecoin node.

The team doesn't anticipate any significant risks to the project implementation, since the data retrieval methods are similar to those recently implemented in our Filecoin CID checker project.


## Deliverables

- Open source repositories dual-licensed (under MIT and APACHE2) licenses for Frontend and Backend
- A service that will allow any network participant to access a new section of the the CID checker webapp and see the list of active storage miners and their prices
- API providing the same information
- Documentation


## Development Roadmap

### Milestone 1 - System design and Data mapping
- Goals:
  - Design and spec the data retrieval and processing mechanism
  - UX/UI design
- Deliverables:
  - UI wireframes
  - Detailed specs on how to retrieve and process the  data from active miners along with the UI and API details
- Outcomes:
  - Expectations, scope and details will be clear for everybody
- Duration: 0.5 week
- Team: Full-time Tech analyst/PM, Full-time Go engineer
- Budget: $2,860

### Milestone 2 - Backend development
- Goals:
  - Implement the data retrieval and processing mechanism
- Deliverables:
  - API
  - Backend code
- Outcomes:
  - Miner asks are automatically gathered from active miner nodes
  - Asks form inactive miners are excluded from the table 
- Duration: 1 week
- Team: Full-time Go engineer, Full-time Tech analyst/PM
- Budget: $5,720

### Milestone 3 - UI/UX and Frontend development
- Goals:
  - Develop frontend
- Deliverables:
  - UI mockups
  - Frontend code
- Outcomes:
  - Active Miner asks are compiled and displayed on the User monitor
- Duration: 1 week
- Team: Part-time UI/UX designer, Full-time Frontend developer, and Part-time PM
- Budget: $5,720

### Milestone 4 - QA and documentation
- Goals:
  - Complete automated tests
  - Fix bugs
  - Publish the code repository
  - Finish writing documentation
- Deliverables: 
  - The code is added to the GitHub repository designated by the Filecoin team
  - Detailed `Readme.md` explaining how to run, test and deploy the application as well as how to contribute
  - Instruction for end-users covering successful and alternative scenarios with troubleshooting details
- Outcomes:
  - All project deliverables are completed and added to the Github repository indicated by Filecoin (website, documentation, codebase)
  - A tested version is running and available for testing from the side of Filecoin team
- Duration: 0.5 week
- Team: Part-time QA engineer, Part-time Go engineer, Part-time Frontend developer, Part-time Tech analyst/PM
- Budget: $3,120

### Milestone 5 - Integration and Deployment to production
- Goals:
  - Integrate the Active Miner discovery service into the Filecoin CID checker service node running on the latest version of Lotus network
- Deliverables: 
  - New page and API successfully running on the Lotus node along with the CID Checker
- Outcomes:
  - Users can navigate to the URL and switch between two screens: the Filecoin CID checker and the Active Miner discovery. Also, access through the API
- Duration: 0.5 week
- Team: Full-time Go engineer, Part-time PM
- Budget: $2,430

## Total Budget Requested

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | System Design and Data mapping | $2,860 | 0.5 week|
| 2 | Backend development | $5,720 | 1 week|
| 3 | UI/UX and Frontend development | $5,720 | 1 week|
| 4 | QA and documentation | $3,120 | 0.5 week|
| 5 | Integration and Deployment to production | $2,430 | 0.5 week|

Project duration: 4 weeks
Total funding: $19,850 (including 10% of total effort for communication)

## Maintenance and Upgrade Plans

As the CID Checker service hosted by Protofire, Active Miner Discovery service will work with at minimum a Filecoin lotus node at Filecoin mainnet launch and for 2 months thereafter. Any updates needed to ensure a live, functional service at launch and for 2 months thereafter with a lotus Filecoin node should be performed at no additional cost unless Filecoin nodes or Filecoin Network have undergone significant changes since Protofire’s commencement of the project. In this case, Protofire will request additional funding should the changes implementation require more than 10 hours/month.

Comment: critical bugs will be fixed for a period of up to 2 months after mainnet launch.
Bugs and feature requests will be created in the Github repository.
After this period, major upgrades and feature requests will be subject to new grants.

# Team

## Contact Info

manuel@protofire.io

## Team Members

| Role | Team member | Role Description |
|---|---|---|
| Tech Analyst / PM | Vitaliy Chernov [LinkedIn](https://www.linkedin.com/in/vitaliy-chernov-45289a14) | Project Manager is responsible for: overseeing the design & development teams; creating specs; Lotus network data analysis and mapping; user stories/scenarios elaboration; drawing workflow diagrams |
| GoLang Developer | Alexander Kochetkov [LinkedIn](https://www.linkedin.com/in/alexander-kochetkov-6273599a/) | GoLang Developer is responsible for: Filecoin dev-node setup, synchronizing with the Lotus network; Defining methods of querying the data from the state; and Backend development |
| UI/UX designer | Gabriel Rodrigues [Github](https://github.com/gabitoesmiapodo) | UI Designer is responsible for the development of a Design System which includes UI and UX |
| Frontend Developer (React) | Mariano Aguero [Github](https://github.com/mariano-aguero) | FE developer is responsible for implementing visual elements that users see and interact with in a web application |
| QA engineer |Franco Venica [Github](https://github.com/francovenica) | QA engineer is responsible for ensuring the product is bug-free and meets client requirements |

## Team Website

http://protofire.io/

## Relevant Experience

Protofire is a team of engineers that helps providers of decentralized infrastructure, protocols and developer platforms to accelerate the growth of their ecosystems. 
Our goal is to invest in building expertise with Filecoin and become a long-term contributor and partner.

The Protofire team has been working on the [Filecoin CID checker and Storage Oracle project](https://github.com/protofire/filecoin-CID-checker) which is currently in progress and is expected to be delivered mid July, 2020. 

Additional information on Protofire relevant expertise and GitHub links can be found in [this document](https://docs.google.com/document/d/1ql7UPQ4GxwSsR1-1Jm5rBVZwb6GWilfi63ze3QSMcGo/edit?usp=sharing). 

As for our commitment to the open-source ecosystem, Protofire develops and maintain the most popular Solidity linter: [Solhint](https://github.com/protofire/solhint) (currently funded by the Ethereum Foundation).

## Team code repositories

https://github.com/protofire

# Additional Information

The team is planning to use UI themes similar to our recent works in the project [Filecoin CID checker](https://github.com/protofire/filecoin-CID-checker/blob/master/UI%20Design/list.png) 