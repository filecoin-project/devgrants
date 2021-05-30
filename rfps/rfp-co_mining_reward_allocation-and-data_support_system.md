# RFP：Co-mining Reward Allocation and Data Support System

**Name of Project：**“Co-mining Reward Allocation and Data Support System”

**Proposal Category：**“dev-core”

**Initiator:** venus-team



## Project Description

Currently, venus-miner has realized co-mining of multiple miners, that is, the right of block of multiple miners are centralized into one program. All miners added to venus-miner uniformly calculate block rights, select messages, package blocks, and share component services, such as Venus and venus-messages. The current reward allocation is still the original method, which is the one who win the right to mine a block gets block rewards. In order to allow all of the co-mining miners to enjoy stable block rewards, we need to develop a reasonable reward allocation mechanism.

The reward allocation mechanism is inseparable from the support of data. It is necessary to develop a complete data support system, in order to record relevant data, such as miner’s join date, records of block mining and rewards, records of mining failures and records, etc.

This RFP has 2 possible tracks：

- [Track 1: Data Support System](#Data-Support-System)
- [Track 2: Reward Allocation Mechanism](#Reward-Allocation-Mechanism)
  
### Data-Support-System
--------------------------------

>NOTE: We don't yet have exact timing for this functionality, but you can assume their existence if that is helpful to you in development.



This track should have the following functions:

- Record join data and exit time of each miner
- Count the actual block mining and block rewards of a specified miner in a specific time period
- Count the block rights of a specified miner in a specific time period
- Count the number of failures and reasons of block mining by a specified miner in a specific time period
- Count the total number of blocks and block rewards of all miners in co-mining system
- Count the total number of block mining failures of all miners in co-mining system and estimate reward loss


### Reward-Allocation-Mechanism
-------------------------------------------

>NOTE: Currently, in the Filecoin network, the block mining of small miners is very unstable in a short period, and it takes a long time to verify either a miner maintains his lucky value at about 100% or not. Co-mining will centralize the block rights of many small miners, and achieve stable income for miners in a short period of time, which requires the development of a reasonable block reward allocation mechanism.
You can refer to the current distribution methods of traditional mining pools and combine the actual Filecoin economic models, such as PPLNS, PPS, FPPS, etc.


## Deliverables

An open-sourced, dual-licensed (under MIT and APACHE2) implementation that:

For Track 1:

- provides efficient data query function
- has a complete record of FIL circulation
- supports any additional features listed above

For Track 2:

- has multiple sets of allocation mechanisms, and can configure template parameters
- designs this allocation mechanism as fair as possible, and ensure miners could have continuous and stable income
- provides a complete record of the rewards and punishments of FIL, in order to be justified and well-founded

For both Tracks:

- have a complete API
- have tutorials with demo usage
- can be in any mainstream language with a preference for ones that ensure easy long-term maintenance
- have a well-documented, human-readable codebase
- are well-tested and usable by a large audience, in order to be convenient for safety audits

>NOTE: You can contact us anytime during the whole process of improving the reward allocation mechanism, in order to determine the final plan as soon as possible.

## Recommended Team

- A team with strong design and system development skills
- Familiarity with current Filecoin mining mechanism
- A team willing to promote Venus open-source community is preferred.

## Milestones & Funding

**Total Funding Amount:** TBD. Please propose a budget in your proposal.

**Suggested Milestones:**

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Finalize scope, workflow design, architectural design | TBD | 3-4 weeks |
| 2 | Data Support System | TBD | 3-4 weeks |
| 3 | Reward Allocation Mechanism | TBD | 3-4 weeks |
| 4 | All project deliverables are completed (website, documentation, codebase) | TBD | 2 weeks
| 5 | Maintenance and Upgrades during Testnet and Mainnet | TBD | 2-3 weeks |

## Acceptance Criteria

**Acceptance criteria for Finalize scope, workflow design, architecture & Design mockups:**
- This milestone's deliverables must represent the final design of the service.
- The workflow design should address the core goals proposed in the description of this brief.

**Acceptance criteria for Data Support System:**
- All of the requirements in Track 1 have been met.
- Have complete API and verifiable examples.

**Acceptance criteria for Reward Allocation Mechanism:**
- All of the requirements in Track 2 have been met.
- Have complete API and verifiable examples.

**Acceptance criteria for All project deliverables:**
- All of the criteria above have been met.
- A developer on our team can use and test the functionality of this service themselves without needing to talk to anyone.

**Acceptance criteria for Maintenance and Upgrades:**
- The application must be usable on the Calibration and robust at the Filecoin Mainnet.

If a milestone is not satisfactorily met, we may not continue to fund your team for this project.

## Resources

venus-miner:
- https://github.com/filecoin-project/venus-miner

venus:
- https://github.com/filecoin-project/venus
