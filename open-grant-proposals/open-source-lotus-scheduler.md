# Open Grant Proposal: `Open Source Scheduler for Lotus`

**Name of Project:** Open Source Scheduler for Lotus by Moran

**Proposal Category:** `mining`

**Proposer:** [@moran666666](https://github.com/moran666666/)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `Yes`

# Project Description

The project has already been open sourced at https://github.com/moran666666/lotus-1.4.0 

The distributed Miner version of Filecoin mining software supports the separation of PoSt-miner, Deal-miner, and Seal-miner functions to realize the distributed deployment of multiple Miners.

## Value
The load of a single Miner node is too high, and the machine is unstable, which can easily lead to the problem of space-time proof failure and power loss;
Solve the problem that the Miner node load is too high, and the block generation failure caused by the calculation is not fast enough when the block is generated;
Solve the problem of video card lock conflict when Window-PoSt and Winning-PoSt are running simultaneously;
Solve problems such as abnormal crash of Miner due to high memory usage when receiving orders, loss of computing power, failure of block generation, etc.;

## Deliverables
Function Description:
- Support the distributed deployment of the same MinerId on multiple machines;
- Support Window-post-miner, Winning-post-miner, Deal-miner, Seal-miner function separation:
- PoSt-miner: Responsible for Window-PoSt and Winning-PoSt, which can be divided into two machines or can be completed by one machine;
- Window-post-miner: Responsible for sector spot check and submission during sector window certification;
- Winning-post-miner: Responsible for random spot check of sectors when producing blocks;
- Deal-miner: Responsible for order acceptance and retrieval, and task allocation for order sector sealing;
- Seal-miner: Responsible for the task distribution of common sector sealing.
- Scheduling management is based on the number of custom tasks, which can accurately control the working status of the machine

## Total Budget Requested
88 FIL
