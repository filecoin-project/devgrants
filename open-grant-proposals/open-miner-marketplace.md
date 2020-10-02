# Open Grant Proposal: `Miner Marketplace`

**Name of Project:** Miner Marketplace

**Link to RFP’s: **

- https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-5-rfps.md
- https://github.com/filecoin-project/devgrants/blob/a2981ff73ba43fde7e31db9ff9ed0b7ce4e84a14/rfps/new-mining-tools-rfps.md#miner-transaction-history-and-earnings-* predictor
- https://github.com/filecoin-project/devgrants/blob/a2981ff73ba43fde7e31db9ff9ed0b7ce4e84a14/rfps/new-mining-tools-rfps.md#miner-hardware-profitability-calculator

**Proposal Category:** `app-dev`

**Proposer:** @Saumay-Agrawal

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

<br>
<br>

# Project Description

Miners are at the heart of the Filecoin network. They are a representative of the value that Filecoin strives to provide.
Hence it becomes very important to gain awareness about the various miners present in the ecosystem.

We want to solve the problem of information asymmetry surrounding the miners in the Filecoin ecosystem by curating relevant information about them and presenting it in the form of miner profiles. This will form the crux of a Miner marketplace & social network.

Miner marketplace will have these key components:

- Standardized listing of all miners - that can be sorted and filtered by different attributes.
- Miner Profile - that contains various details about the miner.
- Client Profile - that contains various details about the client
- Developing Miner<->Client relationships.

Our vision: “Join the social network where people help you become a miner/client and answer your questions/concerns”

<br>

## Deliverables

- Miner Marketplace UI - Search + Listing of all the miners in the network.
  - Miner profiles - clickable from the home page.
  - Client profiles - like Amazon product reviewer profiles.
    - Clients will also have an option to give ratings to the miners based on their interactions with the miner.
  - Calculator View
- Miner Marketplace API
  - That can be polled by different interfaces like Slate to access the data related to interactions between Client and Miner.

#### Search + Listing of all the miners in the network:

- Search via address
- Listing all miners with their attributes.
- This listing can be sorted based on attributes.
- Click on miner -> leads to Miner profile.

#### Miner Profile Details:

A miner profile would contain various details about the miner.
Successful outcome: each miner ends up bookmarking their link to the profile and goes every other day to see how are they amassing social capital in the network.
This may include the likes of:

- Generic information about the miner. Eg:

  - Name
  - Bio,
  - Contact details like email, twitter handle etc (based on miner’s discretion)

- Kind of service (or a combination of services) being provided by the miner:

  - Storage
  - Retrieval
  - Others characteristics like “repair” (when added in the future)

- Attributes measuring miner’s skin in the game

  - Committed capacity
  - Locked funds

- Attributes measuring miner’s performance in the network

  - Number of times miner went offline
  - Block reward collection
  - Storage power
  - Number of storage deals made over a period of time

- Attributes that signal trust of the miner:

  - How many clients have trusted the miner with their data.
  - How much volume per client has been entrusted with the miner.
  - Reviews by clients.

- General fee

  - Deal fees
  - Network transaction fees + Average priority fee

- Miner Transaction History (TBD\*):

  - Problem: A miner’s transaction history can be hard to follow and group logically in current block explorers, especially for new miners.
    - Ref: https://github.com/filecoin-project/devgrants/blob/a2981ff73ba43fde7e31db9ff9ed0b7ce4e84a14/rfps/new-mining-tools-rfps.md#miner-transaction-history-and-earnings-predictor
  - Solution: A clean no-brainer jargon-free transaction history.
    - We are inspired by Zerion style clean history which humanizes historical transaction flow.
    - Sample: https://app.zerion.io/0x5b3ce67ebc795fe7e709815bc49d4300898e1b7b/history

- Other attributes
  - Location
  - Support for offline data transfer
  - Average client rating
  - Powergate Reputation Score

[Note: The above list of attributes is not final. It’s just a suggestion at present. The list of attributes will be finalised via having discussions with the community members in the initial weeks of execution.]
The following image is of our flagship product YieldScan. We intend to have a miner profile as close to this:

