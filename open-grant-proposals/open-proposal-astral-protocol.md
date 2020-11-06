# Open Grant Proposal: `Astral Protocol`

**Name of Project:** Astral Protocol

**Proposal Category:** `app-dev`

**Proposer:** `j-mars JaredChilders johnx25bd`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Spatial data contains information relevant to locations in the physical world. Different locations have different rules - depending on where you are you have to abide to a different regulatory framework.

To create decentralized applications that leverage spatial data and location information, we need to be able to store and access spatial data in ways that ensure it is simple and reliable for Web3 developers to work with. This is the purpose of the Astral Project: to create the bindings between Web3 and spatial data technologies.

The Astral Project ecompasses the research and development of the GeoDID specification and IPLD encoded geoTIFFs. It will also include the development of the astral packages, which will implement the CRUD operations related to the GeoDID Documents, the pre-processing of the GeoTIFFs, and the development of a front-end explorer.

The GeoDID specification will act as the default web3 specification for working with geo-spatial data sets. Each DID Document will contain several assets endpoints and its respective metadata. The IPLD encoded GeoTIFFs will be implemented through an IPLD codec that will encode the GeoTIFF and enable GET Range requests, by a byte serving technique that will query the proper bytes through IPLD selectors.

The front-end explorer will act as a way to query and test the GeoDID and IPLD encoded GeoTIFFs in a visual way. It will let users upload and view the raster imagery that they would like.

The desired result of this project is to bring geospatial capabilities to the web3 ecosystem, as it is a space that was originally built to be web2 native. By creating the necessary specifications and tools, we can enable the use of geospatial data and analysis within the web3 ecosystem, which, in turn, will create a new wave of decentralized applications and use cases of geospatial data in the web3 space.

Our research and development efforts are showing that innovations at the convergence of these technologies will enable an ecosystem of new, durable tools and mechanisms to re-align human and organizational incentives towards agreed-upon social and environmental objectives.

# Value

Our current value is bringing geospatial capabilities to the Protocol Labs Ecosystem and ultimately the greater web3 ecosystem as well. We believe that Filecoin / IPFS is the best option to serve as the default file system of geospatial data in the web3 ecosystem.
For the past 10 years, the geospatial community has been building a solidifying a native ecosystem in the web2 space. AWS S3, AWS Lambda, GCP BigQuery GIS, to name a few. The go-to standard for storing, retrieving, processing, and analyzing geospatial data, has traditionally been with cloud service providers.

As a result, most of the tooling, workflows, specifications, and projects have been built to compliment the web2 space. The Spatio Temporal Asset Catalog(STAC) specification and the Cloud Optimized GeoTIFFs (COGs) are two of the leading specifications/standards used within the geospatial industry.

STAC is supported by an active community of developers, with involvement from a large range of organizations, including Radiant Earth Foundation, Microsoft, Google Earth Engine, Near Space Labs, L3Harris, etc. In addition, COGs are gaining widespread adoption from the likes of Raster Foundry, GDAL, Google Earth Engine, QGIS, and interoperability with Amazon S3.

The problem is that the aforementioned specification and file standard are only beneficial for the web2 ecosystem. They are optimized and designed to leverage cloud architecture, and location based addresses. When porting these to web3, we see that they become useless because they are not interoperable with CIDs and distributed file systems, as they do not offer web3 leveraged features.

The value we will provide to the Protocol Labs and web3 ecosystem is by building tools, specifications and projects that will enable the geospatial community to further leverage our products as an alternative to the traditional centralized options. We believe that we can give the geospatial community cheaper, faster and better solutions for hosting, sharing and/or retrieving geospatial data.

We then plan to bring traditional geospatial tools and specifications to the web3 universe, by creating geoDIDs to extend the STAC Specification and enabling IPLD encoded geoTIFFs to bring byte served tile imagery to the IPFS ecosystem.

Note in the chart below that there is an exponential annual increase of spatial data being uploaded to cloud storage services. It’s only a matter of time before people within this community will want to leverage this type of data within a distributed file system like IPFS, and/or utilize the data to create innovative applications within the web3 space.

