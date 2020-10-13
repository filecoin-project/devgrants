# Open Grant Proposal: `astralDAO`

**Name of Project:** astralDAO

**Proposal Category:** `app-dev`

**Proposer:** `j-mars`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

At Astral we are building the bindings between Web3 and spatial data technologies to improve measures of human dignity and planetary stewardship.
 
To date, no Web3 application has truly been able to bring the trustlessness, transparency and permissionless structure of blockchains into the "real world". We are approaching this issue by developing the ways to make information derived from spatial data accessible to Web3 applications. 
 
Spatial data contains information relevant to locations in the physical world. Different locations have different rules - depending on where you are you have to abide to a different regulatory framework. Numerous decentralized applications make the same assumptions and create the same rules for everyone. And, information about local conditions can be intensely useful in smart contracts.
 
To create decentralized applications that leverage spatial data and location information, we need to be able to store and access spatial data in ways that ensure it is simple and reliable for Web3 developers to work with. This is the purpose of the Astral Protocol: to create the bindings between Web3 and spatial data technologies.
 
Our research and development efforts are showing that innovations at the convergence of these technologies will enable an ecosystem of new, durable tools and mechanisms to re-align human and organizational incentives towards agreed-upon social and environmental objectives.


## Value

Filecoin / IPFS is the natural option to serve as a reliable archive of measurements of the Earth and its systems over time. This data should be archived permanently, as future analytical techniques may uncover signals we can’t detect now, enabling humans of the future to more accurately understand Earth’s natural and human systems, and adapt them to better serve our needs. Furthermore, by developing Web3-native geoprocessing capabilities, a shared understanding of our planet’s health can emerge - crucial to our transition to sustainability.