![Dashboard - Validator Profile](https://user-images.githubusercontent.com/10279686/94892491-63c4ff80-04a2-11eb-8529-6d2f5ca8302e.png)

We also intend to add a transparency score to the mix so to provide gamification incentive for miners to update their data to their profiles:

<img width="858" alt="Screenshot 2020-10-02 at 10 04 36 AM" src="https://user-images.githubusercontent.com/10279686/94892500-6b84a400-04a2-11eb-9947-8e1b508c8548.png">

#### Client Profile Details:

- Generic information about the client. Eg:
- Name
- Bio,
- Contact details like email, twitter handle etc

Attributes measuring client’s participation in the network:

- How many storage deals did they make and with whom?
- How much data are they storing in the network (top client leaderboard PoV)

#### Both miner and client will use auth:

- If possible auth using FIL wallet.
- If not possible, via Keybase or Github will do until auth is possible using FIL wallet.

#### Calculator View

- Since this is a social network, this view will help new miners get answers to their questions like:
- Why should I become a miner?
- What will it take?
- What is the amount of profit I will make? And over what period of time.

Ref: https://github.com/filecoin-project/devgrants/blob/a2981ff73ba43fde7e31db9ff9ed0b7ce4e84a14/rfps/new-mining-tools-rfps.md#miner-hardware-profitability-calculator

#### API Details:

Such data is not only relevant for a client looking to make deals with the miners, but it’s also relevant for various other applications that are being built (or will be built) on top of the Filecoin network like Textile’s Powergate or Slate.

Hence, the data collected about the miners will be made available via an API.

<br>

## Development Roadmap

#### Milestone 1 - Finalisation of API Specsheet & UI (4 weeks)

- Discussion with the community to arrive at a final list of miner attributes relevant for being showcased on the marketplace application
- Finalise the API specsheet based on miner attributes list
- Arrive at high fidelity UI mockups via multiple sprints of community review

#### Milestone 2 - Development Phase (4 weeks)

- Deploying scripts to automate period collection of miner data from the network and dump that data into a DB
- Implementation and deployment of the marketplace API
- Implementation and deployment of the marketplace UI

#### Milestone 3 - Testing, Debugging and QA (4 weeks)

- Testing of the API and UI
- Bug fixes, if found any
- Updates based on the community reviews
- Delivery of final codebase with robust documentation
- Walkthrough/tutorials of the interface

<br>

## Total Budget Requested

Based on discussions with Eshon, the core team was busy with the mainnet launch and we didn’t think it would be a good idea to bother teh team with our questions.
Hence budget has not been finalized since scope of the final application needs to be discussed with the team.

<br>

## Maintenance and Upgrade Plans

**Maintenance**

- After project completion, maintenance or bug fixes if any.
- For next 6 months: support if the system goes down.

**Support**

- We will be available to provide guidance and troubleshooting assistance to
  - any team building on top of the API
  - any user facing hassle in the UI

**Upgrade Plans**

- Integration of https://sourcecred.io/ to measure and reward value creation among participants.

<br>
<br>

# Team

## Contact info

saumay@buidllabs.io

## Team Members

- Design: Abhinav

  - Designer and Frontend developer
  - Designed YieldScan for Polkadot ecosystem chains and Crypto Code School for Tezos.
  - Have experience in designing HCI solutions especially in the domain of data analytics.

- Researcher/Lead Developer: Rajdeep

  - Worked on infrastructure tools for various open source communities
  - Wrapping up the execution of Demux

- Project Manger: Saumay
  - Has 3+ years of product-dev experience across multiple startups, research labs and companies
  - Extensive experience in wrangling data and building ETL pipelines, Go Developer.
  - Successfully executed Demux sprint.

## Team Member LinkedIn Profiles

- Abhinav - http://abhinavthukral.in/
- Rajdeep - https://github.com/rajdeepbharati
- Saumay - https://www.linkedin.com/in/saumayagrawal/

## Team Website

https://buidllabs.io/

## Relevant Experience

Our team has solved similar information asymmetry problems for other networks:

- Livepeer pricing tool
  - Though still in its MVP stage, Livepeer pricing tool enhanced the visibility into off chain pricing data of Orchestrators (akin to Miners) in the Livepeer network
- YieldScan
  - Solves the problem of information asymmetry between the validators and nominators in the Polkadot network.

Besides this, our team has also been actively working on a project in the Filecoin ecosystem

- Demux
  - an API gateway between Livepeer and Filecoin for facilitating decentralised streaming services.

## Team code repositories

- Livepeer pricing tool - https://github.com/buidl-labs/livepeer-pricing-tool
- YieldScan - https://github.com/buidl-labs/YieldScan
- Demux - https://github.com/buidl-labs/Demux
