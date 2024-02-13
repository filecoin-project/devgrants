# Open Grant Proposal: Improve the stability of the lotus miner

**Name of Project:** Decoupling WinningPoSt and WindowPoSt from lotus-miner

**Proposal Category:** `core-dev`

**Proposer:** `sirius`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

The project, which will be developed based on the current lotus source code, is intend to improve the stability of miner in WindowPoSt and mining blocks.

The idea is to take lotus-worker rather then lotus-miner as the entrance  while storing cached or sealed sector files. on the mean time, the lotus-worker should provide services which includes VanillaPoSt of Window and Winning. so that the storage capacity can be expanded via lotus-worker directly.

The logic of PoSt in filecoin-ffi, which mainly includes the distribution of partition calculations, worker scheduling and the collection of the results, is moved to sector-storage

Lotus-worker should supports WindowPoSt and WinningPoSt, which are split from lotus-miner

The details of the solution are as follows: 

- Add WindowPoSt and WinningPoSt seal task types.
- The storage mounted by lotus-worker can support CanStore through parameter configuration.
- Extend lotus-worker to support WindowPoSt and WinningPoSt task types through parameter configuration.
- Extend filecoin-ffi and rust-fil-proof to support getting VanillaPoSt result of Window and Winning and calculating WindowPoSt and WinningPoSt based on VanillaPoSt result.
- Add calculation WindowPoSt and WinningPoSt interface for WorkerCalls.
- Extend index to support global acquisition of SectorStorageInfo and getting sector's url.
- Optimize pubSectorToPriv function to support global acquisition of sector path.
- Extend http_handler of remote to support Vanilla PoSt of Window and Winning.
- Considering real-time performance, independent scheduling of WindowPoSt and WinningPoSt.
- Optimize runPoStCycle to calculate WindowPoSt in parallel for batch.


## Value

- Make lotus more friendly to support the operation of large miners, including WindowPoSt and WinningPoSt.
- The function is activated by parameter configuration, aiming to improve the stability of large miners.
- Compatible with the existing code, try not to make major structural adjustments, and not make destructive changes.



## Deliverables

All codes will be merged into filecoin-project.

# Development Roadmap

|  | milestone | fund | estimated time |
| --- | --- | --- | --- |
| 1 | Program communication and discussion | None | One week |
| 2 | Software design | $5000 | One week |
| 3 | Coding implementation | $15000 | Two weeks |
| 4 | Testing | $10000 | One week |
| 5    | Documentation and tutorials          | $5000  | One week       |
|      |              |      |            |




## Total Budget Requested



Total: $30000



## Maintenance and Upgrade Plans

Our team is deeply involved in the filecoin project and will continue to track and participate in lotus code maintenance.

# Team

## Team Members

- sirius

- gegezai

- kenny688

- wjywood

  

## Team Member LinkedIn Profiles

- https://github.com/siriusmz
- https://github.com/gegezai
- https://github.com/kenny688
- https://github.com/wjywood

## Team Website

https://github.com/wusirdcenter

## Relevant Experience

Since the release of the filecoin code, our team has been tracking and analyzing the filecoin code, and carrying out customized development;

Our team have ever participated in testnet, slingshot, mainnet

Our team have ever created and maintained several miners whose power over 50PB, however the miners are not assets in our team's name



## Team code repositories





# Additional Information