![SpatialDataVolume](https://ars.els-cdn.com/content/image/1-s2.0-S0167739X1730078X-gr1.jpg)

Value: sustained increase of yearly spatial data volume, with focus on Sentinel satellite imagery
 
The applications enabled by the spatial data layer of the decentralized web are wide-ranging and revolutionary. As an example, we built a prototype sustainability-linked bond on Ethereum and IPFS, which aligns financial and ecological incentives by adjusting the amount a borrower needs to pay each year based on a measurement of environmental health - in our case, raster images of air quality in London.
We've also designed a spatial governance protocol for connected devices - a system for applying policies to vehicles and other devices based on their geographic position in zones, represented by vector geometries - while preserving the privacy of everyone involved. We built Hyperaware, an alpha implementation of the protocol, on Arweave, IoTeX and Ethereum.
 
These projects have a common requirement: the capability to work with spatial data on the decentralized web. To solve this, we are now working on the Astral Protocol and the GeoDID specification, which will enable developers to build a whole range of new location-based and spatial decentralized applications - dApps that will underpin a globally coordinated Web3 society.
 
Risks mainly center on adoption. If Web3 does not provide a compelling enough reason for traditional users to switch, our work will remain in our crypto bubble, independent of the real world. Our goal is to create a developer experience similar to centralized technologies, with the additional integrity and availability guarantees Web3 offers, along with the option for users to choose self-sovereignty. 


## Deliverables

- Design draft GeoDID Method Specification for raster imagery, based on the SpatioTemporal Asset Catalog spec.
- Build alpha @astral-protocol modules to create and manage GeoDIDs, and associated spatial data assets, stored on IPFS / Filecoin. Build the alpha distributed networking protocol, to enable validation features etc. Build, test and deploy alpha GeoDID resolver smart contracts.
- Research applications and techniques to create spatial querying +cComputing capabilities on IPFS/Filecoin
- Development: prototype most promising result of 3, like a cloud-native geospatial functionality (Cloud-Optimized GeoTIFFs and lambda tile cutter / on-the-fly analytics functionality) on decentralized platforms.


## Development Roadmap

An ecosystem of location-based dApps will benefit from a standard way of representing spatial data in the Web3 universe. By converging on a versatile, extensible standard, different actors in the ecosystem can develop their systems to be interoperable with that specification. 
For this, we are designing the Astral Protocol: a standardized way of working with spatial data in Web3. Within the Astral Protocol we are creating a geographic decentralized identifier, or GeoDID, which is the primitive for representing spatial data assets in Web3. Based on this specification, we will create a verifiable spatial data registry and develop the tools - software modules, interfaces, etc - required for users to perform different tasks necessary to register, share, revise and consume these spatial data structures.

We have prototyped vector GeoDIDs: in the Jurisdiction Registry for Hyperaware, zone administrators can store the vector geometries representing the boundaries of their policy zones on Arweave and control the decentralized identifier with their Ethereum private key. We also prototyped a decentralized spatial finance application - a sustainability-linked bond that accepts analytics derived from raster imagery stored on IPFS, provided by an oracle.
Based on the learnings from these prototypes we are developing a draft implementation of the GeoDID Method Specification, along with the software tools and interfaces needed to manage spatial data assets registered on Astral. We hold self-sovereignty as a core value at Astral, and are designing all of our products and systems to give users the option of complete autonomy, including the right to choose privacy, if appropriate.

### 1. Draft GeoDID Method Specification v0.0

The GeoDID Method Specification v0.0 will “specify the precise operations by which [Geo]DIDs are created, resolved and deactivated and [Geo]DID documents are written and updated”. This will define the specifics of the verifiable spatial data registries we are designing. 

GeoDIDs will be based on the DID specification, extended to have specific attributes relevant to the representation of geospatial data in vector and raster formats. It will be some time before we have v1.0 of this spec - first, we need to design and prototype various draft implementations of the GeoDID Method to fully understand the components of the core specification.

Our engagement with prospective users from insurance, finance, and spatial data domains has driven us to focus our initial draft on raster imagery. Future versions of the specification will address the need to represent vector geometries and multi-geometries in Web3.

We understand that a large community of experts in the spatial data community have been working to solve many of the problems we want to solve with regards to the cataloguing and access of spatiotemporal raster datasets. Rather than try to reinvent the wheel, we have opted to adopt and build on their work. As such, raster GeoDIDs are designed to comply with the SpatioTemporal Asset Catalog specification as closely as possible. This specification, maintained by the Radiant Earth Foundation, provides a common language to describe a range of geospatial information, so it can more easily be indexed and discovered. In addition to the spec, a community of developers has built a range of tools to create, validate and explore these asset catalogs. To contribute to this effort and leverage the fact that the community is already adopting it, GeoDIDs extend the DID specification to comply with STAC.

An advantage to this: any datasets that can be represented in a STAC can be easily identified by a raster GeoDID. Furthermore, STAC was designed to standardize the cataloguing of raster data - we want to make it as seamless as possible to onboard existing STAC-catalogued spatial data onto IPFS / Filecoin. Onboarding appropriately-licensed imagery catalogued on STAC will be very simple.  So we are taking a STAC-first approach to designing raster GeoDIDs.

STAC was designed to be versatile, and can accommodate “Imagery, SAR, Point Clouds, Data Cubes, Full Motion Video, etc”. Deeper research into the compatibility of each of these spatiotemporal asset types on Web3 data storage systems including IPFS / Filecoin is on Astral’s agenda - but we are starting with GeoTIFFs. 
 
Phase 1 on our Development Roadmap is to design and prototype an initial draft GeoDID Method Specification, creating decentralized identifiers for raster spatial data assets. We will extend the DIDs v1.0 specification. Our goal is to map the DID document structure to those of STAC Catalogs and Items.

More specifically, we believe that the STAC Specification will map to the DID document level. The STAC Specification wraps the sub specifications within it. These include: the STAC Collection Specification, which acts as an extension of the STAC Catalog, and provides additional information about a spatio-temporal collection of data; the STAC Catalog, which specifies a structure to link various STAC Items together to be crawled or browsed; and the STAC Item, which is a GeoJSON Feature with additional foreign members - fields for things like time, links to related entities and assets (including thumbnails). 

For simplicity’s sake, since the STAC Collection is viewed as an extension of a Catalog, we will refer to them as the Catalogs to simplify the explanation in relation to the GeoDID. The STAC Catalog can contain several children - Items, or Catalogs which in turn can also contain several more child Catalogs or STAC Items. By definition of the STAC Spec, the Catalogs maintain the control of the  parent/child relations by using the respective links associated with that relation. 
We plan to replicate this functionality of parent/child relationships by using IPLD, specifically the DAG-CBOR codec and CIDs to represent not only the Catalog and Item JSON files, but also the assets endpoints listed in the STAC Item. The idea is to traverse the “tree” of the particular STAC Catalog from its “root node” , convert them from STAC Spec to GeoDID Spec, and serialize the contents, and encoding them into their respective CIDs. Then encoding the list of nested CIDs with the DAG -CBOR codec to group them into an organized data structure.

For example, let's say that we have a STAC Catalog that has one child Catalog within it, and this child Catalog has two STAC Items within it. From the root Catalog we shall recursively fetch the child Catalog from the list of links, in this case we only have one, that represents the child Catalog. Then we  fetch the Item in the child Catalog and fetch the Item’s assets from its respective endpoints (the COG - Cloud Optimized GeoTIFF and other raster image data). We perform a multihash on the fetched data and convert them into their own respective CIDs. Then we convert the STAC Item into a “GeoDID Item”, by adding the DID metadata and header, and then represent the asset CIDs  as service endpoints.

On the way out of the recursive call we encode the “GeoDID Item” document, by using JSON, serializing it to its binary representation that we can store and/or send to someone else. Then we deterministically derive a CID from the serialized  binary  of the GeoDID Item, which gives us a globally unique identifier for that binary, the content addressable CID. Then we convert the parent STAC Catalog of the “GeoDID Item” to a GeoDID as well, we will call this the “Child GeoDID Catalog”. Next we serialize it and convert it to a CID as well. Finally, we repeat the process for the parent STAC Catalog of the “Child GeoDID Catalog”, converting it into a GeoDID, serializing it, and converting it into a CID.  Keep in mind that the GeoDID Item, Child GeoDID Catalog, and GeoDID Catalog, are all represented as a set of linked GeoDIDs.

In the above example, we created an IPLD block for each GeoDID. We then use the CIDs generated for each block to reference their parent GeoDIDs, that is based on the hierarchy of the  STAC Catalog that was uploaded earlier. With the nested list of JSON encoded CIDs representing their respective GeoDIDs, we can use the DAG-CBOR codec to encode the parent child relationship of them, to create a linked data structure that we can use later for ease of access to this particular set of geo-spatial data.

The benefit of this is that we have a data structure containing the GeoDIDs that represents the replicated parent child relationship of the STAC Specification. This makes it easier for users to query a particular data set, and get access to the collection they need. Using IPLD Selectors, the user can go even further and only require the specific GeoDID Items or GeoDID Catalogs that they need, granted the DID Controller grants them access to it. We plan to further this functionality and build several IPLD codecs that will cater to the spatial data community. Codecs that can encode COGs (Cloud Optimized GeoTIFFs) and other native geo-spatial files. We also want to build a codec that can encode our GeoDID Documents to add further functionality, maybe things like PostGIS functionality, etc. 
These codecs are where most of our value proposition will reside in regards to the Protocol Labs ecosystem. That value proposition is bringing geo-spatial tools and enhanced workflows to the protocol labs ecosystem, as well as building a libp2p network that suits the specialized needs of the geo-spatial community in the web3 space. This is the frontier where the geo-spatial community and web3 community collide. 
 
### 2. Prototype @astral-protocol modules 

**@astral-protocol-core**
The @astral-protocol-core package is the core package of the implementation. This is where we will develop the Astral Node Instance with the libp2p, modular network stack. The aim is create a distributed network of nodes that can handle network activity and gossip about the activity on the network. We hope to extend this further, to leverage the protocol negotiation system and the other distributed networking capabilities to optimize the network for specialized big data transport pipelines, similar to IPFS Cluster. In addition, the core package will contain a document handler that will be responsible for authenticating the DID Documents, making requests to read or update DID Documents, the anchoring of the DID Documents,  and their state changes to the Verifiable Spatial Data Registry. The core package will also contain the Pinning API for both IPFS and Powergate, and the geo-did-resolver package. 
@astral-protocol-client
The @astral-protocol-client package provides a way to interact with the Astral protocol without having to actually run the entire protocol locally. It delegates document validation to a remote Astral node (defined in the@astral-protocol-core package) , however the DID controllers can authorize updates to documents from the client, just as in @astral-protocol-core.
@astral-protocol-api
The @astral-protocol-api package will allow for the @astral-protocol-core and @astral-protocol-client packages to communicate to each other.
@astral-protocol-transformer
The @astral-protocol-transformer package is responsible for the transformation from STACs to GeoDIDs. We plan to make this package a standalone package that can be used by other developers to extend the usage of the GeoDIDs in their own packages, or to convert an existing GeoDID into a validated STAC object. This package will also be imported into @astral-protocol-core and @astral-protocol-client. The transformer will enable us to use existing tools for working with the STAC Spec, like the stac-node-validator, sat-utils etc. 

**@geo-did-resolver**
The @geo-did-resolver package will contain our DID method specification and will be responsible for the creation and dereferencing of the GeoDID Documents. This library is intended to use Ethereum addresses as fully self managed Decentralized Identifiers and wrap them in a DID Document. It supports the proposed Decentralized Identifiers spec from the W3C Credentials Community Group. It requires the did-resolver library, which is the primary interface for resolving DIDs. This DID method relies on the geo-did-registry. This most likely will be an extension of the @ethr-did-resolver.

**@geo-did-registry**
The @geo-did-registry package will contain the Ethereum contract code that allows the owner of an GeoDID to update the attributes that appear in its did-document. It exposes an API that allows developers to call the contract functions using Javascript. This most likely will be an extension of the @ethr-did-registry.

### 3. Research: Prototype Applications and Techniques to Create Spatial Querying + Computing Capabilities on IPFS/Filecoin
To realize the full vision of the spatial decentralized web, we must create robust and verifiable ways to analyze the spatial data held on these distributed storage platforms. Again, the spatial data community has been working for many years on techniques for efficiently analyzing these datasets. 
 
In this phase of our Development Roadmap, Astral will research techniques to create spatial querying and computing capabilities on IPFS/Filecoin. Our aim will be to:

Understand the intricacies of Cloud-Optimized GeoTIFFs stored and accessed on Web3. Are additional enhancements required to create an IPFS-optimized Cloud-optimized GeoTIFF? 

Questions:

- Range reads to fetch relevant GeoTIFF pixels from COGs pinned to IPFS.
- A standard way to fetch relevant raster data - "only a few bands, over a small area" (acgeospatial.co.uk).
- Can COGs hosted on IPFS be consumed by standard COG tools, like tiles.rdnt.io? If not, what adaptations need to be made to these tools to interoperate with IPFS-hosted COGs?
- Research: IPFS-native geospatial technologies. (Submit ipfs STAC extension? If warranted.)
IPLD codecs specialized for native geo-spatial files and/or data, that would grant new features that could help foster a new geo-spatial community in the web3 ecosystem.
- Andrew Hill suggested researching unlimited storage, where projects could store any index on the data. Based on the project needs, they pull the index that makes the most sense - get specific IPFS addresses. 
- By index we mean, different ways you aggregate or organize the data. For example, a project can upload several bounding box indices, and our algorithm/codecs will tell you exactly which DAG nodes you need to get to fill the GeoTIFF pixels.
- User interfaces / graphical interfaces / APIs

We have several other ideas that we want to research in depth, but we want to start out with these ones as they will form the basis of our project and will allow us to conduct much more complex research in the future with the work we have already completed.

### 4. Prototype the feasible outcome of 3.

In this phase of the Development Roadmap we will build a functional prototype of an IPFS-native geospatial application. 
 
As an example proof of concept: a decentralized tile server for IPFS-hosted COGs, employing AWS Lambda-like functionality. Recreating marblecutter-virtual / tiles.rdnt.io / lambda-tiler without relying on AWS Lambda, enabling dynamic tile slicing and on-the-fly analytics on raster imagery. This would enable tileservers running on IPFS, providing developers a ZXY endpoint to fetch dynamically-sliced raster tiles from an IPFS-hosted Cloud-Optimized GeoTIFF, so any satellite image could easily be served to a map instance in a browser from IPFS.
 
However, feedback from Andrew Hill at Textile suggests this may be difficult. We would choose which prototype to build based on the research into the feasibility performed in Part 3. 

### Development Roadmap Budget 

Design the raster GeoDID based on STAC Catalogs / Items, so we have a standard way of representing raster datasets in Web3, for self-sovereign users. Time is spanning over a 6 month period after the grant start (placeholder date as the 1st of november of 2020):

| Milestone | Time | Cost |
| --- | --- | --- |
|  GeoDID Method Specification: research and drafting | Start: 01/11/2020 / Finish: 30/11/2020 |  $5,556 |
|  **@astral-protocol** modules to register and manipulate GeoDIDs, including writing raster data and metadata to IPFS / Filecoin. Alpha Distributed Network Development. | Start: 01/12/2020 / Finish: 31/01/2021 | $11,111 |
|  GeoDID manager graphical interface including map and metadata view and edit functionality. | Start: 01/11/2020 / Finish: 31/01/2021 | $16,666 |
|  Research the compatibility of Cloud-Optimized GeoTIFFs with IPFS: can functionality be replicated? If not, would adapting COGs enable that functionality? Develop Web3 COG. | Start: 01/02/2021 / Finish: 28/02/2021 | $5,556 |
|  Prototype spatial operations on data stored on IPFS. Goal 1: replicate PostGIS functionality on data stored on a distributed back end; Goal 2: replicate cloud-native geospatial functionality (mainly Cloud-Optimized GeoTIFFs) on a distributed back end. Recreate marblecutter-virtual using IPFS PubSub; Goal 3: Spatial indexing functionality on top of IPFS? | Start: 01/03/2021 / Finish: 30/04/2021 | $11,111 |


## Total Budget Requested

Total: $50,000

Breakdown of budget:
- Salary: 80%
- Gitcoin bounty for specialist tasks: 15%
- Operations: 5%


## Maintenance and Upgrade Plans

The completion of the GeoDIDs is only the first step of a bigger vision. We will not only continue to use the GeoDIDs ourselves but also use it in conjunction with real-world partners we will cooperate with, e.g. 4 Earth Intelligence. On top of that, we will continue to expand on the fundamentals described above. This can for example include ideas like:

- Build towards v1.0 of the GeoDID Method specification. This will include additional functionality for a DID optimized to identify spatial data assets, including spatial querying, spatial indexing, etc.
- Develop a decentralized autonomous organization for Astral (astralDAO) to govern the protocol and research the incentive schemes that will underpin the platform usage
- Design a vector GeoDID and administration tools, to be used in registering policy zones for spatial governance applications like Hyperaware.
  - How to deal with questions like subsidiarity / sovereignty and topological collisions (i.e. border conflicts) in an intuitive, decentralized way? See Geolocker.
- R&D privacy preserving GeoDIDs, where data owner can restrict access to the data asset, likely using NuCypher proxy re-encryption or something similar
  - Private peerwise DIDs.


# Team

## Team Members

- John Hoopes IV- Researcher and co-lead at astralDAO. MSc Spatial Data Science and Visualisation (Distinction), Technical Director London Blockchain Labs, Developer Advocate Ordnance Survey.

- João Martins - Technical advisor, researcher and co-lead at astralDAO. Full Stack dApp developer on Ethereum with 2 years of experience. First author of an academic article on group-buying on decentralized networks for increased supply chain coordination.

- Jared Childers - Technical advisor and researcher at astralDAO. Backend Engineer + Cloud Ops with 1 year of experience. Knowledgeable in consensus protocols, and experienced in building various tech stacks, with 2 years of experience in web3 space. 

- Robin Davids - Analyst at Rarestone Capital and Strategic and Token Lead at Rarestone Labs. Worked with some of the best performing blockchain startups of 2019 with a focus on fundraising, token economic design and game theory. Investors in these projects include Binance Labs, Bitfinex, Arrington XRP Capital and many more.

- Darien Ford - Cyber Security Specialist, with 1 year of experience in blockchain. Understanding of security, privacy and cryptographic protocols and secure computation. Experience in cyber and crypto/ blockchain intelligence. Security researcher at astralDAO. 

- Jason James - Software engineer at Bloomberg LP. Lead developer on Hyperaware, won Ripple BlockSprint hackathon for “SpringBlock”,  a market optimisation program for the XRP Ledger. Developed KeepHelper, a suite of dApps and an explorer for Keep Protocol. Developed Iotxplorer, a block explorer for IoTeX Network. 

## Team Member LinkedIn Profiles

- John Hoopes IV: https://www.linkedin.com/in/johnrhoopesiv/
- João Martins: https://www.linkedin.com/in/jlmartins/
- Jared Childers: https://www.linkedin.com/in/jared-childers-343b68195/
- Robin Davids: https://www.linkedin.com/in/robin-davids/
- Darien Ford: https://www.linkedin.com/in/darien-ford-495ba713a/
- Jason James: https://www.linkedin.com/in/jason-james-87537410a/

## Team Website

Astral DAO Landing Page - https://astraldao.org/

## Relevant Experience

Project Experience:
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

- Current implementation of our astral protocol - https://github.com/astralDAO/astralprotocol

Previous code repositories for related projects
- KERNEL Smart Green Bond Project - https://github.com/astralDAO/sl-green-bond
- Hyperaware / Geolocker - https://github.com/johnx25bd/ethlondon
- A library of geographic and topological functions in Solidity - https://github.com/johnx25bd/topo-sol
- Hyperaware - https://github.com/wearehyperaware/hyperaware-core