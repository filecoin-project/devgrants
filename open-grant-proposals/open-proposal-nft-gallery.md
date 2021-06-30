To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `NFT Gallery`

**Name of Project:** `NFT Gallery`

**Proposal Category:** `app-dev`

**Proposer:** `froid1911`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `YES`

# Project description

Since the Cryptokitties project in 2017 NFTs got more and more attention and the **market trippled every year** (\$40 million in 2018, \$141 million in 2019, \$338 million in 2020). 2021 is not yet over, an NFT called "Everydays: The First 5,000 Days" by an artist named Beeple was auctioned off for about \$69 million, but also other NFTs are sold for millions too, e.g. CryptoPunks.

We recognized that right now there is no proper solution to organize your NFTs in galleries and display them whereever you want - at least not in a self soverign way. The only requirement for the presentation mode of your NFTs are a web browser with internet connectivity.

Consider checking into a hotel and your NFTs are already there or display specific NFT on your TV @ home, at your meeting room or somewhere else?

This project aims to bring **your NFTs next to you**. In order to reach this goal we are going to adopt the identity protocol for open applications **idx.xyz** which relies on the general open information protocol **ceramic.network** which again relies on **ipfs** as hot storage and communication layer.

In our product the user can use its social login to enter our app, sort its NFTs in galleries and later display them on any screen with internet connection. This enables a huge number of potential users that can take advantage of the product on many different and potnetially older devices.

Right now we want to use textile powergate as cold storage solution. Alternativly also Filswan could be an option.

## Value 

With our solution we show how Web3 Dapps look and feel  without cloud server.
Additionally it can bring 50.000 existing users from IDX to Filecoin.

Right now we can not identify any product oriented risks, except NFTs identifies itself as a totally scam. 
An additional factor could be that NFTs are only stored in hot storage and disappear at some time if not  in cold storage and not used.

## Deliverables

The final product will be a fully functional web application hosted on IPFS. Cold storage will be provided through a serverless function and a textile powergate.
On the user side an easy access to all types of NFCs is possible an almost any device worldwide without any additional exposure to risk.

## Development roadmap

### 1. UI/UX design and implementation

Good UX/UI take time. In order to avoid pitfalls and receive realworld customer feedback, we create a design in one day and ask friends in the nft space for their feedback. We iterate for one week over and over and come up with a good design at the end of the week. 

Afterwards the UX/UI needs to be implemented, which will take three weeks in order to finish the common components: BaseLayout, LoginComponent, ProfileComponent, ProfileEditComponent, OwnedNFTsComponent, CreateGalleryComponent, GalleryListComponent, GalleryEditComponent and GalleryShowComponent.

When the App is started the BaseLayout will be displayed. 

In case the user is already logged in, the profile in the header menu of the BaseLayout is shown. In the body the OwnedNFTsComponent and the GalleryListComponent is shown. Through drag and drop NFTs can be added to a gallery. Additionally a settings button allows to edit specific settings of the gallery in the GalleryEditComponent. Each gallery has also a direct link to a presentation mode GalleryShowComponent where the gallery is presented with the NFTs and the corresponding settings from the GalleryEditComponent, e.g. a specific slide show or specific stop intervals.

In case the user is not logged in, the BaseLayout shows a login button in the body instead of owned NFTs and identity related galleries.
The functionality for the login button will be implemented in milestone 2.

Stories:
   - Create design in Figma
   - Setup Git repository with ReactApp and Bootstrap
   - Implement evaluated design in proposed components

People: Frank (Design) + Rene (Dev)
Timeline: 1 month, July 1st - August 1st
Funding: USD 10000

### IDX, Ceramic and IPFS as social login

With this milestone we deliver the ability to log into the app through the LoginComponent. The LoginComponent executes the login method from the IDX framework and use Metamask as signing provider. After the login the app loads the basic profile from IDX. In case the user has no existing profile, the ProfileEditComponent shows up as Modal and allows to create and persist a profile on IPFS through IDX and Ceramic.

We rely on the SDKs of IDX, Ceramic, IPFS and the Metamask Web3 provider in order to archieve our Web3 DID login. This allows us to fetch the Ethereum address of the user. Thereby we can load the users owned NFTs from the OpenSea API.

If a gallery is created or edited the gallery will be stored on IPFS through IDX and Ceramic. 

Stories:
   - Provide IDXLogin functionality with Metamask, Ceramic and IPFS
   - Provide extended NFT gallery scheme for the Ceramic network
   - Store galleries after creation or edit in IPFS 

Dev: Frank
Timeline: 2 weeks, July 14th - July 31st
Funding:  USD 5000

### 3. Filecoin as cold storage 

In order to provide long term storage or cold storage for galleries we need to provide a feature which allows the user to persist entire galleries on Filecoin. Right now almost every web3 user has a Metamask wallet, but not every user has a FIL wallet in the browser. Therefore we provide a textile powergate which creates for every NFT-user an account and provides some FIL to persist galleries long term.

Later on we want a more decentralized version. Preferably the user comes with his own FIL provider in this version.

This is an optional for the user and ti is easy to trigger through a checkbox or a button.

Stories:
   - Setup powergate
   - Provide serverless function to create and fund NFT gallery users with FIL
   - Implement cold storage feature for NFT galleries in React app

Dev team (Pair): Frank (Powergate, Frontend) + Rene (Backend)
Timeline: 1 month, August 1st - August 31st
Funding:  USD 10000

## Total budget requested

We request USD 25000.

## Maintenance and upgrade plans

After we launch, we will go on and build a product. Because of protocol changes there will always be the necessity for future updates.
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
- https://www.cryptokitties.co/
- https://www.statista.com/statistics/1221742/nft-market-capitalization-worldwide
- https://www.larvalabs.com/cryptopunks
- https://makersplace.com/beeple/5000-days/
- https://idx.xyz/
- https://ceramic.network
- https://docs.textile.io/powergate/
- https://www.w3.org/TR/did-core/ 
- https://github.com/ceramicnetwork/nft-did-resolver 
- https://docs.opensea.io/reference#getting-assets 
