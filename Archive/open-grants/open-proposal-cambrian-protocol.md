To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: Cambrian Protocol

**Name of Project:** Cambrian Protocol

**Proposal Category:** app-dev

**Proposer:** NicWickman

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

The $40T/yr Human Capital Management market will move on-chain. We refer to this as the future-of-work ecosystem. We are building a dApp designed to enable protocol and DAO grants programs to move on-chain. This solution will combine the ERC-1155 Conditional Token Framework with solutions like Filecoin. The roadmap for this is to move “business” on-chain with a halcyon future that would see a company like Coca Cola fund a smart contract to get water to a new bottling plant. There is a small but passionate ecosystem of projects working in and around DAO tooling, governance, and contracting. We are seeking to develop in a community first, open-source manner that is additive to the solutions around us. We believe we have a unique and important vision – that of accountable centralization or the decentralization of middle management. 

We are starting with low hanging fruits. Bringing smart contracts to the grants process used by Filecoin and other protocols. The Conditional Token Framework is the right solution to enable Digital Organizations to fairly connect human judgment and on-chain components together for doing business, but this solution needs to be decentralized from the ground up. We believe this approach is aligned with Filecoin and we would be thrilled to have the opportunity to build together.

## Value

**What are the benefits to getting this right?**
Decentralization struggles to compete with hierarchical centralized organizations’ abilities to deploy resources. For decentralized businesses to win they must be permissionless, trustless, and programmable. But they also must find a way to enable human coordination. The key to this is to allow for new forms of accountable centralization to serve DAOs. There are several benefits to getting this right. One is the opportunity to decrease the impact of externalities. If the condition for payment is tied to the success of the DAO, centralized organizations will need to evolve how they approach opportunities. Another will be increased meritocracy and open access which will lead to better outcomes with less rent. Another will be less competition and more collaboration. And lastly, optimal inter-organizational sharing of data (including massive Filecoin implementations) and thus better costs and more gains from AI. 

**What are the risks if you don't get it right?**
The risks are we continue in a world without decentralization. Human coordination is the super-power of our species. If decentralized organizations do not absorb centralization and evolve new forms of centralization, decentralization will not be competitive. Increased data silos, increased costs and reduced gains from machine learning and AI. 

**What are the risks that will make executing on this project difficult?**
This project requires building on Ethereum as well as other web 3 solutions which creates platform risk. The long-term goals of the project could run up against regulatory risks related to token use.


## Deliverables

Cambrian Protocol employs the conditional tokens framework (CTF) to allow complex, secure interactions between participants. CTF is an ERC1155-compliant, powerful event-based digital asset class developed by Gnosis. Through enabling conditional logic ("If this, then that") for digital assets, fungible conditional tokens can be minted with value contingent on arbitrarily complex logic derived from real-world and on-chain information. Originally conceived to power prediction markets and futarchic governance, the CTF allows us to conditionalize remuneration of service providers and thus hold them accountable to their benefactors.

Conditional tokens (CTs) are minted when a proposal meets its funding goal to represent the escrowed funds. These CTs are distributed to participants according to the Proposal's Solution and gain their value at its conclusion, after which they can be redeemed for the escrowed collateral. A Solution is concluded when all of its component "Solver" smart contracts have reported outcomes, and these outcomes have been confirmed without dispute or settled after dispute.

Our MVP will be a set of re-useable smart contracts that Filecoin will be able to leverage to coordinate the funding of grants. Following the MVP and this grant, we will be extending the tech to support a wider range of use cases.

## Filecoin / IPFS

An immutable data layer is a critical piece of this infrastructure, now and in the future. Our MVP intends to use IPFS in 2 ways:
1. Committing verbose descriptions for Proposals and their associated Conditions to IPFS.
2. Committing atomic elements of front-end code used to interact with our smart contracts to IPFS.

Regarding point 1, it is important that the terms of a Proposal being funded are known to be the same for all participants. By utilizing IPFS, we can ensure immutability and consistency. We can store the IPFS hash of the details of a Proposal on-chain to inexorably link a configuration of smart contract code to human-readable agreements.

Regarding point 2, we are developing various "Solvers", user-interfaced smart contracts with unique functions for aiding the execution of Proposals. The UI of a Solver must be known and immutable to ensure predictable behaviour. IPFS is the best way to do this in a decentralized fashion. By loading front-end code from IPFS, or checking it against IPFS, users can be confident that what worked yesterday will work the same today as they configure a Proposal in a "no-code" environment.

