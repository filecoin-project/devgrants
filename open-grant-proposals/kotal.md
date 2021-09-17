# Open Grant Proposal: `Kotal - Simplifying IPFS and Filecoin DevOps`

**Name of Project:** Kotal

**Proposal Category:** `devtools-libraries`

**Proposer:** [@mFarghaly](https://github.com/mFarghaly)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Blockchain DevOps (BlockOps) is hard, that's why dApps, wallets and exchanges are using Centralized closed-source Node as a Service solutions like [Infura](https://infura.io) to intgerate with Blockchain networks like Ethereum, IPFS, and Filecoin networks.

90% of Ethereum dApps traffic is going through Infura, and when [Infura goes down](https://www.theblockcrypto.com/post/84232/ethereum-infrastructure-provider-infura-is-down), all dApps lose access to Ethereum network. `We want to prevent this from happening in IPFS and Filecoin networks`.

Kotal is building open-source deployment and integration platform. To make it easy for anyone to deploy highly available, self-managing, self-healing nodes across multiple protocols including IPFS and Filecoin.

[Demo](https://www.youtube.com/watch?v=ziRstkvbiP8&ab_channel=MostafaFarghaly) of Kotal Dashboard

## Value

Using Kotal anyone with little or no BlockOps experience can :

- Deploy highly available self-managing self-healing nodes
- Deploy nodes across multiple Blockchain protocols like IPFS and Filecoin
- Switch between networks like Mainnet, Calibration, Butterfly ... etc
- Join public and private networks
- Deploy nodes on private clouds like `OpenShift`
- Deploy nodes on public clouds like `GCP`, `Azure`, or `Digital Ocean`
- Expose secure integration endpoints
- Manage keys and secrets

## Deliverables

Kotal operator that can be deployed into any Kubernetes cluster and watches for Filecoin and IPFS manifests to be deployed.

## Development Roadmap

### Deploy IPFS Nodes `1 week`

- Define custom kubernetes resource IPFS Node
- Document IPFS Node resource
- Develop IPFS node kubernetes controller that watches for any IPFS Node resource and deploy a go-ipfs `v0.7.0`.
- Create IPFS Node kubernetes custom resource samples

### Deploy IPFS Swarms `2 days`

IFPS swarm is a set of IPFS nodes connecting to each other with different pin set

- Fetching node peer address
- Document fetching peer address
- Allow connecting to peers to form swarms

### Deploy IPFS CLusters `2 weeks`

IPFS is a set of IPFS nodes connecting to each other with the same pin set

- Create custom kubernetes resource IPFS Cluster Peer
- Documnent IPFS Cluster Peer resource
- Develop IPFS Cluster kubernetes controller that watches for any IPFS Cluster resource and deploy a go-ipfs `v0.7.0` node with ipfs-cluster-peer `v0.13.1`
- Document the process of joining IPFS cluster

### Deploy Filecoin Nodes `1 week`

- Define custom kubernetes resource Filecoin Node
- Document Filecoin node custom resources
- Experiment with the possiblility of running multi-client `lotus`, `venus`, `forest`, and `fuhon` nodes
- Develop Filecoin Node controller that watches for any Filecoin Node resource and deploy a lotus `v1.0.4` node.

### Filecoin Backed Pinning Service `1 week`

- Document the process of creating Filecoin backed pinning services using kotal operator and custom resources.

<!-- - The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates) -->

## Total Budget Requested

$30,000 USD

## Maintenance and Upgrade Plans

Kotal team will continue to support and maintain all the code produced for this dev grant. Kotal is not a side project, we're working on it fulltime.

# Team

## Team Members

- Mostafa Farghaly - Founder @ Kotal, ex-Consensys

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/mostafa-farghaly/

## Team Website

https://kotal.co

## Relevant Experience

We have +10 years of combined experience in :

- Smart contract development
- Blockchain DevOps
- Blockchain protocol engineering
- Crypto wallet and exchanges development
- Blockchain dApps development

## Team code repositories

- https://github.com/kotalco
- https://github.com/mFarghaly

# Additional Information

- Kotal won HackFS developer tools prize
- Kotal is backed by Protocol labs and ConsenSys
