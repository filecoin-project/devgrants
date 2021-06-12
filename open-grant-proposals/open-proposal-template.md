# Open Grant Proposal: `Yaytso`

*Yaytso*

**Proposal Category:** `app-dev`

**Proposer:** [Ariel Klevecz](https://github.com/aklevecz)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

### An experience for creating and discovering NFT eggs

The app is currently live [here](https://yaytso.art)

Yaytso contract address: [0x155b65c62e2bf8214d1e3f60854df761b9aa92b3](https://etherscan.io/token/0x155b65c62e2bf8214d1e3f60854df761b9aa92b3)\
Carton contract address: [0x7c05cf1a1608eE23652014FB12Cb614F3325CFB5](https://etherscan.io/address/0x7c05cf1a1608eE23652014FB12Cb614F3325CFB5)

`yaytsos` are user generated NFT eggs. Each `yaytso` is patterned by an uploaded image and/or mouse/touch doodling. Once the user is pleased with their egg-piece they are guided through the process of generating the metadata for the name and description. All relevant data/assets are packaged and pinned to IPFS using NFT.storage from a simple Node.js server. One sneaky special asset is a 2D SVG representation of the `yaytso` generated in the background during the creation process. This image is pinned to IPFS and its content address is saved on-chain as a way to enforce uniqueness. This is a relatively naive approach to enforce `yaytso` uniqueness, but it is at least effective in preventing someone from accidentally creating a duplicate.

The `Yaytso` contract is a fairly boilerplate ERC-721 smart contract. There is neither an owner of the contract, nor any contingencies for generating a NFT besides the unique quality of the hash representing its pattern. The project is designed to evolve with the community that gravitates around it.

The newer core component, which is a feature only usable by myself at the moment, is the ability to lock eggs in `cartons` tied to physical space (lat/lng). A `Carton` contract inherits a `Yaytso` contract and will initiate the transfer of a `yaytso` in a given `carton` to the sender of an appropriately formatted signed message from the `yaytso's` owner. When filling a `carton` with a `yaytso`, the owner must approve the `Carton` contract to transfer the token. The concept of trust in this situation can be exchanged for that of generosity. If a person is taking the time and effort to create and hide a `yaytso` their motivation to recover their own token and lose gas would be much less than creating an experience for someone else in the community. My current approach for playing with this concept is going through the steps mentioned above and then printing a QR code with the format:
```
https://yaytso.art/discover/<signature>/<cartonId>/<nonce>
```
The QR code is then embedded on to a questionably aesthetic poster and pasted onto an observable flat surface out in the world. When a discoverer scans the QR code the app will fetch the `yaytso` associated with the `carton` and render it as a 3D object. Once the user has connected a web3 enabled wallet, using MetaMask or WalletConnect, they can simply click a button to initiate the transfer with the only fee being the gas of the transaction. The `carton` is then unlocked and ready to hold another `yaytso`. A current caveat is a given poster can only be used once, as each poster's embedded message includes a nonce associated with the `carton` in order to invalidate old messages from similar addresses.

## Value

This project offers a variety of use cases and models for interacting with the Filecoin/IPFS ecosystem by both storing *physical* content and using content addressing in creative ways. The real world component also broadens the perspective and applications in a way that makes these systems feel more tangible. A person who is discovering content in physical space and collecting it in digital form will naturally be practicing their understanding of how these systems are connected and will be motivated to learn more. The overall component of play also makes these concepts fun and approachable, which will help balance the confusion of stumbling upon esoteric technical documentation and decentralized jargon.

Usability will likely be the greatest challenge. The process of producing a `yaytso` is not complex, but naturally has some friction within the relatively nascent world of web3 wallets. The discovery of `yaytsos` has similar challenges in usability, and also includes the significant amount of work involved in creating tools and primitives to empower the general user within the process of forming the `yaytso` and `carton` interaction. In the end there is a risk that no one will ever use this besides myself because the value propositions are not seated in economics.

## Deliverables

The final product will be a fully functional web application that can drive all of the above interactions and a Discord server for the community.

And of course a ton of eggs spread around the world.

## Development Roadmap

Assuming a start date of July 1st

### 1. UI/UX Brushing up
Egg creation needs UX/UI love. The pattern process is fairly well fleshed out, but the steps proceeding require some domain knowledge and need more feedback to generate trust.

The map needs more development to make it usable and engaging. At the moment it only allows you to see the location of a single egg, so a logical next feature is a map that displays all of the eggs available in order to garner intrigue and exploration. The status of a given carton (i.e. locked/filled, unlocked/empty) also needs to be implemented.

The application of the pattern onto the `yaytso` should also be updated to be more flexible. At the moment the pattern is cropped to a square and divided equally into four sections vertically. Offering more control over the amount of times a pattern is repeated over the egg will allow for exponentially more creations. Exploring the use of fragment shaders will also allow the user to more easily blend their images into a cohesive pattern in the event that they become frustrated with hard edges between each pattern repetition.

*Software*
- More event feedback from listening to the transactions using ethers.js
- Improving React.js components related to this process
- Creating additional React.js components/pages that explain the behaviors
- Creating an engaging map experience using Google Maps API within React.js components
- Improving the overall design to adhere to consistent UX driven proportions

People: Ariel & Sam  
Timeline: 1 month, July 1st - August 1st  
#### Funding: $6,000


### 2. Priminitives
In order for the `Yaytso` and `Carton` contracts to have purely user generated interactions there must be well defined primitives. Presently, `yaytso`’s as basic customizable egg primitives are functioning, which has been validated by people creating them without any encouragement or guidance. Though, the connection between the `yaytso` primitives and the app environment as a way to visualize one's collection is still underdeveloped.

At the point that the user can easily relate to their collection of `yaytsos` within the app, there should be a discrete path to either place a `yaytso` into an existing `carton` or generate a new one. `carton` generation and placement is contingent on usability work for the various map views. The user will be able to see their current location or search for an area where they would like their `yaytso` to be available. In the event that they are creating a new `carton` they will select a spot, and confirm the transaction to create the `carton`, and subsequently see its official lat/lng and area. The process of placing a `yaytso` into a `carton` includes a few steps, first (as mentioned above) the user must approve the `Carton` contract with the ability to transfer the desired `yaytso`. Once the `Carton` contract has approval, it will allow the user to lock the `carton` with the `yaytso`. Once these two steps are complete, the user will be given an image to download displaying the QR code with the signature necessary to claim the locked `carton's` contents. This image will include the 2D representation of the `yaytso` for additional context and aesthetics.

The point where the user is printing the poster and placing it will be an interesting challenge. It may be worth initially creating `cartons` for people to use that are in easily accessible and not sketchy for postering. There could also be community driven ways to give a user `carton` creation privledges in order to require extra intention and thought. These ideas may evolve as experimentation continues. In this way the goal of these primitives is to develop the set of behaviors necessary to decentralize the entire creation to discovery flow.

*Software*
- Building React.js containers and components for the `carton` flow
- Designing UI elements for each view
- Designing poster templates customized using HTML canvas
- Creating Map views

People: Ariel & Sam  
Timeline: 1 month, August 1st - September 1st  
#### Funding: $6,000

### 3. Community Integrations
Generating excitement and connections is key to producing fun experiences to motivate the movement and creation of `yaytsos`. This is best facilitated through a Discord server that is integrated into the web app. People will be able to associate the wallet holding their `yaytsos` with their Discord account and join the server. The base channels will be spaces for people to share their creations, updates about hidden/found eggs, and general discussion. This will require a simple Node.js API for authoritative Discord bot functions and webhooks. One low hanging webhook will listen for contract events and push them to relevant Discord channels. I believe most people interacting with this space have already adopted Discord or are likely to without much friction. This will also alleviate the pressure to use email and text messages for marketing and sharing information.

The API and Discord integration can also serve as the first pass at user authentication offering some flexibility outside of instantiating a web3 wallet. For example, someone who has authenticated with Discord and their wallet could sign into their account from any device using solely Discord to observe the contents of their wallet. Of course any functions that delegate mutations to their account or the blockchain would still require a wallet to be authenticated, but this will reduce friction toward general usability for checking various statuses. Further down the line this integration could be made more seamless with a secure dedicated `yaytso` wallet.

*Software*
- Building a simple Node.js server for bot and authentication functions
- Creating a Discord server and the base channels
- Designing assets for Discord emojis, avatars, and events

People: Ariel & Sam  
Timeline: 2 Weeks, September 1st - September 14th  
#### Funding: $4,000

### 4. Advancing Geolocation
Truly integrating the experience of discovery between the digital and physical world will include creating constraints and changes in state based on the user’s location. For one, the user should only be able to claim a `yaytso` if their location is within the vicinity of its `carton`. This feature also lends itself to more gamification for scavenger hunts that require a series of steps for the user to find the actual location of a `carton`.

When a user enters a general or given experience they could also see the locations of other people involved. This would help build the interactive feeling of being a part of an adventurous community and lends itself to continuing to explore space in new found ways. I believe this side of the `yaytso` puzzle will have a clearer direction at the point that there is at least a small community to build around.

*Software*
- Integrating the user’s location into the map UI
- Designing experiences based on the user’s location
- Adding logic to the `Carton` contract and/or developing new derivatives
- Adding authoritative control of various `Carton` contract functions to the server

People: Ariel & Sam  
Timeline: 2 Weeks, September 14th - October 1st  
#### Funding: $4,000

## Total Budget Requested

$16,000     Ariel & Sam's time  
$4,000      Ethereum purse for transaction costs and general capital for business/hosting cost  
_____________
#### $20,000   Total
_____________
## Maintenance and Upgrade Plans

The frontend will require a few cycles of refactoring after shipping features.

Upgrading contracts will be inevitable for adding desired features since many of these behaviors are difficult to test without seeing them play out in the wild.

The Discord server will involve some upkeep and attention over time.

Assuming success the project will look for additional funding to grow the team and its continuation into an accelerator or additional grants.

# Team

## Team Members

- Ariel Klevecz
- Sam Thorn

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/ariel-klevecz-38a200195/
- https://www.linkedin.com/in/sam-thorn-8b9404208/

## Team Website

https://yaytso.art

## Relevant Experience

### Ariel Klevecz

Psychologist turned Data Scientist turned Frontend/Fullstack-ish Engineer. 8 years of experience working in software development between analytics and web development. Outside of the professional sphere he has also spent the past 6 years hacking on his own projects and building communities with a focus generating growth through organic interactions. He founded the Yaytso project/idea in the NFT hackathon, finding that the idea elegantly integrated his interests and skills in a way that has been transcendentally motivating.

### Sam Thorn

Sam has studied art most of his life with a focus on graphic design that led him to work at various architecture firms. Endlessly restless he decided to pursue a music career, which led to him touring with various bands around the world. The pandemic forced him to re-evaluate his path, which led him to explore software engineering from a profound interest in better understanding the technology that has engulfed our daily lives. He offers both his high level of expertise in designing and laying out space and ever growing domain knowledge of the technology that drives it. Sam is also an incredible communicator and will be invaluable in bringing the product to the public sphere in a fashion that the lay technologically-interested person will find compelling.

## Team code repositories

https://github.com/aklevecz/yaytso

# Additional Information

Thank you for your time as always PL people. I appreciate all of the encouragement and help you have given me over the past few months. I wouldn’t have been able to continue this funny dream without it <3
