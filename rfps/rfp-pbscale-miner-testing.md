# RFP: PB-scale Miner Testing

**Name of Project:** `Large Miner Testing`

**Proposal Category:** `mining`

**Proposers:**  @keren117

**Deadline:**  April 15th, 2020 23:59 PDT

## Project Description

As the Filecoin testnet has reached PB-scale and node implementations are nearing protocol-completeness, we are interested in understanding how Filecoin mining software performs on large scale configurations.

We are seeking proposals for designing, implementing and running tests of mining and storage hardware at scale if you are running a mining operation in the 5 PB or more range.

  <sub>*Proposals can be emailed directly to devgrants@filecoin.org and your operation's details will be kept confidential.*</sub>

**The main goal is to understand:**

- Sealing rates for Phase II v23 or v24 proof params PoRep
- Performance of ePoSt on 5 PB+ of sealed data
- What other performance bottlenecks exist
- Critical events in the mining process
- How mining software could be improved for large scale environments
- Seal speed per US Dollar (GB / h)

We are especially interested in measuring the cost and performance of sealing per gigabyte-hour, so proposals that help us understand that metric are encouraged. We also invite additional proposals for more optimal configurations and other useful test plans.

<sub>We are only seeking test plan _proposals_ for April 15th along with verification of any current capacity in the latest testnet storage power table, **not** verification of 5 PB capacity. Please do not purchase hardware at this time as there are upcoming changes to the proofs (PoSt and Actors) in progress before the final draft is ready. Also this proposal is unrelated to testnet phase 2.</sub>


#### Application Requirements 

1. Verification of your current capacity and throughput in the testnet storage power table (e.g. a signed message using the method described in [lotus PR #1292](https://github.com/filecoin-project/lotus/pull/1292))
2. A general test plan description involving lotus or go-filecoin 
3. A description of your 5 PB+ mining operation topology under test (including geographic location)


#### Additional Test Criteria that may be considered

Test plans can optionally also include ways to benchmark your operation with respect to some of the topics listed below:

- Benchmarking tools
  - (open sourcing any custom tools you use would be greatly appreciated and may make your proposal more competitive)
- Hardware configurations
	- CPU, GPU, RAM, SSD and HDDs, Switches if any
	- Performance-based BIOS changes if any
	- Sample metrics: 
      - performance and usage over time
      - any cooling requirements and failure rates
- Networking topology, bandwidth and throughput metrics
	- Description of the network topology
	- libp2p metrics, any relays, etc.
	- Number of peers seen over time
- Filecoin software configurations
  - Sector builder and sizes under test (we are especially interested in 32GB sectors)
  - Sector loss monitoring
  - Daemon - Miner - Seal Worker configurations
	  - Including any shared storage
  - Chain checkpointing and backups
  - Sealing and Proofs metrics
	  - Election PoSt at scale e.g. 1-5+ PB
  - Deal state metrics
  - Blockchain metrics
    - e.g. block production, block propagation times, chain storage, etc.
  - Fork detection and related information
  - Automation or Integration testing
  - Bootstrapping and data ingestion optimizations
  - Queuing strategies if any
  - Caching strategies if any
  - Any software modifications made or additional logging tools
- Supporting software configurations 
	- Storage layer management (we are especially interested in this)
  - e.g. RAIDs, filesystems, any software-defined storage, NAS, SAN 
  - including metrics for I/O per second and use of HDDs vs SSDs
  - your storage growth strategies
	- redundancy strategies if any
	- workflow orchestration tools if any
	- networking configurations and tools
   - (e.g. DDOS sentry, multi-node to multiaddr reverse proxy, etc.)
  - Any additional tools used
- Any other relevant metrics that may be useful
	- e.g. data center, location, comparisons to any other networks you may run
- Finally, we are also interested in financial models such as:
  - cost of mining, broken down by capital expenditure, power costs, datacenter costs, etc
  - profitability assuming fixed FIL price
  - slashing
  - proportion of successful blocks on the main chain
  - any other information that may help us understand financial concerns

 *Based on initial results we may ask for additional tests.*


#### Grant Amounts

The goal of this grant is to incentivize sharing testing knowledge and test results to benefit the mining community and understanding how the protocol works at scale. We will keep any proprietary or personal information confidential but will aim to share general knowledge and results with the wider community.

We are not sure how many miners will apply and have a capped budget for this grant so will decide how to dispense funds fairly once all proposals have been submitted and reviewed.

Multiple teams may be accepted based on the quality of your proposal and verification of your storage capacity. Please also include the geographic location of your operation in the proposal.

Grants can be in fiat or a future grant of FIL or a combination.

## Deliverables

Once your proposal is accepted, below are the planned deliverables:

- A specific and detailed test plan involving lotus or go-filecoin.
- A description of your mining operation topology under test.
- A summary of your testing results including any monitoring and metrics screenshots.
- A write-up of your learnings and recommendations.

Deliverables can be emailed to devgrants@filecoin.org or published in a Github repo.


#### Deliverable Requirements:

- A well-documented, human-readable test plan and summary of results and recommendations.
- A listing of all tools and configurations used with documentation and links to any custom tools
- Large-scale hardware environment tests with a current Filecoin node (lotus and/or go-filecoin if feasible)


## Milestones & Funding

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Test plan finalization and a detailed mining operation topology description | 0% | 1-2 weeks |
| 2 | Initial benchmarks and iteration on testplans | 25% | 1-2 weeks |
| 3 | Potential iteration and discussion of results with the Filecoin team | 25% | 2 weeks |
| 4 | Final results, all deliverables and any additional requests for testing based on learnings | 50% | 2-3 weeks |

If a milestone is not satisfactorily met, we may not continue to fund your team for this project.


**Questions about this RFP?**

Email devgrants@filecoin.org
