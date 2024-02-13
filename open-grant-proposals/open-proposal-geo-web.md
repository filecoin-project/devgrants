# Open Grant Proposal: `Geo Web`

**Name of Project:** `Geo Web`

**Proposal Category:** `app-dev`

**Proposer:** gravenp

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

"Using the internet" is transitioning from a discrete action to a continuous state. The prevailing smartphone app model and the World Wide Web weren't built for this. We need a new application paradigm for wearable and embedded computers (e.g. smartglasses). This goes beyond a just designing a new user experience model for augmented reality. As the internet pervades every corner of our physical world, the networks that deliver this content will define the trajectory of our economy, politics, culture, and shared values. We are building the Geo Web to help ensure this future is more decentralized, egalitarian, permissionless, and user-centric.

The Geo Web is a set of open protocols and property rights for anchoring digital content to physical land. It's a persistent augmented reality metaverse. Our partial common ownership (aka Harberger tax) land market is the key to creating more allocative efficiency, an engine for permissionless economic opportunities, and democratic governance on the network. Geo Web citizens license digital land parcel NFTs by paying a network fee based on their self-assessed value of the land. Other citizens can force transfer of the land by paying the current self-assessed value. This dynamic market punishes squatters and encourages productive land usage. Network fees are reinvested back into the network, rewarding builders, creators, promoters, educators, and users. The system reinforces positive network effects and can scale elegantly from early adoption to global scale. We believe that we can build a future in which our public good infrastructure out-competes centralized, private good offerings.

The Geo Web's core insight is its economic (resource allocation) model. Our focus is to keep our core protocols agnostic to the infrastructure, tools, and innovation above and below them in the technology stack. IPFS and Filecoin will play an important part in this vision. Geo Web content seekers will be geographically clustered--ideal for peer-to-peer content transmission and storage. IPFS and Filecoin integrations will help us create a more robust, censorship-resistant, and efficient network on which anyone can build and use.

## Value

If we get this right, the Geo Web can become the World Wide Web of the physical world. With the planned integration, IPFS and Filecoin would function as the default p2p transmission and storage protocols for our network. The value would be new users, uses cases, and tools in the ecosystem. We believe that the Geo Web can attract and onboard non-technical users that wouldn't naturally be drawn toward the distributed web. The Geo Web can also become a sustaining force for additional open-source, p2p, and distributed technology development through our Harberger tax proceeds.

The timing and speed of augmented reality adoption is unknown, so we must foster use cases that deliver value on today's devices while continuing to push the boundaries of what's possible.

Our desire to implement distributed technologies could create UX hurdles that drive users toward centralized alternatives if we don't get it right. The smartphone duopoly of Apple and Google looms large. If we (or others) don't build better p2p application and network alternatives, then their OS and app store dominance will continue into the next computing paradigm. We'll end up with continued innovation suppression, rent seeking, censorship, and the attention economy.

## Deliverables

1. v1 Geo Web Spatial Browser (mobile/desktop web app)
2. v2 Cadastre UI (scalable IPFS publishing, pinning, & identity management)
3. Filecoin storage integration (parcel meta-data & linked content archival)
4. Production-ready smart contracts for ETH L2 mainnet
5. Public documentation site

## Development Roadmap

### Milestone #1 - v1 Geo Web Spatial Browser
* Lead = Vishal
* Design/PM = Graven
* Timeline = Week 1 - 4

**Software Functionality**
* Web app accessbile at a public URL
* Modern desktop and mobile web browser support
* Uses "GPS to land parcel to IPFS" to lookup and automatically resolve linked content
* Displays current parcel/location information (parcel name, licensee, for sale price, etc) for user context
* Includes three user-selected viewing modes:
    * Arbitrary URI web content
        * Display URI
        * User can navigate links in frame
    * Media gallery
        * Scroll-able carousel displaying one file at a time
        * Show media name/title
        * Rotatable models for 3D content
    * Augmented reality
        * Displays content through the camera on compatible smartphones

### Milestone #2 - v2 Cadastre UI
* Lead = Vishal
* Architecture Support = Cody
* Design/PM = Graven
* Timeline = Week 5 - 11
    
**Software Functionality**
* Enable IPFS publishing/linking of additional media types (image, video, & audio) to the gallery
* Scalable linked content and Ceramic doc storage options
    * Integration with IPFS browser node for simple, temporary local storage
    * Integration with Textile Buckets Pinning API for user-provisioned nodes
* Move to Ceramic Network mainnet
    * Limited hosted storage of Ceramic documents associated to land parcels
    * Occasional blockchain anchoring of Ceramic documents
* Production identity and wallet management infrastructure
    * 3ID Connect or hosted alternative
    * Allow users to manage keys across wallets addresses
* UI performance improvements
    * Parcel grid rendering
    * General dependency clean-up
    * Mapping tool optimization

### Milestone #3 - Filecoin storage
* Lead = Cody
* Design/PM = Graven
* Timeline = Week 1 - 2

**Software Functionality**
* Developer specification and documentation
* Filecoin archival of user-provisioned Buckets from the Cadastre
    * Includes back-up of user linked content
* Archive parcel meta-data
    * Pinning Ceramic documents
