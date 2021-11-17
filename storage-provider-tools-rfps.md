# Storage Provider (SP) Tooling Ideas

We are seeking proposals for the following RFPs for SP Tools, SP Tutorials and SP improvements.


*Have a question about any of these RFPs? Email devgrants@filecoin.org*

-----

&nbsp;

## *Storage Provider Tooling Ideas*




  - [Monitoring Tool for Miners](#monitoring-tool-for-miners)
  - [Sector Checker](#sector-checker)
  - [Auto-Add New Sectors based on Capacity](#auto-add-new-sectors-based-on-capacity)
  - [Miner Hardware Profitability Calculator](#miner-hardware-profitability-calculator)
  - [Miner Transaction History and Earnings Predictor](#miner-transaction-history-and-earnings-predictor)
  - [Gas Tool and Guide](#gas-tool-and-guide)
  - [Mining Task Pool for Smaller Miners](#mining-task-pool-for-smaller-miners)
  - [CID Indexing Tool for Miners](#cid-indexing-tool-for-miners)
  - [Miner Docs and Community Guides](#miner-docs-and-community-guides)

&nbsp;

*Thanks to @ribasushi, @charles, @RobQuistNL, @stuberman, @jennijuju and @hsanjuan for suggesting and giving feedback on all these initial ideas.*

&nbsp;

### Monitoring Tool for Storage Providers

#### Overview

A tool, script or tutorial to set up monitoring for miner GPU, CPU, memory and other resource and performance metrics, ideally using Prometheus and Grafana or other common open source tools.

#### Description

This could help miners gather resource and performance snapshots from their system using a Prometheus metrics endpoint (or also Telegraf) and display them in a dashboard UI (like Grafana).

Metrics could also include average time to process sectors, baselines for each storage mining phase, etc. A sample tool to implement this may include:

- https://github.com/zhebrak/nvidia_smi_exporter is a simple wrapper around running the `nvidia-smi` command using the `--query` / `--format` flags to produce a .csv of the data and then exposes it as a Prometheus end point
- Telegraf also supports `nvidia-smi`

Options:

1) *Lightweight monitoring for smaller storage providers* - to support smaller SPs we’d really like to see a simple monitoring setup that could be run on a single machine already running a miner.

2) Dedicated server - miners with more mining machines may also want to add a database to keep track of incoming datasources and potentially query historical data (e.g. PostgresDB or InfluxDB could also be used - Influx also has a plugin for `nvidia_smi`).

&nbsp;
-----
&nbsp;

### Sector Checker

Improve the Lotus Sector CLI to help SPs more intuitively find failed sectors and fix or remove them.

#### Description

Storage Providers need to monitor their sectors and respond to sector health issues. Lotus supports a Sector CLI ([code here](https://github.com/filecoin-project/lotus/blob/master/cmd/lotus-miner/sectors.go)). However it needs to be run separately and then sector logs scanned to address issues.

The CLI tool could be enhanced to check for failed sectors then list them and their recent logs or messages.

If a failed sector is found, the CLI could offer various next steps, such as the option to verify again that a sector has failed as a sanity check, or to show it’s location so manual repair could be attempted. Otherwise it could be removed permanently.

[Automatic sector repair steps could also be added later if there are smart solutions proposed for how to do this.]

Example enhanced sector menu:
```
1) Verify sector
2) List failed sectors
3) Show sector logs and location
4) Remove sector permanently
```

&nbsp;
-----
&nbsp;

### Auto-Add New Sectors based on Capacity

A tool to help SPs automatically pledge new sectors or manage new storage deals as their machine capacity allows.

#### Description

Adding new sectors is currently managed manually. The tool could evaluate at regular intervals how many jobs have accumulated in each phase of a SP’s pipeline and how much extra capacity is available. New sectors via storage deals or auto-pledging could be added as resources allow.

This tool can be external to Lotus.


&nbsp;
-----
&nbsp;

### SP Hardware Profitability Calculator

A general calculator for *hardware* setup costs and how that impacts Sealing Rates.

#### Description

Many SPs consider their sector Sealing Rate when analyzing their hardware configurations. Suggestions for additional important and measurable parameters to consider are welcome.

A complete Mining Profitability Calculator for Filecoin would consider investment in both hardware and capital. For this grant we are interested mainly in the hardware component. (A basic calculator analyzing the amount of collateral a miner needs over time per unit of storage is in progress separately by another team.)

For all calculations, specific parameters may change but it helps to have the formulas in place and network variables can be filled in later.

An [example Reference Architecture](https://filecoin.io/vintage/mining-hardware-config-testnet-v3.pdf) for a medium-sized SP is also available (from the [Filecoin Guide to Storage Mining](https://filecoin.io/blog/filecoin-guide-to-storage-mining/) blog post).

&nbsp;
-----
&nbsp;

### SP Transaction History and Earnings Predictor

SPs need to make sure they have enough funds in their wallets to support their storage mining and growth. They also want to understand their overall profits and losses over time. Tools to support this are of interest in this grant.

1) **Miner Transaction History** - Aggregate and explain the transaction history of a miner's earnings and fees.

2) **Earnings Predictor** - Based on a miner’s history (e.g. 1 month of past data), extrapolate into the future a miner’s potential earnings.

#### Description

##### 1. Miner Transaction History

Improving how a miner’s income and expenses from storage mining are calculated over time can help them estimate the amount of funds they need to keep in reserve and also debug how well their miner is doing.

The goal is to help miners better understand the history of all their incoming and outgoing transactions in terms of collateral pledged, rewards, penalties, gas costs ( over time), and any other relevant data.

##### **Options**

- Option 1. Explain the Transaction History for any given Storage Miner address and their earnings and fees schedule.
  - A miner’s transaction history can be hard to follow and group logically in current block explorers, especially for new miners
    <small>
    - [Miner t015903 on Filfox.io](https://filfox.info/en/address/t015903)
    - [Miner t015903 on Filscan.io](https://filscan.io/#/tipset/address-detail?address=t015903)</small>


- Option 2. Map every step of the storage mining process and explain how much each event costs. A sample [state machine for storage mining is here](https://github.com/filecoin-project/lotus/blob/b212368a70fee3db10eeb450ecb33a10b67b5f23/extern/storage-sealing/fsm.go#L211).
  - Explaining where a miner’s funds are going and when the miner will get them back would be very useful

- Option 3. PRs to improve official documentation on fees are also welcome. Useful descriptions will be awarded at the discretion of the docs team after review.


#### 2. Earnings Predictor

Because miners have different hardware configurations, sealing rates and deal success rates, building an Earnings Predictor from day zero with no miner history can be fuzzy. However predicting earnings based on past and current miner performance may be tangible. [Also see the Basic Miner HW ROI calculator RFP].

Example inputs:
- “If a miner’s sealing rate is X + my current success rate is Y + fault fees are Z... rate of growth would be...”
- “Based on these historical and operational costs (e.g. energy, space, networking, etc.) total expenditure will likely be...” 
- “Given my current benchmarks and PC1, PC2, C1, C2 times…” (using Lotus benchmarks would be great input)

Before and after reaching the 10 TiB minimum consensus power should be considered.

Rewards are also based on dynamic network conditions, baseline assumptions could be made, such as assuming the network will grow linearly which impacts how many blocks you can mine in the future (or you can try using different growth trajectories). Also currently there is only testnet data available.

A scaffold of an earnings prediction calculator based on past performance could be useful to other SPs. A spreadsheet model, Observable notebook or CLI tool or similar could be used and plotting could be kept in FIL.


<small>
Notes

- Fees may range in units from FIL to nanoFIL (windowPost) to attoFIL (gas fees) and it would be nice for a fee schedule explainer to tally all costs over a given time period.
- WindowPost may have several inputs and outputs, including gas and penalties.
- Owner vs Worker account interactions are also of interest.
  
</small>

&nbsp;
-----
&nbsp;

### Gas Tool and Guide

A web tool or guide to analyze Filecoin Gas pricing and how fees are calculated.

#### Description

A tool to explain and analyze Gas including base fees, fee cap (for each Tipset) and average gas premiums could be helpful to all community members. A schedule of estimated costs for various transaction types could also be helpful, as well as showing recently mined transaction averages and possibly MPool data and averages.

[Eth Gas Station](https://ethgasstation.info/) is one example resource but what specific tool is built to explain gas calculations is open.

Modeling current average gas costs can help SPs and developers better understand the current MPool and why their transactions are not being mined, especially if their gas is too low compared to the network average.

The EIP-1559 Gas Model was implemented in Filecoin (relevant [Changelog](https://github.com/filecoin-project/lotus/blob/efd2dff0cac40934ec5b4472e48887ecbb2efe44/CHANGELOG.md#gas-changes)). A Lotus JSON RPC API call to estimate gas in Lotus is a TODO in [Issue 3326](https://github.com/filecoin-project/lotus/issues/3326) and there is a [Gas Estimation function here](https://github.com/filecoin-project/lotus/blob/18c025f10e99b35cf7cd2eebe10de5163280378e/node/impl/full/gas.go#L189).

&nbsp;

### Mining Task Pool for Smaller Storage Providers

> NOTE: Creating a SP pool in Filecoin is not easy to do and cannot be implemented in a fully decentralized way at this time.

A way to pool resources and tasks to smaller SPs behind a single node. One goal is to attain the 10 TiB minimum consensus storage power collaboratively as a group sooner to have a chance to earn a % of block rewards earlier on.

#### Description

SPs regularly ask whether a mining pool is possible in Filecoin.

1. Collateral is difficult to pool in a trustless, decentralized way without a spec-actor update which can be proposed as a future FIP. 

    Some groups have also proposed a centralized service provider external to Filecoin for pooling collateral that SPs would have to trust, or a staking system.

2. Another area of research is to target the FSM scheduler to support farming tasks to smaller remote SPs in the same geographic region as a worker pool, all behind a single node and SP id. Smaller SPs could work together in this way to earn block rewards as a collective.

We are particularly interested in Option 2. A discussion thread for this topic is also on Github is at https://github.com/filecoin-project/lotus/discussions/4005. 
	
This grant could support a good FIP proposal or a proposed architecture + scheduler suggestions.


&nbsp;
-----
&nbsp;

### CID Indexing Tool for SPs

A CID indexing tool for all sectors that a storage provider has, as software that sits on top of a Filecoin node and sends data to a community aggregator.

#### Description

Storage providers who offer more information about data and sector status are likely to be more attractive to storage clients.

A CID indexer could be run as a sidecar to Lotus to keep track of all sectors a SP has:

- Grabs all the IPLD data structures of the client data
- Understands every CID
- Maps CIDs to sectors and offsets
- Creates a local CID index
- Then storage miners could share their CID index with a aggregator for community visibility

Sectors that SPs have can also be observed at https://spacegap.github.io.

Optionally this tool could also map pieceCIDs to payload / data CIDs (as used in IPFS) to support Retrieval Miners and Clients. https://github.com/mgoelzer/cid_oracle is another tool that scans the Filecoin blockchain for pieceCID to payload CID mappings.

(originally proposed by @jbenet)

&nbsp;
-----
&nbsp;

### Storage Provider Docs and Community Guides

Community members are welcome to contribute to the following:

1. The **Filecoin Storage Provider Docs** are currently being improved and we welcome community members to contribute PRs especially on topics below.

2. **Real-world community guides** ranging from *blog posts, notes, videos and tutorials* with additional tips and analysis on why you made certain choices to help other storage providers.

All contributions will be judged based on quality and grant award amounts determined afterwards.

#### Description

*(Not all submissions may be eligible - if you're not sure about a topic, ask us!)*

#### Description - 1. Filecoin Storage Provider Docs

The mining docs at [docs.filecoin.io/mine](https://docs.filecoin.io/mine/) aim to be a canonical guide to mining that is growing. They include a guides like the  [example architectures](https://docs.filecoin.io/mine/mining-architectures/#protocol-labs-example-architecture), the [troubleshooting page](https://docs.filecoin.io/mine/lotus/miner-troubleshooting/) or any other that will benefit from contributions and feedback.

#### Description - 2. Real-world Community Guides

If you have a successful storage miner - small, medium or large...

📷  *We'd love to see photos or videos of your storage miner setup and learn about why you made certain choices and what you've learned along the way.*

🚴 *Or walk us through a full setup and all the additional steps you took whether it's Linux fu or networking tips or hardware optimizations or your storage layer redundancy strategy or outtage recovery strategy.*

Here are some topics of interest:
- How did you set up a rig??
   - Which CPUs, GPUs, networking, types of drives, etc. did you choose?
   - How does your sealing pipeline look like and how are you distributing tasks between your miner and the workers?
- Setup tricks for Lotus
   - How to dynamically adjust prices?
   - What custom deal filters have you set up?
- Redundancy Strategies
   - How are you aggregating/safeguarding your storage?
   - e.g. ZFS, JBOD, RAID (what type?), Ceph, GlusterFS and what performance do you get out of your solution?
   - SSD vs NVMe
- Monitoring tools
   - from basic scripts to dashboards
   - monitor resources, detect failures
- Disaster Recovery
   - What are the failure cases? How do you recover from them?

Guides on these sample topics can complement the Mining Docs with more real-world examples to help other miners get started and work through the trade-offs. Content might be reviewed and included directly or indirectly in the official docs.

#### Grant Award Ranges

All contributions will be judged based on quality and award amounts determined afterwards (at the discretion of the grants and docs teams).

- **Docs PRs** ($5 - $150) - For quality PRs accepted to [docs.filecoin.io/mine](https://docs.filecoin.io/mine/)

- **Entire Topic** ($100 - $500) - e.g. a useful write-up about some major important topic useful to a lot of miners e.g. your Redundancy strategy with benchmarks and analysis (and can it be used for chain data as well, etc. more detail please!)

- **Miner Video or Mining Tutorial** ($100 - $500) - Filecoin Miner Show and Tells ([No. 1](https://www.youtube.com/watch?v=jO5hJiwKAjA), [No. 2](https://www.youtube.com/watch?v=pHi85ZNs3AY), [No. 3](https://www.youtube.com/watch?v=jqbfETY3v6Q), [No. 4](https://www.youtube.com/watch?v=1JtQnhvxlVg)) have been popular with community members. We'd love to see more infomrative videos from community miners.

&nbsp;

*Thanks to @ribasushi, @charles, @RobQuistNL, @stuberman, @jennijuju and @hsanjuan for suggesting and giving feedback on all these initial ideas.*


&nbsp;


-----

### Gitcoin CLR Grant Funding

These proposals are posted to the **[Gitcoin (Filecoin) Liftoff category](https://gitcoin.co/grants/liftoff?)** where community members can show their support and signal it's a valuable idea.

Your **Open Grant Proposals** can also be posted to Gitcoin Grants. Suggest your own Filecoin Mining Tool project idea and the mining community can give feedback and help crowdfund it.

👉 Protocol Labs will match ALL community contributions by a **quadratic funding** formula used by Gitcoin CLR Grants.

-----

To apply for any RFPs see our [Proposal Guidelines](#proposal-guidelines) below for how to apply.

*Have a question about any of these RFPs? Email devgrants@filecoin.org*


-----

### Proposal Guidelines
### Filecoin Dev Grants

We generally fund projects that can be built in a 6 week to 2-3 month time frame and evaluate proposals based on:

- The quality of the proposal and near-term value to the Filecoin ecosystem
- Your team’s technical experience, open source contributions and interest in diving into how Filecoin works
- Likelihood that your team will continue to support the Filecoin ecosystem long-term and commitment to maintaining your project for one year

Note that all proposals must be open sourced via MIT and Apache2 licenses.


**Proposal Requirements**

Proposals should include a value proposition about how it will benefit the Filecoin ecosystem, technical detail about what your team intends to build and evidence your team is capable of creating good, re-usable open source code, compelling product demos and great documentation, and a reasonable technical development plan broken down into milestones. Here's a [good sample proposal](https://github.com/ipfs/devgrants/blob/master/targeted-grants/IPFS-mobile-design-research.md).

Proposals should include:

1. Project Description
   - Brief description
   - Value to the Filecoin ecosystem
2. Deliverables
   - An explanation of your technical solution and architecture
      - Imagine that an experienced software developer will evaluate your proposal
3. Milestones & Funding requested
   - Most projects have at least 4 milestones
   - Budget and estimated timeframe for each milestone
4. Team
   - Roles and Experience
       - Teams with a history of high-quality open source code repos and live applications and products are preferred.

We also accept **Open Grant Proposals** where you can suggest your own Filecoin project idea. [More info](https://github.com/filecoin-project/devgrants/blob/master/open-grant-proposals/open-proposal-template.md)

To submit a proposal, fork and make [a PR](https://github.com/filecoin-project/devgrants/pulls) to this repo by the next wave deadline - Oct 1st 23:59 PDT (For priority consideration. We will evaluate later proposals submitted after the deadline as capacity allows.)

&nbsp;

---

*Have a question about any of these RFPs? Email devgrants@filecoin.org*
