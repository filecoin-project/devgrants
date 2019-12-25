# Open Grant Proposal: `Layer 0 Filecoin Gateway for Scalability`

**Name of Project:** Layer 0 Filecoin Gateway for Scalability

**Proposal Category:** `core-dev`

**Proposer:** [IPFS-Force](https://github.com/ipfs-force-community) & [bloXroute](https://github.com/bloXroute-Labs/)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `Yes`

# Project Description

The goal of this project is to spead up Filecoin blocks and messages propagation via gateways which could be deployed in backbone network with specifically designed software for transparently exchanging Filecoin network information. The gateway design is not to replace the current p2p solution, but playing a role as a high-throughput high-speed relay node for the network.

This gateway could be deployed in a normal linux system. It also allow Filecoin to leverage the bloXroute Blockchain Distribution Network (BDN), the “layer 0 scalability solution”, to reduce network latency, improve mining efficiency and eventually enable more use cases.

This project will be developed by a collaboration team of bloXroute and IPFS-Force.

bloXroute is a network-layer based blockchain scalability solution that allows blockchains to scale on-chain, *without protocol changes*. bloXroute solves the network scalability bottleneck by addressing the substantial time required for all nodes to synchronize when having many widely spread nodes and handling large volumes of TPS. Most importantly, bloXroute by design does this in a neutral way.

Currently, the BDN supports Ethereum and Bitcoin Cash on bloXroute Mainnet. Additional support is being implemented for other blockchains.

IPFS-Force is an IPFS/Filecoin community focusing on IPFS ecosystem and Filecoin services development. During Filecoin Devnet and Testnet, IPFS-Force engineers have spending a lot of time in studing specs, participating test, issuing bugs, and contributing code. IPFS-Force has solid experience and good understanding of IPFS/Filecoin network to support this project.

## Value

1. Filecoin nodes will be able to propagate and hear blocks and transactions faster;
2. Filecoin blockchain will be allowed to increase the block size and decrease block interval to increase TPS without facing fork problems(if they want);
3. Filecoin will be able to achieve the above without any changes to existing protocol and at low deployment cost.

## Deliverables

**Filecoin gateway for access to bloXroute BDN.**

1. The fully functional gateway software which could be directly installed.
2. The codebase is open-sourced and dual-licensed under MIT and APACHE2 licenses.
3. Well-documented Deployment Document, User-Guide.


The work involves the following:

- Integration with p2p protocol of Filecoin blockchain;
- Conversion of messages from Filecoin p2p protocol to bloXroute BDN open-sourced p2p protocol;
- Block compression and faster propagation;
- Faster transaction propagation;
- Testing;
- Docker container to run software in docker environment;
- PyPi package for software install using `pip` package manager;
- Documentation.

## Development Roadmap

### Milestone 1

* libp2p protocol and bloXroute p2p protocol analysis
* Architecture design
* Design Doc

__Resources__ :

1. Product Owner - 10 hours
1. Architect - 20 hours
1. Developer - 20 hours

### Milestone 2

* Implementation of Filecoin gateway

__Resources__ :

1. Product Manager - 10 hours
1. Architect - 20 hours
1. Developer - 450 hours

### Milestone 3

* Testing Filecoin gateway with bloXroute Testnet

__Resources__ :

1. QA - 40 hours
1. Developer - 20 hours


## Total Budget Requested

Total Budget: $37,000.00
 
 | Role | Rate/Hr | HC | Man-Hour | Man-Week | Price |
 |-----|---------|----|-----------|-------------|------|
 | Architect | $100 | 1 | 40 | 1 | $4,000.00|
 | PO | $50 | 1 | 20 | 1 | $1,000.00|
 | PM | $50 | 1 | 20 | 1 | $1,000.00|
 | Developers| $60 | 2 | 490 | 12 | $29,400.00 |
 | QA| $40 | 1 | 40 | 1 | $1,600.00 |

## Maintenance and Upgrade Plans

Maintenance provided by the team will include the following:
1. On-demand bug fixing;
1. Upgrades during changes of Filecoin blockchain p2p protocol;
1. Upgrades during changes of bloXroute BDN p2p protocol;
1. Documentation updates as software evolves.

# Team
This is a collaboration project, to be developed by [bloXroute](https://github.com/bloXroute-Labs/) and [IPFS-Force](https://ipfser.org/)

## Team Members

- Sponser: Eyal Markovich, Steven Li
- Architect: Sergey Ilin
- Project Manager: Katrina Liu
- Product Owner: Stone Shi
- Developer: Sergey Ilin, Caesar Wang
- QA: Yunrui Duan

## Team Member LinkedIn Profiles

- Eyal Markovich: https://www.linkedin.com/in/eyalmarkovich/
- Steven Li: https://www.linkedin.com/in/xinlee/
- Sergey Ilin: https://www.linkedin.com/in/sergeyilinn/
- Katrina Liu: https://www.linkedin.com/in/katrina-liu-a16a84127
- Stone Shi: https://www.linkedin.com/in/taoshengshi/ 
- Caesar Wang: https://www.linkedin.com/in/麟-王-97a836149/   

## Team Website

- [bloXroute](https://bloxroute.com/)
- [IPFS-Force](https://ipfser.org/)

## Relevant Experience

Example of gateways for Ethereum and Bitcoin:

- GitHub: https://github.com/bloXroute-Labs/bxgateway
- Docker Hub: https://hub.docker.com/r/bloxroute/bxgateway
- PyPi: https://pypi.org/project/bloxroute-gateway/

## Team code repositories

Example of gateways for Ethereum and Bitcoin - [bloXroute Gateway repository](https://github.com/bloXroute-Labs/bxgateway)
