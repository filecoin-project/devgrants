# Contact: `CTO: futjrn@herc.one`
# RFP Proposal: `FIL Your Blocks`

**FIL Your Block:**

**Link to RFP:** Please link to the RFP that you are submitting a proposal for.

**RFP Category:** `app-dev`

**Proposer:** `Lrgeoemtry`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `Yes`

# Project Description

Hi there, we're the Hercules Development team. We've been enjoying IPFS for sometime and would like to be a part of this jounrey as it scales. We plan to have our designer whip up some really sleek UI for a Block Explorer we would use (as devs and a use case) as well as one that others interested in the FIL ecosystem would enjoy and understand intuitively.
- For Milestone 1 we will have the mocks and the basic ui on a staging environment, and hopefully if the FIL docs are good we'll have basic realtime dev data from the FIL network populating the fields. 
- For Milestone 2 we'd like to work closely with those in charge to ensure Milestone 1 is behind us while improving the useability and complete functionality of the explorer. 
- For Milestone 3 we'll have everything documented appropiately so anyone can build it while deciding an appropiate maintainence agreement post build. 


## Deliverables

- Fully functional block explorer website, hosted/maintained/managed by your team. Publicly accessible via a `https://filyourblocks.org` site.
  - Will also work on mobile and react to different mobile ratios. 
  - Real-time updates based on changes in the network
  - Fast to load
  - Good UX and visual design
