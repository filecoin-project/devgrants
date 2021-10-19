# Developer Tooling Ideas

We are seeking proposals for the following RFPs for various developer tools.

  - [Shared Blocklists / Wantlist of content CIDs](#shared-blocklists--wantlists-of-content-cids)
  - [CID Indexing Tool for Miners and Storage Clients](#)
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

### Shared Blocklists / Wantlists of Content CIDs

Lotus Filecoin has added the ability for miners to create blocklists of content piece CIDs they do not want to store or serve retrieval requests for (See [lotus PR 2069](https://github.com/filecoin-project/lotus/pull/2069)). This may be required for miners to comply with local law enforcement requests (which lists to respect and which items to block are entirely up to the miner operator).

This RFP is for a way for blocklists to be shared by the community, potentially with some basic metadata around the reasons for blocklisting. A way for community members to propose CIDs to blocklist would also be useful.

Related projects in IPFS have proposed a [content-decider framework](https://github.com/ianjdarrow/content-decider) and [DNR lists](https://github.com/ipfs/camp/blob/master/DEEP_DIVES/25-do-not-replicate-lists-dnr.md#do-not-replicate-lists---dnr).


&nbsp;
-----
&nbsp;

### CID Indexing Tool for Miners and Storage Clients

A CID indexing tool for all sectors that a storage miner has, as software that sits on top of a Filecoin node and sends data to a community aggregator.

Alternatively, a CID metadata index for storage clients to batch and keep track of larger archives stored on Filecoin.

#### Description

Storage miners who offer more information about CID data and sector status are likely to be more attractive to storage clients.

A CID indexer could be run as a sidecar to Lotus to keep track of all sectors a miner has:

- Grabs all the IPLD data structures of the client data
- Understands every CID
- Maps CIDs to sectors and offsets
- Creates a local CID index
- Then storage miners could share their CID index with a aggregator for community visibility

Sectors that miners have can also be observed at https://spacegap.github.io.

Optionally this tool could also map Filecoin pieceCIDs to payload / data CIDs (as used in IPFS) to support Retrieval Miners and Clients. https://github.com/mgoelzer/cid_oracle is another tool that scans the Filecoin blockchain for pieceCID to payload CID mappings.


&nbsp;
-----
&nbsp;

### Auto-Add New Sectors based on Capacity

A tool to help miners automatically pledge new sectors or manage new storage deals as their machine capacity allows.

#### Description

Adding new sectors is currently managed manually. The tool could evaluate at regular intervals how many jobs have accumulated in each phase of a miner’s pipeline and how much extra capacity is available. New sectors via storage deals or auto-pledging could be added as resources allow.

This tool can be external to Lotus.

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
