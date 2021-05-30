# RFP：venus-sealer Task Management System

**Program Name：**“venus-sealer Task Management System”

**Category of Proposal：**“dev-core”

**Initiator:** venus-team


## Program Introduction

At present, Venus still share with lotus-miner the same tasking system, which is unsatisfactory in terms of the utilization of computing resources. In other words, this system cannot make full use of the computing power of our devices due to the fact that the majority of such system resources are wasted. Therefore, we are in need of developing a more flexible and efficient tasking system, which includes task dispatch and control, abnormal task handling and let users themselves to determine tasking and  resource consumption in a reasonable way, thus enhancing computing power of Venus miners.

Two essential modules:  One is venus-sealer tasking system, the other is venus-worker resource consumption and control system. 

Please refer to the details as per below.

- [Track 1: venus-sealer Tasking System](#venus-sealer-Tasking-System)
- [Track 2: venus-worker Resource Consumption System](#venus-worker-Resource-Consumption-System)

### venus-sealer-Tasking-System

--------------------------------

>Notice: We cannot offer the correct timing as to when this function can be released. However, you may assume its existence if it helps on your development.

Must-have functions:

- Reasonable task allocation
- Rational tasking order, thus saving maximum amount of time
- Correct and clear handling of abnormal tasks, reduce loss to full extent or reduce non-effective resource consumption
- Always maintain a desirable amount of task in the pool
- Able to redispatch about-to-expire tasks in a rational way
- Prioritization control in accordance with real orders and garbage orders
- Able to launch multiple task pool management system with properties like idempotence
- Avoid network branching
- Able to endure high concurrency and high load capacity request to a certain extent
- Able to query clearly states of all tasks in the pool
- Able to query correctly whether worker component is in idle or busy state
- Able to calculate suggested task ratio based upon time consumption of tasks in different phases.



### venus-worker-Resource-Consumption-System

-------

- Able to fix cross-machine access of temporary file for worker component
- Able to configurate flexibly how many tasks to take
- Able to configurate flexibly under which phase a task is working
- Able to specify which GPU to use
- Split up the storage of temp files and computing power files
- Users could configurate both temp file and computing power files that caters to different storages
- Worker component can take tasks in an efficient way


## Deliverables

An open-sourced, dual-licensed (under MIT and APACHE2) implementation that:

For Track 1:

- Able to assign tasks in an explicit manner
- Shorten the completion time of tasks
- Able to maintain steady amount of tasks in the pool, freeing worker component from idling state
- Rational handling mechanism for abnormal tasks
- Able to redispatch about-to-expire tasks
- Idempotence for multiple task pools
- High concurrency and high load capacity endurance
- Able to check the state of worker component, idle or busy
- Able to set up how many cores to use


for Track 2:

- Ensure mass file access between workers on different machines won't happen
- Able to configurate flexibly amount of tasks to take and which phase to run under
- Able to specify which GPU to use
- Able to designate storage path of temporary files and computing power files
- Able to setup how many cores to use


for both Tracks:

- Worker component could encapsulate computing power 24 by 7.
- Users could make full use of computing resources by means of configuration.
- Enhance resource usage of devices.
- Demonstration tutorials is in place.
- Develop using mainstream computer language so as to ensure broader code adoption, reuse and interoperability in the future.
- well-recorded and highly readable code database is essential
- Both tracks are fully tested, facilitating security check

>Notice: During the process of perfecting tasking system, you are most welcome to contact us at any time so that the final scheme can be determined.

## Recommended Team

- Have rich experience in mass system development
- familiar with the current mining mechanism of Filecoin
- Willing to propel the development of venus opensource community

## Milestones & Funding

**Total Funding Amount:** TBD. Please propose a budget in your proposal.

**Suggested Milestones:**

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1          | Finalization of working process and system structure | TBD | 3-4 weeks    |
| 2          | Realization of data support system | TBD | 3-4 weeks    |
| 3          | Realization of rewarding mechanism | TBD | 3-4 weeks    |
| 4 | All deliverables are in place (webpage,docs,codebase) | TBD | 2 weeks |
| 5 | Maintenance and upgrading during Testnet and Mainnet | TBD | 2-3 weeks |

## Acceptance Criteria

**Acceptance criteria for Finalize scope, workflow design, architecture & Design mockups:**
- This milestone's deliverables must represent the final design of the service.
- The workflow design should address the core goals proposed in the description of this brief.

**Acceptance criteria for all program deliverables:**

- Meet all the criteria above.
- All developers within our team can use and test the functions of this service without communicating with others outside this team.

**Acceptance criteria for Maintenance and Upgrades:**

- The application must be usable on the Calibration and robust at the Filecoin Mainnet.

We might stop funding your team on this project in case of the milestones listed above are not met with satisfactory result.

## Resource Link

venus-sealer:

- https://github.com/filecoin-project/venus-sealer