* Limited storage per land parcel funded by the Geo Web

### Milestone #4 - Mainnet-ready smart contracts
* Lead = Cody
* PM = Graven
* Timeline - Week 3 - 12

**Software Functionality**
* NFT DIDs & ownership of root document (2 weeks)
    * Define the method(s) for land parcels "owning" vs merely linking to downstream content
* Research and finalize scaling solution choice (2 weeks)
    * Ethereum-based L2 network (Optimistic or ZK roll-up solution)
* Port and validate current testnet contracts to L2 network (1 week)
* Implement land coordinate grid size that balances granularity/transaction fees on L2 (2 weeks)
* Establish production contract upgrade process and multi-sig (1 week)
* Internal security testing to prepare for an external audit (2 weeks)

### Milestone #5 - Public documentation site
* Lead = Graven
* Timeline = Week 2 - 12

**Software Functionality**
* Gitbook-based documentation site for technical and non-technical users
* Documentation Sections
    * Geo Web Intro (1 week)
        * Introductory material for technical & non-technical users
    * Getting Started (3 weeks)
        * Overview of important concepts, technical requirements for interacting with the Geo Web, & use cases
    * Community & Governance (2 weeks)
        * Covers organizational aspects of the project including our open org vision, DAO, use of SourceCred, & uses of network funds
    * Developers (4 weeks)
        * Deep dive into the details of project concepts, smart contracts, integrations (IPFS, Filecoin, Ceramic, etc), and building on the Geo Web
* Infrastructure, formatting, testing, & production deployment (1 week)

## Total Budget Requested

Milestone | Week # | Budget Requested
------------ | ------------- | -------------
v1 Geo Web Spatial Browser | 1 - 4 | $6,000
v2 Cadastre UI | 5 - 11 | $13,125
Filecoin integration | 1 - 2 | $4,250
Mainnet-ready smart contracts | 3 - 12 | $9,500
Public documentation site | 2 - 12 | $5,500
**Total** | **1 - 12** | **$38,375**

**Use of Funds**
* 88% - Salaries
* 6% - Targeted community bounties/contract work
* 6% - Operations (e.g. hosting, Filecoin storage, etc)

## Maintenance and Upgrade Plans

Our goal is to bootstrap the project into a sustainable open organization that uses Harberger tax funds to support core development, incentivize creators to build on the platform, and reward users for their participation in the network. We believe the nature of our project lends itself to creating permissionless opportunities, but we will likely augment that with a full-time core team.

We are committed to exit to community. We especially want to give Geo Web citizens a voice in the allocation of their "taxes" (at the appropriate level) and envision a democratically governed Geo Web DAO.

This Filecoin grant would go a long way toward realizing and accelerating our mission, but we're committed to building, maintaining, and upgrading this project for the long-haul, regardless.

# Team

## Team Members

* Graven Prest
* Cody Hatfield
* V. Vishal

## Team Member LinkedIn Profiles

* https://www.linkedin.com/in/gravenprest/
* https://www.linkedin.com/in/codyhatfield/
* https://github.com/10dimensions & https://www.sites.google.com/view/synthesise/home?authuser=0

## Team Website

https://www.geoweb.network/

## Relevant Experience

**Graven Prest** - Graven is an experienced founder and product leader. He was previously COO of an IoT edge computing platform startup. He's spent his career managing technical teams and products across industries. His idea for the Geo Web started with the realization that fair/efficient allocation of land was being ignored on geo-spatial augmented reality platforms and has morphed into an obsession about the mechanism design, governance, and user experience of the next internet paradigm.

**Cody Hatfield** - Cody is a builder and a problem-solver. He was the co-founder of various small software startups and a senior engineer at a VC-backed startup before dedicating himself full-time to Web3 a little over a year ago. Cody has been the architect and driving force for Geo Web development since the project started at HackFS in 2020. His expertise includes smart contracts, the IPFS ecosystem, and iOS. In 2020, he received and completed an [IPFS microgrant](https://github.com/ipfs/devgrants/issues/40) to store iOS backups on IPFS.

**V. Vishal** - Vishal is a mechanical and software engineer with a passion for emerging technology including AR, VR, robotics, machine vision, and artificial intelligence. He previously helped build the spatial browser apps for a different geo-spatial AR project. He has built numerous [professional](https://www.sites.google.com/view/synthesise/professional?authuser=0) and [exploratory](https://www.sites.google.com/view/synthesise/experimental?authuser=0) projects focused on AR, mapping, and spatial computing.

## Team code repositories

* https://github.com/Geo-Web-Project
* https://github.com/codynhat
* https://github.com/10dimensions

# Additional Information

Cody and Graven met at the ETHDenver dWeb Summit in 2020 and have pushed the idea of the Geo Web forward through participation in HackFS, the Gitcoin Apollo Fellowship, and engagement with other IPFS/Filecoin ecosystem members like Ceramic Network & Textile. We are passionate about the distributed web and believe we have found our calling for where we can contribute. Regardless of the relative success of the Geo Web, the work that we contribute and the ideas that we explore can benefit the entire Filecoin, distributed web, and blockchain ecosystems.
