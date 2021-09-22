# RFP Proposal: `Backup your blockchain to Filecoin`

## Backup Ethereum using IPLD:

Link to RFP: https://github.com/quorumcontrol/devgrants/blob/master/rfps/new-wave-5-rfps.md

RFP Category: `app-dev` (though somewhere between app and `devtools-libraries`)

**Proposer:** @tobowers (@quorumcontrol)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Ethereum relies too heavily on nodes like Infura. This is known by the community but it is difficult to get around at the moment. One path forward involves using semi-trusted, available *community* storage (like Filecoin) combined with state proofs (see: [eth-proof](https://github.com/zmitton/eth-proof)). IPLD already started down this path with a standard way of storing ETH blocks. Filecoin combined with IPFS/IPLD can start the process of real decentralization from nodes like Infura.

This allows for really interesting use cases. For example: NFT ownership/display *without* having to consult a node like Infura (using block headers and state proofs). Or: sneaker net transactions where connectivity is difficult or banned.

This project will involve a bit of research and a bit of engineering but the goal is to provide long-term storage of the Ethereum blockchain on the Filecoin network and make it available over IPFS (via IPLD).

## Deliverables

The start of the project will deliver Ethereum blocks pinned to Filecoin and available on the IPFS network. This is inherently useful in and of itself as clients can use the block headers and difficulty to validate the longest chain themselves.

The next step is storing the event logs. This step is a bit of research and a bit of implementation. Naively, we can just store the log trie and the events. However, the useful bit is an index. Making logs p2p indexable and available allows for nodes to read a lot from the network without being connected to the Ethereum p2p network at all.

The area requiring the most research is storing the state trie itself. Ideally the project will end up with the full ethereum state and history stored on Filecoin, but the first two steps are the most important for clients and we will consider this a stretch goal.

## Development Roadmap

### Week 1-3: $15,000
Work by two engineers and one project manager.

* stream ethereum blocks to Filecoin and make them available to IPFS using Powergate.
* update the TIP of the chain (IPNS? OrbitDB?)
* research and implement p2p broadcast of the blocks (GossipSub?)

### Week 4-8: $20,000
Work by two engineers and one project manager.

* stream all event logs to Filecoin and make available to IPFS using Powergate
* index event logs (HAMT? OrbitDB?)

### Week 8-10: $20,000
Work by single R&D Engineer

* research incentive layer to make storage self-perpetuating
   * deliverable here is documentation
* research storing full state along with blocks and events
   * deliverable here is (most likely) documentation

## Total Budget Requested

USD $45,000. This amount will be tiered with hitting the milestones.

## Maintenance and Upgrade Plans

Software that we are building as a team could benefit from an architecture like this and so we view it as extremely useful and would love to continue updating. The Ethereum community is large and hopefully there would be many users that could help maintain the software and the data itself.

# Team

## Contact Info

topper@quorumcontrol.com

## Team Members

* Topper Bowers - @tobowers
* Alabo Briggs - @alabobriggs
* Kevin Tharayil

## Team Member LinkedIn Profiles

* Topper Bowers - https://www.linkedin.com/in/topperbowers/
* Alabo Briggs - https://www.linkedin.com/in/alabo-briggs-31744a161/
* Kevin Tharayil - https://www.linkedin.com/in/kevintharayil/

## Team Website

https://quorumcontrol.com

## Relevant Experience

Quorum Control is a long time builder on libp2p and IPLD (with our network Tupelo). @tobowers is a contributor to a few of the various Protocol Labs repositories and maintains an active interest in helping move forward libp2p and IPLD.

In general we've been working in the DLT space for years. We love the community and come at these problems from solid architectural decisions based on long-time general software development.

Quorum Control is building a new way of thinking about L2 and this kind of infrastructure layer would be extremely valuable.

## Team code repositories

* https://github.com/quorumcontrol/tupelo
* https://github.com/quorumcontrol/tupelo-wasm-sdk
* https://github.com/quorumcontrol/dgit
* https://github.com/quorumcontrol/ambient-stack
* https://github.com/quorumcontrol/eth-kms
* https://github.com/quorumcontrol/chaintree



