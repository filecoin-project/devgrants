# Open Grant Proposal: `Meme of the Day`

**Name of Project:** Meme of the Day

**Proposal Category:** `app-dev`

**Proposer:** `BTCAlchemist`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Memes are a unique form of artistic communication that helps people experience ideas and feelings that they would not have otherwise known. Memes accumulate layers and layers of meaning and facilitate deep communication between members of a subculture. Memes and meme slogans are especially dear to the Web3 community (ex. Hodl, Funds are Safu, guy holding “Buy Bitcoin” sign behind Federal Reserve Chair Janet Yellen) and hold great promise to promote new ideas and to expand adoption of Web3 technology.

The problem is that no platform exists to serve as a hub for memes that showcases the power of Filecoin and Web3 technology. Meme of the Day will provide this, enabling users to upload memes as NFTs to a blockchain and to Filecoin, vote on their favorite memes, buy and sell memes, and uniquely share sales profits as a result of their interaction on the platform. Soon, this could all be available on one application that offers a social and gamified experience with real rewards.

## Value

The benefits to getting this right using Filecoin are increased visibility  of Filecoin's  utility for long-term storage and creating an ecosystem for NFT memes in a borderless, decentralized network that is accessible around the world.

If we don’t get this right, the adoption of Filecoin and Web3 technology will be much slower. Memes are fun and catchy ways to get people to pay attention to the utility of this technology. They are also easy to share and quick to view. Filecoin and Web3 offer the unique possibility for users to mint a meme as a unique NFT as part of a decentralized social network with real incentives. Therefore, memes and Meme of the Day offer a unique entryway into Web3 knowledge to both beginners and advanced users alike.

Executing on this project may be difficult due to the risks of unpredictable market adoption, unknown performance of Filecoin mainnet after its launch, and unknown Filecoin mainnet costs for storing and retrieving files such as memes.

## Deliverables

-   Functioning website landing page, meme upload page, dynamic home page, and My Memes page.
    
-   From meme upload page, ability to mint NFTs stored on Matic testnet and store associated meme images on Filecoin testnet.
    
-   Smart contract for NFT generation, use with Textile database, and upload to Filecoin.
    
-   Smart contract that enables users to pay a fee to upvote meme NFTs.
    
-   Smart contract that enables users to buy/sale meme NFTs through the dApp and to share profit with upvoters.
    
-   User can confirm successful NFT minting and Filecoin image upload, via My Memes page.
    
-   Integration of Textile to store memes on Filecoin and IPFS and to store mutable data.
    
-   Integration of Fleek for CICD, hosting, and pinning memes for faster distribution of data on IPFS network.
    
-   Build and implement user ID system and voting system.
    
-   Matic PoS bridge functionality so NFTs generated and residing on Matic network will become NFTs residing on Ethereum.
    
-   Create economic model for meme sale profit-sharing.
    
-   Create community mechanism to remove inappropriate memes.
    
-   Create an ETH-MATIC token exchange feature to facilitate easy transactions on the dApp.
 
-   Frontend updates to incorporate above deliverables.
    
Detailed functionality is in the development roadmap below.

## Development Roadmap

**Milestone 1**

People: Anmol Agarwala (backend development), Matthew Fiorello (project management, research, testing), Matt Prime (backend development), Shadab Khan (frontend development)

Timeframe: By October 30, 2020 (estimate 112 hours)

Funding requested: 8,400 DAI

Functionality:

1. Users arrive on the landing page showing a few of the top memes. DApp uses the local browser storage to store ephemeral identity for now.
	 - If already present in local storage, use the same to fetch the memes from Textile.
	 - If not, create key pair, store in local storage, and use that to fetch the token to interact with Textile.

2.  Fetch top-voted memes from Textile Threads/Buckets to display on landing page.
	- Use one collection and one bucket for now (scaling to come later).
	- End users use our single Textile User API key.

