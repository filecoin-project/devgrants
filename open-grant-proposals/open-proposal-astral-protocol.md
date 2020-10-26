# Open Grant Proposal: `Astral Protocol`

**Name of Project:** Astral Protocol

**Proposal Category:** `app-dev`

**Proposer:** `j-mars`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

At Astral we are building the bindings between Web3 and spatial data technologies to improve measures of human dignity and planetary stewardship.

To date, no Web3 application has truly been able to bring the trustlessness, transparency and permissionless structure of blockchains into the "real world". We are approaching this issue by developing the ways to make information derived from spatial data accessible to Web3 applications.

Spatial data contains information relevant to locations in the physical world. Different locations have different rules - depending on where you are you have to abide to a different regulatory framework. Numerous decentralized applications make the same assumptions and create the same rules for everyone. And, information about local conditions can be intensely useful in smart contracts.

To create decentralized applications that leverage spatial data and location information, we need to be able to store and access spatial data in ways that ensure it is simple and reliable for Web3 developers to work with. This is the purpose of the Astral Protocol: to create the bindings between Web3 and spatial data technologies.

Our research and development efforts are showing that innovations at the convergence of these technologies will enable an ecosystem of new, durable tools and mechanisms to re-align human and organizational incentives towards agreed-upon social and environmental objectives.

# Value

Filecoin / IPFS is the natural option to serve as a reliable archive of measurements of the Earth and its systems over time. This data should be archived permanently, as future analytical techniques may uncover signals we can’t detect now, enabling humans of the future to more accurately understand Earth’s natural and human systems, and adapt them to better serve our needs. Furthermore, by developing Web3-native geoprocessing capabilities, a shared understanding of our planet’s health can emerge - crucial to our transition to sustainability.