![SpatialDataVolume](https://ars.els-cdn.com/content/image/1-s2.0-S0167739X1730078X-gr1.jpg)

The applications enabled by the spatial data layer of the decentralized web are wide-ranging and revolutionary. We are learning by building - we built a [prototype sustainability-linked bond](https://github.com/astralDAO/sl-green-bond) on Ethereum and IPFS, which aligns financial and ecological incentives by adjusting the amount a borrower needs to pay each year based on a measurement of environmental health - in our case, analytics derived from raster images of air quality in London.

We've also designed a spatial governance protocol for connected devices - a system for applying policies to vehicles and other devices based on their geographic position in zones, represented by vector geometries - while preserving the privacy of everyone involved. We built [Hyperaware](https://hyperaware.io/), an alpha implementation of the protocol, on Arweave, IoTeX and Ethereum.

These projects have a common requirement: the capability to work with spatial data on the decentralized web. But first we need to develop the specifications and tools needed to work with this type of data in the web3 space, without having to opt for a web2 alternative. Once we develop this, we open a brand new world of possibilities within the web3 space, that will allow: developers to leverage geospatial data within their applications; data providers to store and distribute their data efficiently and effectively; data scientists to manipulate, analyze, and share their findings in a more user friendly way.

# Deliverables

- IPLD-Encoded GeoTIFFs, enabling the ability for CID GET Range Requests (Byte Serving capabilities on IPFS and/or Filecoin)
- Draft GeoDID Method Specification for raster and vector GeoDIDs
- Build @astral-protocol modules to manage CRUD operations of GeoDIDs on IPFS / Filecoin
- Develop a Filecoin GeoDID front-end browser/explorer.

# Development Roadmap

An ecosystem of location-based dApps will benefit from a standard way of representing spatial data in the Web3 universe. By converging on a versatile, extensible standard, different actors in the ecosystem can develop their systems to be interoperable with that specification.
For this, we are designing the Astral Protocol: a standardized way of working with spatial data in Web3. Within the Astral Protocol we are creating a geographic decentralized identifier, the GeoDID, which is the primitive for representing spatial data assets in Web3. Based on this specification, we will create a verifiable spatial data registry and develop the tools - software modules, interfaces, etc - required for users to perform different tasks necessary to register, share, revise and consume these spatial data structures.

## IPLD-Encoded GeoTIFFs, enabling the ability for CID GET Range Requests (Byte Serving capabilities on IPFS and/or Filecoin)

A [Cloud Optimized GeoTIFF (COG)](https://www.cogeo.org/) is a regular GeoTIFF file, aimed at being hosted on a HTTP file server, with an internal organization that enables more efficient workflows on the cloud. It does this by leveraging the ability of clients issuing ​HTTP GET range requests to ask for just the parts of a file they need. “COG is the ideal pair for a STAC Item” - the two standards were designed to complement one another.

By pre-processing the GeoTIFF and breaking it into several pieces, a number of internal ‘tiles’ are created inside the actual image, instead of using simple ‘stripes’ of data. With tiles, much quicker access to a certain area is possible, so that just the portion of the file that needs to be read is accessed.

In addition, during the pre-processing multiple ‘overviews’ will be computed and incorporated into the image file - basically several downsampled versions of the same image - so that you can query the highest quality version depending on the level of resolution desired.

In order to achieve this, the client uses HTTP GET Range requests to request the range of bytes that are within the zoom scope, from the server. This method is also called byte serving, where the client can request just the bytes that it needs from the server. On the broader web it is very useful for serving things like video, so clients don’t have to download the entire file to begin playing it.

We would like to develop an IPLD-encoded GeoTIFF, which can hopefully be extended to provide byte serving capabilities to other files types as well. We can do this by developing an IPLD codec that will encode the GeoTIFF, by breaking the GeoTIFF into tiles and their respective overviews, to enable byte served tiles to the client.

Instead of using HTTP GET Range requests, we can enable CID GET Range requests, where the selected/targeted bytes are encoded within the CID, for ease of access from the client. We’re thinking that we can accomplish this by the use of IPLD selectors. This will enable a more effective way to query data from IPFS by significantly reducing downloading times, costs, and resource use - and serve as a step towards IPFS-native geospatial technology.

The IPLD-encoded GeoTIFFs will also be included in the service endpoints in our raster GeoDID Documents.

### Draft GeoDID Method Specification for raster and vector GeoDIDs

The GeoDID Method Specification will “specify the precise operations by which [Geo]DIDs are created, resolved and deactivated and [Geo]DID documents are written and updated” ([W3C DID Specification](https://www.w3.org/TR/did-core/#dfn-did-methods)). This will define the specifics of the verifiable spatial data registries we are designing.

GeoDIDs will be based on the DID specification, extended to have specific attributes relevant to the representation of geospatial data in vector and raster formats. It will be some time before we have v1.0 of this spec - first, we need to design and prototype various draft implementations of the GeoDID Method to fully understand the components of the core specification.

We understand that a large community of experts in the spatial data community have been working to solve many of the problems we want to solve with regards to the cataloguing and access of spatiotemporal datasets. This especially includes identifying the crucial metadata associated with the actual spatial data assets. So, rather than try to reinvent the wheel, we have opted to adopt and build on their work. As such, raster GeoDIDs are designed to comply with the SpatioTemporal Asset Catalog specification as closely as possible. This specification, maintained by the [Radiant Earth Foundation](https://www.radiant.earth/), “provides a common language to describe a range of geospatial information, so it can more easily be indexed and discovered” ([SpatioTemporal Asset Catalogs](https://stacspec.org/)).

Based on this spec, a community of developers has built a range of tools to create, validate and explore these asset catalogs. To contribute to this effort and leverage the fact that the community is already adopting it, GeoDIDs extend the DID specification to comply with STAC.

An advantage to this: any datasets that can be represented in a STAC - including “Imagery, SAR, Point Clouds, Data Cubes, Full Motion Video, etc” - can be easily identified by a GeoDID. Furthermore, STAC was designed to standardize the cataloguing of spatiotemporal data - we want to make it as seamless as possible to onboard existing STAC-catalogued spatial data onto IPFS / Filecoin. Onboarding appropriately-licensed imagery catalogued on STAC will be very simple - and much of it is discoverable through the [STAC Index](https://stacindex.org/). So we are taking a STAC-first approach to designing raster GeoDIDs.

To ease the process of converting between STAC Items / Catalogs and GeoDIDs, our goal is to map the DID document structure to those of STAC Catalogs and Items.

More specifically, we believe that the STAC Specification will map to the DID document level. The STAC Specification consists of sub-specifications, which include: the STAC Item, which is a GeoJSON Feature with additional foreign members - fields for things such as time, links to related entities and assets (including thumbnails and full spatial data assets); the STAC Catalog, which specifies a linked data structure representing various STAC Items, other STAC Catalogs and their relationships; the STAC Collection, which acts as an extension of the STAC Catalog and provides additional information about a spatio-temporal collection of data.

For simplicity’s sake, since the STAC Collection is viewed as an extension of a Catalog, we will refer to them as the Catalogs to simplify the explanation in relation to the GeoDID. The STAC Catalog can contain several children - Items, or Catalogs which in turn can also contain several more child Catalogs or STAC Items. According to the STAC Spec, Catalogs maintain the control of the parent/child relations by using the respective links associated with that relation.
We plan to replicate this functionality of parent/child relationships by using IPLD, specifically the DAG-CBOR codec and CIDs to represent not only the Catalog and Item JSON files, but also the assets which the endpoints listed in the STAC Item resolve to (like GeoTIFF files, ASCII files, MPEGs etc). The idea is to traverse the “tree” of the particular STAC Catalog from its “root node” , convert them from STAC Spec to GeoDID Spec, and serialize the contents, and encode them into their respective CIDs. Then by encoding the list of nested CIDs with the DAG -CBOR codec, we will group them into an organized data structure.

For example, let's say that we have a parent STAC Catalog that has one child Catalog within it, and this child Catalog has two grandchildren STAC Items within it. From the root Catalog we shall recursively fetch the child Catalog from the list of links, in this case we only have one, that represents the child Catalog. Then we fetch the Item in the child Catalog and fetch the Item’s assets from its respective endpoints (ex. the IPFS-OG - IPFS Optimized GeoTIFF, basically the IPLD encoded GeotIFF). We perform a multihash on the fetched data and convert them into their own respective CIDs. Then we convert the STAC Item into a “GeoDID Item”, by adding the DID metadata and header, and then represent the asset CIDs as service endpoints.

On the way out of the recursive call we encode the “GeoDID Item” JSON document, serializing it to its binary representation that we can store and/or send to someone else. Then we deterministically derive a CID from the serialized binary of the GeoDID Item, which gives us a globally unique identifier for that binary GeoDID Document Object, the content addressable CID. Then we convert the parent STAC Catalog of the “GeoDID Item” to a GeoDID as well, we will call this the “Child GeoDID Catalog”. Next we serialize it and convert it to a CID as well. Finally, we repeat the process for the parent STAC Catalog of the “Child GeoDID Catalog”, converting it into a GeoDID, serializing it, and converting it into a CID. Keep in mind that the GeoDID Item, Child GeoDID Catalog, and GeoDID Catalog, are all represented as a set of linked GeoDIDs.

In the above example, we created an IPLD block for each GeoDID. We then use the CIDs generated for each block to reference their parent GeoDIDs, that is based on the hierarchy of the STAC Catalog that was uploaded earlier. With the nested list of JSON-encoded CIDs representing their respective GeoDIDs, we can use the DAG-CBOR codec to encode the parent child relationship of them, to create a linked data structure that we can use later for ease of access to this particular set of geospatial data.

The benefit of this is that we have a data structure containing the GeoDIDs that represents the replicated parent child relationship of the STAC Specification. This makes it easier for users to query a particular data set, and get access to the collection they need. Using IPLD Selectors, the user can go even further and only require the specific GeoDID Items or GeoDID Catalogs that they need.

Just as STAC is designed to complement COGs, GeoDIDs are designed to complement IPFS-Optimized GeoTIFFs, enabling Web3-native geospatial technologies for self sovereign users.

In addition to the STAC-based GeoDIDs for identifying raster spatiotemporal data assets, we will include the option for users to register vector datasets. Vector GeoDIDs will, of course, identify simple vector spatial data assets such as points, lines and polygons, and multigeometries. If possible, we will design the spec to accommodate 3D and temporal vector data assets such as STL files in addition to GeoJSON, SHP and Geopackage data.

We believe it is likely that we will be able to mirror the design of the STAC-inspired raster siblings, but early in our process we will research into potential changes to the spec that may be required by these different assets.

We have experimented with the creation of vector GeoDIDs for the Jurisdiction Registry of Hyperaware - [docs](https://hyperaware.io/demo/docs) and [demo](https://hyperaware.io/demo/jurisdiction-registration). We also prototyped and described an early iteration of the concept as Geolocker at ETHLondon 2020 - [devpost](https://devpost.com/software/geolocker) and [slides](https://docs.google.com/presentation/d/12yECH03OwrQ9ksJba7KSmJDk1F-HEWFr2FVyFWiK2vY/edit?usp=sharing).

Part of phase 1 on our Development Roadmap is to design and prototype a draft GeoDID Method Specification and creating decentralized identifiers for spatial data assets. We will extend the DIDs v1.0 specification.

## Build @astral-protocol modules to manage CRUD operations of GeoDIDs on IPFS / Filecoin

**@astral-protocol-core**
The @astral-protocol-core package is the core part of the implementation which will define the Astral instance. The Astral Instance will grant the user a set of CRUD methods to interact with GeoDIDs. It will contain a **transformer**, that will enable us to use existing tools for working with the STAC Spec, as well as the transformation from STACs to GeoDIDs and vice versa. In addition, the core package will contain a **document handler** that will listen for events from our smart contracts. These events will trigger actions for authenticating the DID Documents, making requests to read or update DID Documents, the anchoring of the DID Documents, and their state changes to the Verifiable Data Registry.

The alpha implementation of the core package will also contain the Pinning API for both IPFS and Powergate, and a resolver method, which will contain our DID method specification and will be responsible for the creation and dereferencing of the GeoDID Documents. This library intends to use Ethereum addresses as fully self managed Decentralized Identifiers and wrap them in a DID Document. It supports the proposed [Decentralized Identifiers spec](https://www.w3.org/TR/did-core/) from the W3C Credentials Community Group. It requires the [did-resolver library](https://github.com/decentralized-identity/did-resolver), which is the primary interface for resolving DIDs.

**`@astral-protocol-contracts`**
The `@astral-protocol-contracts` package will act as the Verifiable Data Registry for the GeoDID Documents as well as the Ethereum contract code for the verifiable spatial data registry.

This standard supports setting a URI value for all the GeoDIDs created and allows for id substitution in client apps. Our URI will have the format of <code>did:geo:{id}</code> (subject to change) and each client app can input the corresponding GeoDID ID to have the full GeoDID representation.

Client dapps of the Astral Protocol will interact with the Spatial Assets Registrar contract to create and register GeoDIDs for users.

## Develop a Filecoin GeoDID front-end browser.

This will be the front-end interface that allows spatial data providers to register spatial assets that follow the STAC spec and transform them into a GeoDID format, managing all the related CRUD operations within the Filecoin network and Ethereum registry smart contracts.

We believe web3 currently has some interaction barriers and we want to make it as frictionless as possible to register a spatial asset for a data provider. Given this, the interface will be built using React according to the latest front end methodologies and will be UX focused, allowing for a seamless and beautiful overview of GeoDIDs using react-mapbox-gl.

It will also allow for a seamless browsing of registered GeoDIDs and their properties, allowing a user to quickly query and find any spatial data asset they find relevant over the Filecoin network. DID Controllers will sign into the client-side dapp with Metamask or a similar gateway. This will automatically fetch the GeoDID(s) they have registered, and provide UI elements enabling them to update metadata or spatial data assets, and to deregister the DID. This architectural design provides the DID Controller full sovereignty over their spatial data assets.

# Development Roadmap Budget

In sum, the roadmap will consider designing the GeoDID specification based on STAC Catalogs / Items, so we have a standard way of representing location data in Web3 for self-sovereign users, and building the initial version of Astral Protocol, which will manage the GeoDID primitive over the decentralized web.

Time is spanning over a 3 month period after the grant start (placeholder date as the 16th of november of 2020). Some parts of the considered milestones will be developed in parallel within the team, hence the conflicting week spaces given:

| Milestone                                                 | Time         | Cost       |
| --------------------------------------------------------- | ------------ | ---------- |
| IPLD-Encoded GeoTIFFs                                     | Weeks 1 - 6  | \$8,333.33 |
| GeoDID Method Specification for raster and vector GeoDIDs | Weeks 1 - 4  | \$4166,66  |
| @astral-protocol modules                                  | Weeks 6 - 12 | \$6,250.00 |
| Filecoin GeoDID front-end browser                         | Weeks 6 - 12 | \$6,250.00 |

## Total Budget Requested

Total: \$25,000 for a 3 month period for the development of the IPFS-Optimized GeoTIFF, a draft GeoDID Method Specification, and the interfaces and packages to create and manage GeoDIDs. This sum will support the two current full-time developers, as well as serve for any gitcoin bounties we intend to launch to support covering the development of specific parts of the protocol.

Breakdown of budget:

- Salary: 80%.
- Gitcoin bounty for specialist tasks: 15%.
- Operations: 5%.

# Maintenance and Upgrade Plans

The completion of the first iteration of the astral-protocol and the GeoDID method specification are only the first steps of a bigger vision. We will not only continue to use the GeoDIDs ourselves but also use it in conjunction with real-world partners we will cooperate with, e.g. 4 Earth Intelligence. On top of that, we intend to continue to expand on the fundamentals described above. This can for example include ideas like:

- R&D privacy-preserving GeoDIDs, where data owners can restrict access to the data asset, using a proxy re-encryption scheme or a secure enclave computation system.
- R&D on furthering the on-demand byte serving capabilities to other large file types, including creating spatial querying capability for vector data (a [Web3 Feature Service](https://en.wikipedia.org/wiki/Web_Feature_Service)?).
- Leverage on Layer 2 networks on Ethereum to cut down substantially on transaction fee costs for the GeoDID registry.
- Build towards v2.0 of the GeoDID Method specification. This will include additional functionality for a DID optimized to identify spatial data assets, including spatial querying, spatial indexing and management of raster imagery.
- Deepen engagement with W3C to promote the adoption of the GeoDID Method Specification by the standard-setting body, and the technology by relevant ecosystem players.

# Team

## Team Members

- John IV- Researcher and co-lead at astralDAO. MSc Spatial Data Science and Visualisation (Distinction) @ UCL Centre for Advanced Spatial Analysis, Technical Director @ London Blockchain Labs, Developer Advocate @ Ordnance Survey.

- João Martins - Researcher and co-lead at astralDAO. Full Stack dApp developer on Ethereum with 2 years of experience. First author of an academic article on group-buying on decentralized networks for increased supply chain coordination. MSc Industrial Engineering and Management (Distinction).

- Jared Childers - Technical advisor and researcher at astralDAO. Backend Engineer + Cloud Ops. Knowledgeable in consensus protocols and experienced in building various tech stacks, with 2 years of experience in Web3 space.

## Advisors

- Robin Davids - Analyst at Rarestone Capital and Strategic and Token Lead at Rarestone Labs. Worked with some of the best performing blockchain startups of 2019 with a focus on fundraising, token economic design and game theory. Investors in these projects include Binance Labs, Bitfinex, Arrington XRP Capital and many more.

- Jason James - Software engineer at Bloomberg LP. Lead developer on Hyperaware, won Ripple BlockSprint hackathon for “SpringBlock”, a market optimisation program for the XRP Ledger. Developed KeepHelper, a suite of dApps and an explorer for Keep Protocol. Developed Iotxplorer, a block explorer for IoTeX Network.

## Team Member LinkedIn Profiles

- John Hoopes IV: https://www.linkedin.com/in/johnrhoopesiv/
- João Martins: https://www.linkedin.com/in/jlmartins/
- Jared Childers: https://www.linkedin.com/in/jared-childers-343b68195/
- Robin Davids: https://www.linkedin.com/in/robin-davids/
- Jason James: https://www.linkedin.com/in/jason-james-87537410a/

## Team Website

Astral DAO Landing Page - https://astraldao.org/

# Relevant Experience

Project Experience:

- APOLLO / ETH Online early Astral Protocol - https://github.com/astralDAO/astralprotocol (Protocol Labs 3rd Place)
- Hyperaware - https://hyperaware.io/
- Sustainability-linked Bond - https://github.com/astralDAO/sl-green-bond

Skills:

- IPFS / Filecoin
- Smart Contract development on Ethereum
- Back-end development with NodeJS
- Front-end development with React
- Experience in Decentralized Identifiers
- Spatial Data Science and Visualization
- Machine Learning

## Team code repositories

- Current implementation of the astral protocol - https://github.com/astralDAO/astralprotocol

Previous code repositories for related projects

- KERNEL Smart Green Bond Project - https://github.com/astralDAO/sl-green-bond
- Hyperaware - https://github.com/wearehyperaware/hyperaware-core |
- Geolocker - https://github.com/johnx25bd/ethlondon