In our roadmap beyond the scope of this grant, the development of Solvers will be open source and will include additional functionality such as reputation tracking and fraud detection. These functions too will depend on a reliable data layer, and we believe Filecoin is the best solution in the ecosystem to support this. Further, as the development of these smart contracts becomes decentralized, it is crucial in our view that their interfaces are immutably decentralized as well.

To summarize, we believe that IPFS/Filecoin is not only useful for the exchange of large corpuses of text, but critical for the functionality of data-dependant smart contracts and the secure decentralization of their associated UIs. We intend to leverage this in our modular architecture for conditional transactions.



## Development Roadmap

Our roadmap identifies four major milestones:
 
  1. Minimum viable dev-friendly stage - Basic "Solver" smart contract functionality for proposing and funding work on a conditional lump-sum basis.
  2. Minimum viable human-friendly stage - Basic interface for creating and funding proposals, reporting conditions and redeeming funding
  3. Improved utility stage - Supporting contracts to provide functionality for recurring funding, redeemable funding over multiple milestones, and more sophisticated arbitration. Corresponding interface development.
  4. DAO-friendly stage - Developing more robust, on-chain methods for negotiating Proposals to replace the Minimally Viable "propose-only" system.

### Minimum Viable "Dev-Friendly" Stage ###
This milestone represents a functional proof-of-concept which may be used to allocate lump-sum funding to escrow which may be redeemed when conditions are met.
 
  - An entity can interact with a smart contract to create a "Proposal" with a funding goal. This Proposal identifies:
  - An entity to receive funding.
  - The ERC-20 token used as funding. 
  - An amount to be funded.
  - The conditions which must be met for the funding to be redeemed.
  - A "Keeper" address responsible for reporting on the conditions.
  - An "Arbiter" address responsible for ruling over a dispute.
  - A "Solver" contract which manages the scheme when the funding goal is achieved.
  - The configuration of the Solver contract instance for the Proposal.

  This stage includes one minimally viable Solver contract. This contract:
  - Interacts with a Conditional Tokens contract to generate fungible conditional tokens (CTs) redeemable for the project funding, contingent on the corresponding outcomes of the specified conditions.
  - Distributes CTs to the parties specified in the Proposal.
  - Provides a method for the Keeper to report on the results of conditions.
  - Provides a method for raising a dispute to arbitration before condition results are confirmed.
  - Provides a method for the Arbiter to modify the reported results of conditions.
 
**Buidlers:**  
Nic Wickman & Ryan Walker, both Solidity developers.
  
**Timeline:**  
October 1st 2021.
  
**Funding Breakdown:**  
$5000/mo developer pay, x2 developers, x2 months = $20,000  
$20,000 total.

### Minimum Viable "Human-Friendly" Stage ###
This milestone represents a functional and enjoyable user interface for non-developers to utilize the software developed in Stage 1. Development will run mostly concurrently with the latter half of Stage 1.  

**Buidlers:**  
Future Front-End Hire  
 
**Timeline:**  
October 15th 2021.  
  
**Funding Breakdown:**  
$5000/mo front-end developer pay for future hire  
$5,000 total  
  
### Improved Utility Stage ###
This milestone represents modular additions to Stage 1 and Stage 2, allowing greater utility than the minimally viable "lump-sum" payment scheme. Following this milestone, the interoperability of Solvers should be proven and entities procuring work can opt for more flexible schemes.
  
We intend to build:
  - An additional Solver contract to be used in conjunction with others, which adds a condition to release a proportion of funding over time.
  - A contract(s) to support a recurring funding scheme, such that subsequent Proposals are automatically funded and their solutions set in motion as previous milestones are met.   - This allows redemption of conditional tokens in stages.
  - Purpose-built contracts to serve as Arbiters and Keepers, allowing for consensus-based and hierarchal levels of executing Keeper and Arbiter functions.
  - New interfaces for non-developers to make use of this added functionality.

**Buidlers:**  
Nic Wickman, Ryan Walker, Future Front-End Hire  
 
**Timeline:**  
December 31st 2021  
 
**Funding Breakdown:**  
$5000/mo developer pay 3x, for 1.5 months = $22,500  
$22,500 total  

