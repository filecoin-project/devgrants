# RFP Proposal: `Filexplorer.org`

**Name of Project:** Filexplorer.org

**Link to RFP:** [RFP: Block Explorer](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-block-explorer.md)

**RFP Category:** `app-dev`

**Proposer:** [@anish-agnihotri](https://github.com/anish-agnihotri)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Filexplorer.org (a play on words between the token name of FIL and explorer resulting in FIL(e)xplorer) is a proposed easy to use, visually appealing, streamlined, and developer + consumer friendly block explorer for Filecoin.

Built with the common principles of block explorers in mind, it aims to be a two-part implementation:

1. A simple, dynamic, and responsive web-based tool that reads metadata from the blockchain and displays it in a digestable format, in real-time. Similar to existing solutions for other currencies (think [Blockchain.com Explorer](https://www.blockchain.com/explorer), [Etherscan](https://etherscan.io/), and [LibExplorer](https://libexplorer.com/)), the tool would provide a clear view of the state of the network, and allow users to visually interact with and manipulate historic (and real-time) data from the blockchain.
2. While not directly requested in the RFP, a part of building such a web-based tool would involve utilizing a Filecoin node and interacting with it via HTTP requests. Thus, for developers and Filecoin data enthusiasts, Filexplorer.org would also expose a real-time development REST API which can be used to conveniently integrate the block explorers data into other applications built by developers on Filecoin (many existing block explorers already do this, for example, [Blockchain.com API](https://www.blockchain.com/api/blockchain_api), [Etherscan API](https://etherscan.io/apis), [LibExplorer API](https://libexplorer.com/apis)).

Besides this, the scope provided in the RFP has been fully realized and understood. The core metrics (including wallet addresses, node information, message detail, transaction data, block height, block time) will be delivered, alongside various additional metrics such as historic supply, 24h statistics (volume, market cap, transactions), number of active nodes, etc.

## Deliverables

Final deliverables will include:

* Fully functional block explorer website, built with Preact and NodeJS.
	* Secured with a Let's Encrypt SSL certificate to ensure `https://` protocol compliancy.
	* Mobile-responsive design via media queries, real-time metric updating with 0.5s polling for front-end (rather than a WebSocket implementation), aesthetically pleasing and easy to use layout.
	* Hosted in a North American datacenter via OVH with European, Asia, and Oceania CDNs to ensure speed in loading static content across region.
		* Specifically for hosting, two instances will be used (SSD3, SSD2). One for hosting the main application front-end and back-end. The second for hosting the MongoDB server and documentation.
* Open-sourced Github repo containing sub repos for each component of the platform (licensed accordingly with both MIT and Apache specifications):
	* Sub-repo for front-end in Preact (Preact-core, Preact router, Axios)
	* Sub-repo for back-end in Express (NodeJS, Axios)
	* Sub-repo for Filecoin to MongoDB bridge (NodeJS)
	* Sub-repo for documentation and milestone tracking
* Well-documented codebase hosted on SSD2 instance using [MkDocs](https://www.mkdocs.org/).
* User-facing documentation (hosted on seperate subdomain running MkDocs), and contributing guidelines + good first issues to promote future open-source contributions from the community.

## Development Roadmap

The following milestones describe the development outline of filexplorer.org. Please note: the number of people working on each milestone has been omitted since this RFP response is being delivered individually.

| Phase | Milestone Description | Funding | Timeline |
|-------|-----------------------|---------|----------|
|      1 | Setup, Design, Front-end framing                     |        $750 |   3 weeks (October 1st - 21st)       |
|      2 | Back-end, MongoDB, Completed Implementation                      |       $1500  |   8 weeks (October 22nd - December 16)       |
|      3 |   Documentation, API Guides, Addition to Shipyard                    |       $500  |   1 week (December 17 - 21, excluding winter festivities)       |
|      4 |  Long-term maintenance and support                     |       $750  |  9 months (January - September 2020)        |


#### Phase 1
The first phase involves a few things. This involves multiple submilestones:

1. Procuring domain name and hosting (setting up load balancing, static asset CDN, SSL certificate via Let's Encrypt)
2. Setting up Github organization, appropriate licensing for each sub-repo, and integration with Github Actions to automatically deploy to staging and development environments on commit.
3. High-fidelity design mockups in Adobe XD. These will include finalized top level summary page mockups, and somewhat finalized secondary page mockups. Secondary page mockups are not set in stone since I'd like to iterate and continue to add upon the displayed metrics and their styling as I work.
4. Work-in-progress staging site deployed with:
	1. Working basic data retrieval via back-end and MongoDB.
	2. Fully implemented, responsive, header, footer, and CSS framework.
	3. Completed page sitemap.

For the time being, I am planning on developing with a Preact front-end, which is a highly optimized and minified variant of React. The end goal is to deliver a performant platform, which Preact will help in doing.

#### Phase 2
Phase 2 is the largest portion of the project since it involves:
1. Back-end completion.
	1. During Phase 2, the back-end must be completed up to spec in Express with completed and deployed endpoints in use by the front-end. In specific, the following metrics are being targetted for the time being, although more may be added as development progresses: 
		1. Top level:
			1. Block stats
				1. Tipset Height
				2. Number of blocks in tipset
				3. Hash of parent block in tipset
				4. Avg. block time
				5. Last block miner address & PeerID
				6. Storage Power
				7. Number of messages in block
				8. Block Size
				9. Block Reward
				10. Timestamp
		2. Secondary:
			1. All secondary metrics will be added, except for:
				1. Average sector size
				2. Actors:
					1. Node latency
2. Exposed API completion.
	1. The exposed API will be a simple Express outgoing endpoint available at api.filexplorer.org which brings commonly used developer metrics. It will allow: 
		1. GET requests for commonly used metrics (think: high-level deal data)
		2. POST requests to retrieve messages, block information, transaction details.
3. Filecoin node to MongoDB script completion.
	1. This script will allow new transactions to be stored in a MongoDB cached instance allowing for faster retrieval, and better historic data retrieval. A large part of block explorers is their ability to index complete histories of blockchain metadata, and thus, this script will poll the node endpoint at quarter-second intervals, timestamping its requests.
4. And, finally, Front-end completion:
	1. By this point of time, most of the Preact components will have already have been built (with the framing in Phase 1). Thus, it is only a matter of adding them to their respective pages, setting up props, and using Axios to retrieve data from the back-end.
		1. A large focus of the front-end will be maintaining responsiveness.
		2. Victory and other data visualization libraries will be used to display network heatmaps, charts, and visualize other statistics.
		3. A universal search bar (at the top) will be the main focal point of the front-end which will allow for POST requests including block peerID, addresses, content ID, and hash as the message.
#### Phase 3
Phase 3 is relatively simpler compared to Phase 1 & 2, but equally important. During this phase:

1. I will expand on the comments throughout the code base. 
2. Setup two documentation portals (one for development, and one for a user to easily spin up their own instance of filexplorer.org)
3. Setup an API experiment ground where users can poll the API without a REST client or code.
4. Migrate repositories to the Filecoin Shipyard:
	1. This will be a multi-step process involving: 
		1. Merging each of the sub-repos into one linked monorepo.
		2. Fixing Github Actions deployment hooks to ensure website deployment continues as normal.
		3. Adding support for one-click deployment via Docker and Heroku. Users can use a simple docker command to run each of the sub components of the platform, or deploy their own instance to Heroku with one click.

#### Phase 4
The last phase focuses on continual maintenance and upgrades:
1. A large part of this phase will focus on setting up Analytics and tracking how users use the website to better optimize the user flow.
2. Monthly server maintenance to ensure performance is up to par.
3. Development:
	1. Using the additional funds, I'll be throwing up a few bounties on Gitcoin to develop with the filexplorer.org API. This will help gain insight into the developer flow, while also encouraging development growth on Filecoin through the block explorer.
	2. Additionally, the funds will be used to make continual updates to the platform, rated at a few hours (think 4-5, to ensure website stays on top of any protocol changes, plus adding new metrics) of dedicated development per month.
4. Documentation
	1. This phase will also focus on making it as easy as possible for new contributors to pick up with development. I'll be writing good first issues, contributors guide, styling guides, and additional documentation to support community development input.


## Total Budget Requested

The total budget requested for this RFP response is `$3,500`.

## Maintenance and Upgrade Plans

As referenced in the development roadmap, `$750` is allotted to long-term maintenance, support, and continued development over nine months. Please see *Phase 4* roadmap for more information.

# Team

## Team Members

- [Anish Agnihotri](https://github.com/anish-agnihotri)

## Team Member LinkedIn Profiles

- Anish Agnihotri prefers not to use a LinkedIn profile. Rather, links to relevant information can be found through his personal website [here (https link)](https://anishagnihotri.com). Specifically, the following profiles are of particular relevance to this RFP:
	- [Github (https link)](https://github.com/anish-agnihotri). Anish's Github features his open-source contributions to blockchain projects, and provides insight into his code style and proficiency. He has contributed to various blockchain projects, including, but not limited to: [Gitcoin (https link)](https://github.com/gitcoinco/web), [DAppNode (https link)](https://github.com/dappnode?type=source), and the [Fellowship of Ethereum Magicians (FEM)](https://github.com/FEMBusinessModelsRing).
	- [Gitcoin (https link)](https://gitcoin.co/profile/anish-agnihotri). Anish is an active Gitcoin contributor, completing bounties posted by large open-source blockchain projects. To date, he has helped contribute to the core Gitcoin platform, and tens of other bounties across various organizations.
	- [Devpost (https link)](https://devpost.com/348712712). Anish is a quick prototyper, as is evident from his Devpost profile. Over the course of six hackathons, Anish has successfully developed various decentralized applications, with a >100% success rate (11 prizes over 6 hackathons). He is very involved in the blockchain community, with his next hackathon being ETHBoston in September.
	- [Twitter (https link)](https://twitter.com/_anishagnihotri). Anish's Twitter speaks for his passion for blockchain.

## Team Website

Since this is an RFP response by an individual, a personal website can be found [here](https://anishagnihotri.com).

## Relevant Experience

Anish brings relavent blockchain experience and proven delivery track-record. He is proficient with the necessary web technologies (mainly JavaScript), and has completed both bounties and hackathons in the industry.

He has strong design and development skills. For web he is proficient with: 

* Front-end: 
	* HTML (Pug, EJS, Handlebars)
	* CSS (SASS/SCSS/Less/Stylus)
	* JS (Jquery, Babel, React, etc.), TypeScript
* Back-end:
	* NodeJS (Express, Feathers, etc.)
* Additional: 
	* Solidity, Swift
	* Heavy experience working with:
		* Git + version control
		* Docker, CI (I would most likely use Github Actions for this project to ensure everything is transparent, open-source, and so that it is easy for contributors to pick up)

Uniquely, though, he brings past experience building block explorers of such a scale. He is currently working on a block explorer for Facebook's Libra currency (see: similar projects repository) which is user- and developer- friendly, streamlined, and easy to use. He would be more than happy to deploy a live testing environment and provide further insight if deemed necessary.

## Team code repositories

### Similar projects:
* [Librasearch](https://github.com/librasearch) is an open-source, transparent, and reliable explorer and metrics platform for Facebook's Libra currency under development by Anish. It is developed with a Preact front-end, WebSocket communication layer, and Express + FeathersJS (NodeJS) back-end.

### Related projects:
* [SignRecord](https://github.com/Anish-Agnihotri/SignRecord) and [Encrypton](https://github.com/Anish-Agnihotri/Encrypton) are publicly verifiable document record and credentialization platforms backed by IPFS.
* [UEscrow](https://github.com/Anish-Agnihotri/UEscrow) is an escrow platform built for the UCash ERC-20 token.

# Additional Information

Although this RFP requested for completion by a team, I am applying as an individual developer. I would be more than happy to hop onto a call and discuss my thought process to justify taking on a project of this size as an individual developer, and why I believe it would provide more transperancy and insight.
