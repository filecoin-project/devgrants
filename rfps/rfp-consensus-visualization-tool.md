# RFP: Consensus Visualization Tool

**Name of Project:** `Consensus Visualization Tool`

**Proposal Category:** `app-dev`

## Project Description

We are seeking proposals for an open source blockchain consensus visualization tool that demonstrates Filecoin's Expected Consensus process. There is currently a chain visualizer at http://user.kittyhawk.wtf:8000/ that visualizes chain activity on the go-filecoin User Devnet. However, it only shows the heaviest (main) chain and does not include potential chain forks. We are specifically looking for a visualization tool that shows the main chain and also other forks.

#### About Expected Consensus (EC)

Expected Consensus is different from blockchain consensus algorithms like Proof of Work and somewhat different from Proof of Stake. It based on the heaviest weighted chain which tracks the most total storage power.

A miner's odds of being elected to produce a block in Expected Consensus is proportional to their storage power in the network, or proven storage in active use. Blocks are produced tracking proven storage in the network. Total proven storage in use is how chains are weighted, and the network eventually converges around the heaviest chain.

Regarding forks in EC, from the Filecoin Specification:

> **It is possible for forks to emerge naturally in Expected Consensus.** Just as there can be zero miners winning a round, multiple miners can be elected as leaders in a given round. **This in turn means multiple blocks can be created per round.** In order to avoid wasting valid work done by miners, EC makes use of all valid blocks generated.
>
> Therefore the Filecoin chain can contain multiple valid blocks at each new chain height. All valid blocks in a round form what is called a **Tipset**. This greatly increases chain throughput by allowing blocks to propagate through the network of nodes more efficiently.
>
> Blocks from a given round are assembled into Tipsets according to certain rules (they must share the same parents and have been mined at the same height). Different miners may mine on different Tipsets because of network propagation delay.
>
> [More on Tipsets in the Spec...](https://filecoin-project.github.io/specs/#tipsets)

Expected Consensus based on Storage Power Mining is a very exciting consensus algorithm in Filecoin. We would like to educate those new to Filecoin on how it works. We are also interested in observing when bad forks happen and probe when and why they may be occuring.

#### Related Tools

- A great example of an interactive tool that shows what is happening on the Ethereum chain is [https//ethviewer.live](http://ethviewer.live/).
- A cool live blockchain sonification and visualization tool from Aleth.io can be seen at [https://audiokitpro.com/the-sound-of-blockchain](https://audiokitpro.com/the-sound-of-blockchain/).
- There are also explorers that show information about uncles and chain reorgs such as [https://etherscan.io/blocks_forked](https://etherscan.io/blocks_forked).

> (If you have other ideas for visualizations or tools that you think would be helpful for observing Filecoin consensus let us know!)

## Deliverables

An open-sourced, dual-licensed (under MIT and APACHE2) implementation that:

- provides an interactive visualization of Filecoin consensus viewable in web browsers
- or alternatively, a proposal to extend and enhance the existing explorer at [http://user.kittyhawk.wtf:8000](http://user.kittyhawk.wtf:8000/) ([Github repo](https://github.com/filecoin-project/filecoin-explorer))
- displays new messages, blocks, tipsets, ancestors, forks, miners and related information via live updates
- visualizes what is happening as messages are pooled into blocks forming Tipsets that extend Parent and GrandParent Tipsets as consensus is formed or forks occur
- shows when natural and bad forks occur
- provides explainers for what is happening and a glossary of terms


And also:

- has a well-documented, human-readable codebase
- works with a Filecoin node API (local or remote) and database or cache if needed to perform the intended workflow
- has tutorials with demo usage
- can be in any mainstream language with a preference for ones that ensure easy long-term maintenance
- is well-tested and usable by a large audience during Testnet and Mainnet

> NOTE: Node API improvements are likely between now, Testnet and Mainnet. We will work with node implementers to document relevant API calls and provide coordinated opportunities for questions and feedback. A filecoin-api-client npm library also exists but is currently out of date.

## Recommended Team

- A small team with strong design and front-end web development skills (please show evidence of this in your proposal)
- Familiarity with interactive visualization libraries (such as d3.js or others)
- Familiarity with using node APIs and a solid understanding of blockchain concepts

## Milestones & Funding

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Finalize scope, a list of node API endpoints to be used, UI mockups + feedback rounds with the DevGrants team, architectural design | TBD | 2-3 weeks |
| 2 | Implementation interoperable with a Filecoin node and User tested | TBD | 4 weeks |
| 3 | All project deliverables are completed and added to the [Filecoin Shipyard](https://github.com/filecoin-shipyard) (website, documentation, codebase) | TBD | 2 weeks |
| 4 | Maintenance and Upgrades during Testnet and Mainnet | TBD | 2 weeks |

If a milestone is not satisfactorily met, we may not continue to fund your team for this project.

## Acceptance Criteria

**Acceptance criteria for Finalize scope, a list of node API endpoints to be used, UI mockups/prototype + feedback rounds with the DevGrants team, architectural design:**
- This milestone's deliverables must represent the final design of the service and its intended interoperability with a Filecoin node API and functionality.
- The design should address the core goals proposed in the description of this brief, with a focus on educating users about how consensus is forming in the Filecoin network.
- The design team should engage in feedback rounds with the DevGrants team on mockups and user flows.
- If additional tools or infrastructure would be helpful for production deployment that is clearly scoped.

**Acceptance criteria for Implementation interoperable with a Filecoin node and User tested:**
- The service must enable the functionality specified in Milestone 1 in at least one mainstream language.
- A functioning demo of the service to be presented and testable by the PL team.
- Additional feedback rounds with the DevGrants team as implementation progresses.
- The tool is tested with various stakeholders and potential users for comprehensibility, utility and engagement.

**Acceptance criteria for All project deliverables:**
- All of the criteria above have been met.
- A developer on our team can use and test the functionality of this service themselves without needing to talk to anyone.

**Acceptance criteria for Maintenance and Upgrades during Testnet:**
- The application must be usable on the Filecoin Network during Testnet and Mainnet.

If a milestone is not satisfactorily met, we may not continue to fund your team for this project.

## Resources

#### Filecoin Network Stats and Explorers

lotus Devnet
- Grafana Network Dashboard: https://lotus-metrics.kittyhawk.wtf

go-filecoin User Devnet
- NetworkStats: https://stats.kittyhawk.wtf
- Dashboard: http://user.kittyhawk.wtf:8010/
- Explorer: http://user.kittyhawk.wtf:8000/

> NOTE: A DevGrant RFP for a comprehensive Filecoin Block Explorer with full search has been awarded to a team in wave 1. In contrast, this RFP is specifically about exploring ways to explain and visualize Expected Consensus in Filecoin.

#### Staging Devnet

In addition to those listed in the [Related Tools](#Related-Tools) section above:

- https://www.blockchain.com/btc/tree/114688199
- https://dailyblockchain.github.io/
- https://reports.aleth.io/
- https://bitnodes.earn.com/nodes/network-map/

----
**Questions about this RFP?**

Contact @eshon or ask in the [Filecoin DevGrants forum](https://discuss.filecoin.io/c/devgrants).