![SpatialDataVolume](https://ars.els-cdn.com/content/image/1-s2.0-S0167739X1730078X-gr1.jpg)

_Value: sustained increase of yearly spatial data volume, with focus on Sentinel satellite imagery_

The applications enabled by the spatial data layer of the decentralized web are wide-ranging and revolutionary. As an example, we built a prototype sustainability-linked bond on Ethereum and IPFS, which aligns financial and ecological incentives by adjusting the amount a borrower needs to pay each year based on a measurement of environmental health - in our case, raster images of air quality in London.
We've also designed a spatial governance protocol for connected devices - a system for applying policies to vehicles and other devices based on their geographic position in zones, represented by vector geometries - while preserving the privacy of everyone involved. We built Hyperaware, an alpha implementation of the protocol, on Arweave, IoTeX and Ethereum.

These projects have a common requirement: the capability to work with spatial data on the decentralized web. To solve this, we are now working on the Astral Protocol and the GeoDID specification, which will enable developers to build a whole range of new location-based and spatial decentralized applications - dApps that will underpin a globally coordinated Web3 society.

Risks mainly center on adoption. If Web3 does not provide a compelling enough reason for traditional users to switch, our work will remain in our crypto bubble, independent of the real world. Our goal is to create a developer experience similar to centralized technologies, with the additional integrity and availability guarantees Web3 offers, along with the option for users to choose self-sovereignty.

# Deliverables

- Design the GeoDID Method Specification, based on the SpatioTemporal Asset Catalog spec and build alpha @astral-protocol modules to create and manage GeoDIDs, and associated spatial data assets, stored on IPFS / Filecoin. Fuse the GeoDID specification with the ERC-1155 standard to enable interchangeable proofs of human location through the means of NFTs: the GeoNFT.
- Develop and market Geolocker, the first spatial dApp making usage of the Astral Protocol. Geolocker will be a mobile dApp for secure minting of sybil proof GeoNFTs, binding the GeoDID specification. Users collect GeoNFTs when they check-in on places, events or complete certain tasks, enabling decentralized location-based value generation.

# Development Roadmap

An ecosystem of location-based dApps will benefit from a standard way of representing spatial data in the Web3 universe. By converging on a versatile, extensible standard, different actors in the ecosystem can develop their systems to be interoperable with that specification.
For this, we are designing the Astral Protocol: a standardized way of working with spatial data in Web3. Within the Astral Protocol we are creating a geographic decentralized identifier, the GeoDID, which is the primitive for representing spatial data assets in Web3. Based on this specification, we will create a verifiable spatial data registry and develop the tools - software modules, interfaces, etc - required for users to perform different tasks necessary to register, share, revise and consume these spatial data structures.
The GeoDID identifier will be fused together with the Ethereum ERC-1155 standard into a new web primitive called the GeoNFT. These NFTs will be created in an efficient manner in a so called Spatial Assets Registry smart contract, which will be compliant with current Web3 NFT interfaces and effectively allow for interchangeability and composability of location-data in Web3 applications to unlock yet undiscovered use-cases.

We are also creating the first spatial mobile dapp, Geolocker, which will make use of the Astral Protocol. Humans know that where they are matters, but smart contracts do not know where they are. Current location-based schemes are centralized, unfair and invasive and there are no real economic incentives to share location. To tackle this, Geolocker will incentivize users to check-in to their location and collect GeoNFTs. We see potential convergence with dapps that could make use of location data, like events and ticketing, gaming and governance dapps, and we know that usage of Geolocker will drive adoption to the Filecoin network as each GeoNFT will be directly linked to a newly pinned GeoDID.

We hold self-sovereignty as a core value at Astral, and are designing all of our products and systems to give users the option of complete autonomy, including the right to choose privacy, if appropriate.

## 1. Create the GeoDID Method Specification and prototype @astral-protocol modules

The GeoDID Method Specification will “specify the precise operations by which [Geo]DIDs are created, resolved and deactivated and [Geo]DID documents are written and updated”. This will define the specifics of the verifiable spatial data registries we are designing.

GeoDIDs will be based on the DID specification, extended to have specific attributes relevant to the representation of geospatial data in vector and raster formats. It will be some time before we have v1.0 of this spec - first, we need to design and prototype various draft implementations of the GeoDID Method to fully understand the components of the core specification.

Our engagement with prospective users from insurance, finance, and spatial data domains has driven us to focus our initial draft on raster imagery. Future versions of the specification will address the need to represent vector geometries and multi-geometries in Web3.

We understand that a large community of experts in the spatial data community have been working to solve many of the problems we want to solve with regards to the cataloguing and access of spatiotemporal datasets. Rather than try to reinvent the wheel, we have opted to adopt and build on their work. As such, GeoDIDs are designed to comply with the SpatioTemporal Asset Catalog specification as closely as possible. This specification, maintained by the Radiant Earth Foundation, provides a common language to describe a range of geospatial information, so it can more easily be indexed and discovered. In addition to the spec, a community of developers has built a range of tools to create, validate and explore these asset catalogs. To contribute to this effort and leverage the fact that the community is already adopting it, GeoDIDs extend the DID specification to comply with STAC.

An advantage to this: any datasets that can be represented in a STAC can be easily identified by a GeoDID. Furthermore, STAC was designed to standardize the cataloguing of spatiotemporal data - we want to make it as seamless as possible to onboard existing STAC-catalogued spatial data onto IPFS / Filecoin. Onboarding appropriately-licensed imagery catalogued on STAC will be very simple. So we are taking a STAC-first approach to designing GeoDIDs.

Part of phase 1 on our Development Roadmap is to design and prototype a draft GeoDID Method Specification and creating decentralized identifiers for spatial data assets. We will extend the DIDs v1.0 specification. Our goal is to map the DID document structure to those of STAC Catalogs and Items.

More specifically, we believe that the STAC Specification will map to the DID document level. The STAC Specification wraps the sub specifications within it. These include: the STAC Collection Specification, which acts as an extension of the STAC Catalog, and provides additional information about a spatio-temporal collection of data; the STAC Catalog, which specifies a structure to link various STAC Items together to be crawled or browsed; and the STAC Item, which is a GeoJSON Feature with additional foreign members - fields for things like time, links to related entities and assets (including thumbnails).

For simplicity’s sake, since the STAC Collection is viewed as an extension of a Catalog, we will refer to them as the Catalogs to simplify the explanation in relation to the GeoDID. The STAC Catalog can contain several children - Items, or Catalogs which in turn can also contain several more child Catalogs or STAC Items. By definition of the STAC Spec, the Catalogs maintain the control of the parent/child relations by using the respective links associated with that relation.
We plan to replicate this functionality of parent/child relationships by using IPLD, specifically the DAG-CBOR codec and CIDs to represent not only the Catalog and Item JSON files, but also the assets endpoints listed in the STAC Item. The idea is to traverse the “tree” of the particular STAC Catalog from its “root node” , convert them from STAC Spec to GeoDID Spec, and serialize the contents, and encoding them into their respective CIDs. Then encoding the list of nested CIDs with the DAG -CBOR codec to group them into an organized data structure.

For example, let's say that we have a STAC Catalog that has one child Catalog within it, and this child Catalog has two STAC Items within it. From the root Catalog we shall recursively fetch the child Catalog from the list of links, in this case we only have one, that represents the child Catalog. Then we fetch the Item in the child Catalog and fetch the Item’s assets from its respective endpoints (the COG - Cloud Optimized GeoTIFF and other raster image data). We perform a multihash on the fetched data and convert them into their own respective CIDs. Then we convert the STAC Item into a “GeoDID Item”, by adding the DID metadata and header, and then represent the asset CIDs as service endpoints.

On the way out of the recursive call we encode the “GeoDID Item” document, by using JSON, serializing it to its binary representation that we can store and/or send to someone else. Then we deterministically derive a CID from the serialized binary of the GeoDID Item, which gives us a globally unique identifier for that binary, the content addressable CID. Then we convert the parent STAC Catalog of the “GeoDID Item” to a GeoDID as well, we will call this the “Child GeoDID Catalog”. Next we serialize it and convert it to a CID as well. Finally, we repeat the process for the parent STAC Catalog of the “Child GeoDID Catalog”, converting it into a GeoDID, serializing it, and converting it into a CID. Keep in mind that the GeoDID Item, Child GeoDID Catalog, and GeoDID Catalog, are all represented as a set of linked GeoDIDs.

In the above example, we created an IPLD block for each GeoDID. We then use the CIDs generated for each block to reference their parent GeoDIDs, that is based on the hierarchy of the STAC Catalog that was uploaded earlier. With the nested list of JSON encoded CIDs representing their respective GeoDIDs, we can use the DAG-CBOR codec to encode the parent child relationship of them, to create a linked data structure that we can use later for ease of access to this particular set of geo-spatial data.

The benefit of this is that we have a data structure containing the GeoDIDs that represents the replicated parent child relationship of the STAC Specification. This makes it easier for users to query a particular data set, and get access to the collection they need. Using IPLD Selectors, the user can go even further and only require the specific GeoDID Items or GeoDID Catalogs that they need, granted the DID Controller grants them access to it. We plan to further this functionality and build several IPLD codecs that will cater to the spatial data community. Codecs that can encode COGs (Cloud Optimized GeoTIFFs) and other native geo-spatial files. We also want to build a codec that can encode our GeoDID Documents to add further functionality, maybe things like PostGIS functionality, etc.
These codecs are where most of our value proposition will reside in regards to the Protocol Labs ecosystem. That value proposition is bringing geo-spatial tools and enhanced workflows to the protocol labs ecosystem, as well as building a libp2p network that suits the specialized needs of the geo-spatial community in the web3 space. This is the frontier where the geo-spatial community and web3 community collide.

The remainder of phase 1's roadmap entails the creation of the following Astral Protocol packages:

**@astral-protocol-core**
The @astral-protocol-core package is the core package of the implementation. This is where we will develop the Astral Node Instance. Within the instance it will contain a transformer, that will enable us to use existing tools for working with the STAC Spec, as well as the transformation from STACs to GeoDIDs. In addition, the core package will contain a document handler that will listen for events from our smart contracts. These events will trigger actions for authenticating the DID Documents, making requests to read or update DID Documents, the anchoring of the DID Documents, and their state changes to the Verifiable Data Registry. The core package will also contain the Pinning API for both IPFS and Powergate, and the geo-did-resolver package.

**@astral-protocol-api**

The @astral-protocol-api package will supply endpoints for the @astral-protocol-core. This will enable ease of access and integration in our mobile dapp.

**@geo-did-resolver**
The @geo-did-resolver package will contain our DID method specification and will be responsible for the creation and dereferencing of the GeoDID Documents. This library is intended to use Ethereum addresses and NFT metadata as fully self managed Decentralized Identifiers and wrap them in a DID Document. It supports the proposed Decentralized Identifiers spec from the W3C Credentials Community Group. It requires the did-resolver library, which is the primary interface for resolving DIDs. In addition, the DID method relies on the minting of a ERC-1155 standard token, which will act as the registry. The relation will be a 1:1 relation from GeoDID to NFT.

**@astral-protocol-contracts**
The @astral-protocol-contracts package will act as the Verifiable Data Registry for the GeoDID Documents as well as the Ethereum contract code that allows a user to mint a GeoNFT. This contract code follows the [ERC-1155 standard](https://eips.ethereum.org/EIPS/eip-1155) which allows the the inclusion of any combination of fungible and non fungible tokens, all in a single deployed contract.
This standard supports setting a URI value for all the tokens created and allows for id substitution in client apps. Our URI will have the format of did:geo{id} (subject to change) and each client app can input the corresponding GeoDID id to have the full GeoDID representation. We intend to adopt the ERC-1155 Metadata URI Json schema as part of our GeoDID specification and create a combination of the two, allowing interoperability between both ERC-1155, the STAC and the DID specifications.
Client dapps of the Astral Protocol will interact with the Spatial Assets Registrar contract to mint the GeoNFTs for users. These GeoNFTs may be composed in other dApps to represent proofs of human location, effectively bridging the Blockchain - real world chasm.

## 2. Develop and market Geolocker

Geolocker is location based incentivization, controlled by you. People know that their location data matters, but often they realize they do not control it, as it falls in the hands of centralized actors who accrue all its value. Besides, at the moment Smart Contracts do not know where you are, which added to the lack of economic incentives to share human location, creates a real world to blockchain disconnect. Geolocker wants to change that by giving the first step in the direction of enabling decentralized location-based value generation.

The way Geolocker works is simple: a user moves around in the real world, presses the check in button whenever near a particular place and a GeoNFT is minted, proving their location. Under the hood, the user's geospatial data and timestamp are recorded, as well as their interest-point bounds in the map. This metadata is incorporated in our GeoDID specification and pinned over Filecoin.

The user will have full sovereignty over the privacy of their location data by having the ability to obfuscate details about their data. This will come as an improvement right after an alpha release of the geolocker dapp. The intention is to use a privacy-preserving module that allows computations over encrypted data, namely to prove presence at a location without revealing who was there. Research in this module will include secure enclave protocols that are interoperable with Ethereum smart contracts or proxy re-encryption schemes such as the one implemented by NuCypher.

A primary concern with the usage of GPS data to build such kind of dApp is the potential of spoofing one's location and thereby cheating the system. For this purpose, we are exploring the possibility of usage of decentralized and fault tolerant solutions such as the one provided by [FOAM](foam.io). This solution provides consensus on whether someone is verifiably at a certain point in time and space, accounting for the GPS vulnerabilities.

The development of Geolocker also entails the creation of $ASTRAL, an utility currency that will underpin the Astral ecosystem and Astral Protocol usage. In its first use case in Geolocker, users will be incentivized to collect GeoNFTs as they move in the world, receiving tokens for being top collectors in a given zone/timeframe. Later, when astralDAO is created, users will also be rewarded with $ASTRAL as they contribute to governance decisions. For the purpose of Geolocker, users will also be able to mint special booster NFTs with \$ASTRAL that provide extra bonuses for the collection of GeoNFTs and thus location data sharing.

The mobile dApp will be prototyped using a known cross-platform mobile framework - Flutter. This means more cost-effective development as the app will be built for both Android and IOS at the same time. The intention is to build a frictionless UX, integrated with known mobile Ethereum wallets such that our solution is always non-custodial. Your keys, your data. We understand that the community for mobile dApps is still small but we see this as an opportunity to incentivize the masses for real world decentralized app usage, right in their smartphones

As for the marketing of the dApp there are many use-cases that we can partner with to achieve sufficient user traction. We envision partnering with event organizers that wish to promote a verifiable and automated ticketing system to access an area. In this case, the verification of one's location through the GeoNFT and the ownership of a ticket NFT could automatically grant access to a stage, without human or mechanical interaction. Payments inside the event area could be done through an extension of our dApp.
Another interesting use case from an advertising perspective, could be physical stores that want to incentivize people to come and spend inside. In a nutshell, if a user visits a store and mints a GeoNFT inside it, an additional reward is given. From the store's perspective it is essentially an immutable and verifiable way to prove that a customer visited their store and was exposed to a product that they wanted to show.

We theorize that sufficient gamification and user traction in the dApp will provide a pathway of real world usage of Filecoin in the back scenes due to the constant pinning of GeoDIDs over Filecoin and the need for their persistent availability for other dApps that might consume this primitive.

# Development Roadmap Budget

In sum, the roadmap will consider:

- Designing the GeoDID specification based on STAC Catalogs / Items, so we have a standard way of representing location data in Web3 for self-sovereign users, and building the initial version of Astral Protocol, which will manage the GeoDID primitive over the decentralized web.
- Developing and marketing of Geolocker, the first mobile spatial dApp to incentivize proofs of human location.

Time is spanning over a 6 month period after the grant start (placeholder date as the 1st of november of 2020):

| Milestone                                                            | Time                                   | Cost     |
| -------------------------------------------------------------------- | -------------------------------------- | -------- |
| GeoDID Method Specification and @astral-protocol modules             | Start: 01/11/2020 / Finish: 31/01/2021 | \$25,000 |
| Geolocker mobile dApp and \$ASTRAL governance /cryptoeconomic design | Start: 01/02/2021 / Finish: 30/04/2021 | \$25,000 |

## Total Budget Requested

Total: \$50,000 for a 6 month period for the development of the Astral Protocol and the Geolocker dapp. This sum provides a much needed security at a pivotal time of the project and will support the two current full time developers in it, as well as serve for any gitcoin bounties we intend to launch to support covering the development of specific parts of the project.

Breakdown of budget:

- Salary: 80%.
- Gitcoin bounty for specialist tasks: 15%.
- Operations: 5%.

# Maintenance and Upgrade Plans

The completion of the first iteration of the astral-protocol, the GeoDID method specification and the Geolocker spatial dapp are only the first steps of a bigger vision. We will not only continue to use the GeoDIDs ourselves but also use it in conjunction with real-world partners we will cooperate with, e.g. 4 Earth Intelligence. On top of that, we will continue to expand on the fundamentals described above. This can for example include ideas like:

- R&D privacy preserving GeoDIDs, where data owners can restrict access to the data asset, using a proxy re-encryption scheme or a secure-enclave computation system.
- Leverage on Layer 2 networks on Ethereum to cut down substantially on transaction fee costs so that the dApp can be scaled and massified.
- Build towards v2.0 of the GeoDID Method specification. This will include additional functionality for a DID optimized to identify spatial data assets, including spatial querying, spatial indexing and management of raster imagery.
- Develop a decentralized autonomous organization for Astral (astralDAO) to govern the protocol and research further incentive schemes that will underpin the ecosystem usage.

# Team

## Team Members

- John Hoopes IV- Researcher and co-lead at astralDAO. MSc Spatial Data Science and Visualisation (Distinction), Technical Director London Blockchain Labs, Developer Advocate Ordnance Survey.

- João Martins - Technical advisor, researcher and co-lead at astralDAO. Full Stack dApp developer on Ethereum with 2 years of experience. First author of an academic article on group-buying on decentralized networks for increased supply chain coordination. MSc Industrial Engineering and Management (Distinction).

- Jared Childers - Technical advisor and researcher at astralDAO. Backend Engineer + Cloud Ops with 1 year of experience. Knowledgeable in consensus protocols, and experienced in building various tech stacks, with 2 years of experience in web3 space.

- Robin Davids - Analyst at Rarestone Capital and Strategic and Token Lead at Rarestone Labs. Worked with some of the best performing blockchain startups of 2019 with a focus on fundraising, token economic design and game theory. Investors in these projects include Binance Labs, Bitfinex, Arrington XRP Capital and many more.

- Darien Ford - Cyber Security Specialist, with 1 year of experience in blockchain. Understanding of security, privacy and cryptographic protocols and secure computation. Experience in cyber and crypto/ blockchain intelligence. Security researcher at astralDAO.

- Jason James - Software engineer at Bloomberg LP. Lead developer on Hyperaware, won Ripple BlockSprint hackathon for “SpringBlock”, a market optimisation program for the XRP Ledger. Developed KeepHelper, a suite of dApps and an explorer for Keep Protocol. Developed Iotxplorer, a block explorer for IoTeX Network.

## Team Member LinkedIn Profiles

- John Hoopes IV: https://www.linkedin.com/in/johnrhoopesiv/
- João Martins: https://www.linkedin.com/in/jlmartins/
- Jared Childers: https://www.linkedin.com/in/jared-childers-343b68195/
- Robin Davids: https://www.linkedin.com/in/robin-davids/
- Darien Ford: https://www.linkedin.com/in/darien-ford-495ba713a/
- Jason James: https://www.linkedin.com/in/jason-james-87537410a/

## Team Website

Astral DAO Landing Page - https://astraldao.org/

# Relevant Experience

Project Experience:

- APOLLO / ETH Online early Astral Protocol - https://github.com/astralDAO/astralprotocol
- Hyperaware - https://hyperaware.io/
- KERNEL Smart Green Bond Project

Skills:

- IPFS/Filecoin experience
- Smart Contract development on Ethereum
- Back-end development with NodeJS
- Front-end development with React
- Distributed Ledger Technology
- Big Data and Analytics
- Experience in Decentralized Identifiers
- Geo-Spatial Data Science + Analytics
- Encompasses Machine Learning and Deep Learning

## Team code repositories

- Current implementation of the astral protocol - https://github.com/astralDAO/astralprotocol

Previous code repositories for related projects

- KERNEL Smart Green Bond Project - https://github.com/astralDAO/sl-green-bond
- Hyperaware - https://github.com/wearehyperaware/hyperaware-core | https://github.com/johnx25bd/ethlondon
