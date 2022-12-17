# RFP Proposal: `Filecoin file system CRUD API`

**Name of Project:** Filecoin file system CRUD API

**Link to RFP:** [https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#s3-glacier-api-for-filecoin](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#s3-glacier-api-for-filecoin)

**RFP Category:** `devtools-libraries`

**Proposer:** `mitchellpkt`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** “Yes”

# Project Description

### Motivation

Modern web applications depend on object storage for a variety of data retrieval operations, with S3 being the most popular option due to its ease of use and developer-friendly interface. Next generation Web3 applications would benefit greatly if this interface was extended to be interoperable with modern decentralized persistence layers like Filecoin. This project focuses on this interoperability layer by building an S3-compliant interface with Filecoin to give developers a drop-in replacement for simple CRUD operations so they can easily migrate their existing S3 API calls to Filecoin and IPFS. 

![https://i.imgur.com/YiGCeIt.png](https://i.imgur.com/YiGCeIt.png)

### Overview

The S3 interface has become the standard API for accessing object stores and has numerous open source client and server implementations.  The AWS S3 interface is feature-rich due to its close integration with adjacent cloud offerings, though most users only need a subset of these features to perform simple CRUD operations.  This project aims at delivering that key CRUD functionality in an architecture that can be expanded on to accommodate incremental additional feature sets that would eventually match the full S3 API feature set. As such, it is critical that we focus on core components that will include critical functionality like pagination and other mechanisms needed to succinctly perform CRUD actions. 

For our demonstration, we will modify existing open source software (that interfaces with Amazon’s S3-backed API) to seamlessly interact with our FFS-backed API. A natural extension would be a frontend management platform integrated with a (fiat and/or cryptocurrency) payment system.

## Deliverables

The final deliverable is open-source code (and documentation) for a CRUD API that provides convenient access to the FFS, along with a demo that interfaces with a live instance of our API.

## Development Roadmap

### Milestone 1: Design API spec
We’ll start by designing the basic API specification and functionality, and system architecture. Our API will be a layer on top of the functionality that Powergate offers, to leverage its abstraction of Filecoin market processes.

By the end of the first week, we will share an API design doc to get feedback and ensure that we’re providing stakeholders the specific interfaces needed.  We will produce rough OpenAPI specs to describe the endpoints, along with some of the underlying transaction logic that users would expect from an S3-compliant API. 

Deliverables:
Formalized design docs shared for feedback  
Initial schema design and OpenAPI specifications

Timeline: 2 weeks
Contributors: Marco (Developer), Rob (Infrastructure), Mitchell (Project manager)

### Milestone 2: Infrastructure Deployment
We will initialize IPFS and Filecoin nodes on Insight servers and have MVP of our API deployed for testing and development. Professional DevOps configuration is crucial for usability by future persons and businesses, so we want a consistent and reproducible environment.

To both develop and test the API, we will stand up the necessary infrastructure components including an IPFS node, Filecoin node, and Powergate.  We will use Terraform, Terragrunt, and Ansible to build automated deployments of the infrastructure (though based on the scope of the RFP, we will prioritize building a robust API stack over automating existing components.)

Deliverables:
Immutable deployments of necessary infrastructure in both testing and development environments
Continuous integration pipelines for related components 

Timeline: 1 week
Contributors: Marco (Developer), Rob (Infrastructure), Mitchell (Project manager)

### Milestone 3: API development and documentation
CRUD operations will be developed in Golang and deployed to enable FFS manipulation through the Powergate-backed API. We will be following endpoint standards for a Restful API using OpenAPI. Documentation will be generated for API operators and users.

Deliverables:
RESTful API that transfers data to Filecoin & IPFS.
Live node running on Insight servers.
API deployment and operations documentation

Timeline: 4 weeks
Contributors: Marco (Developer), Rob (Infrastructure), Mitchell (Project manager)

### Milestone 4: Demo with a front-end
We’ll create a demo to show off our RESTful API performing CRUD operations. Potential applications include personal backup tools, archive management, static website deployment, file migration, etc. *(We welcome input on use cases of interest)* 

The demo may be a toy/dogfooded application, as our goals are primarily to ensure the API works as intended, is well documented, and has the right structure to be expanded upon to accommodate additional features. We hope to submit this for the gallery of demos for mainnet launch.

Deliverables:
Demo with live API on the backend

Timeline: 1  week
Contributors: Marco (Developer), Rob (Infrastructure), Mitchell (Project manager)

## Long-term possibilities

This open source infrastructure codebase will make it easy for anybody to spin up an API to interact with the FFS, either for personal use or to integrate with a payment layer for an FFSaaAPIaaS business.

Insight as an organization has several strengths that make us an ideal organization to manage both the development of the API codebase and operations managing publicly accessible endpoints. We are experienced in building automated deployments of blockchain infrastructure components, and deploying reliable public infrastructure at scale. From a development perspective, we have a strong pool of talented DistSys and DevOps engineers who are eager to contribute to exciting open source projects. The Insight ecosystem also includes a “Founders Program” to quickly bring viable products to market.

# Team

## Contact Info

Point of contact: Mitchell Krawiec-Thayer ([mitchell@insightfellows.com](mailto:mitchell@insightfellows.com))

## Team Members

Lead Developer: Marco Rodriguez

-  Decentralized Consensus Fellow at Insight
-  Created data collection system for citizen science with IPFS backend ([video](https://fellows.link/marco_video), [code](https://fellows.link/marco_code))
-  Distributed systems expert with Golang experience
-  Github: [https://github.com/mrodriguez3313](https://github.com/mrodriguez3313)

DistSys DevOps: Rob Cannon

-  Automated deployment expert
-  Infrastructure architect and DevOps engineer
-  GitHub: [https://github.com/robc-io](https://github.com/robc-io)
-  Medium: [https://medium.com/@robcannonxyz](https://medium.com/@robcannonxyz)
 
Principal Investigator: Mitchell Krawiec-Thayer, Ph.D.

-  Head of Research, Developers in Residence at Insight
-  Data Science and Protocol Privacy for Monero Research Lab
-  Currently leading peer-to-peer network security project for Zcash
-  Experience with simulations, modeling, and experimental design/analysis
-  GitHub: [https://github.com/mitchellpkt](https://github.com/mitchellpkt)
-   Medium: [https://medium.com/@mitchellpkt](https://medium.com/@mitchellpkt)

Other Insight contributors:

-  DevOps and Data Engineering mentors will advise on system design and implementation strategy.
-  Code & documentation reviewers will be assigned as milestones near completion.
-  Additional thanks to office and administrative staff for creating a productive workspace.

## Team Member LinkedIn Profiles

-  Mitchell: [https://www.linkedin.com/in/mitchellpkt/](https://www.linkedin.com/in/mitchellpkt/)
-  Rob: [https://www.linkedin.com/in/rob-cannon-21571317/](https://www.linkedin.com/in/rob-cannon-21571317/)
-  Marco: [https://www.linkedin.com/in/marco-a-rod/](https://www.linkedin.com/in/marco-a-rod/)

## Team Website

[https://github.com/insight-infrastructure](https://github.com/insight-infrastructure)

## Relevant Experience

Insight specializes in open-source production-grade infrastructure for distributed systems and blockchain ecosystems. Recent projects involve a distributed network analysis suite ([funded by the Zcash Foundation](https://grants.zfnd.org/proposals/21786689-zcash-observatory)), a blockchain data pipeline and analytics stack ([funded by the ICON Foundation](https://forum.icon.community/t/grant-application-blockchain-analytics-and-data-pipelines/871/3)), load-balanced endpoints ([for Polkadot](https://github.com/insight-w3f/)), and a cryptocurrency security audit ([funded by the Monero community](https://ccs.getmonero.org/proposals/research-post-quantum-monero.html)).

## Team code repositories
-  DevOps tooling: [github.com/insight-infrastructure](github.com/insight-infrastructure)
-  DistSys and Blockchain R & D: [github.com/insight-decentralized-consensus-lab](github.com/insight-decentralized-consensus-lab)
-  R & D for ICON: [github.com/insight-icon](github.com/insight-icon)
-  R & D for Web 3 Foundation: [github.com/insight-w3f](github.com/insight-w3f)
-  Insight Fellows Program: [github.com/insightdatascience](github.com/insightdatascience)

# Additional Information

1) It would be very helpful to have a technical liaison from Filecoin who is available for brief (weekly?) check-ins throughout the grant execution. It’s valuable to have an available contact who can confirm that we’re on the right track, and producing results that are both representative and useful. 

2) We are always happy to iterate the proposal based on your priorities and advice. Let us know what you'd like to see modified!

Thanks for your time,

Mitchell, Marco, and Rob
