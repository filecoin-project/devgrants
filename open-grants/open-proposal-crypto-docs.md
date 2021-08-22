To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: CryptoDocs - a private Google Docs alternative backed by IPFS and Ethereum

**Name of Project: CryptoDocs**

**Proposal Category:** `app-dev`

**Proposer:** `polluterofminds` & `zherring`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** 

Yes

# Project Description

There are many IPFS-based text editors that have been developed. None, however, have matured or been built out enough to be considered production-worthy applications. We will build a production-ready and business-capable alternative to Google Docs that leverages IPFS and Ethereum. 

CryptoDocs will be a collaborative document editing application that supports the following: 

* Document creation and editing
* Team-based access with smart contract controls
* Real-time collaboration
* Encryption
* Document sharing
* Commenting
* IPFS storage
* Filecoin archival

There is a wide market of people and organizations that need a privacy-preserving and decentralized alternative to Google Docs. While there may be an eventual business model for such a product, we want to build this as a public good to start. It will be free and open source. 

CryptoDocs will leverage Ethereum-based wallet authentication. Using the same wallet-based authentication, it will enable client-side encryption of documents. Those documents will be stored on IPFS (likely through a pinning service) with an optional connection to a locally running IPFS node. 

Documents can be optionally backed up to Filecoin for long-term storage and redundancy. 

Real-time collaboration should be enabled with as little server involvement as possible. This means we will need to make use of libp2p or create a simple deployable Websockets or webRTC server. 
Team-based access will be controlled by a smart contract (likely on the Polygon network). Access can be granted and revoked by sending transactions to said contract. 

The document editor will be a rich text editor built in the vane of something like Dropbox Paper or Medium. It will not be a replacement for Microsoft Word and it will not have nearly as many capabilities as Google Docs. This is by design. In our experience, most people use less than 10% of the features available in Google Docs. 


## Value

IPFS and Filecoin have many uses, but the most prominent current use is NFTs. We would like to show the world that both protocols coupled with Ethereum/Polygon can create a replacement system to a Web2 behemoth. 

If we get this right, we will be providing a service desperately needed by activists, journalists, individuals, and businesses. The right to privacy and encryption is fundamental. However, building proper tooling around this right has been less than profitable. That is why we need to build this as a public good first and consider revenue strategies as a potential by-product. 

Getting this wrong could mean would mean yet another IPFS and Filecoin based text editor on the mountain of rarely used services that exist today.

The risks that make executing this project difficult include a range of things, including: 

* Understanding libp2p better
* Transaction costs (even for Polygon)
* Simplifying the process of making storage deals on Filecoin
* Pinning files (we cannot take on the cost of a pinning service, so we either need each user/team to do this or consider some alternative)


## Deliverables

* WYSIWYG Docs Editor dApp With
* Customer interviews
* CRUD (Create, Read, Update, Delete) of Documents
* Share & Collaboration Between Individuals
* Sharing per Wallet via MetaMask
* Crypto & DAO Native Feature Set - these will be ideated & prioritized based on user and organization interviews across a wide array of user types
* Privacy and Security Feature Set - tbd Based on Interviews


## Development Roadmap

### Milestone 1

**Deliverables**
* 8 Interviews Done with Prospective Customers/Users 
* Initial Feature Set + Product Requirements Doc Finalized
* Landing page built
* Authentication with Metamask complete

**Requested Budget**
$5000

**Timeline**
1 month 

### Milestone 2

**Deliverables** 
* V1 of Product along core user flows design (Wireframes) 
* User testing (5-8 usability tests conducted)
* Clickable prototype for wireframes
* Basic access control smart contract written

**Requested Budget**
$5000

**Timeline** 
1 month

### Milestone 3 

**Deliverables** 
* V1 of Brand 
* V2 of Core User Flows (Polished Designs) 
* V1 of Remaining Designs (Wireframes)
* WYSIWYG editor completed
* Basic IPFS CRUD functionality complete

**Requested Budget** 
$5000

**Timeline** 
1 month

### Milestone 4 

**Deliverables**
* V1 of Doc Site & Beta Sign-Up
* V.01 Alpha Release (Private) 
* Single-player alpha support (private alpha, no team access yet) 
* Real-time collaboration 
* Filecoin backups

**Requested Budget** 
$5000

**Timeline** 
1 month

### Milestone 5

**Deliverables**

* V.02 Beta Release 
* Beta Launch (Limited)
* Access control contract complete
* Team access complete
* Access logs written to Filecoin cold storage

**Requested Budget** 
$5000

**Timeline** 
1 month

### Milestone 6

**Deliverables**

* v1 General Release
* IPFS storage complete
* Filecoin back retrieval support
* Mainnent access control contract deployed

## Total Budget Requested

$30,000

See breakdown above.

## Maintenance and Upgrade Plans

We will provide reasonable maintenance to the open-source product. We will also likely (based on reception) continue building functionality to find sustainability for the project. 

# Team

## Team Members

* Justin Hunter
* Zach Herring


## Team Member LinkedIn Profiles

* https://www.linkedin.com/in/justin-hunter-b30a1b80/
* https://www.linkedin.com/in/zherring/ 

## Team Website

TBD (working on final name before purchasing domain)

## Relevant Experience

[Justin Hunter](https://polluterofminds.com) has founded two prior companies in the blockchain space—Graphite and SimpleID. In both cases, he was exposed to the phenomenal community that builds around blockchain projects. He delivered successful, heavily used applications. He is currently the head of product at Pinata on their IPFS solution. Justin has also successfully completed a previous grant for the Filecoin Foundation for the first Lotus desktop app client, Nelumbo. 

Justin is a mentor for Tachyon/Filecoin Accelerator, Base Camp accelerator, and a dozen or so individual projects. 

[Zach Herring](http://zachherring.com) has been a product designer for 15 years. In Web2, he’s collaborating with product leadership to design the generation of products for Fortune 100 companies. In Web3, Zach led design and research projects for ConsenSys’s portfolio of companies including Gitcoin, uPort, 3Box, Atomic Loans, Travel Blocks, ConsenSys Space, and many others. He co-started the ConsenSys Relays Hackathon and Grants program (2019-2020). He is currently freelancing, launching Quadratic Funding platforms FundOSS and DowntownStimulus, and he is the fractional COO/CPO at Maiden Global.

Zach is an Advisor for Atomic Finance, Maiden Labs, Tachyon, and Kernel, as well as a member of the MetaCartel, RaidGuild, and Deep Work DAOs.


## Team code repositories

* https://github.com/polluterofminds
* https://github.com/graphite-docs 
* https://github.com/zherring 

# Additional Information

Justin has the direct experience to build this product. In building Graphite, he came very close to this exact solution, but he came at it from the SaaS angle first. This hampered its development and progress. That said, Graphite scaled to over 50,000 users before it was ultimately shut down. Justin can leverage that experience in this project.