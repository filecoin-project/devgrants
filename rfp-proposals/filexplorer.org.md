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

Please describe in details what your final deliverable for this project will be.

## Development Roadmap

Please break up your development work into a clear set of milestones. You can use the milestones suggested in the RFP or create your own. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section).

For each milestone, please describe:

- The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the RFP scope.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates)

## Total Budget Requested

Sum up the total requested budget across all milestones, and include that figure here. Ensure that it does not exceed the total funding limit on the RFP.

## Maintenance and Upgrade Plans

Specify your team's long-term plans to maintain this software and upgrade it over time.

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

Uniquely, though, he brings past experience building block explorers of such a scale. He is currently working on a block explorer for Facebook's Libra currency (see: similar projects repository) which is user and developer friendly, streamlined, and easy to use. He would be more than happy to deploy a live testing environment and provide further insight if deemed necessary.

## Team code repositories

### Similar projects:
* [Librasearch](https://github.com/librasearch) is an open-source, transparent, and reliable explorer and metrics platform for Facebook's Libra currency under development by Anish. It is developed with a Preact front-end, WebSocket communication layer, and Express + FeathersJS (NodeJS) back-end.

### Related projects:
* [SignRecord](https://github.com/Anish-Agnihotri/SignRecord) and [Encrypton](https://github.com/Anish-Agnihotri/Encrypton) are publicly verifiable document record and credentialization platforms backed by IPFS.
* [UEscrow](https://github.com/Anish-Agnihotri/UEscrow) is an escrow platform built for the UCash ERC-20 token.

# Additional Information

Although this RFP requested for completion by a team, I am applying as an individual developer. I would be more than happy to hop onto a call and discuss my thought process to justify taking on a project of this size as an individual developer, and why I believe it would provide more transperancy and insight.
