To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Filecoin Twitter Thread Rollup backed by NFTs`

**Name of Project:** FilecoinRollup

**Proposal Category:** `app-dev`, `docs`

**Proposer:** `@jamesmorgan`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `Yes`

# Project Description

- Twitter thread rollup and timestamp bots are not a new thing, however what they currently dont do it utilise distributed,
 decentralised storage, such as the Filecoin network. and then allow the creator to turn them into a tradeable NFT 

- Existing bots/solution relay on centralised storage and are limited in the what can be done with the thread whats its snapshot'd.

- The creation of a NFT off the back of the timestamped, Filecoin stored rollup will enable bring two new things to the party:
    - Facilitating trading of the thread - popular, viral or controversial threads may gain in value 
    - Creating a source of revenue to maintain the tweeter bot and its Filecoin storage costs - we could possible charge $1-2 for creating the NFT as well as enabling treading on OpenSea with a secondary sales commission of 2% which will then go back into maintain the Filecoin storage
    - Popularising Filecoin in general on NFT platforms - often MFTs use IPFS but in theory should be migrating to a Filecoin solution with a proper incentivisation layer - this would be a good candidate to test this out and popularise its use

## Value

- What are the benefits to getting this right?

* An example of how to use Filecoin in an NFT (popular future usecase) and an open source Github demo project
* Promote the use of Filecoin in the twitter sphere in general
* Provide a simple and related tool which can be used by many and demonstrates Filecoin

- What are the risks if you don't get it right?

* There may be reputational risk for the project if it fails, rendering the twitter bot unloved or sidelined.  

- What are the risks that will make executing on this project difficult?

I believe the technologies is not the hard part at least for ourselves, we have good experience in IPFS, building webapps and NFTs however
there may be a problem in the incentivisation model in that supporting the file storage may become costly overtime. One option to avoid this is snapshot the
thread and store centrally, only pushing to filecoin when an NFT is created and the small fee is paid. 
 
Filecoin is still emerging and the APIs may change in the short/medium term - keeping up to date may become probalatic but i think its a fairly simply setup
so this shouldn't be seen a huge risk in my mind.

## Deliverables

The deliverable for the project will be as follows:

- Twitter bot - hosted on GCP/AWS (free tier most likely is suitable)

- Filecoin integration to capture the thread and store on Filecoin

- Simple one page web based UI to see rolled up threads and buy them as an NFT is possible
    - Hosted on a free service like Firebase
    - Create a simple DB for stored some metadata about the thread
    - Simple minting functionality to create the NFT with web3 integration
     
- NFT contract that allows user to mint and pay small nominal fee (this can easily by added to OpenSea for trading)
    - The NFT `tokenURI()` will utilise the Filecoin hosted image

## Development Roadmap

# Milestone 1

* Creation of a simple Twitter bot which can rollup and timestamp a twitter thread - 32 hours (approx. 4 days) and includes the following
    - Twitter API integration 
    - Data stored in cloud DB 
    - Bot hosted in a cloud environment and running - most likely Google Cloud Run - serverless/stateless Dockerised instances

* Simple UI to list out rolled up threads - 16 hours (approx. 2 days)
    - VueJS based
    - Hosted on either Cloud Run or Firebase
    - Eventually will have Filecoin and Web3 integration

# Milestone 2

* Creation of a basic NFT contract - 24 hours (approx. 3 days)
    - OpenZepplin based (ERC-721)
    - Full test coverage and open source
     
* Filecoin integration to push images to Filecoin and pay the associated Fees - 16 hours (approx. 2 days)
    - API push and pay fees 
    
* Simple UI to select the rolled up thread and mint a NFT - 24 hours (approx. 3 days)
    - Select the rolled up thread, mint the token - using the Filecoin hash to dedupe previous threads that may have already been minted
    - Web3 auth only - no username/password
    - Filecoin integration
    - web3 integration

## Total Budget Requested

* Total estimated time to complete this includes the use of two main resources, development time and design time.
* Total approx days for both of these are 14 days with a baseline of $400 a day to cover both dev and design resources 
* $5,600 in total 

## Maintenance and Upgrade Plans

Long term this can be a community driven initiative and in theory wont need huge amounts of support/upgrades. 

Once running it should in theory also provide enough fees to support the Filecoin storage.

If needed we at BlockRocket will patch and fix critical bugs. 

# Team

## Team Members

- https://github.com/jamesmorgan
- https://github.com/andygray
- https://github.com/vince0656

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/jamesemorgan/
- https://www.linkedin.com/in/andrewmgray/
- https://www.linkedin.com/in/vincentmda/

## Team Website

* https://blockrocket.tech/ - BlockRocket is a UK based web3 consulting and engineering firm

## Relevant Experience

We have built several web3 product for both retail and enterprise clients. 

We also have specific experience in building things on IPFS and Ethereum/web3 as well as building several NFTs over the last few years. 

## Team code repositories

* https://github.com/blockrockettech
* https://github.com/knownorigin/known-origin-web3-marketplace