3.  Click upload button.
	- Connect Metamask to dApp, and connect to the Matic Mumbai testnet from the frontend.
	- Once user selects and clicks upload of meme, interact with smart contract, show cost, and mint NFT.
	- With image in browser cache, instruct Textile to archive this image to Filecoin testnet, push image file to Textile bucket (IPFS storage cache). When Filecoin mainnet launches, we would update and determine who would pay for the deals made.
	- Filecoin testnet sends file hash to Textile that sends it to dApp frontend, smart contract is triggered, generates NFT using ERC-721 standard, and user must accept fee to pay for this on Matic testnet.
	- Once Matic testnet confirms it, then tokenID is known. Smart contract returns tokenID to the frontend to use with the Textile database and push metadata for each meme onto Textile database (ex. IPFS hash, owner votes).
	- Display link to “View Your Memes” page.

4.  Show “View Your Memes” page -- similar to landing page but filters for memes associated with that user.
	- For each user meme, show link to Matic transaction details and output the uploaded meme image.

**Milestone 2**

People: Anmol Agarwala (backend development), Matthew Fiorello (project management, research, testing), Matt Prime (backend development), Shadab Khan (frontend development)

Timeframe: By December 15, 2020 (estimate 112 hours)

Funding requested: 8,400 DAI

Functionality:

1.  Build a user ID system
	 - Research to find appropriate system to implement a smooth user identification, similar to Web2 experience but also secure.
	Ex. 3Box.io decentralized identities
	Test and solicit feedback on user experience
	Solicit feedback from Textile team
	- Integrate user ID with Metamask or another wallet that supports ERC-721 tokens, which tracks the user’s owned memes, upvotes, wallet addresses, and other mutable data.

2.  Implement voting system
	- Build a new smart contract that enables users to pay a fee to upvote meme NFTs.
	- Upvoted meme NFTs receive a higher ranking on the site.
	- User votes are stored in their user ID, along with their wallet address, which enables them to receive profit share if upvoted memes are sold.
	- Specific costs will be addressed in milestone 3.

3.  Meme sale
	- Create a new smart contract that enables users to buy meme NFTs through the dApp and share profits with upvoters.
	- Ownership of a meme would be transferred after the buyer pays the current owner of meme. Current owner of the meme will define the value of the meme prior to this action through our frontend. The properties of NFTs are defined in EIP-721, and the standard requires the following methods: balanceOf(owner), ownerOf(tokenId), transferFrom(from, to, tokenId) which can be used for making a transfer in our own smart contract. Hash of the meme defining picture of memes stored on Filecoin and tokenID of NFT will not change, only the owner of tokenID will change from previous user to new user.
	- Research existing NFT sale smart contract code (ex. OpenSea).
4.  Update frontend
	- Enable user to make a purchase offer for a meme NFT.
	- Update meme NFT profiles to include votes, last sale price, and last sale date.
	- Integrate voting system and meme sale into displayed memes on all web pages.

**Milestone 3**

People: Anmol Agarwala (backend development), Matthew Fiorello (project management, research, testing), Matt Prime (backend development), Shadab Khan (frontend development)

Timeframe: By December 31, 2020 (estimate 80 hours)

Funding requested: 6,000 DAI

Functionality:

1.  Create an easy way for users to exchange ETH for MATIC tokens to facilitate easy transactions on the dApp.
    
2.  Build Matic PoS bridge functionality so NFTs generated and residing on Matic network will become NFTs residing on Ethereum.
    
3.  Create economic model for profit-sharing, including the cost for votes, commission paid to voters, and commission paid to dApp. If needed, seek input from economic consultant.
    
4.  Create community mechanism to remove inappropriate memes. We would need a decentralized way to remove inappropriate content from the platform.
	- Economic incentives to the community regulating the content might also increase participation. For example, a minted NFT marked as banned from the community may result in that NFT being destroyed and its value being distributed to the users. Users could mark inappropriate memes with a ban indicator from the app frontend.
	- We need to research this, solicit feedback from Web3 professionals, and determine the appropriate mechanism.
5.  Frontend development
	- Incorporate ETH-MATIC token exchange, Matic-Ethereum bridge, and meme removal mechanism.
	- Build home page with dynamic content.
	- Make design user-friendly and easy to navigate.
 
## Total Budget Requested

|  Milestone | Work Time | Duration | Budget |
|--|--|--|--|
| Milestone 1 | 112 hours | 4 weeks | 8,400 DAI |
| Milestone 2 | 112 hours | 4 weeks | 8,400 DAI |
| Milestone 3 | 80 hours | 4 weeks | 6,000 DAI |
| **Total** | **304 hours** | **12 weeks** | **22,800 DAI** |


