# RFP: Simple Storage Webapp

**Name of Project: Simple Storage Webapp**

**Link to RFP:** [https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#simple-storage-webapps](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#simple-storage-webapps)

**RFP Category:**  `app-dev`

**Proposer:** @acostalima

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Filecoin is a decentralized storage network that provides an algorithmic market. This market runs on a blockchain where clients spend a protocol token (also called "Filecoin") hiring Miners to store and distribute their data. The Simple Storage Webapp aims to enable common users to be part of the market, either becoming a Filecoin Miner or a Storage Client. Considering that Simple Storage Webapp does not expect users to have a prior background on how Filecoin works, this app should also provide educational illustrations to onboard users interested in understanding what is happening behind the curtains, for both Clients and Miners.

One one side, the Simple Storage Webapp should enable storage providers to participate in the Filecoin storage market by allowing them to commit storage to the Filecoin protocol, put ask orders in the network and visualize crucial metrics and statistics of the Miner.

On the other side, market Clients should be able to store their files on the network, as well as to list their files and retrieve them. Clients must pay storage Miners for storing their files, as well as retrieval Miners for retrieving files, as a compensation for both storage and bandwidth costs incurred by Miners.

We also propose a collaboration of mutual benefit with Jim Pick (@jimpick) where we will actively contribute to the development of the [Lotus JS API client](https://github.com/filecoin-shipyard/js-lotus-client) and consume said API in the web app to integrate it with Filecoin's network. 

## Deliverables

1. UI/UX design
    - Mockups
    - Educational illustrations showcasing Filecoin workflows
2. Up to date and easy to use Lotus JS client
    - Implementation + npm package published
    - Documentation
3. Web app ready for deployment
    - Client Dashboard
    - Miner Dashboard
    - Documentation
4. Github repository with Lotus node and reverse proxy ready for deployment

## Development Roadmap

**Expected start date:** No later than May 1, 2020

**Expected end date:** End of June, 2020

**Estimated duration:** 2 months

Please find below the work breakdown for a total of 5 milestones.

## 1. Planning, Research & Concept

- People involved: Lead Engineer, Lead Designer, Front-End Engineer
- Duration: May 1-22, ~3 weeks
- Dependencies: None
- Estimated Budget
    - Number of hours: 160h + 120h (design) = 280h
    - Total (USD): $18 368
- Definition of done:
    - Client and Miner dashboard mockups
    - Project bootstrapped
    - GitHub repository created
    - Educational illustrations
- Action Plan:
    - [Lead Designer] Conception and design of UI kit
        - We intend to use [Material UI](https://material-ui.com/) with minimalistic styles tailored to this project. Therefore, we don't have to design and implement UI components from scratch. This approach allows us to save time, reduce costs, accelerate the implementation of the UI to get things moving quickly while providing quality UX.
    - [Front-End Engineer] Web app initial setup
        - Git repository
        - Code structure
        - CI/CD
    - [Lead Designer, Lead Engineer support] Design auth and wallet flows
        - Basic auth with Lotus JWT tokens
        - Wallet flows supported by the Lotus API [https://github.com/filecoin-project/lotus/blob/master/api/api_full.go#L68-L80](https://github.com/filecoin-project/lotus/blob/master/api/api_full.go#L68-L80)
    - [Lead Designer, Lead Engineer support] Design the client Store/Retrieve flows
        - Store and Retrieve flows should be designed according to the Filecoin storage / retrieve spec flows
            - This enables a better explanation regarding how the Filecoin protocol works
        - Storage Flow
            1. Discover available miners
                - Use API to get list of StorageMiners actors with their current asks
            2. Negotiation
                - Select a miner to negotiate
                - Add Funds for the deal as necessary via the StorageMarket actor API
                - Propose a deal to the intended StorageMiner using the client API
                    - Wait for success, or try a different StorageMiner
                - Transfer Data
                    - Client opens a push request for the payload using the DataTransfer Module API
            3. Publishing
                - Wait for the content to be published on the chain, by querying the storage deal via the client API
            4. Hand off
                - Show the clients current and future payments, using the client API
        - Retrieve Flow (assuming retrieve v0, some changes might occur if we tackle v1 instead)
            1. Find a provider of a given piece
                - Query the network to find the provider, as well as its address
            2. Query the provider
                - Reach to the provider about the intended piece to check its availability
                - Send a retrievalDealProposal using the RetrievalProtocol
                    - Wait for an accept message from the provider
                - Create payment channel with funds
                - Consume blocks over the RetrievalProtocol
                    - When the provider requires payment to proceed, it sends payment request and does not send any more blocks
                - Client creates and stores a payment voucher off-chain, and provides the voucher reference
                    - Wait for the provider to redeem the voucher
                - Client consumes blocks again until a new payment is required
                    - This process continues until the end of the query
    - [Lead Designer, Lead Engineer support] Design the "Miner Actions" and the "Miner Metrics & Statistics" views
        - Miner actions page
            - Commit storage to the Filecoin Protocol through the Miner API
            - Place storage asks in the market through the Miner API
        - Visualize properties, metrics and statistics using the Miner API
            - Type of actor {Storage, Retrieval, Repair}
            - Miner sectors
                - Storage deals
                - Committed capacity with no deals
                - States {PreCommit, Active, TemporaryFault}
            - Specific properties according to the type of miner (data from the interfaces)
                - Example: MinerPoStState {Ok, Challenged, DetectedFault}
            - Miner statistics
                - Committed Power
                - Power %
                - Blocks mined
                - Blocks mined %
    - [Lead Designer, Lead Engineer support] Create educational illustrations showcasing Filecoin workflows
        - Miners actions
        - Storage Flow
        - Retrieve Flow

### Notes

- The goal is not to come up with a super fancy UI, although we will make sure Filecoin workflows are crystal clear to developers on the UX side of things.
- The task to create educational illustrations can potentially be pushed to a 2nd phase. A 2nd phase is out of the scope of present proposal.
- The task to design the miner metrics and statistics can potentially be pushed to a 2nd phase. A 2nd phase is out of the scope of present proposal.

## 2. Lotus JS client

- People involved: Lead Engineer
- Duration: May 22-June 22,  ~1 month
- Dependencies: None
- Estimated Budget
    - Number of hours: 160h
    - Total (USD): $10 496
- Definition of done:
    - JS API published to npm
    - JS API is documented
    - JS API is unit tested
- Action Plan:
    - Assist Jim Pick (@jimpick) in the development of the [JS client](https://github.com/filecoin-shipyard/js-lotus-client)
    - Develop a subset of the JS API according to project needs by abstracting Filecoin workflows and use cases
        - Identify which JSON-RPC API methods are needed to:
            - Wallet actions
            - Complete the Storage Flow
            - Complete the Retrieval Flow
            - List File storage deals
            - List Miner storage asks
            - List Miner information
    - Write down API documentation

### Notes

- At the time of writing, we were not able to identify which API methods we need to call to get the information we need to complete the flows due to the lack of documentation.

## 3. Storage Client Dashboard

- People involved: Front-End Engineer, Lead Engineer (Reviewer/Support)
- Duration: May 22-June 5, ~3 weeks
- Estimated Budget
    - Number of hours: 120h
    - Total (USD): $7 872
- Dependencies
    - Milestone 1
- Definition of done:
    - Storage Client UI backed by a mocked JS client
- Action Plan:
    - [Front-End Engineer] Implement the Store Flow
    - [Front-End Engineer] Implement the Files listing
    - [Front-End Engineer] Implement the Retrieval Flow
    - [Front-End Engineer] Write down documentation

## 4. Miner Dashboard

- People involved: Front-End Engineer, Lead Engineer (Reviewer/Support)
- Duration: June 5-June 19, ~2 weeks
- Estimated Budget
    - Number of hours: 80h
    - Total (USD):  $5 248
- Dependencies
    - Milestone 1
- Definition of done:
    - Miner UI backed by a mocked JS client
- Action Plan:
    - [Front-End Engineer] Implement the Market Actions page
    - [Front-End Engineer] Implement the Metrics and Statistics Page
    - [Front-End Engineer] Write down documentation

### Notes

- We can potentially create a more simplistic version of the Miner dashboard by pushing Metrics and Statistics to a 2nd phase.

## 5. Web app integration with a Lotus node

- People involved: Lead Engineer, Front End-Engineer
- Duration: June 19-July 3, ~2 weeks
- Estimated Budget
    - Number of hours: 80h
    - Total (USD): $5 248
- Dependencies:
    - Milestones 2
- Definition of done:
    - Miner and Storage Client UIs backed by working Lotus node
    - Remote/publicly hosted Lotus node deployed for the live web app to communicate with
    - Web app deployed to GitHub Pages
- Action Plan:
    - [Lead Engineer] Lotus JWT tokens management
    - [Lead Engineer, Front-End Engineer] Replace mocked JS API client with concrete implementation resulting from milestone 2
    - [Lead Engineer] Prepare Git repository with code and instructions on to deploy a Lotus node behind a reverse proxy
        - Necessary step to get around CORS issues when communicating with a Lotus node from a web browser
    - [Lead Engineer] Deploy remote Lotus node
    - [Lead Engineer] Deploy web app

## Total Budget Requested

- Estimated budget
    - Number of hours: 720h (dev & design) + 40h (project management) = 760h
    - Total (USD): $49 856

The project will be billed upon completion of each milestone.

## Maintenance and Upgrade Plans

Issues, regardless of their nature, will be tracked on GitHub to be addressed in the future. We can consider establishing  a monthly retainer to provide post-grant maintenance, with a pre-established minimum allocation (reserved time). We shall discuss whether this is reasonable or not.

### Future work

We see this project as groundwork and a gateway for an advanced open-source toolkit around the Filecoin ecosystem. We have several ideas, some of which are listed below:

- Integration of other Filecoin-related tools in the web app
    - [Filecoin CID Checker and Storage Oracle](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#filecoin-cid-checker-and-storage-oracle)
    - [Filecoin Chain State Explorer](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#filecoin-chain-state-explorer)
- Add support for [erasure coding and basic PGP](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#storage-client-application-with-erasure-coding-and-basic-pgp)
- Display & visualize more insights about the network
    - Distinguish miner types with targeted visualizations and actions
- Add support for other miner management features
- Consider leveraging Nomios to tie identity with storage deals

If there are no eligible candidates to implement The Filecoin CID Checker and Storage Oracle project in the short-term, we'd be very keen to do it next.

# Team

## Contact info

DRI: André Costa Lima (andre.lima@moxy.studio)

In future e-mails, please CC:

- Filipe Dias (filipe@moxy.studio)
- André Cruz (andre@moxy.studio)
- Vasco Santos (vasco.santos@moxy.studio)
- Hugo Dias (hugo.dias@moxy.studio)

## Team Layout

Exact members are left unspecified for the time being. Once we have clarity on the actual start date, we will provide an adequate team at once. Please read further below in "Relevant Experience" section for more information on MOXY's background.

For now, we propose the following profiles for the execution team: 

- 2 Software Engineers
    - 1 Lead Software Engineer
        - Responsible for overseeing the implementation of the project from a technical perspective.
        - In charge of conceiving, implementing and integrating the necessary APIs to communicate with the Filecoin network.
    - 1 Front-end Engineer: responsible for the implementation of the UIs as idealized by the Lead UI/UX Designer.
- 1 Lead UI/UX Designer: responsible for the conception of the proposed use cases and user flows.
- 1 Project Manager: responsible for reporting on the project's progress to key stakeholders and monitor its execution for successful project delivery.

## Team Member LinkedIn Profiles

N/A

## Team Website

[https://moxy.studio](https://moxy.studio)

## Relevant Experience

MOXY has been collaborating with Protocol Labs in a few projects with relevant contributions for quite some time now. 

Our flagship project in the domain of decentralized technology is [Nomios](https://nomios.io/), an Identity Manager (IDM) wallet based on web technologies leveraging libp2p, in which we delivered a web app where we were responsible for its complete implementation from both an engineering and creative direction standpoints. More on the UI/UX work developed can be found on [Behance](https://www.behance.net/gallery/82496807/Nomios-Wallet-Landing-page-web-app). Links to code repositories can be found in the section right below.

Discussify, a browser extension enabling real-time and peer to peer discussions on the web built upon [peer-star-app](https://github.com/peer-base/peer-base), is another example of a project which we led from inception to completion engineering- and design-wise. More on the UI/UX work developed can be found on [Behance](https://www.behance.net/gallery/75281815/Discussify). Links to code repositories can be found in the section right below.

Many members of our own team have been actively involved in several other projects such as [JS libp2p](https://libp2p.io/), [JS IPFS](https://js.ipfs.io/), [IPFS GUI](https://github.com/ipfs/ipfs-gui) and [ProtoSchool](https://proto.school/).

The projects above are a great examples on how capable we are as engineers and designers. This is why we believe we're an outstanding fit to this project.

## Team code repositories

### Nomios: Identity Manager (IDM) wallet based on web technologies

- Identity Manager Concept & Research: [https://github.com/ipfs-shipyard/pm-idm/blob/master/docs/idm-concept.md](https://github.com/ipfs-shipyard/pm-idm/blob/master/docs/idm-concept.md)
- Identity Manager Specification: [https://github.com/ipfs-shipyard/pm-idm/blob/master/docs/idm-spec.md](https://github.com/ipfs-shipyard/pm-idm/blob/master/docs/idm-spec.md)
- IDM wallet in Javascript: [https://github.com/ipfs-shipyard/js-idm-wallet](https://github.com/ipfs-shipyard/js-idm-wallet)
- The postMessage bridge to be used by both IDM wallets and IDM clients: [https://github.com/ipfs-shipyard/js-idm-bridge-postmsg](https://github.com/ipfs-shipyard/js-idm-bridge-postmsg)
- A collection of shared React components to be used in the Nomios IDM Wallet: [https://github.com/ipfs-shipyard/nomios-web-uikit](https://github.com/ipfs-shipyard/nomios-web-uikit)
- IDM wallet UI for the web: [https://github.com/ipfs-shipyard/nomios-web](https://github.com/ipfs-shipyard/nomios-web)
- [nomios.io](http://nomios.io) website: [https://github.com/ipfs-shipyard/nomios.io](https://github.com/ipfs-shipyard/nomios.io)

### Discussify: Unlock a fully decentralized layer of discussion on any website

- Project management: [https://github.com/ipfs-shipyard/pm-discussify](https://github.com/ipfs-shipyard/pm-discussify)
- Browser extension: [https://github.com/ipfs-shipyard/discussify-browser-extension](https://github.com/ipfs-shipyard/discussify-browser-extension)
- Style guide: [https://github.com/ipfs-shipyard/discussify-styleguide](https://github.com/ipfs-shipyard/discussify-styleguide)
- Extension published in Chrome web store: [https://chrome.google.com/webstore/detail/discussify/bfmnjjkobeboejeocbompgljbiafbgcc?hl=en](https://chrome.google.com/webstore/detail/discussify/bfmnjjkobeboejeocbompgljbiafbgcc?hl=en)

### IPFS: Projects in which we have been collaborating

- JS libp2p: [https://github.com/libp2p/js-libp2p](https://github.com/libp2p/js-libp2p)
- JS IPFS: [https://github.com/ipfs/js-ipfs](https://github.com/ipfs/js-ipfs)
- IPFS GUI: [https://github.com/ipfs/ipfs-gui](https://github.com/ipfs/ipfs-gui)
- ProtoSchool: [https://github.com/ProtoSchool/protoschool.github.io](https://github.com/ProtoSchool/protoschool.github.io)

### Other open-source contributions

- MOXY: [https://github.com/moxystudio?type=source](https://github.com/moxystudio?type=source)
- NPMS: [https://github.com/npms-io](https://github.com/npms-io)

# Additional Information

## Filecoin core support & collaboration

- Before submitting this proposal, we had a chat with Jim Pick (@jimpick) about this project and agreed that joining efforts will help both parties.

## Assumptions

- PL will provide the necessary infra resources to deploy the Lotus node.

## Risks

- Jim Pick mentioned Filecoin is changing quickly lately which means there's a possibility of encountering difficulties while developing the JS API client. If breaking changes, and even small changes, are introduced in the JSON-RPC API, we will have to adapt the JS API client accordingly to be/remain compatible which may impact our estimates. We shall track Filecoin's JSON-RPC API evolution in an attempt to mitigate this risk.