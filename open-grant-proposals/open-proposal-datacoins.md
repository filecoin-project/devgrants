# **Open Grant Proposal: Datacoins**

Name of Project: Filecoin as a data/API/algorithm marketplace (a design for layer-2, data-backed tokens that would make data open, tradable, and programmable).

Proposal Category: Choose one of core-dev, app-dev, devtools-libraries, **technical-design**, docs

Proposer: chrisamccoy

Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?: "Yes".

# **Project Description**

Full presentation here: [https://docs.google.com/presentation/d/1--LD-9jRipSeRv5VBiCSie0pSwCq7_jumL7a9H1_ngc/edit#slide=id.g6cac93f92c_0_94](https://docs.google.com/presentation/d/1--LD-9jRipSeRv5VBiCSie0pSwCq7_jumL7a9H1_ngc/edit#slide=id.g6cac93f92c_0_94)

A data/API/algorithm marketplace built on top of Filecoin so the (developer) world can build with each other’s data. 

According to [IDC](https://www.seagate.com/files/www-content/our-story/trends/files/idc-seagate-dataage-whitepaper.pdf), the world will emit 175 zettabytes of data by 2025. Most of this data will be created and consumed in silos, so their value diminishes soon after they are consumed. Second, AI/ML models use large amounts of training data and data "cleaning" companies such as ScaleAI [raise millions of dollars](https://techcrunch.com/2019/08/05/scale-ai-and-its-22-year-old-ceo-lock-down-100-million-to-help-label-silicon-valleys-data/?guccounter=1) in funding to structure and label data for AI applications. Lastly, most applications use APIs and algorithm instances from other applications or services for their business logic, so “data” in this sense also comes from APIs and algorithms they use. So there is clearly a need for a marketplace where developers can discover the “type” of data they need, purchase access to the data, and use the data in their applications. A “value chain” where the value of the data progressively improves as it is refined is possible with this model. Data discoverability will also preserve the value of the data for a longer period of time. This makes “data is the new oil” a reality.

The proposed data marketplace has the following salient features:

* Any existing app/service can be migrated onto the Filecoin marketplace with minimal changes. Contrast this with existing dApp platforms, which require complete rewrite of apps/services in their platform-specific programming languages.

* The marketplace provides services to encrypt sensitive information at rest and a host of anonymization schemes. Developers don’t have to reinvent the wheel on this. This enables even sensitive information to be traded without data privacy concerns.

* The marketplace provides services to help developers categorize their data for easy discoverability on the marketplace. Once categorized, anyone can discover and purchase the data.

* The marketplace provides services to help developers classify their data where each class of data can be priced differently based on their value.

* Data categorization and classification allow fine-grained access control over the data.

* Existing guarantees that Filecoin provides are automatically extended to the data, which "decentralize" the “trust” in the data compared to centralized cloud service providers.

* Filecoin token is used as the medium of exchange not only among apps/services to purchase data, but also by customers who use their services. This increases the value of the token over time.

* A new miner type — Compute Miners — expands Filecoin ecosystem. These miners act as edge computing nodes providing scalable infrastructure for data and compute-heavy services of the future.

## **Value**

Filecoin bills itself as "a Decentralized Market for Storage". From a value-proposition perspective, “cost” will be the primary factor for why consumers may be interested in Filecoin vs traditional cloud-based storage providers. Since the cost of cloud storage is continually dropping “low-cost” will not be a winning advantage for a long time. There is a need to expand the Filecoin ecosystem in such a way that it can serve developers, who in turn will bring more data into the ecosystem. However, just providing a convenient API for developers is not sufficient. A full-fledged data marketplace is needed for reasons described above. The marketplace should work in such a way that data buyers can discover, purchase, and use the data without human intervention. This proposal makes Filecoin a “data cloud”.

* What are the benefits to getting this right?

    * Filecoin will become the "go to" place for data needs. It expands from the current “decentralized storage and retrieval infrastructure” to “decentralized data cloud”, while fully supporting running any data and compute-heavy services written in any language. 

    * The current generation of dApp platforms are limited to writing smart contracts and DeFi apps. They are not cost effective to run even a small web application. This proposal, if successfully executed, will make Filecoin the first decentralized platform that supports running any application.

* What are the risks if you don't get it right?

    * If the implementation is subpar or it so happens that there is actually no demand for "clean" data, the risk is lost investments. This proposal doesn’t alter anything on existing Filecoin implementation, so it doesn’t affect in any way how it will continue to function in its current capacity. 

* What are the risks that will make executing on this project difficult?

    * The scope of this project is pretty big, but no bigger than a typical enterprise solution. The proposal uses proven distributed computing primitives, which mitigate the implementation risks. 

    * No new research on cryptography or any other area is necessary. However, economic models must be built to validate the cost of hosting apps and services on the marketplace because the "Filecoin data cloud" infrastructure must be profitable to developers.

## **Deliverables**

* 3 months:

    * Create a PoC to demonstrate end-to-end functionality of the Marketplace.

    * Demonstrates at least 2 services creating tradable data.

    * Data categorization, classification, seach, and data purchase APIs.

    * Simple data purchase flow with a wallet.

    * Data access authorization after the purchase.

* 6 months:

    * Define Secure Container interface.

    * Allow packaging of existing apps/services to integrate with the Marketplace.

    * Persistence plugin interface to allow storing different *types* of data.

    * Interface to define data categorization.

    * Interface to define data classification.

    * Interface to mark sensitive information in the data.

    * Interface for Anonymization schemes.

    * Interface for data encryption at rest.

* 9 months:

    * Data discovery API.

    * Data price negotiation API.

    * Wallet integration to purchase data.

    * Wallet integration to store authorization for purchased data.

    * Start developing the economic model for Compute, Storage, and Retrieval Miners.

    * Prepare for the Marketplace Testnet.

* 12 months:

    * Work with the developer community to onboard the first set of apps/services on the Marketplace.

    * Stabilize APIs and wallet interfaces.

    * Run the Testnet with a sample set of apps/services.

    * Security and code audit.

    * Performance and scalability evaluation.

* 15 months:

    * Compute, Storage, and Retrieval Miners are more likely to be on full-fledged cloud service providers. 

    * Develop models on the cost of hosting apps/services to help developers price their data.

    * Prepare for the second Testnet to test the economic models for developers and miners.

* 18 months:

    * Bug fixes, including security and economic model issues.

    * Launch the Marketplace Mainnet.

## **Development Roadmap**

* See deliverables above.

## **Total Budget Requested**

Engineering resources and skills required.

1. Software architect (SA) - 1. Oversees end-to-end delivery from architecture to deploying the Marketplace Mainnet.

2. Backend engineers (BE) - 4. Expertise in distributed computing, NoSqL, databases. Proficiency in Javascript/Node.js or Python.

3. DevOps (DO) - 2. Experience in Docker, Kubernates, AWS deployment.

4. UI engineers (UI) - 3. Experience in WebApp development (React, Vue.js, etc.) and hybrid mobile app development.

5. Project Management (PM) - 1. Community development and communication, evangelization, etc.

6. UX design - 1. This is a part-time position to design the interactions for data purchase, wallet integration, data explorer, and so on.

7. Legal and compliance - A part-time position to shape the regulatory and legal framework for open and tokenized data as it relates to Filecoin’s own framework and philosophy. We have a lot of experience working at the intersection of data, policy, and regulation. This is an important component to scope out as the project is being developed. 

* 3 months:

    * 1 SA, 1 BE, 1 PM, 1 Legal/Compliance

    * Expenses also include hosting, SaaS infrastructure, legal and accounting

Baseline amount requested: $30k per month, $90k total

Maximum amount requested: $50k per month, $150k total

* 6 months:

    * 1 SA, 2 BE, 1 DO, 1 UI, 1 PM, 1 UX

For discussion

* 9 months:

    * 1 SA, 4 BE, 2 DO, 3 UI, 1 PM, 1 UX

* 12 months:

    * 1 SA, 4 BE, 2 DO, 3 UI, 1 PM

* 15 months:

    * 1 SA, 4 BE, 2 DO, 3 UI, 1 PM

* 18 months:

    * 1 SA, 4 BE, 2 DO, 3 UI, 1 PM

Hosting:

* Hosting account on AWS to deploy the Marketplace application. The cost breakdowns will be available once the architecture and implementation details are approved.

## **Maintenance and Upgrade Plans**

Once delivered, anyone in the community can volunteer to maintain and support the system. If there are no volunteers available, a core team will continue to support the system. 

# **Team**

## **Team Members**

* Chris McCoy (PM, Research, Product strategy)

* Rag Bhagavatha (CTO, Chief Architect)

* Charles Belle (Legal/Compliance)

* Jay Pal (DevOps and backend engineering)

## **Team Member LinkedIn Profiles**

* Chris McCoy: [https://www.linkedin.com/in/chrisamccoy/](https://www.linkedin.com/in/chrisamccoy/)

* Rag Bhagavatha (CTO, Chief Architect) [https://www.linkedin.com/in/raghavendra-bhagavatha-4b168b4/](https://www.linkedin.com/in/raghavendra-bhagavatha-4b168b4/)

* Charles Belle [https://www.linkedin.com/in/charlesbelle?trk=people-guest_people_search-card](https://www.linkedin.com/in/charlesbelle?trk=people-guest_people_search-card)

* Jay Pal: [https://www.linkedin.com/in/laitkor](https://www.linkedin.com/in/laitkor)

## **Team Website**

Please link to your team's website here (make sure it's https)

[http://storelabs.org](http://storelabs.org)

New site (not yet released)

[https://dl.dropbox.com/s/npq39bt3yqpwgoj/sc_website_new_v84.jpg](https://dl.dropbox.com/s/npq39bt3yqpwgoj/sc_website_new_v84.jpg)

About page (not yet released)

[https://dl.dropbox.com/s/79ogxra37oyzqfn/sc_website_about_v48.jpg](https://dl.dropbox.com/s/79ogxra37oyzqfn/sc_website_about_v48.jpg)

Stake $STORE page (not yet released)

[https://dl.dropbox.com/s/0bwxjxbmxc8a7m2/sc_website_mine-store_v44.jpg](https://dl.dropbox.com/s/0bwxjxbmxc8a7m2/sc_website_mine-store_v44.jpg)

Staking Calculator

http://research.storelabs.org/stakingcalculatoradvanced

## **Relevant Experience**

At Store Labs, the team has architected a similar platform. The team members have experience in distributed computing, enterprise applications, and decentralized economic and governance model designs.

## **Team code repositories**

[https://github.com/StorecoinProject](https://github.com/StorecoinProject).

# **Additional Information**

Please include any additional information that you think would be useful in helping us to evaluate your proposal.

**Background:** We've been big fans of Juan and your team since the very beginning. As for STORE (formerly Storecoin), we started as a zero-fee base layer project coordinated by a ratified and democratic-inspired governance. As we realized how a sufficiently decentralized and scalable computing platform could form the foundation for data being represented by a private key at scale, we evolved our research to go very deep into tokenized data -- or what we have been calling *datacoins*. We've stayed relatively quiet as a project to-date, have been milestone-focused from day one, and have been able to build an early, long-term base of future miners along the way. Here's a bit more on the economics of staking $STORE. [https://research.storelabs.org/stakingcalculatoradvanced](https://research.storelabs.org/stakingcalculatoradvanced)

Our north star has been believing that once data is tokenized, it's then open and tradable for any other developer in the world to build with. The more structured and labeled data is, the more machine learning-ready it is (and therefore the more valuable). The result is that data becomes a tradable and a programmable commodity. Said another way, we think that we figured out how tokenized data can be profitable for the developer, the miner, and even the end user. Our work builds off of our Cost of Computing Research at [http://research.storelabs.org/cpt](http://research.storelabs.org/cpt) (you'd enjoy this paper). 

Below is a high level proposal of what we could bring to Filecoin. We have a world class CTO/distributed systems engineer who would lead the implementation. 

Outside of the Ecosystem Fund, we're very open to exploring ways to long-term collaborate with Filecoin. Let me know if you want to jump on a quick strategy call to dive in a bit more. I can send you over a STORE deck too. 

STORE Proposal for the Filecoin Ecosystem Grant

**Filecoin today**

- Decentralized storage for data.

- "File"-based storage metaphor.

- Targeted at anyone to store their data and retrieve them later on -- mostly by the owners of that data.

- Incentivizes storage providers with their token.

**Our proposal:**

- Aimed at app developers who want to trade data produced by their apps/services.

- App data is "structured" and it can be discovered by anyone including other app developers to use in their apps.

- Support all data formats -- "structured data", not just file-based data. The data can be "pre-created" -- streaming data, files, JSON, binary, etc. -- by apps or apps can publish their APIs or algorithms, which when invoked create the data "on-demand."

- This allows developers to sell data in API and algorithm format, not just pre-created data.

- This in turn allows API to API or algorithm to algorithm communication where cooperating apps can create "pipelines" of "continually refined" data.

- Developers price their data/APIs/algorithms in FIL.

- The infrastructure provides libraries for end to end encryption and anonymization capabilities for sensitive information.

- Developers "bring" their existing apps into the new infrastructure without having to rewrite the whole app. Only a shim is required for existing services to sell their data/APIs/algorithms on Filecoin.

**Why?**

- This proposal turns Filecoin into more than a file-based storage system.

- It targets developers with the ability to sell/use data to/from other apps. This builds an open data marketplace, which in turn fuels the need for more storage.

- Filecoin will become the go-to place for any data where data can be purchased and used programmatically without human intervention.

- Addition roles (in addition to the current storage providers, etc.) are created for certifying data quality, etc., so the ecosystem can grow exponentially.

