# RFP Proposal: `EC-Eyes`

**Name of Project:**

Consensus Visualization Tool

**Link to RFP:** 

[Consensus Visualization Tool](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-consensus-visualization-tool.md)

**RFP Category:** 

`app-dev`

**Proposer:** 

`hashquark-research`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** 

Yes

# Project Description

Expected Consensus (EC) is a probabilistic Byzantine fault-tolerant consensus protocol. Just as there can be 0 miners win in a round, multiple miners can be elected in a given round. This in turn means multiple blocks can be created in a round. Due to the existence of potential forks in EC, a miner can try to unduly influence protocol fairness. This means they may choose to disregard the protocol in order to gain an advantage over the power they should normally get from their storage on the network. A miner should be slashed if they are provably deviating from the honest protocol.

This is detectable when a given miner submits two blocks that satisfy any of the following “consensus faults”:
(1) double-fork mining fault: two blocks mined at the same epoch.
(2) time-offset mining fault: two blocks mined off of the same Tipset at different epochs.
(3) parent-grinding fault: one block’s parent is a Tipset that provably should have included a given block but does not.

It is possible for forks to emerge naturally in Expected Consensus. EC relies on weighted chains in order to quickly converge on ‘one true chain’, with every block adding to the chain’s weight. This means the heaviest chain should reflect the most amount of work performed, or in Filecoin’s case, the most storage provided.

We want to provide a real-time data visualization platform named **Expected Consensus Eyes (EC-Eyes)** to show the fork behavior that is taking place in the filecoin network. Give miners or professional technicians means to investigate the organic evolution in network activity, observe when bad forks happen and probe when and why they may be occuring.

Our project will give a more comprehensive and user friendly demonstration of the Expected Consensus that can be clearly observed and easily understand to Filecoin users.

## Deliverables

An open-sourced, dual-licensed (under MIT and APACHE2) implementation that:

- provides an interactive visualization of Filecoin consensus viewable in web browsers
- displays new messages, blocks, tipsets, ancestors, forks, miners and related information via live updates
- visualizes what is happening as messages are pooled into blocks forming Tipsets that extend Parent and GrandParent Tipsets as consensus is formed or forks occur
- shows when natural and bad forks occur (e.g. >51% malicous attack)
- provides explainers for what is happening and a glossary of terms

And also:

- has a well-documented, human-readable codebase
- works with a Filecoin node API (lotus, local or remote) and database 
- in mainstream language with a preference for ones that ensure easy long-term maintenance
- is well-tested and usable by a large audience during Testnet and Mainnet
- has tutorials with demo usage
- participate in online or offline activities to promote products in the community

## Development Roadmap

