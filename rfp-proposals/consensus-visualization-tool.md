# RFP: Consensus Visualization Tool

**Name of Project:** `Consensus Visualization Tool`

**Proposal Category:** `app-dev`

**Proposal Type:*** `rfp`

## Summary
This document outlines Protofire’s (a sub-division of [Altoros](https://www.altoros.com/)) proposition on providing a blockchain specialist developer team to build the [Consensus Visualization Tool](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-consensus-visualization-tool.md#rfp-consensus-visualization-tool). We believe that we can build a robust solution and contribute with our experience to the Filecoin network community.

## Who we are

[Protofire](https://protofire.io) is a team of engineers that helps providers of decentralized protocols, infrastructures and developer platforms accelerate growth of their ecosystems. By providing hands-on coding and contributions, Protofire specializes in supercharging developer adoption and network usage. We ship applications, smart contracts, and developer tools (SDKs/APIs/sample apps), as well as assist you in improving performance/cost of oracles.

Having been interested in Filecoin, our team researched the network to get a deeper understanding of the structure, scalability, and security. 

Having experience working with different protocols, networks and as specialists in developing blockchain technologies, we believe that our team qualifies as suitable for delivering the Consensus Visualisation tool.

#Consensus Visualization Tool

## Objetives

The objectives of this proposal is to develop an open-source blockchain consensus visualization tool that demonstrates Filecoin's [Expected Consensus](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-consensus-visualization-tool.md#about-expected-consensus-ec) process. It must show the main chain and also other forks.

## Deliverables

This proposal covers all the deliverables described in the RFP that is available by this [link](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-consensus-visualization-tool.md#deliverables). \
Additional deliverables are:


*   Open source Github repository with public access
*   Hosted application working with Testnet and Mainnet
*   The tutorial with demo usage that will be published in the repo.
*   Blog post that will be published on Protofire medium account and shared through linkedin, twitter and other platforms
*   Updated estimates for milestones 2-4

## Scope of Work
Below you can find the table describing the milestones schedule, tasks and deliverables that are based on the the requirements stated in [RFP](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-consensus-visualization-tool.md).


<table>
<tr>
<td><strong>Milestone</strong>
</td>
<td><strong>Tasks________________________________</strong>
</td>
<td><strong>Deliverables & Outcome</strong>
</td>
<td><strong>Fund</strong>
</td>
<td><strong>Effort_____</strong>
</td>
</tr>
<tr>
<td>#1
</td>
<td>
- Research, analysis

- Install Lotus (Node+Miner)
- Install Go-Filecon and analyze heartbeats
- Learn the process and details about nodes and consensus is represented
<p></p>
- Define UI requirements

- Information
- Charts
- Nodes and network data
<p>- Design mockups and final UI.
<p>- Endpoints definition
<p>- Architecture & infrastructure definition
<p>- Validation of scope and roadmap definition
<p>- Write backlog tickets

</td>
<td><strong>Deliverables:</strong>

- Document with defined scope
- UI mockups designs 
- Infrastructure design
- API endpoint definitions
- Roadmap document and completed Backlog
- Updated estimates for milestones 2-4

<p>
<strong>Outcomes:</strong>

Definition of what and how the visual tool accomplishes the objective(s), alongside with a prioritization of them (scope and roadmap). This definition will be made up by the deliverables previously listed, so that the engineering team and stakeholders goals are aligned at the end of the feedback rounds and for the milestones ahead.
   </td>
   <td>30K
   </td>
   <td>3 weeks
   </td>
  </tr>
 <tr>
<td>#2
</td>
<td>
- Organize sprints of 2 weeks each one
<p>- Frontend

- Setup
- UI layout design
- Dev React components
- Data connection to backend
- Unit tests
- CI

<p>- Backend (if needed)

- Setup
- API endpoints unit tests 
- New endpoints
- Unit Tests
- CI
<p>- Local/Develop and Cloud/Test environments setups
<p>- Demos per sprint
<p>- Feedback rework

<p>Sprint duration may be adapted according to team size and scope; as well as demos & feedback rework sessions.

</td>
<td><strong>Deliverables:</strong>

- Consensus Visualization Tool Dapp
- Dapp based on React+Typescript and interactive visualization libraries (d3.js, Highcharts, Nvd3, rechart, etc) and other libraries 
- Dapp displays new messages, blocks, tipsets, ancestors, forks, miners and related information via live updates
- Additional tools, infrastructure or backend if it's defined
- Tests: Apply units tests, CI and manual QA


<p>
<strong>Outcomes:</strong>

Generate a working implementation that meets the objectives previously defined, and that is approved by stakeholders.
   </td>
   <td>TBD
   </td>
   <td>4 weeks
   (TBD)
   </td>
  </tr>
  <tr>
<td>#3
</td>
<td>
<p>- Improve documentation and support information (if needed): README, wikis, tutorials, etc.
<p>- Transfer ownership of CI/CD and services that support the architecture to Filecoin (if needed, use free/open source-based service when possible).
<p>- Move codebase/repos to Shipyard and adapt to meet Filecoin standards.
- Work on feedback 



</td>
<td><strong>Deliverables:</strong>

- Changes and improvements from feedback
- Well-documented, human-readable codebase
- Blog post and/or tutorial with demo usage


<p>
<strong>Outcomes:</strong>

Wrap up the project's codebase to add it to the Shipyard so it can be further modified or maintained by a Filecoin developer/community. The blogpost or tutorial may improve the understanding of how the project works and represents the consensus process (ideal to aid new people looking for understanding the consensus process) and, maybe, tell something cool about the development experience to improve community engagement.
   </td>
   <td>TBD
   </td>
   <td>2 weeks
   (TBD)
   </td>
  </tr>
  <tr>
<td>#4
</td>
<td>
Maintenance and Upgrades during Testnet and Mainnet

</td>
<td><strong>Deliverables:</strong>

- Feedback: changes and improvements

<p>
<strong>Outcomes:</strong>

Protofire team will support problems and bugs detected during the agreed period.
   </td>
   <td>TBD
   </td>
   <td>2 weeks
   (TBD)
   </td>
  </tr>
  <tr>
<td><strong></strong>
</td>
<td><strong></strong>
</td>
<td><strong>TOTAL (Milestone 1)</strong>
</td>
<td><strong>30K</strong>
</td>
<td><strong>3 weeks</strong>
</td>
</tr>
<tr>
<td><strong></strong>
</td>
<td><strong></strong>
</td>
<td><strong>TOTAL (Full project)</strong>
</td>
<td><strong>TBD</strong>
</td>
<td><strong>~11 weeks</strong>
</td>
</tr>
</table>



## Assumptions
*   Code will be hosted in the public Protofire Github repository
*   Long term maintenance should be agreed with Filecoin
*   We assume that API ([Lotus](https://lotu.sh/en+api#what-methods-can-i-use-20883)) has all necessary endpoints and is well documented so that the visualization tool can consume the corresponding data and transform it into a graphical representation.
*   We recommend starting with sprint 0 for the milestone 1, to define UI mockups and endpoints.
*   The frontend and backend will be hosted by Filecoin

## Acceptance Criteria

The proposed tool will adhere to the acceptance criteria defined [here](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-consensus-visualization-tool.md#acceptance-criteria). Before starting the project we will make a detailed document with the acceptance criteria based on the final scope.

### Protofire Relevant Experience

Protofire has delivered a network explorer for the [Enigma Protoco](https://enigma.co)l that is similar to the Consensus Visualization Tool. Enigma Network Explorer demonstrates the Enigma Consensus process handling events and data for workers (nodes), epochs(rounds), tasks and users. Users can follow up on the status and statistical information of the network. This app works with complex architecture processing data from Ethereum and Enigma network.

We built a robust infrastructure behind the Dapp where we process the Ethereum data through building a [subgraph](https://thegraph.com/), increasing the data access speed to the frontend and creating a backend API (NodeJs) in order to process statistical data and manage complex formulas to handle different events. The complete solution was developed using containers based on docker-compose that allowed for easy deployments on cloud services.

Our engineering team was responsible for the complete development process from business analysis, scope, data schema definition and UI/UX design to the development and QA. The development team focused on building a stable and robust backend while ensuring the strong user experience.

<p></p>

![](https://github.com/cristianmalfesi/chm/blob/master/images/Enigma%20Network%20Explorer_Home.png)

<table>
 </td>
   <td>The main page intends to show a quick overview of the network status. All data of the network, progressive chart, Epocs boxes, and tasks are updated in real-time. The user has all the information on the screen and has a one-click access to further details.
We have used React, Typescript, web3, material-ui, Apollo, Koajs+hapi, etc.
   </td>
  </tr>
</table>
<p></p>

![](images/Enigma%20Network%20Explorer%20-%2008%20Worker%20Single@2x.png)

<table>
 </td>
   <td>The dashboard shows complete details of different entities and allows to organise information using a filter, a keyword search or sort out data by certain parameters, etc. Based on the subgraph + backend-API, we managed to provide faster access to blockchain data compared to solutions based on Web3 connection.
   </td>
  </tr>
</table>
<p></p>

![](images/Enigma%20Network%20Explorer_Task_details.png)

<table>
 </td>
   <td>Users have complete information on all entities: workers (nodes), tasks and users. All entities are synchronized and are linked to each other. 
   </td>
  </tr>
</table>


## Key Personnel and Roles

Below are the roles proposed for the project implementation. Some staff members may take on multiple resource roles.


<table>
  <tr>
   <td>
    <strong>Role</strong>
   </td>
   <td>
    <strong>Resource</strong>
   </td>
   <td>
    <strong>Resource Description</strong>
   </td>
  </tr>
  <tr>
   <td>
    Product Manager
   </td>
   <td><p>Cristian Malfesi <br><br><a href="https://team.altoros.com/cv1b3d1a/CristianMa">Link to CV</a></p>
     </td>
   <td>
    Project Managers are responsible for overseeing the design & development teams. 
   </td>
  </tr>
  <tr>
   <td>
    Technical Architect
   </td>
   <td>
    <p>Franco Vitorio <br><br><a href="https://team.altoros.com/cv86ff9a/FrancoV">Link to CV</a></p>
   </td>
   <td>
    Technical architects are responsible for providing guidance and oversight on technical requirements for the product.
   </td>
  </tr>
  <tr>
   <td>
    Frontend Engineer
   </td>
   <td>
    <p>Jorge Shirai <br><br><a href="https://team.altoros.com/cv4f2d89/JorgeS">Link to CV</a></p>
   </td>
   <td>
    FE engineers are responsible for developing the front end services for the product. Experts using React, Javascript, Typescript and related interactive visualization libraries (web3.js, d3.js apollo, web3, koajs, hapi, mongoose and much more) 
   </td>
  </tr>
  <tr>
   <td>
    Backend Engineer
   </td>
   <td>
    <p>Lisandro Corbalán <br><br><a href="https://team.altoros.com/cv22ffc5/LisandroC">Link to CV</a></p>
   </td>
   <td>
    BE engineers are responsible for developing the back end services for the product. Work with these technologies: NodeJs, API, GraphQL, SQL/NonSQL,CI/CD, etc..
   </td>
  </tr>
  <tr>
   <td>
    QA and Reviewer
   </td>
   <td>
    <p>Nicolás Dominguez <br><br><a href="https://team.altoros.com/cv1a7c58/NicolasF">Link to CV</a></p>
   </td>
   <td>
    QA engineers are responsible for ensuring the product is bug-free and meets client requirements.
   </td>
  </tr>
  <tr>
   <td>
    UI Designer
   </td>
   <td>
    <p>Gabriel Rodriguez <br><br><a href="https://team.altoros.com/cv7d294b/Gabriel%20RodriguezA">Link to CV</a></p>
   </td>
   <td>
    UI Designers are responsible for the development of a Design System which includes UI and UX.
   </td>
  </tr>
</table>


## Project Management

The Project Manager will be the primary Point of Contact for Filecoin. Work arrangements and communication plans include:

*   Team will be working remotely across geographies and timezones.
*   Shared Slack channel will be set up to maintain active dialogue with the Filecoing team.
*   Slack webhooks will be set up from all project management tools for visibility on progress.
*   Visibility will be ensured through weekly updates, demos, time and progress reports.
*   Team will be working based on 2-week sprints and follow Agile methodologies (Scrum, Kanban).
*   The project is organized through a board that allows daily monitoring. We recommend Zenhub.


## Grant Payment Terms

This is a proposal for a fixed bid grant. Filecoin is requested to pay as follows:

*   50% upon start of the project (USD 15K) and 50% (USD 15K) upon project completion, with net15 payment terms.
*   Any changes to the scope of work or overages to the price must be agreed in writing by the parties through a change request.
*   All work is expected to be done remotely, with no travel required.


## Capabilities of our team and related experience

We have extensive experience in developing protocols, tooling, dApps, from PoCs and prototypes to MVPs, etc. To learn more, please visit [our website](https://protofire.io).

Protofire works exclusively with entrepreneurs who are builders of decentralized infrastructure protocols, applications, and ecosystems.

## Our services, customers and works

[About Protofire](doc/PROTOFIRE%20Overview%20.pdf)

