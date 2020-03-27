# RFP Proposal: `Reputation Service`

**Name of Project:** `Reputation Service`

**Link to RFP:** [Reputation System](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-reputation-system.md)

**RFP Category:** `app-dev`

**Proposer:** [@viaruc](https://github.com/viaruc)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

This project's purpose is to build a service that allows Filecoin clients and other network participants to evaluate miners' quality of service. The **Reputation Service** purpose is to be thoroughly integrated into storage/retrieval workflows and tracking all reputation related information on-chain.

Due to not extensive knowledge of Filecoin architecture we've made a number of assumptions:
* `Miner Actor` state currently does not track miner's performance
* `Miner Actor` state is extendable and can be repurposed
* New `Actors` can be introduced on-chain
* Push and Pull Flows have a clear identification of which Deal they are part of

Having these assumptions in mind our goal is to deliver a service that would work together with [Push](https://filecoin-project.github.io/specs/#push-flow) and [Pull](https://filecoin-project.github.io/specs/#pull-flow) flows. Complementing these flows with an additional step that would store deal resulting information in `Miner Actor State` or a new `Actor` (that will be introduced in the scope of our development) that will have a reference to a `Miner Actor`. This way we could not only store information defined in RFP requirements but other reputation related data (deal-making events, calculated risk-score, etc) which will be used to define the quality of provided services.

This approach will allow us to introduce machine learning driven recommendations as well as add more information about miners as the Filecoin ecosystem grows.

## Deliverables

* A Golang service with an RPC capability for web app interactions 
* Sample web application for demonstrating the flows of leaving a feedback
  * for pushing a file 
  * for pulling a file
* Well documented **Reputation Service** API
* Well documented human-readable codebase of both **Reputation Service** and sample web application 

## Development Roadmap

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | **Goal:** Finalize scope, workflow design, and architectural design <br> **Amount of members:** 2 | 12800 USD | 2 weeks |
| 2 | **Goal:** Reputation Service implementation <br> **Amount of members:** 2 | 51200 USD | 8 weeks |
| 3 | **Goal:** Sample web application demonstrating interoperability of go-filecoin and the reputation  service <br> **Amount of members:** 1 | 6400 USD | 2 weeks |
| 4 | **Goal:** All project deliverables (website, documentation, codebase) <br> **Amount of members:** 3 | 9600 USD | 2 weeks |

The estimated timeframe for each milestone is a matter of current understanding of reputation system scope. It might change depending on the scope definition in the 1st milestone.

## Total Budget Requested

Total requested budget - 80000 USD

Estimated time of delivery - 12 weeks.

## Maintenance and Upgrade Plans

We are looking forward to maintaining the implementation for the upcoming year. Addressing bugs and issues of the delivered functionalities. 

While the current implementation only enables clients to evaluate miners on their own we are looking forward to implementing a memory-based recommender system to suggest clients better fitting miners.

# Team

## Contact Info

Contact e-mail: [slava@monetha.io](mailto:slava@monetha.io)

## Team Members

- [Martynas Adomaitis](https://www.linkedin.com/in/martynas-adomaitis-27b83845/) - Full-stack Developer 
- [Dmitrij Koniajev](https://www.linkedin.com/in/dimchansky/) - Backend Developer
- [Tadas Kepalas](https://www.linkedin.com/in/kepalas/) - DevOps
- [Slava Ruckis](https://www.linkedin.com/in/slava-ruckis/) - Team Lead

## Team Website

* https://monetha.io/platform
* https://www.monetha.io/reputational-identity

## Relevant Experience

The Monetha platform utilizes an underlying protocol that is meant to solve the lack of transparent reputation for digital identities - https://github.com/monetha/verifiable-data-layer. With this mindest in mind can establish digital identities and transparently collect feedback and build-up the reputation profile in a censorship-resistant and transparent manner allowing clients to get more confidence when evaluating the reputation of individual miner.

Pilots worth noticing:

* Reducing Digital Divide Challenge by Unicef - https://github.com/monetha/unicef-challenge-reducing-digital-divide
* Reputational Identity - https://www.monetha.io/reputational-identity (demo video https://www.youtube.com/watch?v=y6RAUSuYReA)
* Hacking adoption at EthBerlinZwei 2019 - https://github.com/viaruc/decentralized-ticket-management

We closely work with teams behind [Perun Network](https://www.perun.network/) and [Wolfram Blockchain Labs](https://www.wolframblockchainlabs.com/)

## Team code repositories

* https://github.com/monetha
* https://github.com/monetha/go-verifiable-data
* https://github.com/monetha/js-verifiable-data
* https://github.com/monetha/unicef-challenge-reducing-digital-divide
