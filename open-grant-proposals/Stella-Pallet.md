## Open Grant Proposal: Stella Pallet - lightweight integration with Filecoin Storage Market Deals

**Name of the Project**: Stella Pallet

**RFP Category**: app-dev, devtools-libraries, technical-design

**Proposer:**: @yangwao

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

We (Substrate ecosystem) are facing the problem that currently there is no out-of-the-box solution to communicate Parity Substrate based parachains and Filecoin.  We assume that the there is a huge potential for this integration in various fields that include but are not limited to zkProofs storage, Earth Observation value-added data sets (object detection, labeled images, segmented images),  AI/ML models, meta-data structures and various multimedia files. 

With the latest developments in decentralized machine learning and AI such as federated learning we see a lot of potential in integration of Filecoin as the storage layer, Polkadot/Substrate as the consensus layer. 

We don't want to reinvent IPFS pinning industry and we see a lot of potential within Filecoin Storage market deals. Moreover additional value could be brought to Filecoin with the leverage of Substrate smart contracts module in creative ways and embracing various curved bonding models, i.e. web3 revenue primitives.

### Regarding sizes of deep learning.

Deep learning models are getting smaller:

"Incredibly, the smaller architectures to the right don’t perform much worse than the large ones to the left. An architecture like VGG-16 (300–500MB) performs about as well as a MobileNet (20MB) model, despite being nearly 25X smaller." - [Deep Learning has a size problem](https://heartbeat.fritz.ai/deep-learning-has-a-size-problem-ea601304cd8)

![sizeofdeeplearning](https://github.com/starmesh/stella/blob/master/sizes-of-deep-learning.png?raw=true)

Source  [arxiv.org/abs/1605.07678](https://arxiv.org/abs/1605.07678), [neural network architectures](https://towardsdatascience.com/neural-network-architectures-156e5bad51ba), [analysis of deep neural networks](https://medium.com/@culurciello/analysis-of-deep-neural-networks-dcf398e71aae)

With the combination of Substrate and Filecoin we can disrupt the storage industry and ML/AI markets. Primary we are interested into storing trained models and meta-structures for remote sensed data.

[Looks like Filecoin community is in](https://twitter.com/yangWao/status/1240552454418321409) :)

With Stella pallet any Substrate parachain (other modes are solo chain and bridge) can become knowledge capturing **open-silo**.

Stella pallet will enable to bring storage market deals to Substrate chains. Enabling smart contracts to store files in a self-sovereign way. 

Node will no need to do local pinning (potentially resource expensive) or register for API keys of IPFS pinning services.

## Value

- What are the benefits to getting this right?

With Stella Pallet, anybody could create democratised and incentivised data markets i.e. for ML models, but not [under single umbrella corporation](https://tfhub.dev/) and enable Polkadot/Substrate ecosystem access to large file storage and Filecoin. It could help to bootstrap the Filecoin and Substrate to become underlying infrastructure for federated learning.

- What are the risks if you don't get it right?

As both Filecoin and Substrate are dynamic emerging eco-systems there is always a risk in the major spec change or delays due to missing crucial parts. We will continue work to get it delivered to be usable as our building block. 

- What are the risks that will make executing on this project difficult?

Both systems (Filecoin, Substrate) are complex and dynamic, codebases are fundamentally unpredictable, so our aim to design for positive emergence is to find the most efficient and simple way to connect the systems. Lightweight implementation is our priority at the first place.

## Deliverables

Pallet module with KodaDot dashboard module that will be able to use Storage Market Deals.

Person would be able to submit extrinsic to leverage Storage market deal for requester to store their data. 

Docker container that runs Substrate node with Stella Pallet and KodaDot.

Well-documented API for the service conforming to industry best practice.

Tutorial workflow with demo usage and explanation on design.

Will be in Rust and VueJS/Typescript 

Well-documented, human-readable codebase

## Development Roadmap

### Milestone 1 - Project Initialisation and technical design

Team

2 Engineers & 1 Product Manager 

Work

Engineering

- Project initialisation and setting up presence in digital space.
- Research Storage market deals in deep and be aware of possibilities.
- Research on recent trends with [developing Custom Pallet](https://substrate.dev/docs/en/tutorials/build-a-dapp/pallet)
- Learn best practices from [Substrate recipes cookbook](https://substrate.dev/recipes/)
- Basic reputation model research and development

Product Management & Research

- Creating detailed flowchart of pallet communication
- Communication across research teams between Substrate and Filecoin for best approaches
- Diagrams as blueprints for visualisation and building
- Engineering guidance

Time

4 weeks

### Milestone 2 - Implementing technical design

Team

3 Engineers & 1 Product Manager

Work

Engineering

- Implementation of proof of connecting with Storage markets interaction
- Create a simple credit based system
- Creating basic smart contract within [!ink](https://substrate.dev/docs/en/development/contracts/ink#__docusaurus) as default example.
- Implementation of node roles (Store, Fetch, Inspector)
- Implementation of basic reputation system layer (Honest nodes)
- Creating UI for interaction with default extrinsics to KodaDot
- Docker containers for setup and deployment scripts

Product Management

- Communication across research teams between Substrate and Filecoin for best approaches
- Engineering guidance
- Write down lessons learned during development for future iterations

Time 

6 weeks

### Milestone 3  - Smoketests, Testing & Benchmarks

Team

2 Engineers & 1 Product Manager

Work

Engineering

- One full week of smoketests
- One full week of sanity tests
- Preparation for Distribution
- Docker container and deployment scripts for easier use for developers
- Fix found bugs and iterate for first wide-usable alpha pallet version

Product Management

- Putting documentation together
- We will record a screencast that explains how a user can spin up one of those Substrate nodes with Stella Pallet
- Write tutorial with explanation on design

Time

4 weeks

## Total Budget Requested

The requested budget is 45000USD. M1 15000, M2 16000, M3 14000

The grant will partially fund the development costs and fully cover technical design.

Note that the whole project management everyday costs are free of charge due to the good faith of our team.

## Maintenance and Upgrade Plans

- We see this as very first PoC and we will iterate over this version and release as Storage Market Deals will change or Substrate part will adjust with their moving spec. As both sides are heavily bleeding edge, we can't be sure of continuity on actual codebase. Everything we will resolve eventually.
- We plan to fully support project for at least 6 months as we plan use it in current design till new one will obsolete this.
- Support for upgrading to main net when it launches

# Team

## Team Members

- Matej Nemcek
- Arseny Akinfiev
- Viktor Valastin

## Team Member LinkedIn Profiles

- [linkedin.com/in/mnemcek/](https://www.linkedin.com/in/mnemcek/)
- [linkedin.com/in/arseny-akinfiev/](https://www.linkedin.com/in/arseny-akinfiev/)
- [linkedin.com/in/vikival](https://www.linkedin.com/in/vikival)

## Team Website

[Starmesh.xyz](https://starmesh.xyz)

[vue-polkadot.js.org](https://vue-polkadot.js.org) - Try our beta - [dev-vue-polkadot.netlify.com](https://dev-vue-polkadot.netlify.com) 

## Team code repositories

- [yangwao](https://github.com/yangwao)
- [arsenyjin](https://github.com/arsenyjin)
- [vikiival](https://github.com/vikiival)

## Relevant Experience

We've developed KodaDot which is one and only working alternative to web wallets right now for Substrate ecosystem.

Matej and Viktor hacked at [EthBerlinZwei with Fry the Defi](https://devpost.com/software/fry-the-defi-jgo5bc) 

Arseny hacked at [EthberlinZwei with Supercharger Network](https://devpost.com/software/supercharger-network) 

Matej and Arseny met at [EthCapetown in winning Dtok team](https://devpost.com/software/dtok-amfc4e)

# Additional Information

### Technical draft

![stella_draft](https://github.com/starmesh/stella/raw/master/stella_v0.1.png)

Regarding Milestone 2, we are thinking to [embed DEX](https://github.com/alexxuyang/substrate-dex) for exchanging Asset ↔ FIL, not sure right in time of grant application, we will evaluate along the way.

[What is Pallet?](https://substrate.dev/docs/en/development/module/#what-is-a-pallet)

### Starmesh & Team

We are actively doing research in terms of Earth Observation, distributed systems and machine learning for [Starmesh.xyz](http://starmesh.xyz) become real vision.

Matej did few [IPFS hacks](https://github.com/yangwao/ipfs-hypercube) back in 2016, understands IPFS under hood.

### Conclusion and Afterthoughts

From Tensorflow community perspective, Substrate off-chain workers could be used to make [Tensorflow snapshots for future preprocessing](https://www.youtube.com/watch?v=n7byMbl2VUQ). 

[Sizes of Bert pre-trained models](https://github.com/google-research/bert#bert). 

ML training workloads increasingly bottlenecked on data preprocessing.

We would like to be pioneering distributed high performance spacecraft computing for Mars ;)

We have vision that our implementation could lead anyone to plugin in Tensorflow Lite for their workers on Substrate part. That's not part of this implementation.

We also see that most intelligence will be at the edge of the networks. 

"On-device ML could be used on over 250B microcontrollers in the world today". "Smartphones with usable ML are at 1B devices." [Citation TensorFlow Summit 2020](https://youtu.be/HlBGYxO8RaU?list=PLQY2H8rRoyvzuJw20FG82Lgm2SZjTdIXU&t=20978)

We are team behind [KodaDot](https://twitter.com/KodaDot) & [Starmesh.xyz](http://starmesh.xyz)