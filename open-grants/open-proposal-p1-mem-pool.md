# Open Grant Proposal: Multi-Sector Memory Pool Support for The Sealing Precommit Phase 1

**Name of Project:** Multi-Sector Memory Pool Support for Precommit Phase 1 of Sealing

**Proposal Category:** `storage-proofs-porep`

**Proposer:** macro-ss

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Please respond with either "Yes"

# Project Description
It is well known that the PoRep needs huge memory resource on the label creating during the sealing PreCommit Phase 1, which is composed of the base + exp layers. One 32GB-sector label creating will consume 64GB memory, and the 64GB sector needs 128GB. If we run N jobs with N sectors in parallel, the total memory comsumption will be N * 2 * sector_size.

In order to seal more data of one server, the common method is to enlarge the DDR memory to TB level, which also means high cost at the same time, so it is very important to make full use of these memory resource as possible as we can.

We find it needs long time on the label caculation for every layer, which means we have too much memory not been touched within some time. For example, if we need 20 minutes to finish one layer of a 32GB-sector task, then it just needs 2GB in the first 75s, and 4GB for the first 150s in roughly estimated, etc. if we split the sector into multi blocks as following, it seems a good scenario for memory pool model in pipeline, which almost has the same performance as before.
  
    job-1: (Block 1) -> (Block 2) ... -> (Block N)
    job-2:              (Block 1) -> (Block 2) ... -> (Block N)
    ...

Let's assume N jobs runing with N sectors, it will consume N * 2 * sector_size for all jobs working in parallel, which is the maximum threshold, and the minmum threshold case is (N + 1) * sector_size in that one job can be done with exp layer ready on every job at least. The job wil be pending when the memory pool is only making sure the fastest job fully done, and which also will be waked up once other jobs's old expansion layer released.

So the memory pool size range is as following:
- MEM_POOL_SIZE <= N * 2 * sector_size
- MEM_POOL_SIZE >= (N + 1) * sector_sizeo

In the use case, it would be better that MEM_POOL_SIZE can be allowed changing by enviornment. we can use the middle case for good pipeline work in default as following,
- MEM_POOL_SIZE = (3 * N + 1) * sector_size / 2


Summary the impelmentation as following:
- memory pool management, such as init/acquire/release ops, etc.
- unsafe multi blocks support.
- multi task work on condition variables support.
- refactor fill_buffer, create_label_runner, etc. with multi blocks.

## Value
- Make full use of the memory during Precommit Phase 1 of Sealing.

## Deliverables
Around 6 weeks  

## Development Roadmap

- Week 1: Complete the formal specification
- Week 2~3: Development
- Week 4: Test, Fix bugs and do some optimization
- Week 5: Test more and submit it for official review
- Week 6: Release

## Total Budget Requested

$20000 
The funds will be earmarked for the development of memory pool support on sealing precommit phase1.


## Maintenance and Upgrade Plans

We plan to continue supporting and maintaining the code for at least the next two years (24 months);  
At the same time, we will also consider the upgrading if the sealing algorithm is upgraded.

# Team

## Team Members

macro-ss
coder-lb  
marco-swift
alexzhenyu

## Team Website

- [https://storswift.com](https://storswift.com) 


## Relevant Experience

Our team start to develop for IPFS & Filecoin two years ago. We are familiar with IPFS & Filecoin architecture and code, and have delevoped our optmized version of sealing code, worker task secheduling code, devops management system, and so on. From the very beginning, we have been focused on Filecoin security solutions. We research offline signature, cold wallet and multisig wallet solutions. We also develop a framework to ensure the security of devops for Filecoin clusters.

## Team code repositories

- [https://github.com/storswift](https://github.com/storswift)   
- [https://github.com/storswiftlabs](https://github.com/storswiftlabs)  

# Additional Information

We believe Web3 is the future. The best way to predict the future is to create the future.
