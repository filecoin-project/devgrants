To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `NFT Gallery`

**Name of Project:** `NFT Gallery`

**Proposal Category:** `app-dev`

**Proposer:** `froid1911`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `YES`

# Project Description

We recognized that there is right now no good solution to organize self soverign your NFTs in Galleries and present them anywhere, e.g. at home, at hotels, at offices etc.. 

This project aims to bring **identity focussed NFTs to every screens**. In order to reach this goal we adopt **ceramic.network** and **idx.xyz** for Identities and **ipfs** and **filecoin** as communication and data layer for the galleries. Additionally it supports almost every NFT through the **did:NFT method**, which was proposed by Joel some month ago.

The user can login/register with **idx.xyz**. If he has no Profile, he can create one. Otherwise he will get redirected to the Manager. The Manager allows to CRUD Galleries and organize NFTs into those Galleries with Drag&Drop. The App and the galleries will be managed on IPFS and the user has the possibility to also store the gallery on filecoin for longterm.

## Value 

With our solution we provide a DApp which tackles a NFT Owner in Meatspace and provide a nice solution entirely decentralized.
**filecoin** could leverage through **idx.xyz** and **ceramic.network**, because they already both: a large user base from 3box and a lot of app integrations, e.g. zerion, gitcoin and co.

Right now we can not identify any risks.

## Deliverables

The final product will be a fully functional web application hosted on IPFS, persisted on Filecoin 

## Development Roadmap

### 1. UI/UX Design and Implementation

Good UX/UI takes time. In order to avoid pitfalls and get realworld customer feedback. We create a design in figma in one day and ask friends in the nft space for feedback. We iterate in one week over and over and afterwards come up with a good design, which needs to be implemented as react app. For the implementation we expect that it will take three weeks in order to finish the common components: BaseLayout, LoginComponent, ProfileComponent, ProfileEditComponent, OwnedNFTsComponent, CreateGalleryComponent, GalleryListComponent, GalleryEditComponent and GalleryShowComponent.

When the App is started it loads the BaseLayout. 

In case the user is already logged in it shows the Profile in the Header Menu of the BaseLayout and in the Body the OwnedNFTsComponent and the GalleryListComponent. Through Drag and Drop it should be possible to put NFTs in a gallery. Additionally a settings Buttons allows to edit specific settings of the gallery in the GalleryEditComponent. Each Gallery has also a directlink to a presentation mode GalleryShowComponent where the gallery is presented with the NFTs and the settings from the GalleryEditComponent.

In case the user is not logged in the BaseLayout shows a Login Button in the Body.

Software:
   - Setup Git Repository
   - Building ReactApp based on Bootstrap and all required components
   - Fetching owned NFTs through OpenSea API

People: Frank (Design) + Rene (Dev)
Timeline: 1 month, July 1st - August 1st
Funding: USD 10000

### 2. Ceramic Network Integration

With this milestone we delivers the ability to login into the app (LoginComponent) with Metamask. After the login the app loads the Profile of this user in the ProfileComponent. In case he has no existung Profile ProfileEditComponent shows up, which allows to create and persist a Profile in ceramic on **ipfs**.

We rely on the SDKs of IDX and Ceramic and use the Web3 Provider of Metamask. This allows us to fetch the Ethereum Address of the user, which is required for the OwnedNFTsComponent in order to fetch user owned NFTs.

Software:
   - IDX/ Ceramic Login Functionality with Metamask
   - Extended NFT Gallery Schema, based on Ceramic Gallery Schema
   - Storage of Galleries in Ceramic Network with Extended NFT Gallery Schema

Dev Team (Pair): Frank + Rene
Timeline: 2 weeks, August 2nd - August 14th
Funding:  USD 5000

### 3. Filecoin Integration 

In order to provide long term storage for galleries we need to provide a feature which allow the user to persist entire galleries on Filecoin. 

Right now we just need an easy working solution. Therefore we setup an Powergate and provide a service where new Users of the NFT Galleries get an account with some Fil in order to  Store their galleries.

Software:
   - Setup Powergate
   - Small Microservice to create and fund Powergate Users with some FIL
   - Implement Filecoin Storage for NFT Galleries

Dev Team (Pair): Frank + Rene
Timeline: 2 weeks, August 14th - August 31th
Funding:  USD 5000

## Total Budget Requested

We request USD 20000.

## Maintenance and Upgrade Plans

After we launch, we will make a lot of changes based on users feedback, Ceramic network as well as Filecoin network upgrades. There will never be a final version, we will be do continuously updates to this product.

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