### DAO-Friendly Stage
This milestone represents making our technology more easily usable by decentralized organizations by improving the minimal Proposals process with revisionary functionality. While the minimum version permits all-or-nothing Proposals created by a single entity, the upgrades version will permit atomic changes to an existing Proposal. This should allow DAOs to better negotiate terms and incorporate the system into their regular operations.
 
This stage involves:
  - Upgrading the Proposal contract(s) with functionality to receive revisions to existing Proposals.
  - Upgrading the Proposal contract(s) to be extensible with DAO-specific methods for invoking their revisionary functions.

**Buidlers:**  
Nic Wickman, Ryan Walker, Future Front-End Hire  
   
**Timeline:**  
January 31st 2021  
 
**Funding breakdown:**  
$5000/mo developer pay 3x, for 1.5 months = $22,500  
Smart contract audits = $15,000  
$37,500 total  



## Total Budget Requested
$85,000  
At this stage, we believe smart contract audits are prudent given the resource-handling nature of the technology. If these are omitted from the calculations, our total funding requested is $70,000  
 
Smart contract development: $50,000  
Front-end development: $20,000  
Security auditing: $15,000  


## Maintenance and Upgrade Plans

We have a very extensive vision for Cambrian Protocol. We also are committed to working in an open-source manner that takes careful consideration of other future-of-work projects. We believe there will be opportunity for projects to merge and for an exit to community. The goal for this software is to power business going forward as part of the larger web 3 ecosystem. 

In the immediate future following the scope of this grant, we will be soliciting DAOs and protocols to understand their operational and resource allocation needs. Our development team will build new Solvers and other supporting functionality to meet these needs, making them accessible to the broader community as we go. 
Our long-term plan involves incentivizing the community to develop and curate Solvers through a staking scheme to distribute minimally extractive fees. We intend to ultimately exit to the community through the launch of a DAO when it appears continued support of the technology will be sustainable without centralized leadership.


# Team
We are a small three-person team that is working on adding additional team members by the fall. 

## Team Members

- Nic Wickman is a devout futurist hailing from the intersection of art and technology in VFX. His trajectory has seen him lead VFX teams on award-winning projects, develop VR for the real estate space, publish consumer apps, and design and deploy novel AI into production. More builder than speculator, he came to appreciate the potential of blockchain as the Ethereum ecosystem flourished. 

- Paul Malin is an entrepreneur with multiple exits under his belt. His career has focused on accounts, strategic alliances, sales and other business development efforts. He discovered Bitcoin at $70 and is dutifully obsessed with the potential of blockchain technology to create an internet of value. He spent his 20s in a rock band, holds an MBA from the University Toronto, and a BSc in Chemistry from the University of Alberta.

- Ryan Walker studied robotics and electrical engineering in college while maintaining a key interest in emerging technologies. He’s an industry professional of 10 years with a formidable side-project portfolio, including the blockchain-based MMO ecosystem “Worlds”, which allows digital assets to be transferred between several independently developed games. Outside of his collaboration with the Cambrian team, he develops for Oculus on cutting-edge Augmented Reality technologies.


## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/nicholaswickman/
- https://www.linkedin.com/in/pmalin/

## Team Website
https://cambrianprotocol.com

## Relevant Experience

Nick and Ryan bring strong and varied development chops to the team. Both are talented solidity engineers. Nick’s background is in VFX and AI engineering, and his blockchain work includes a fairness-centric “Mechanical Turk” implementation for crowdsourcing work on-chain. Ryan’s prior expertise is in firmware and open-source hardware, who’s blockchain portfolio includes “Worlds”, a protocol for managing assets in a massively decentralized MMO game. This team has a unique approach to the future of work – the decentralization of middle management that speaks to the vision of the team. It’s one thing to build the token platform to enable on-chain services transactions, it’s entirely another to rethink how business coordination can be optimized in response to blockchain technology. We’re very proud of where we’re starting.

As well, as the blockchain space evolves it increasingly needs to engage with the traditional corporate environment. It needs to engage with people. Not only does this team include outstanding development talent, it also includes a co-founder with extensive corporate development experience. The ability to onboard digital organizations is going to be essential to the success of Cambrian Protocol and to the growth of Filecoin. 


## Team code repositories
https://github.com/NicWickman
https://github.com/Machine-Hum 

# Additional Information

We are seeking grants from protocols we see as foundational to Web 3, but we are also in the process of raising a $500k seed round. In the interest of offering a variety of options to Filecoin, we would certainly welcome participation in our seed round. As well, we are open to issuing credits against future fees.
