# RFP Proposal: `Shared Blocklists of Content CIDs`

**Name of Project:** Shared Blocklists of Content CIDs

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-4-rfps.md#shared-blocklists-of-content-cids

**RFP Category:** `app-dev`

**Proposer:** [@mgarciap](https://github.com/mgarciap)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

The motivation behind the proposal is to deliver a positive change to the experience of end users and developers engaged in the Filecoin network. 

"Blocklisted CID" is intended as an additional service combined with the Filecoin [CID checker and Storage Orace](https://github.com/protofire/filecoin-CID-checker)

The proposed solution will aggregate information from the "blocklist of Piece CIDs" managed by Storage miners and will be run as a shared service on a Lotus network:
- A web-page indicating the aggregated list "Blocklisted CID" added in a chronological order.
- A convenient search mechanism by the Piece CID will help to find basic metadata around the reasons for blocklisting any particular Piece CID.

This is a proposal for one of the high priority RFP ideas listed in **New RFP Ideas for Wave 4**, the [Shared Blocklists of Content CIDs](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-4-rfps.md#shared-blocklists-of-content-cids)
> Lotus Filecoin has added the ability for miners to create blocklists of content piece CIDs they do not want to store or serve retrieval requests for (See lotus PR 2069). This may be required for miners to comply with local law enforcement requests (which lists to respect and which items to block are entirely up to the miner operator).
> This RFP is for a way for blocklists to be shared by the community, potentially with some basic metadata around the reasons for blocklisting. A way for community members to propose CIDs to blocklist would also be useful.
>

## Value for the community
- Users, Retrieval miners and the Community at large need a shared service that allows for checking the Piece CIDs "blocklisted" by Storage Miners, as well as related information (such as metadata around the reasons for blocklisting).
- The "Blocklisted CID" will add transparency preventing users and miners from dealing with illicit (or, unwilling) content and comply with local regulations.

## Deliverables

- Open source repositories dual-licensed (under MIT and APACHE2) licenses for Frontend and Backend.
- Service that will allow any network participants to access a website (combined with the CID checker) and see the "Blocklisted CIDs" and related information.
- Documentation.

## Development Roadmap

### Milestone 1 - System design and Data mapping
- Goals:
  - Design the mechanism of data fetching from the Storage miner's blocklists, as well as automated update
- Deliverables:
  - UI wireframes
  - Algorithm of fetching the data from miners' blocklists
- Outcomes:
  - Specs and design complete
- Duration: 1 week
- Team: Full-time Tech analyst, Full-time Go engineer, PM
- Budget: $5,720

### Milestone 2 - Backend development
- Goals:
  - Create the mechanism of automated data fetching 
- Deliverables:
  - Backend code
- Outcomes:
  - The list of CIDs aggregated from Storage Miners' blocklists
  - CID-related metadata is retrieved and compiled automatically 
- Duration: 2 weeks
- Team: Full-time Go engineer, Full-time Tech analyst, PM
- Budget: $11,440

### Milestone 3 - UI/UX and Frontend development
- Goals:
  - Develop frontend
- Deliverables:
  - UI mockups
  - Frontend code
- Outcomes:
  - The aggregated list of blocklisted CIDs is compiled and displayed on the User monitor
- Duration: 1 week
- Team: Part-time UI/UX designer, Full-time Frontend developer, Part-time PM
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
- Team: Part-time QA engineer, Part-time Go engineer, Part-time Frontend Engineer, Part-time Tech analyst, Part-time PM
- Budget: $2,860

### Milestone 5 - Integration and Deployment to production
- Goals:
  - Integrate the "Blocklisted CID" service with the Filecoin CID checker service node run on the latest version of Lotus network
- Deliverables: 
  - Two services successfully running on the Lotus node
- Outcomes:
  - Users can navigate to the URL, switch between two screens: the Filecoin CID checker and the Blocklisted CID, and use the search function
- Duration: 0.5 week
- Team: Full-time Go engineer, Part-time PM
- Budget: $2,150


### Assumptions
- This application depends on components recently added to the Lotus Filecoin: the ability for miners to create blocklists of content piece CIDs they do not want to store or serve retrieval requests for (See lotus Pull Request [#2069](https://github.com/filecoin-project/lotus/pull/2069)). We expect that it doesn’t impact on the estimates otherwise they will have to be revisited.
- The Filecoin team will provide a point of contact for technical questions so our development doesn’t get blocked when we have technical issues or questions impacting on delivery dates and team allocation costs.

## Milestones & Funding

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | System Design and Data mapping | $5,720 | 1 week|
| 2 | Backend development | $11,440 | 2 weeks|
| 3 | UI/UX and Frontend development | $5,720 | 1 week|
| 4 | QA and documentation | $2,860 | 1 week|
| 5 | Integration and Deployment to production | $2,150 | 0.5 week|

Project duration: 6-7 weeks
Total funding: $27,890 (including 10% of total effort for communication)


## Maintenance and Upgrade Plans

As the CID Checker service hosted by Protofire, Shared Blocklists of Content CIDs will work with at minimum a Filecoin lotus node at Filecoin mainnet launch and for 2 months thereafter. Any updates needed to ensure a live, functional service at launch and for 2 months thereafter with a lotus Filecoin node should be performed at no additional cost unless Filecoin nodes, Filecoin Network have undergone significant changes since Protofire’s commencement of the project. In this case, Protofire will request additional funding should the changes implementation require more than 10 hours/month.
 - Critical bugs will be fixed for a period of up to 2 months after mainnet launch.
 - Bugs and feature requests will be created in the Github repository.

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

As for our commitment to the open-source ecosystem, Protofire develops and maintains the most popular Solidity linter: [Solhint](https://github.com/protofire/solhint) (currently funded by the Ethereum Foundation).

## Team code repositories

https://github.com/protofire

# Additional Information
The team is planning to use UI themes similar to our recent works in the project [Filecoin CID checker](https://github.com/protofire/filecoin-CID-checker/blob/master/UI%20Design/list.png)
