To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `NFT Gallery`

**Name of Project:** `NFT Gallery`

**Proposal Category:** `app-dev`

**Proposer:** `froid1911`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `YES`

# Project Description

We recognized that there is right now no good solution to organize self soverign your NFTs in Galleries and present them to others or yourself anywhere you are, e.g. at home, at hotels, at offices etc.. 

This project aims to bring **identity related NFTs to your screens**. In order to reach this goal we adopt the open social protocol **idx.xyz** as decentralized identity solution which relies on the general open information platform **ceramic.network** which again relies on **ipfs** as Hot Storage.

The User can login with its **idx.xyz** Profile and manage their galleries with NFTs. The Galleries are stored on IPFS as Hotwallet and can be stored on **Filecoin** as Cold Storage through Textile Powergate and a small Microservice.

## Value 

With our solution we provide a DApp which tackles a NFT Owner in Meatspace and provide a nice solution entirely decentralized.
**filecoin** could leverage through **idx.xyz** and **ceramic.network**, because they already both: a large user base from 3box and a lot of app integrations, e.g. zerion, gitcoin and co.

Right now we can not identify any product oriented risks, except NFTs identifies itself as a totally scam.

## Deliverables

The final product will be a fully functional web application hosted on IPFS.
Cold Storage will be provided through a Serverless function and a Textile Powergate.

## Development Roadmap

### 1. UI/UX Design and Implementation

Good UX/UI takes time. In order to avoid pitfalls and get realworld customer feedback. We create a design in figma in one day and ask friends in the nft space for feedback. We iterate in one week over and over and afterwards come up with a good design, which needs to be implemented as react app. For the implementation we expect that it will take three weeks in order to finish the common components: BaseLayout, LoginComponent, ProfileComponent, ProfileEditComponent, OwnedNFTsComponent, CreateGalleryComponent, GalleryListComponent, GalleryEditComponent and GalleryShowComponent.

When the App is started it loads the BaseLayout. 

In case the user is already logged in it shows the Profile in the Header Menu of the BaseLayout and in the Body the OwnedNFTsComponent and the GalleryListComponent. Through Drag and Drop it should be possible to put NFTs in a gallery. Additionally a settings Buttons allows to edit specific settings of the gallery in the GalleryEditComponent. Each Gallery has also a directlink to a presentation mode GalleryShowComponent where the gallery is presented with the NFTs and the settings from the GalleryEditComponent, e.g. a specific slide show or specific stop intervals.

In case the user is not logged in, the BaseLayout shows a Login Button in the Body instead of owned NFTs and identity related galleries.
The functionality for the login button will be implemented in milestone 2

Stories:
   - Setup Git Repository with ReactApp and Bootstrap
   - Implement evaluated design in proposed components
   - Display owned NFTs of specific ETH Address

People: Frank (Design) + Rene (Dev)
Timeline: 1 month, July 1st - August 1st
Funding: USD 10000

### 2. Ceramic Network Integration

With this milestone we delivers the ability to log into the app through the LoginComponent with executes the login method from the IDX Framework and use Metamask as Signing Provider. After the login the app loads the Basic Profile from IDX. In case the user has no existung Profile, the ProfileEditComponent shows up as Modal allows to create and persist a Profile on IPFS through IDX and ceramic.

We rely on the SDKs of IDX, Ceramic,IPFS and the Metamask Web3 Provider in order to archieve our Web3 DID Login. This allows us to fetch the Ethereum Address of the user. Thereby we can load the user owned NFTs from the OpenSea API.

If a gallery is created or edited the gallery will be stored on IPFS through IDX and Ceramic. 

Stories:
   - Provide IDXLogin Functionality with Metamask, Ceramic and IPFS
   - Provide Extended NFT Gallery Schema for Ceramic Network
   - Store Galleries after creation or edit in IPFS 

Dev Team (Pair): Frank + Rene
Timeline: 2 weeks, August 2nd - August 14th
Funding:  USD 5000

### 3. Filecoin Integration 

In order to provide long term storage or cold storage for galleries we need to provide a feature which allows the user to persist entire galleries on Filecoin. Right now almost every web3 user has a Metamask wallet, but not every user has FIL Wallet in the browser. Therefore we provide a Textile Powergate which creates for every NFT User an Account and provide some FIL to persist Galleries long term.

Later on we want a more decentralized version of that where ideally the user comes with own FIL Provider.

The feature is for the user optional and is easy to trigger through a checkbox or a button.

Stories:
   - Setup Powergate
   - Provide Serverless function to create and fund NFT Gallery Users with FIL
   - Implement Cold Storage Feature for NFT Galleries in React App

Dev Team (Pair): Frank (Powergate, Frontend) + Rene (Backend)
Timeline: 2 weeks, August 14th - August 31th
Funding:  USD 10000

## Total Budget Requested

We request USD 25000.

## Maintenance and Upgrade Plans

After we launch, we will go on and build a product. Because of protocol changes we will probably never have a final version.
Therefore at some time we'll plan an exit to community.

# Team

## Contact Info
frank.pfeift@protonmail.com

## Team Members

- [Frank](https://github.com/froid1911): Tech lead, Filecoin & Ceramic expert
- [Ree](https://github.com/froid1911): Frontend Developer

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/fpolster/

## Team Website

No Team Website right now. Its our first Grant.

## Relevant Experience

We both have a Master of Science in Computer Engineering.
We work since 2017/2019 for MaibornWolff as Software Engineers in the Web3 department. 
We also attended on multiple Hackathons and Conferences e.g. annual EF DevCon, ETHCC, ETHDenver, ETHBerlin and ETHBerlinZwei

Frank has also some relationships to the Ceramic Network Team and does Filecoin Mining.

## Team code repositories

- https://github.com/froid1911
- https://github.com/ant1pattern
- https://github.com/maibornwolff


# Additional Information

Made with <3

# Some References
- https://idx.xyz/
- https://ceramic.network
- https://docs.textile.io/powergate/
- https://www.w3.org/TR/did-core/ 
- https://github.com/ceramicnetwork/nft-did-resolver 
- https://docs.opensea.io/reference#getting-assets 
