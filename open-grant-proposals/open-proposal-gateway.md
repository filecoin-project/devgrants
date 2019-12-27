# Open Grant Proposal: `Layer 0 Filecoin Gateway for Scalability`

**Name of Project:** Layer 0 Filecoin Gateway for Scalability

**Proposal Category:** `core-dev`

**Proposer:**  [IPFS-Force](https://github.com/ipfs-force-community) & [bloXroute](https://github.com/bloXroute-Labs/)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `Yes`

# Project Description

The goal of this project is to spead up Filecoin blocks and messages propagation via gateways which could be deployed in backbone network with block agnostic software for transparently and neutrality exchanging Filecoin network information. The gateway design is to leverage the current [IPLD](https://github.com/ipfs/go-ipld-cbor) & [libp2p](https://github.com/libp2p/go-libp2p-pubsub) & [IPFS](https://github.com/ipfs/go-ipfs-blockstore) solution, but also integrate the technology and lesson learned from bloXroute's Blockchain Distribution Network (BDN), to play a role as a high-throughput high-speed relay node for the network.

To achieve business & technology neutrality, this gateway will be open-sourced; and could be deployed in a normal linux system and operated/deployed by third party (or any entity) in a BDN. With the agility of IPFS software stack, the gateway could scale to support other blockchains to avoid locking in risk.

The gateway could run in a standalone way, also could be integrated with any BDN on demand, bloXroute BDN is an option.

This project will be developed by a collaboration team of IPFS-Force and bloXroute.

bloXroute is a network-layer based blockchain scalability solution that allows blockchains to scale on-chain, *without protocol changes*. bloXroute solves the network scalability bottleneck by addressing the substantial time required for all nodes to synchronize when having many widely spread nodes and handling large volumes of TPS. Most importantly, bloXroute by design does this in a neutral way.

Currently, the BDN supports Ethereum and Bitcoin Cash on bloXroute Mainnet. Additional support is being implemented for other blockchains.

IPFS is a global, versioned, peer-to-peer filesystem. It combines good ideas from previous systems such Git, BitTorrent, Kademlia, SFS, and the Web. It is like a single bittorrent swarm, exchanging git objects. 

IPLD is the data model of the content-addressable web. It allows us to treat all hash-linked data structures as subsets of a unified information space, unifying all data models that link data with hashes as instances of IPLD. [Several blockchains](https://ipld.io/implementations/) are already IPLD. 

IPFS-Force is an IPFS/Filecoin community focusing on IPFS ecosystem and Filecoin services development. During Filecoin Devnet and Testnet, IPFS-Force engineers have spending a lot of time in studing specs, participating test, issuing bugs, and contributing code. IPFS-Force has solid experience and good understanding of IPFS/Filecoin network to support this project.

## Value

1. Filecoin nodes could sustain under different countries's complex network environment;
2. Filecoin nodes will be able to propagate and hear blocks and transactions faster;
3. Filecoin blockchain will be allowed to increase the block size and decrease block interval to increase TPS without facing fork problems (if they want);
4. Filecoin will be able to achieve the above without any changes to existing protocol and at low deployment cost.

## Deliverables

**Filecoin gateway for access to a BDN , bloXroute could operate one BDN as option**

1. The fully functional gateway software which could be directly installed.
2. The codebase is open-sourced and dual-licensed under MIT and APACHE2 licenses.
3. Well-documented Deployment Document, User-Guide.


The work involves the following:

- Deep dive the filecoin current block sync protocol implementation;
- Figure out the bottle-neck and root-cause of current protocol;
- Deploy gateway on to backbone network and Testing;
- Integration bloXroute BDN open-sourced p2p protocol with libp2p/IPFS protocol of Filecoin blockchain;
- Conversion of messages and faster propagation;
- Block compression and faster propagation;
- Faster transaction propagation;
- Testing;
- Docker container to run software in docker environment;
- PyPi package for software install using `pip` package manager;
- Documentation.

## Development Roadmap

### Milestone 1

* libp2p protocol and bloXroute p2p protocol analysis
* Architecture design (joint team with bloXroute, filecoin and ipfsforce)
* Design Doc

__Resources__ :

1. Product Owner - 10 hours
1. Architect - 20 hours
1. Developer - 20 hours

### Milestone 2

* Implementation of Filecoin gateway without block/message compression

__Resources__ :

1. Product Manager - 10 hours
1. Architect - 20 hours
1. Developer - 200 hours

### Milestone 3

* Implementation of Filecoin gateway with block/message compression

__Resources__ :

1. Product Manager - 10 hours
1. Architect - 20 hours
1. Developer - 250 hours

### Milestone 4

* Testing Filecoin gateway

__Resources__ :

1. QA - 40 hours
1. Developer - 20 hours
1. cloud vm and bandwith fee for dedicated filecoin gateway


## Total Budget Requested

Total Budget: $38,500.00    
please review the above milestone and we can settle down the budget accordingly. 
 
 | Role | Rate/Hr | HC | Man-Hour | Man-Week | Price |
 |-----|---------|----|-----------|-------------|------|
 | Architect | $100 | 1 | 60 | 1 | $6,000.00|
 | PO | $50 | 1 | 10 | 1 | $500.00|
 | PM | $50 | 1 | 20 | 1 | $1,000.00|
 | Developers| $60 | 2 | 490 | 12 | $29,400.00 |
 | QA| $40 | 1 | 40 | 1 | $1,600.00 |

## Maintenance and Upgrade Plans

Maintenance provided by the team will include the following:
1. On-demand bug fixing;
1. Upgrades during changes of Filecoin blockchain p2p protocol;
1. Upgrades during changes of BDN protocol;
1. Documentation updates as software evolves.

# Team
This is a collaboration project, to be developed by [IPFS-Force](https://ipfser.org/) and [bloXroute](https://github.com/bloXroute-Labs/)

## Team Members

- Sponser: Steven Li, Eyal Markovich
- Architect: Steven Li (ipfsforce), Sergey Ilin (bloXroute), ?(filecoin)
- Project Manager: Katrina Liu
- Product Owner: Taosheng Shi (Stone)
- Developer: Caesar Wang, Karol Stolarski
- QA: Yunrui Duan

## Team Member LinkedIn Profiles

- Steven Li: https://www.linkedin.com/in/xinlee/
- Eyal Markovich: https://www.linkedin.com/in/eyalmarkovich/
- Katrina Liu: https://www.linkedin.com/in/katrina-liu-a16a84127
- Taosheng Shi(Stone): https://www.linkedin.com/in/taoshengshi/ 
- Caesar Wang: https://www.linkedin.com/in/麟-王-97a836149/   
- Sergey Ilin: https://www.linkedin.com/in/sergeyilinn/
- Karol Stolarski: https://www.linkedin.com/in/karol-stolarski/

## Team Website

- [IPFS-Force](https://ipfser.org/)
- [bloXroute](https://bloxroute.com/)

## Relevant Experience

Filecoin relevant resource:
- IPFS: https://ipfs.io/   
- IPLD: https://ipld.io/   
- libp2p: https://libp2p.io/   
- filecoin lotus: https://github.com/filecoin-project/lotus

Example of gateways for Ethereum and Bitcoin:

- GitHub: https://github.com/bloXroute-Labs/bxgateway
- Docker Hub: https://hub.docker.com/r/bloxroute/bxgateway
- PyPi: https://pypi.org/project/bloxroute-gateway/

## Team code repositories

Filecoin lotus: https://github.com/filecoin-project/lotus
Example of gateways for Ethereum and Bitcoin - [bloXroute Gateway repository](https://github.com/bloXroute-Labs/bxgateway)
