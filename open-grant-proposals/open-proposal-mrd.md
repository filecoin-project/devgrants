# RFP Proposal: `DDPFT consensus`

**Name of Project:**

**Link to RFP:** Please link to the RFP that you are submitting a proposal for.

**RFP Category:**  `technical-design`

**Proposer:** [@plotozhu](https://github.com/plotozhu)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:**
"YES"

# Project Description
For retrieve markets of Filecoin, data traffic occurs off chain and results should be submitted to chain. To achieve this, client node should send receipts to retrieving miner on accepted data.

Cause it was designed as every 256KB per chunk and length of receipt should be about 160Bytes, occupying about 0.1% bandwith of total nodes. It would mean that if filecoin had 100T bandwith,  on chain bandwith for receipts  would be about 100G, and tps would reach 100G/160 = 625M, which was unaccpetable.

We present a algorithm call MRD(Mergable Receipts Delivery) to solve this problem.


## Value
With MRD, client node sends receipt to retrieval node on each data chunk, retrieval node collects receipts. Multiple receipts can be merged to one, retrieval miner can merge, pack these receipts and broadcast to chain periodly.
We have tested this algorithm in thounds of retrieval nodes and millions of clients, and proved it worked well.

There are still some risks should be considered:
1. Malicious client nodes may deny to send receipts after data accepted, a machanism should be used to reduce the cheating and a reputation sub-system should be used increase the cost of cheater.
2. Retrieval nodes send packed receipts periodly, corresponded client nodes may out of token that time, and strategies of data traffic should be carefully considered.


## Deliverables

* thesis describes the algrorithm and proof:
  * main workflow
  * detailed description for each step
  * proof
* reference design code or
* Well-documented, human-readable codebase, pluggable and adapted to go-filecoin.

## Development Roadmap

Total Funding Amount: $200K-$550K.

Milestones: Make sure that the values in the Funding column add up to the Total Funding Amount listed above.

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | algrorithm description and proof of mrd | $50K | 4 weeks |
| 2 | prototype source code of mrd  | $100K | 6 weeks |
| 3 | Completed implementation of mrd | $200K | 6 weeks |

Can be processed parallelly
| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | algrorithm description and proof of mrd | $50K | 4 weeks |
| 2 | prototype source code of mrd  | $50K | 6 weeks |
| 3 | Completed implementation of mrd | $100K | 6 weeks |

## Total Budget Requested

Total budget costs from $200K up to $550K, to achieve a robust and stable version to used in production version

## Maintenance and Upgrade Plans

This algrorithm and its implementation will be open source, and will be designed as a consensus module eash to integrated.

# Team

## Team Members

- Tony zhu
- Jason Jiang
- Lili
- Messi Chu

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

NONE
