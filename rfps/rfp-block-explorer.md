# RFP: Block Explorer

**Name of Project:** Block Explorer

**RFP Category:** `app-dev`

**Proposer:** [@michellebrous](https://github.com/michellebrous)

## Project Description

Decentralized systems consist of a complex network of nodes that must agree or come to “consensus” on the “current state” of the broader system. It is essential that Filecoin network participants have a persistent, clear view of the state of the network (last block number and hash, time since last block, etc.) to understand whether their nodes are in consensus with the network or transactions have been confirmed.

The Filecoin Project would like to sponsor a talented external team to build a dynamic, easy to use, and visually appealing public block explorer for the Filecoin network. A block explorer is typically a web-based tool that reads metadata from a blockchain and displays it in a digestible and searchable way. Example metrics typically covered on block explorers include wallet addresses, node information, message detail, transaction data, block height, block time, and more.  

A very early prototype of a Filecoin block explorer can be found [here](https://user.kittyhawk.wtf:8000). This is just a simple version and we expect new explorers to be much more feature-ful and useful.

This project complements, but is separate from, the [Filecoin Network Stats Dashboard](https://stats.kittyhawk.wtf).

## Deliverables

- Fully functional block explorer website, hosted/maintained/managed by your team. Publicly accessible via a `https://` site.
  - Must also work on mobile and be mobile-friendly
  - Real-time updates based on changes in the network
  - Fast to load
  - Good UX and visual design
- Open-sourced repo for block explorer codebase, dual-licensed under [LICENSE-MIT](https://github.com/filecoin-project/devgrants/blob/master/LICENSE-MIT) and [LICENSE-APACHE](https://github.com/filecoin-project/devgrants/blob/master/LICENSE-APACHE) (see this [License section](https://github.com/filecoin-project/devgrants#license) for how it can look)
- Well-documented codebase so anyone can learn from your application development process
- User-facing documentation for anyone to spin up your block explorer locally

## Recommended Team

- A small team with strong design and web development skills (please show evidence of this in your proposal)
- Experience creating novel data visualizations and extracting metadata from a blockchain or a complex tech back-end (APIs may not exist to extract all the information the project might need)

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
We anticipate a homepage showing summary statistics, with the ability to click for more detailed information. **NOTE: These are just suggestions! We will not select teams purely on the basis of how much of this list they include in their proposals or early mockups. We would like teams to be very thoughtful about the work they are doing, and will prefer teams that are thoughtfully choosing what to include in their product as opposed to doing just what we suggest.**

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


## Milestones & Funding

**Total Funding Amount:** TBD. Please propose a budget in your proposal.

**Milestones:** Make sure that the values in the Funding column add up to the Total Funding Amount listed above.

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | High-fidelity design mockups, running staging site with some UI elements implemented | TBD | 4 weeks |
| 2 | Completed implementation of block explorer | TBD | 6 weeks |
| 3 | All project deliverables are completed and added to the [Filecoin Shipyard](https://github.com/filecoin-shipyard) (website, documentation, codebase) | TBD | 2 weeks |

## Acceptance Criteria

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

## Resources

Example Block Explorers:
- https://www.blockchain.com/explorer
- https://blockchair.com/
- https://explorer.bitcoin.com/bch
- https://polkascan.io/
- https://0xtracker.com/

Filecoin brand card (TODO link)
