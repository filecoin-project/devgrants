To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `NFT Gallery`

**Name of Project:** `NFT Gallery`

**Proposal Category:** `app-dev`

**Proposer:** `froid1911`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `YES`

# Project Description

We recognized that right now there is no proper solution to organize your NFTs in galleries and display them whereever you want - at least not in a self soverign way.
Consider checking into a hotel and your NFTs are already there or display specific NFT on your TV @ home, at your meeting room or somewhere else?

This project aims to bring **your NFTs next to you**. In order to reach this goal we adopt the identity protocol for open applications **idx.xyz** which relies on the general open information protocol **ceramic.network** which again relies on **ipfs** as hot storage and communication layer.

In our product the user can use its social login to enter our app, sort its NFTs in galleries and later display them in any screen with internet connection.

Right now  we want to use textile powergate as cold storage solution. Alternativly Filswan could be an option.
## Value 

With our solution we show how Web3 Dapps look and feel.
Additionally it brings the already 50.000 existing users vom IDX to Filecoin.

Right now we can not identify any product oriented risks, except NFTs identifies itself as a totally scam. (könnte die NFTs irgendwie manipuliert, kopiert oder verfälscht werden??!)

## Deliverables

The final product will be a fully functional web application hosted on IPFS.
Cold storage will be provided through a serverless function and a textile powergate.

## Development Roadmap

### 1. UI/UX Design and Implementation

Good UX/UI takes time. In order to avoid pitfalls and get realworld customer feedback, we create a design in one day and ask friends in the nft space for feedback. We iterate for one week over and over and come up with a good design at the end of the week.

Afterwards it needs to implemented, which will take three weeks in order to finish the common components: BaseLayout, LoginComponent, ProfileComponent, ProfileEditComponent, OwnedNFTsComponent, CreateGalleryComponent, GalleryListComponent, GalleryEditComponent and GalleryShowComponent.

When the App is started the BaseLayout is loaded. 

In case the user is already logged in it shows the profile in the header menu of the BaseLayout and in the body the OwnedNFTsComponent and the GalleryListComponent. Through Drag and Drop NFTs can be added to a gallery. Additionally a settings button allows to edit specific settings of the gallery in the GalleryEditComponent. Each gallery has also a direct link to a presentation mode GalleryShowComponent where the gallery is presented with the NFTs and the settings from the GalleryEditComponent, e.g. a specific slide show or specific stop intervals.

In case the user is not logged in, the BaseLayout shows a login button in the body instead of owned NFTs and identity related galleries.
The functionality for the login button will be implemented in milestone 2.

Stories:
   - Create design in Figma
   - Setup Git repository with ReactApp and Bootstrap
   - Implement evaluated design in proposed components

People: Frank (Design) + Rene (Dev)
Timeline: 1 month, July 1st - August 1st
Funding: USD 10000

### IDX, Ceramic and IPFS as Social Login

With this milestone we deliver the ability to log into the app through the LoginComponent which executes the login method from the IDX framework and use Metamask as signing provider. After the login the app loads the basic profile from IDX. In case the user has no existing profile, the ProfileEditComponent shows up as Modal (????) allows to create and persist a profile on IPFS through IDX and Ceramic.

We rely on the SDKs of IDX, Ceramic, IPFS and the Metamask Web3 provider in order to archieve our Web3 DID login. This allows us to fetch the Ethereum address of the user. Thereby we can load the users owned NFTs from the OpenSea API.

If a gallery is created or edited the gallery will be stored on IPFS through IDX and Ceramic. 

Stories:
   - Provide IDXLogin functionality with Metamask, Ceramic and IPFS
   - Provide extended NFT gallery scheme for the Ceramic network
   - Store galleries after creation or edit in IPFS 

Dev team (Pair): Frank
Timeline: 2 weeks, July 14th - July 31st
Funding:  USD 5000

### 3. Filecoin as cold storage 

In order to provide long term storage or cold storage for galleries we need to provide a feature which allows the user to persist entire galleries on Filecoin. Right now almost every web3 user has a Metamask wallet, but not every user has FIL wallet in the browser. Therefore we provide a textile powergate which creates for every NFT user an account and provide some FIL to persist galleries long term.

Later on we want a more decentralized version. In that ideally the user comes with his own FIL provider.

The feature is for the user optional and is easy to trigger through a checkbox or a button.

Stories:
   - Setup powergate
   - Provide serverless function to create and fund NFT gallery users with FIL (so klar ist der Satz für mich nicht, ich weis aber nicht genau was du sagen willst)
   - Implement cold storage feature for NFT galleries in React app

Dev team (Pair): Frank (Powergate, Frontend) + Rene (Backend)
Timeline: 1 month, August 1st - August 31st
Funding:  USD 10000

## Total budget requested

We request USD 25000.

## Maintenance and upgrade plans

After we launch, we will go on and build a product. Because of protocol changes there will always be the necessity for updates.
When the product is setup we plan to exit and hand over the maintainance the to community.

# Team

## Contact info
frank.pfeift@protonmail.com

## Team members

- [Frank](https://github.com/froid1911): Tech lead, Filecoin & Ceramic expert
- [René](https://github.com/dev-nes9): Backend Developer & Frontend developer

## Team member LinkedIn profiles

- https://www.linkedin.com/in/fpolster/

## Team Website

Currently there is no team Website yet. It will be our first step.

## Relevant experience

We both have a Master of Science in Computer Engineering.
We worked for five years until July 2021 for a german IT consulting company at the Web3 department. We had mainly large clients, e.g. BMW or Deutsche Bahn.
We also attended multiple Hackathons and Conferences e.g. annual EF DevCon, ETHCC, ETHDenver, ETHBerlin and ETHBerlinZwei

Frank has also some relationships to the Ceramic network team and does Filecoin mining.

## Team code repositories

- https://github.com/froid1911
- https://github.com/ant1pattern


# Additional information

Made with <3

# References
- https://idx.xyz/
- https://ceramic.network
- https://docs.textile.io/powergate/
- https://www.w3.org/TR/did-core/ 
- https://github.com/ceramicnetwork/nft-did-resolver 
- https://docs.opensea.io/reference#getting-assets 
