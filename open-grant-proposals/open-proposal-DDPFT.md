# RFP Proposal: `DDPFT consensus`

**Name of Project:**

**Link to RFP:** Please link to the RFP that you are submitting a proposal for.

**RFP Category:**  `technical-design`,`core-dev`

**Proposer:** [@plotozhu](https://github.com/plotozhu)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:**
"YES"

# Project Description

There are two problems for EC: the first one is that algorithm may elect zero or multiple leaders in a round, the second one is that depends an external random value -- which is not pratical yet.

Filecoin had raised SSLE(Secret Single Leader Election), if implemented, SSLE can resolve the first problem, but the second problem not resolved yet: how to produce or get the random value?

DDPFT provides another way to enhance EC,  For the first problem,  a committee can be elected to vote for most-matched nodes.  To collect several nodes info, committee members should pend for a period, which will result block interval -- just as  expected.

For the second problem, with the solution for problem one, we can get blocks in expected interval, we can use the Ri <= Sig(hash(Ri-1,Ai-1)) as new random value, Ri-1 is the random used for previous block and Ai-1 is the codebase of the block.

Liveness and finality also be discussed and proved.


## Value

With DDPFT, multiple candidates will be elected with different priority, it can resist DOS attack and keep Liveness. The new random can only be revealed after new block, and easy to verify. DDPFT will provide high tps, short confirmation time, and it is fair to each miner, with very little power consumption.

There are still some risks should be considered:
1. Is the random safe and unpredictable?
2. Commitee nodes may be attack by ddos
3. Malicious committee node may attack nodes with most priority


## Deliverables

* thesis describes the algrorithm and proof:
  * main workflow
  * detailed description for each step
  * proof
* reference design code or
* Well-documented, human-readable codebase, pluggable and adapted to go-filecoin.

## Development Roadmap

Total Funding Amount: TBD. Please propose a budget in your proposal.

Milestones: Make sure that the values in the Funding column add up to the Total Funding Amount listed above.

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | algrorithm description and proof | TBD | 4 weeks |
| 2 | prototype source code  | TBD | 6 weeks |
| 3 | Completed implementation of DDPFT | TBD | 6 weeks |



## Total Budget Requested

Total budget costs from $200K up to $500K, to achieve a robust and stable version to used in production version

## Maintenance and Upgrade Plans

This algrorithm and its implementation will be open source, and will be designed as a consensus module eash to integrated.

# Team

## Team Members

- Tony zhu
- Jason Jiang
-

## Team Member LinkedIn Profiles



## Team Website



## Relevant Experience

1. Adapted ethereum to dynamic shard blockchains and reached 2000 tps with 64 shards, because of PoW, it was much vulnerable when sharded(2018)


 2. In 2019, we have developed ESWARM - a decentralized storage and distribution network, running on thousands of nodes in China, and served several customs. ESWARM is based on ethereum’s swarm, and optimized for video, especially for apples m3u8 stream. With zipped peer-to-peer receipts, ESWARM can record and calculate data transactions between millions of nodes--we have deployed thousands of full nodes and served millions of light(client) nodes.




## Team code repositories

*	Github repository for shard chain:

>   https://github.com/plotozhu/SideChain/

>   https://github.com/plotozhu/MDC

* Github repository for ESWARM(private now, access key will provided on request):

  https://github.com/plotozhu/MDCMainnet

# Additional Information

Other RFP's, such as zippable receipts for data traffic， player sdk with mixed-CDN will be proposed next
