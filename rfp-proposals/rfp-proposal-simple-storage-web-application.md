# RFP Proposal: `Simple Storage web application`

**Name of Project:** Simple Storage web application

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-4-rfps.md#simple-storage-webapps

**RFP Category:** `app-dev`

**Proposer:** [@mgarciap](https://github.com/mgarciap)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

The motivation behind the proposal is to deliver a positive change to the experience of end users and developers engaged in the Filecoin network, aiming to accomplish the goals for one of the high priority RFP ideas listed in [New RFP Ideas for Wave 4](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-4-rfps.md#filecoin-cid-checker-and-storage-oracle), the **Simple Storage webapp**.

The project we propose to build provides a convenient “drag and drop” web mechanism enabling end users to store files on the network and retrieve them in a simple way. The main features include:

- Home page with an ‘Upload file’ call to action and the list of already stored files and their basic details. Each file will provide a link to their full detail and download action.
- Upload file flow: a wizard that will walk the user through the steps of choosing a file (simple button or drag and drop), setting up requirements, requesting the price,  processing payment and final uploading. 
- Download file flow.
- File details page with information such as miner, CIDs, etc.
- Onboarding help such as flow’s step-by-step descriptions and tooltips will be provided for new users (user can chose to hide them)

The implementation will rely on Textile's Powergate (and the corresponding JS client) functionalities to handle storage and deals management among other Filecoin network required interactions.

We will leverage the Protofire team's experience building the Ocean Protocol Marketplace integration with Filecoin POC as well as integrate the UI with the [Filecoin CID checker and Storage Oracle](https://github.com/protofire/filecoin-CID-checker). 

## Value for the community
- Provide a quick onboarding of new users by walking them through an end-to-end very simple storage web application, plus providing an introduction to Filecoin network concepts.
- Serve as an open-source example for a light web storage application.
- Hide complexity of the underlying technology (Filecoin node API, deal management, etc) lowering newcomers' friction.
- Hopefully, serve as reference to identify missing features or gaps in the Filecoin ecosystem of end-user-facing apps.

## Deliverables

- UI Mockups (Figma or Zeplin) and product specifications.
- Open source repositories dual-licensed under MIT and APACHE2 licenses for Frontend and Backend.
- Web Application hosted by Protofire
- Documentation.


## Development Roadmap

### Milestone 1 - Complete specifications
- Goals:
  - Create UI wireframes and mockups
  - Finalize specs and architecture
  - Validate specs with the Filecoin team
- Deliverables:
  - Application specs and architecture design
  - List of risks and mitigation plan
  - Refined development plan for upcoming milestones
  - Figma or Zeplin project with high-fidelity design mockups
- Outcomes:
  - Expectations, scope, effort and budget will be more clear for everybody
- Duration: 1 week
- Team: Full-time Fullstack developer/engineer, UI/UX designer and Part-time PM
- Budget: 

### Milestone 2 - Upload file flow
- Goals:
  - Backend development
  - Frontend development
  - Steps for the full cycle of making a deal
- Deliverables:
  - Backend and frontend code
- Outcomes:
  - As an end user I will be able to upload a file and it will be stored in Filecoin
- Duration: 1.5 week
- Team: Full-time Fullstack developer/engineer, Part-time Frontend developer and Part-time PM
- Budget:

### Milestone 3 - List files owned by the user
- Goals:
  - Implement file listing UIs
  - Implement backend and frontend logic
- Deliverables:
  - Backend code with new API endpoints
  - UI listing the files owned by the user along with their basic details such as CIDs and miner info.
- Outcomes:
  - After uploading a file to Filecoin in the previous Milestone, a user will be able to check it was properly uploaded by having a UI that will list it.
- Duration: 1.5 week
- Team: Full-time Fullstack developer/engineer, Part-time Frontend developer and Part-time PM
- Budget:

### Milestone 4 - Download file flow
- Goals:
  - Implement UIs
  - Implement backend and frontend logic
- Deliverables:
  - New features in the backend code
  - New features in the frontend code to order download and then notify the user when it is ready for downloading.
- Outcomes:
  - A user will be able to choose a file from the list of owned files and initiate the downloading flow
  - A user will be notified when the file is ready to be downloaded
  - A user will be able to download the file to his/her local computer.
- Duration: 1.5 week
- Team: Full-time Fullstack developer/engineer, Part-time Frontend developer and Part-time PM
- Budget:


### Milestone 5 - QA and documentation
- Goals:
  - Publish the code repository
  - Write and publish a blog post
  - Fix bugs
- Deliverables: 
  - The code is added to the GitHub repository designated by the Filecoin team
  - Detailed `README.md` explaining how to run, test and deploy the application as well as how to contribute
  - Instruction for end-users covering happy and not happy outcomes with troubleshooting details
	- Blogpost publicated on Medium shared on Filecoin community
- Outcomes:
  - All project deliverables are completed and, may be, added to the [Filecoin Shipyard](https://github.com/filecoin-shipyard) or any other organization indicated by Filecoin (website, documentation, codebase)
- Duration: 1 week
- Team: Full-time Fullstack developer/engineer and Part-time PM
- Budget: 


### Assumptions
- The web application hosted by Protofire will connect to a filecoin hosted instance provided by Filecoin.
- The user running the web application already has a synchronized Filecoin Node + Powergate installation (and the corresponding dependencies running) that the application will use. Alternatively, the project can document the steps to prepare a setup like that.
- Deals/transactions will be performed using accounts created by Powergate's FFS instances and FIL funding is assumed to happen as part of the workflow. In Testnet/Devnet the user will copy an address from the UI (generated by Powergate FFS instance) and use the Faucet/external mechanism to fund it. In a local/mocked Devnet the account always have FIL. The same applies for retrieval deals.
- This application depends on components that are under heavy development. We expect that it doesn’t impact on the estimates otherwise they will have to be revisited.
- The Filecoin team will provide a point of contact for technical questions so our development doesn’t get blocked when we have technical issues or questions impacting on delivery dates and team allocation costs.

## Milestones & Funding

| Milestone | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Complete specifications | $2,500 | 1 week|
| 2 | Upload file flow | $4,100 | 1.5 week|
| 3 | List files owned by the user | $4,100 | 1.5 week|
| 4 | Download file flow | $4,100 | 1.5 week|
| 5 | QA and documentation | $2,500 | 1 week|

Project duration: 5 to 6 weeks
Total funding: $17,300


## Maintenance and Upgrade Plans

Bugs and feature requests will be created in the GitHub repository. Critical bugs will be fixed for a period of up to 2 months after delivery. After this period, a scope of work with the bugs and features can be created and applied for a grant.

# Team

## Contact Info

manuel@protofire.io

## Team Members

| Role | Team member | Role Description |
|---|---|---|
| Tech Analyst / PM | Cristian Malfesi [LinkedIn](https://www.linkedin.com/in/cristian-malfesi) | Project Manager is responsible for: overseeing the design & development teams; creating specs; Lotus network data analysis and mapping; user stories/scenarios elaboration; drawing workflow diagrams |
| Full-stack Blockchain Engineer | Jorge Shirai [Github](https://github.com/unjapones) | Full-stack Blockchain Engineer is responsible for: frontend & backend setup and implementation; Implement methods of querying the data and interacting with the Powergate |
| UI/UX designer | Gabriel Rodrigues [Github](https://github.com/gabitoesmiapodo) | UI Designer is responsible for the development of a Design System which includes UI and UX |
| Frontend Developer (React) | Mariano Aguero [Github](https://github.com/mariano-aguero) | FE developer is responsible for implementing visual elements that users see and interact with in a web application |

## Team Website

http://protofire.io/

## Relevant Experience

Protofire is a team of engineers that helps providers of decentralized infrastructure, protocols and developer platforms to accelerate the growth of their ecosystems. 
Our goal is to invest in building expertise with Filecoin and become a long-term contributor and partner.
Our Relevant Expertise and GitHub links can be found in [this document](https://docs.google.com/document/d/1ql7UPQ4GxwSsR1-1Jm5rBVZwb6GWilfi63ze3QSMcGo/edit?usp=sharing). 

As for our commitment to the open-source ecosystem, Protofire develops and maintain the most popular Solidity linter: [Solhint](https://github.com/protofire/solhint) (currently funded by the Ethereum Foundation).

## Team code repositories

https://github.com/protofire

# Additional Information

## Sample Mockups from other similar tools on the market

These screenshots have been taken from https://play.temporal.cloud/uploads.