| Milestone No. | Milestone Description                                        | Funding | Estimated Timeframe |
| ------------- | ------------------------------------------------------------ | ------- | ------------------- |
| 1             | Finalize scope, a list of node API endpoints to be used, UI mockups + feedback rounds with the Filecoin DevGrants team, architectural design | $6000   | 2-3 weeks           |
| 2             | Implementation interoperable with a Filecoin node and User tested | $17000  | 4 weeks             |
| 3             | All project deliverables are completed and added to the [Filecoin Shipyard](https://github.com/filecoin-shipyard) (website, documentation, codebase) | $4500   | 2 weeks             |
| 4             | Maintenance and Upgrades during Testnet and Mainnet          | $2500   | 2 weeks             |

### Milestone 1: Finalize scope

Specifics:

The researcher will collate the data metrics to be presented and the corresponding node API endpoints to be used. The product manager and UI designer work together to discuss the interaction design and draw the UI mockups. The development engineer will design the technical architecture diagram. We will keep communicating with Filecoin Dev Grants team about these tasks at any time, and make continuous modifications according to the feedback.

People Involed:

1 Researcher, 1 Product Manager, 1 UI Designer, 1 Development Engineer.

### Milestone 2: Develop

Specifics:

Back-end development engineers collect data and provide real-time API. Front-end development engineers draw web pages and complete interactive graphics development. The front-end and back-end engineers work together for integration testing.

People Involed:

3 Development Engineer, 1 Test Engineer.

### Milestone 3: Delivery

After the deployment goes online, collect user feedback and modify according to the comments. Write documentation and provide friendly user manuals. Open source after code consolidation.

People Involed:

1 Development Engineer, 1 Test Engineer, 1 Product Manager.

### Milestone 4: Maintenance 

According to the function adjustment and upgrade of the main network, make corresponding adjustment on the product.

People Involed:

1 Development Engineer, 1 Test Engineer, 1 Product Manager.

## Total Budget Requested

Total Budget: $30000

## Maintenance and Upgrade Plans

Maintaining the system actively for 1 year. 

# Team

## Contact Info

E-mail:

- Allen: allen@hashquark.io
- Candice: hanfengyi@hashquark.io

## Team Members

Team leader:

- Chen LI (Leo)

Team members:

- Lianghui ZHANG (Allen)
- Fengyi HAN (Candice)
- Qingquan ZHU (Wendy)
- Zeshu WANG
- Zhixiang HU (Tony)
- Xiaoguang ZHANG
- WenFeng NI
- Guobao JIANG
- Xiaofeng ZHOU
- MengZhao SHEN
- Shiyue DAI

## Team Member LinkedIn Profiles

- Allen: https://www.linkedin.com/in/zhanglianghui/)
- Candice: https://www.linkedin.com/in/fengyi-han-23b28a12b/
- Zhixiang HU: https://www.linkedin.com/in/tonyhzx/
- Xiaoguang ZHANG: https://www.linkedin.com/in/晓光-张-7a71b092/
- Wendy: https://www.linkedin.com/in/wendy-zhu-207b19140/

## Team Website

[HashQuark](https://www.hashquark.io/)

## Relevant Experience

### PolkaCube

Besides involved in Incubation for Web3, our project [PolkaCube](https://labs.hashquark.io/#/polka) has received a grant from Web3 Foundation. PolkaCube is a project focused on providing a better staking experience for the validators and nominators of the Polkadot ecology, which include comprehensive on-chain key staking statistics monitoring, optimized staking strategy guidance, wallets integration and DApps to explore the Polkadot ecosystem and more possibilities.

And the Phase1 of PolkaCube Staking Monitoring include many on-chain metrics. The dashboard contains the amount of current validators, circulating supply, staking ratio, inflation, estimated daily reward of each validator, latest block and finalized block number, current epoch and era progress,etc. Charts and graphs also be provided for some indicators.

### EtherPocket

[EtherPocket](https://labs.hashquark-stg.io/#/eth) is an ongoing project that focuses on the transition from Ethereum to Ethereum 2.0. It provides a simple explaination of Ethereum 2.0 staking and a testnet that can be easily implemented. It will help all Ethereum users to participate in staking  with no barriers. More features will be released after the beacon chain is launched.

## Team code repositories

- [HashQuark Research Github](https://github.com/hashquark-research)


# Additional Information

HashQuark, member of [HashKey Group](https://www.hashkey.com/), is a staking service provider focusing on public blockchains built upon the consensus algorithm like PoS and DPoS, and has experiences running nodes for over 40 public blockchains, including Kusama, Cosmos, IRISnet, Tezos, Klaytn, Harmony, TomoChain, Dash, IOST, Cocos, IoTeX, Factom, V SYSTEMS, ChainX, etc. HashQuark Labs is committed to the ecology and research of PoS and staking blockchains, focusing on the development of high-quality PoS projects, and providing a set of tools to enable the industry to better understand and join future products. HashQuark Open Staking Platform, part of HashQuark, has entered into partnerships with the world’s leading crypto wallets and exchanges, joining in the efforts to build a more enabling staking ecosystem. HashQuark now ranks the **No.1** staking provider globally in [StakingRewards](https://www.stakingrewards.com/providers) and has been recently named the best block producer by TokenInsight. 

CEO Leo and other team members attended quite a number of events as keynote speakers/panelists, including HashKey International Digital Asset Summit, Cosmos & IRIS launch party, Bitalk Shanghai Meetup, Global Blockchain (Hangzhou) Forum, Jinse Finance Salon, 2019 2nd Global Graphene Blockchain Developer Conference, Staking Conference, HashKey Night, etc. Other events include Polkadot Shanghai Meetup, Wanxiang Blockchain Labs & PlatON & HashKey Group meetup, and Consensus 2019.