## Maintenance and Upgrade Plans

Additional maintenance and upgrade plans include the following:

-   After Filecoin mainnet launches, incorporate new code, storage costs, and storage terms
    
-   Add functionality for users to comment and add their favorite memes, associated with their user ID and stored in Textile database
    
-   Connect to Matic mainnet and build PoS bridge with checkpoints between Matic network and Ethereum mainnet
    
-   Add meme categories
    
-   Increase dapp capacity for scaling to thousands of users

# Team

## Team Members

- Matjaz Primec    
- Anmol Agarwala
- Matthew Fiorello
- Shadab Khan

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/matjaz-primec-bb4ba53/
- https://www.linkedin.com/in/sylar217/
- https://www.linkedin.com/in/mfiorello/
- https://linkedin.com/in/shadab2005/


## Team Website

Team website: Planning to deploy it via Fleek soon

Figma design prototype: https://www.figma.com/proto/JvdqkUkO0IbS3O4GCfJYj5/Meme-of-the-Day-Home?node-id=9%3A99&scaling=min-zoom

## Relevant Experience

Our team has relevant skills, experience, and passion to advance the Filecoin and Web3 ecosystems.

Matjaz Primec has a background in ecommerce development and now for some years also in development on blockchain technologies. He has strong experience with building large corporate systems in Web2-era technologies, and now he uses them in development of Web3-era apps. He is one of the winners of the Fantom Foundation software developer contest with creating a proof of a concept for “Meme of the Day” fun social app. Proof of concept allowed users to create a meme on the blockchain with the meme image stored on IPFS. Matjaz is more backend Solidity smart contract development-oriented but also able to do simple frontend React interfaces. He has experience in DeFi through interaction with Aave, KyberSwap, and similar smart contracts of other protocols; swapping of ERC-20 tokens; adding liquidity; and using other functions (flash loans) on different liquidity pools through Web3.js.

Anmol Agarwala is a backend C++ developer with a full-time job at Microsoft and a Web3 enthusiast. He has been participating in hackathons, including HackFS, APOLLO, EthOnline, and many more to come. He has a particular interest in decentralized identity and following Microsoft Project ION and Ceramic Network -- Anmol has done small contributions to both the projects. HackFS was a very good learning experience around the Web3 stack, and we are using some of them in our Meme of the Day project.

Matthew Fiorello has a background in business consulting, corporate finance, cryptocurrency, and blockchain technology. He runs a crypto estate planning consultancy to help people safeguard their crypto assets in this life and after death. Blockchain work includes building a data model for a United Nations blockchain project, winning the Fantom Foundation software developer contest, and advising an Ethereum developer training company. Matthew also has diverse experience using, tracking, and organizing crypto assets; published articles on DeFi; and earned blockchain course certifications. Skills he offers to the project include project management, business development, marketing, finance, research, and testing.

Shadab Khan is a frontend engineer currently working with an ecommerce startup in India, https://bulbul.tv. He is a Google certified Mobile Web Specialist (https://www.credential.net/31c023a0-7df2-47e0-97c0-fb3db6bd9c45). Shadab is proficient in React and GraphQL. He has been working with startups for most of his career and really enjoys working in a fast-paced environment. He is quickly learning and implementing experience with the Web3 world.

## Team code repositories

Predecessor to current vision; user uploads a meme image that is saved in IPFS, which creates a hash that is stored on an Ethereum testnet: [https://github.com/BTCAlchemist/meme-of-the-day-dApp-eth/](https://github.com/BTCAlchemist/meme-of-the-day-dApp-eth/)

[https://github.com/matprime/ERC-721_NFT_creation_demo](https://github.com/matprime/ERC-721_NFT_creation_demo)

[https://github.com/matprime/ez-flashloan](https://github.com/matprime/ez-flashloan)

[https://github.com/cod1ng-earth/filDID](https://github.com/cod1ng-earth/filDID)

[https://github.com/ceramicnetwork/CIP/issues/60](https://github.com/ceramicnetwork/CIP/issues/60)

# Additional Information

Thank you for considering our application! We welcome your comments and questions.