- Open-sourced repo for block explorer codebase, dual-licensed under [LICENSE-MIT](https://github.com/filecoin-project/devgrants/blob/master/LICENSE-MIT) and [LICENSE-APACHE](https://github.com/filecoin-project/devgrants/blob/master/LICENSE-APACHE) (see this [License section](https://github.com/filecoin-project/devgrants#license) for how it can look)
- Well-documented codebase so anyone can learn from your application development process
- User-facing documentation for anyone to spin up your block explorer locally


## Detailed Requirements & Constraints

### User Flows
This tool will most often be used by Filecoin developers, token holders, clients, and miners to investigate transactions, debug their nodes, or generally explore the chain. We have done some thinking about the user needs we would like this tool to satisfy. You can use this as a starting point or take this in a totally new direction. Some example user stories:

- *Prospective Client*: I am considering using Filecoin for my data storage needs. I decide to visit the Filecoin block explorer to get a pulse on important storage contract parameters before using the network.
- *Current Client*: I recently hired a Filecoin storage miner to store some of my data. I want to use the Filecoin block explorer to easily monitor the status of my storage providers, keeping tabs on their deal activity and any potential reputational metrics.
- *Potential Miner*: Before signing up and pledging collateral to mine Filecoin, I want to see how frequently blocks are mined, the size of the block reward, and storage deal information so I can understand mining in more detail.
- *Current Storage Miner*: I haven’t mined a block in a while and I want to check the chain state to make sure that my node is in sync with the rest of the chain, and to make sure that the network is still working as it should. I want to be able to see the nodes coming to consensus and understand mining statistics such as when the last block was mined.
- *Investor / Token Holder*: I recently transferred FIL from one wallet address to another, and would like to confirm the transaction happened as well as record the relevant block data that corresponds to the transaction. 
- *Developer*: I am building an application on top of Filecoin and want to ensure that my application is in sync with the latest chain-state information. I also want to confirm my deal information with corresponding block data using the block explorer.
- *Accountants / Investors*: I want to be able to retrieve a list of transaction details for a period of time as well as ending token balances per wallet for tax and accounting purposes.

### Data to Display
We anticipate being able to provide a homepage showing summary statistics, with the ability to click for more detailed information as requested in the RFP.

- **Top Level / Home Page Summary Statistics**: *Clean, streamlined view of the network. Ideally most people will get all the top level stats they’re looking for from this page without having to navigate away from it.*
	- [Creative visualization](http://www.ethviewer.live/) of blocks mined and nodes (or peers) coming to consensus / [visualization of the blockchain growing in real time](https://user.kittyhawk.wtf:8000)
	- Include a [universal search bar](https://blockstream.info/) that allows users to search by block height, transaction, block hash, or address 
	- Best Block (or in Filecoin’s case, “Best Tipset”) (i.e., [a summary overview of stats](https://ethstats.net/))
	- Prioritized Block Stats including some, perhaps not all, of the following:
		- Tipset Height
		- Number of blocks in tipset: Number of blocks in the current best tipset. A tipset is a set of blocks at the same height that share the same parent set.
		- Hash of each parent block in a tipset
		- Time since last block: Time since a miner last created a block
		- Avg. block time: Average time between blocks that are created / mined
		- Last block miner address
		- Last block peerID
		- Storage Power (%): The probability that a storage miner will win the ability to mine the next block. Miners gain power by storing data, sealing it, and proving they still have it (i.e., providing a Proof-of-Spacetime).
		- Ticket
		- Stateroot
		- Number of messages in each block
		- Block Size (GB)
		- Block Reward
		- Clicking on the block height number will bring you to a different view that provides detailed block metadata (see Block Metadata list below)

- **Secondary Views: Detailed Blockchain Metrics**: *Each bullet is a separate tab or view, though it may make sense to combine some. Tabs: Explorer (home page above), Block Data, Deals, Actors*
	- High Level Deal Data:
		- Average deal price (normalized to FIL/GB/month or $/GB/month) over time
		- Interactive graph of deal volume over time
		- Average deal duration 
		- Average deal size
		- Average deal replication factor
		- Average sector size
		- Average # of deals / block
	- Transaction Detail Table:
		- Content ID 
		- Miner address
		- Client address
		- Deal price
		- Deal duration
		- Deal Size
		- Hash, age, amount (in FIL and USD)
		- Table should be easy to read, query, and sort
	- Actors: Include an index card layout of high level actor information that is easy to read, query, and sort. A table view should also be included:
		- Differentiates between a storage or retrieval miner, or a client
		- Actor Address
		- Miner address (if applicable)
		- Double clicking on the address will take you to detailed info view for each actor:
		- Node Type
		- Node latency
		- Uptime
		- Nonce
		- Ticket 
		- Messages (To, From, Value, Nonce, Messages, Param, Signature)
		- Message receipts
		- Number of nodes
		- Total supply of Filecoin
		- Chain height
		- Block reward


## Development Roadmap

# M1:
> - UI Mocks, Approval, Design and Front End Implementation to Staging under an https://staging.filyourblock.com to tool around in. Will be built in React and Node so as to be available on both desktop and mobile envs. 
> - 1 project manager, 1 designer, and 2 developers (front & back end)
> - Our proposed budget for Milestone 1 is $168,000 which can be paid in BTC, ETH, or Wire.
> - With funds cleared for Milestone 1 we can assume this task will take 1 month and 2 weeks to bring to the standard requested in the RFP. Any scope time will be carried into Milestone 2 whereas time is applicable when FIL leaders approve of the UI in staging.
# M2: 
> - Work will begin on Milestone 2 when the Milestone 1 UI is approved and finalized. We will get the front end on a real site (thinking https://filyourblock.com) with real / dev network data populating the fields. This will be functional with associated code in the designated repository.
> - We will need 1 project manager and 3 developers during Milestone 2 to stay within scope time.
> -  To compensate our proposed budget for Milestone 2 is $210,000 paid in BTC, ETH, or Wire.
> - With funds cleared for Milestone 2 we can assume this task will take 1 month 3 weeks to finalize the standard requested in the RFP. Any scope creep will be carried into Milestone 3.
# M3:
> - Finalize documentation, finalize scope of RFP, finalize agreement for post work 
> - We will need 1 developer and 1 project manager during Milestone 3 to stay within scope time. An executive business developer will handle the post build maintenance agreement.
> - To compensate our proposed budget for Milestone 3 is $72,000 paid in BTC, ETH, or Wire.
> - With funds cleared for Milestone 3 we can assume this task will take roughly 1 month with finalized testing. 

`If approved Milestone 1 through Milestone 3 should take 4 months an 1 week if all proposed budget is paid in a timely manner with FIL leadership available for day-to-day checkups and approval of design and measure.` 

## Total Budget Requested
> - Work days = 8 hours
> - Work weeks = 40 hours
> - Work months = 160 hours
> - Developer= $250/hour
> - Designer = $200/ hour 
> - Project Manager = $200/hour 

## Total Proposed Budget $506,000 paid in BTC, ETH, or Wire.

> - Hourly figures as seen in https://www.fullstacklabs.co/blog/2019-software-development-price-guide-and-hourly-rate-comparison

# Maintenance and Upgrade Plans

`We plan to have our SVP handle the post maintenance agreement. 
We'd like to continue to build with the FIL leadership and community and can come to negotiable terms post build that benefit everyone.`

## Acceptance Criteria `Brought in For Team's Convienence` 

**Acceptance criteria for milestone 1: High-fidelity design mockups**:
- These mockups must represent the final design of the website (okay to make very minor changes here and there).
- Mockups must include several of the features listed above in the Detailed Requirements and thoughtfully display these features in a visually compelling and logical way
- Mockups must represent a functionally complete block explorer. Having drastic areas of missing functionality will not qualify as having completed the milestone.
- Mockups must be visually compelling and demostrate that the final app will be easy to use.
- The staging site must be hosted and running on your suggested front and back end systems. Site page structure and most UI elements are implemented, although some UI elements might be "placeholders" that are not necessarily "hooked in" or capturing real-time data from the Filecoin network yet

**Acceptance criteria for milestone 2: Completed implementation of block explorer**:
- Block explorer must display activity from the [Filecoin user devnet](https://github.com/filecoin-project/go-filecoin/wiki/Devnets#user). You can join the Filecoin community chat in order to ask more questions about how this should work, or poke around other products such as the [network stats dashboard](https://stats.kittyhawk.wtf).
- The block explorer must be fast to load, responsive on mobile, and accessible by standard web browsers from anywhere in the world.
- The block explorer design must match the designs accepted for milestone 1.

**Acceptance criteria for milestone 3: All project deliverables (website, documentation, codebase)**:
- The codebase must be added to the [Filecoin Shipyard](https://github.com/filecoin-shipyard)
- The codebase must be open-sourced and dual-licensed under MIT and APACHE2 licenses
- The codebase must be well-documented and human-readable (bonus points if it's modularly architected)
- There should be documentation so anyone can spin up the block explorer locally against a local filecoin network or any other filecoin network (including the user devnet).
- There should be a maintenance and upgrade plan for the block explorer website and codebase over time

If a milestone is not satisfactorily met, we may not continue to fund your team for this project.

# Team

`Hercules SEZC`

## Team Members

> - Futjrn (Project Manager)
> - Chance Cordelia (back end dev)
> - DaxDax (network dev)
> - Linux08 (front end dev)
> - Ibrahim (design)

## Team Member LinkedIn Profiles

> - https://www.linkedin.com/in/logan-ryan-golema-b0161190 
> - https://www.linkedin.com/in/julianamei
> - https://www.linkedin.com/in/daxdax89
> - https://www.linkedin.com/in/linux08


## Team Website

> - https://herc.one 
 (our launched product)
> - https://anthemgold.com
 (our launched product)
> - https://anthemvault.com
 (our launched product)
> - https://amagimetals.com
 (our launched product) 
> - View our History: https://anthemgold.com/history

## Relevant Experience

`We have been building in blockchain for 8+ years. We have been using IPFS for the length of our current project. Explorers are really about organization and delivery of content and we'd like to be a part of building yours :)` 

## Team code repositories

> - https://Github.com/hercone
> - https://Github.com/anthemgold
> - https://Github.com/herchackathon
> - https://Github.com/julianapeace
> - https://Github.com/linux08
> - https://Github.com/daxdax89

# Additional Information

`Pick us! We love being organized and explorers are the epitome of organization. As a use case of IPFS we'll use this just as much as you do and plan on building it to be amazing for Storage Use Cases, traders, and Miners alike!`
