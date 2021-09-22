To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Sector Repair Tool`

**Name of Project: Sector Repair Tool**

**Proposal Category:** core-dev

**Proposer:** catthehunter

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

During the long-term sector management and maintenance, sector errors may occur due to various reasons, such as disk problems, sector loss, and sector damage during migration. Therefore, the rework and repair function are required for wrong sectors. Sector redo generates the storage data of the sector by taking the key data of the sector as input (sector number, ticket, minerID) to complete the sector recovery target.
The project mainly carries out the repair when the CC empty sector encounters uncontrollable problems. For example, the sector file is deleted by mistake; the file is corrupted and unreadable caused by abnormal storage power failure or internet failure; or the file is corrupted and unreadable caused by hard disk hardware damage error, etc. 
The repair approach is to get sector ticket, sector common CID from the sector attribute data of the miner storage. Then, according to the sector number, we redo the process of data creation and generation from AP to P2 in the lotus miner, or we do the same process in the lotus-redo tool. Finally, the recovered sector data can be written into the storage. But if there is no original data for the deals, the data cannot be recovered.

## Value

Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:
- What are the benefits to getting this right?
A: By reworking and repairing wrong sectors, it will reduce sector loss damage and penalties for requiring to terminate sectors, and fix repair issues during sector maintenance.
- What are the risks if you don't get it right?
A: So far there is no risk.
- What are the risks that will make executing on this project difficult?
A: Under the circumstance of lacking raw data, recovering sectors with actual transaction data can not be acchived.

## Deliverables

We plan to create a sector repair tool, and the approaches will be one of the three options below: 
1. Redo the sector-related functional code and release it with Lotus-Miner new version updates
2. Redo the sector-independent program code and Lotus-redo project code
3. Redo sector-independent program executables (binary), Lotus-redo (binary)

## Development Roadmap
No.     Milestone                                                                                                                time                budget    
1       Lotus-Miner sector state machine adds redo state, the corresponding redo state flow rules and flow logic.                2 persons/ per week      $3,700
2       Lotus-Miner sector and storage relationship management (local) reworks the storage information of the redone sector.     2 persons/ per week      $3,750
3       Compatible processing of Lotus-worker to redo sectors.                                                                   1 person/ per week       $1,500
4       Lotus-redo independent redo tool.                                                                                        1 person/ per week       $1,500
5       32G/64G sector redo function test.                                                                                       1 person/ per week       $1,500
One way to carry out the proposal is the sector repair tool being a part of the lotus miner. Another way is that it can be an external tool. Both are in the contents of this proposal and will be implemented in this proposal.  
## Total Budget Requested

Total budget is about $12,000.

## Maintenance and Upgrade Plans

We will track the lotus official version for updates and provide corresponding maintenance and upgrades, or the project can be incorporated directly into the official version update

# Team

## Team Members

- Team Member 1: Xianrui Zeng
- Team Member 2: Caiyu Huang
- Team Member 3: Gexue Zhang
- Team Member 4: Bo Peng
- Team Member 5: Teng Li

## Team Member LinkedIn Profiles

- Team Member 1 LinkedIn profile: https://www.linkedin.com/in/xianruizengb38a16218/
- Team Member 2 LinkedIn profile: https://www.linkedin.com/in/caiyu-huang-455574218/
- Team Member 3 LinkedIn profile: https://www.linkedin.com/in/gexue-zhang-485bb37b/
- Team Member 4 LinkedIn profile: https://www.linkedin.com/in/bo-peng-021398219/
- Team Member 5 LinkedIn profile: https://www.linkedin.com/in/teng-li-44939a219/

## Team Website

None.

## Relevant Experience

We have our own lotus version which has been maintaining all the time. Its features include:
1.Refactoring the task distribution mechanism（Only on the same host, the task flows from AP to C1）
2.A supplement to flow logic of sector state (sectors can enter removed state under any other state, which is convenient to maintain. )
3.Sector data is written in the storage directly from the worker host server, instead of using HTTP network transmission between worker and miner. 
These features have never been uploaded to the lotus official staff, and our version has not been uploaded on Github. 
We have been following the IPFS project continuously from the beginning. As soon as the Filecoin mainnet went alive in October 2020, we started preparing to build nodes. On December 1st 2020, We ran our first node, F092887. Currently, the nodes we are building and operating are the ones below: 
f0121810
f0136808
f092887
f0110808
f0704940
f0704966
f0728817
f0811662
f0705136
f0500685
f01040516
f01043666
f01074227
We can modify the node labels as authentication if necessary.

## Team code repositories

None.

# Additional Information

None.
