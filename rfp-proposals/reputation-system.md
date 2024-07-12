# RFP Proposal: `Reputation System`

**Name of Project:** Reputation System

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-reputation-system.md

**RFP Category:** `app-dev`

**Proposer:** `rfunduk`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

As the number of storage miners increases on the network, knowing the quality and reputability of miners on the network becomes an unscalable task for any specific participant. Understanding the quality of any given miner can be especially important for storage clients, who may have different requirements about the types of miners with whom they might wish to store their data.

Figment is looking to develop a web application that will allow network participants to track relevant historical information about miners’ performance, including:

- Number and % (where applicable) of deals with no penalties
- Number and % (where applicable) of slashed contracts
- Number and % (where applicable) of dropped contracts
- Number and % of failed deals (if possible) -- i.e. the number of deals that were - attempted but failed, possibly due to this miner having spotty connectivity
- % of retrieval requests successfully fulfilled
- Number of files retrieved
- Lifetime data stored
- Lifetime data retrieved

More metrics may be added overtime, especially related to the potential loans, or delegations, of tokens to miners. A miner’s page will resemble the validators’ pages on Figment’s Hubble platform (i.e. https://hubble.figment.network/cosmos/chains/cosmoshub-3/validators/D9F8A41B782AA6A66ADC81F953923C7DCE7B6001) with the tracked metrics listed above.

Figment believes focusing on impartial on-chain data is the best way to kickstart the reputation system at mainnet launch as external forces such as network updates might affect a miner’s performance and user feedback. A simple interface providing all relevant metrics will be beneficial to a user-friendly experience with miner selection. We will create a new Ruby on Rails web app and use a Postgres database.  We’ll configure servers to host the web app and database using Amazon Web Services (AWS).  The web app models will be designed around Filecoin primitives and will be viewable in the open source code. Figment’s reputation system will be open-sourced and its data queryable by network participants if they elect to do so. 

In addition to miner metrics, the reputation system web application will allow network participants to subscribe to alerts tracking specific miner events such as M deals missed over the last N deals or upon a slashing event. This feature allows participants to proactively update their miner selection when a provider becomes unreliable. An example of tracked events for the Cosmos network can be found here: https://hubble.figment.network/cosmos/chains/cosmoshub-3/events

Network participants will be able to elect to receive those alerts via twitter, telegram or email.



## Deliverables

1. An open-sourced, dual-licensed (under MIT and APACHE2) service that will allow network participants to read miner metrics and access a reputation system.
2. Sample web application that uses both this service and go-filecoin to perform the intended workflow.
3. An events and alert system tracking miner performance.
4. Well-documented API for the service conforming to industry best practices.
5. Well-documented, human-readable codebase.


## Development Roadmap

The Service Provider will add the following components and functionality to the Filecoin Reputation System application:

*Milestone 1 - Finalize scope, workflow design, and architectural design (10 days)*
1. Define deliverable priorities with Client
2. Review existing Filecoin codebase to review available data
3. Finalize desired architecture and extent of modularity

*Milestone 2 - Setup (10 days)*
1. Run Filecoin full node/syncing blockchain

    We will download the node software and stand up permanent server infrastructure with backups to keep testnet and mainnet blockchains up to date.

2. Create new Reputation System application architecture and database configuration

    We will create a new Ruby on Rails web app and use a Postgres database.  We’ll configure servers to host the web app and database using Amazon Web Services (AWS).  The web app models will be designed around Filecoin primitives and will be viewable in the open source code.

3. Sync from Filecoin network to Reputation System database

    Using the nodes setup in Step 1, we’ll create a syncing progress to regularly transfer data from the Filecoin blockchain into the local Postgres database.  We’ll setup schedules to handle multiple testnets and mainnet in parallel, as well as instrument the syncing code to test for errors and alert when syncing is delayed.

4. Monitor, test, debug

    We’ll watch the syncing processes on live networks and simulate slowness and outages to ensure that the syncing code can adapt to various situations.

5. Deliverables report

    We'll deliver a short report describing our work on the deliverables of the milestone. In case of open-source work, basic documentation in the form of a Readme file (see resources) will be provided.

*Milestone 3 - Miner Analytics and API (28 days)*

1. Historical miner performance analytics like uptime, % of slashed contracts, and % of dropped contracts

    We will compute and store historical performance analytics in the Postgres database so users can track miners over time and view things like outages (prolonged periods of missed deals).

2. Transactions viewer

    We will index and store transactions that occur and present them with links for things like sender/receiver accounts, etc.  In addition, a list of transactions will be viewable for an account.

3. Account viewer

    We will index and store actions related to an account, such as number of files retrieved, transactions sent/received, lifetime data retrieved, and balance.

4. Search function

    We will develop a search function that will allow network participants to view, search, and filter miners based on their reputation scores.

5. API access

    The data presented on the webpages for Milestones 3.1 - 3.4 above will also be accessible via API.

6. Deliverables report

    We'll deliver a short report describing our work on the deliverables of the milestone. In case of open-source work, basic documentation in the form of a Readme file (see resources) will be provided.

*Milestone 4 - Miner Events and Alerts (12 days)*

1. Setup Events - Dropped contracts, slashed contract, % parameter change, storage capacity change, joined/left active set.

    We will modify the blockchain syncing process to incorporate the historical miner analytics from the Postgres database so we can detect events and create alerts for long range analytics like “miner missed X of last 100 deals”, “miner missed X deals in a row”, etc.

2. Setup Email subscriptions

    For the Miner events created above, we will add the ability for users to subscribe via email.  Users will be able to configure their subscriptions for things like “Miner missed X deals in a row” where X can be a range of numbers.

3. Event history per Miner

    We will store all events detected for a Miner in the Postgres database.  Events can be viewed in a time range or filtered by event type.

4. Global event feed + Twitter account (ex. https://twitter.com/HubbleAlert/)

    We will present all events detected for all Miner in a single view that can be filtered by time range and event type. In addition, we will create a Twitter account that will contain all detected events.

*Milestone 5 - All Project Deliverables (10 days)*

1. An open-sourced, dual-licensed (under MIT and APACHE2) service that will allow network participants to read miner metrics and access a reputation system.
2. Sample web application that uses both this service and go-filecoin to perform the intended workflow.
3. Well-documented API for the service conforming to industry best practices.
4. Well-documented, human-readable codebase.
5. All work results are to be reviewed and approved by the Client and Service Provider will conduct any and all requested changes.


## Total Budget Requested

a. For the services rendered by the Service Provider as required by this Agreement, the Client will provide compensation (the “Service Fee”) in the form of a team rate of $1450 per workday split equally in USD and FIL at last private sale price (see Appendix A for team breakdown). Paid FILs should be vested upon distribution. FILs will be used to increase Figment’s storage capacity as a miner.

b. The Client will pay the Service Provider with the following release based schedule and the final payment must also include the open-sourcing of the software.

  - Payment 1 ($14,500): Finalized scope and architecture approved by client (Milestone 1)
  - Payment 2 ($55,100) Validator Analytics (Milestone 2 and 3) running on testnet
  - Payment 3 ($17,400): Events and Alerts (Milestone 4) on testnet
  - Payment 4 ($14,500): Finalized deliverables (Milestone 5) running on mainnet, code open sourced and documented, README helpers for installation and configuration, and deployment options like Docker available

    For a total of $101,500 USD ($50,750 in USD and $50,750 in FIL)

c. All costs and expenses of the Service Provider are covered by the Service Fee.



## Maintenance and Upgrade Plans

The software will be maintained at our expense for the first 365 days following the mainnet launch. Thereafter, the Client agrees to be charged maintenance fees following the options below:

- Option 1: $100,000 interest-free loan in FIL to be used for increasing our miner’s storage capacity
- Option 2: A monthly payment of $4,000 USD paid in fiat

Major upgrades and feature requests will be subject to new grants.


# Team

## Contact Info

yannick@figment.network


## Team Members

- Andrew Cronk (Project Manager)
- Matt Harrop (CTO/DevOps)
- Ryan Funduk (Tech Lead/Backend Engineer)
- Bartosz Hejman (Web/Front-End Engineer)

We are confident in our team’s ability to deliver the product within the agreed upon timeframe and with the quality expected by the Filecoin community.


## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/andrewcronk/
- https://www.linkedin.com/in/matt-harrop-141b2/
- https://www.linkedin.com/in/rfunduk/
- https://www.linkedin.com/in/bartosz-hejman-a613b117/

## Team Website

https://figment.network/  
https://figment.network/solutions/hubble/

## Relevant Experience

The team committed to this project has built or is working on deploying [Hubble](https://hubble.figment.network/cosmos/chains/cosmoshub-3), our validator analytics platform, for [9 leading Proof-of-Stake networks](https://figment.network/solutions/hubble/). We have repeatedly shown our capacity to adapt to new blockchains and have built a comprehensive platform coordinating validators and educating token holders across chains.

We are confident that we can deliver a high quality product for the Filecoin community that will allow token holders to make educated choices regarding provider selection and that will increase the quality of the miners’ services.


## Team code repositories

Team repository: https://github.com/figment-networks  
Hubble repository: https://github.com/figment-networks/hubble


# Additional Information

&ndash;
