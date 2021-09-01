
# Open Grant Proposal: `DeFi Marketplace`

**Name of Project:**

**Proposal Category:** `app-dev`

**Proposer:** `aaitor` on behalf of [Nevermined](https://github.com/orgs/nevermined-io/)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

**[Nevermined](https://nevermined.io)** is a data ecosystem solution created by **[Keyko](https://keyko.io/)** that provides the capabilities of building bespoke networks where different entities can share and monetize their data and make an efficient and secure usage of it even with untrusted parties. With the explosion of the data and AI market, entities have the necessity of organizing, understanding, using and sharing their data internally and externally. Nevermined provides Data Sharing & Compute to the Data solutions that unlock data for AI.

As part of our DeFi strategy, we would like to implement an open marketplace based on Nevermined technology where we make accessible different kind of reports about DeFi protocols. The back-office of the solution will be in charge of crawling the different datasets, clean, normalize and aggregate in some cases. As a result of this we plan to generate hundreds of reports daily and we think Filecoin/IPFS would be a perfect storage solution for copying these file.

As part of the marketplace we will offer the following functionality:

- Search and discovery of DeFi reports organize by categories, tags, publication date
- Access to free and/or paid DeFi reports for the users
- Browsing the user history data

In Keyko we have previous experience building marketplaces using Nevermined and bringing user adoption to the different networks where we integrated the technology. Also making easier to get access to DeFi data, can setup this tool as a reference Dapp for the crypto investment community.

## Value

Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:

- What are the benefits to getting this right?
  We think we can bring **users adoption** to Filecoin ecosystem. We plan to download hundreds of files in a daily basis and facilitate the discovery and access to them to the community. Because the nature of these files, they are not going to be very big in size, but because the information they contain (especially some reports) it can be very valuable. Using Filecoin as storage of these valuable reports can help to identify Filecoin as a reference solution as backend of relevant data.

- What are the risks if you don't get it right?
  If the solution is not executed right the main risk is we don't attract enough user adoption.

- What are the risks that will make executing on this project difficult?
  Time to market, there is good interest on DeFi data now. The main difficulty here is if we don't execute quickly and we don't get enough user attention.


## Deliverables

Please describe in details what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished.

### DeFi Marketplace Frontend application

A frontend application implementing the DeFi Marketplace. This application will have the following sections:
  - Home page. Welcome page with some initial information about the Marketplace. The Home page will be divided into different sub-sections:
    * Trending reports - With a list of the Top 3 or 5 or X reports selected as “trending”. This list of reports could be fetched from a database or static file in control by the Keyko Fund team
    * Report Categories - A sub-list of the DeFi report categories (list of categories here)
    * Recently Published - A list of the latest reports published in the marketplace.
  - Search results page. When the user uses the search box or clicks in the category page or similar, a page with the list of results will be displayed. The search results page should allow users to filter and refine the search results by different options:
    * Date of Publication
    * Category (list of categories here)
    * Price (free and range of prices)
  - Details Page. When a user clicks to see a specific report anywhere in the application, this page will be open. In this page we want to show to the user all the information related to a specific asset/report. The complete list of metadata associated with an asset can be found [here](https://docs.nevermined.io/architecture/specs/metadata/#main-attributes).
  - User Reports Page. In this page, the user should be able to see a list of all the reports purchased in the marketplace and download them.
  - Information and Help. Static section where we will show basic information about the Marketplace, what information can be found, payment, etc.


### Back-office

The back-office application in charge of:

  - Downloading and generating the multiple DeFi reports. It will be based in the Keyko Open Source framework [DeFi Crawler](https://github.com/keyko-io/defi-crawler-py)
  - Uploading the different datasets to Filecoin
  - Register the datasets into the Nevermined DeFi Marketplace



## Development Roadmap

Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section).

For each milestone, please describe:
- The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates)

---

### Milestone 0. Research/Architecture

The main objective is to define the architecture and identify the low level integrations between Nevermined, Filecoin and DeFi crawlers. Tasks:

* Definition of the Nevermined integration pattern with Filecoin and the crawlers
* Definition of sequence flows and messages between protocols
* Documentation of the changes required
* Blog post & communication about the Filecoin grant and integration with the Nevermined DeFi Marketplace

Duration: **1 week**


### Milestone 1. DeFi Marketplace product definition

The main objective is to define the complete use case functionality from a user point of view. Tasks:

* Define and detail the features supported by the marketplace
* Lower level definition of the sitemap and flows
* Definition of the user stories
* Definition of the DeFi categories

Duration: **1 week**

### Milestone 2. Marketplace design

The main objective is to create a design implementing the main functionalities described in the previous milestones. Tasks:

* Create the wireframes (Figma) with all the user flows, modals and messages
* Integration of the wireframes in a HTML/CSS frontend application
* Review of the user flows and core functionality

Duration: **2 weeks**

### Milestone 3. Back-office implementation

The objective is to create a group of backend agents able to fetch DeFi data from different protocols. Tasks:

* Implement the boilerplate agent to be reused across all the different report generators
* Implement the core agents for the main DeFi protocols identified
  - Fetching the data
  - Uploading the data to Filecoin
  - Registering the assets into the Marketplace
* Unit and integration testing

Duration: **3 weeks**

### Milestone 4. Marketplace integration

The main objective is to integrate the frontend with the backend providing a totally functional marketplace. Tasks:

* Integrate the different sections with the backend (home, search, details page)
* Integration of download flow allowing users to get access to data stored into Filecoin
* End to end testing

Duration: **3 weeks**

### Milestone 5. Deployment and Communications

The objective is to deploy the Marketplace in a production environment and communicate to the users the benefits of the solution built using Nevermined and Filecoin. Tasks:

* Deploy the off-chain components into Keyko cloud infrastructure
* Deploy the Smart Contracts in a EVM based network
* Validate the integration with Filecoin in a production environment
* Create a blog post explaining the benefits of the solution
* Share with our community via Linkedin, Twitter and Discord

Duration: **1 weeks**


## Total Budget Requested

For us the project described fits into the `Application Development` category with the main objective of bringing usage to Nevermined and Filecoin networks. Taking into account the milestones and duration, we consider a budget of 100.000 USD (or the equivalent in FIL token) would be realistic for the total completion of the project. That budget will be used into:

* Product design (UX, wireframes)
* Development (including architecture, coding, etc.)
* Infrastructure cost for the execution and operations of the off-chain components in the Keyko cloud infrastructure
* Marketing & communications


### Budget breakdown

| Milestone              | Duration| FTE       | Cost  |
|------------------------|---------|-----------|-------|
| #0. Architecture       | 1 week  | 1.5 FTE   | 7.5k  |
| #1. Product Definition | 1 week  | 1.5 FTE   | 7.5k  |
| #2. Marketplace design | 2 weeks | 2   FTE   | 20k   |
| #3. Back-office        | 3 weeks | 2   FTE   | 30k   |
| #4. Integration        | 3 weeks | 2 FTE     | 30k   |
| #5. Deployment & Comms | 1 week  | 1 FTE     | 5k    |
|                        |         |           |       |
| **Total**              | 11 weeks| 10 FTE    | 100k  |


## Maintenance and Upgrade Plans

All the implementations resulted from this development will be Open Source and merged as part of the Nevermined upstream code. As a result of that, the code and functionality will be supported as long the Nevermined components are being used by the community.


# Team

## Team Members

- Ivan Alberquilla (Github: [https://github.com/ialberquilla](@ialberquilla)) - (worked previously in Filecoin/Protocol Labs projects - **Notary App**)
- Rodolphe Marques (Github: [https://github.com/r-marques](@r-marques)) - (worked previously in Filecoin grant - **wave#6**)
- Pedro Gutierrez (Github: [https://github.com/Pedro-vk](@Pedro-vk))
- Enrique Ruiz (Github: [https://github.com/eruizgar91](@eruizgar91))
- Aitor Argomaniz (Github: [https://github.com/aaitor](@aaitor)) - (worked previously in Filecoin grant and Filecoin/Protocol Labs projects)


## Team Member LinkedIn Profiles

- [Ivan Alberquilla](https://www.linkedin.com/in/ialberquilla/)
- [Rodolphe Marques](https://www.linkedin.com/in/rodolphemarques/)
- [Pedro Gutierrez](https://www.linkedin.com/in/pedrogp/)
- [Enrique Ruiz](https://www.linkedin.com/in/enrique-ruiz-garc%C3%ADa-a2123439/)
- [Aitor Argomaniz](https://www.linkedin.com/in/aitorargomaniz/)


## Team Website

- https://www.nevermined.io/
- https://keyko.io/


## Relevant Experience

Beyond our experience during the last 2 years building Nevermined, our team has several years of background in data, blockchain and machine learning. We have worked in several organizations and projects related to these topics. As a proof of that, during the last year and a half our team participated in the delivery network launch of different blockchain projects: (Ocean Protocol/2019, Celo/2020, Filecoin/2020, Bancor/2020, Aave/2021, The Graph/2021). This is complemented with many years of experience building Open Source software in different organizations (Github orgs):

* [https://github.com/keyko-io](@keyko-io)
* [https://github.com/nevermined-io](@nevermined-io)
* [https://github.com/bigchaindb](@bigchaindb)
* [https://github.com/oceanprotocol](@oceanprotocol)
* [https://github.com/stratio](@stratio)
* [https://github.com/xaynetwork](@xaynetwork)
* [https://github.com/filecoin-project](@filecoin-project)
* [https://github.com/celo-org](@celo-org)
* [https://github.com/bancorprotocol](@bancorprotocol)


## Team code repositories

All the Nevermined projects are Open Source and can be found on Github (https://github.com/nevermined-io/).
Here a list of the most relevant repositories:

* https://github.com/keyko-io/defi-crawler-py
* https://github.com/nevermined-io/contracts
* https://github.com/nevermined-io/docs
* https://github.com/nevermined-io/cryptoarts
* https://github.com/nevermined-io/gateway
* https://github.com/nevermined-io/sdk-js
* https://github.com/nevermined-io/sdk-py
* https://github.com/nevermined-io/sdk-java
* https://github.com/nevermined-io/tools
* https://github.com/nevermined-io/cli


# Additional Information

Please include any additional information that you think would be useful in helping us to evaluate your proposal.
