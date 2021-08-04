To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Sector Repair Tool`

**Name of Project: Sector Repair Tool**

**Proposal Category:** core-dev

**Proposer:** catthehunter

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Please describe exactly what you are planning to build. Make sure to include the following:
During the long-term sector management and maintenance, sector errors may occur due to various reasons, such as disk problems, sector loss, and sector damage during migration. Therefore, the rework and repair function are required for wrong sectors. Sector redo generates the storage data of the sector by taking the key data of the sector as input (sector number, ticket, minerID) to complete the sector recovery target.


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

No.  ll                                                                                      Milestone                                                                                      ll                time                ll      budget     ll
1         Lotus-Miner sector state machine adds redo state, the corresponding redo state flow rules and flow logic.                             2 persons/ per week             $3,700
2         Lotus-Miner sector and storage relationship management (local) reworks the storage information of the redone sector.        2 persons/ per week              $3,750
3         Compatible processing of Lotus-worker to redo sectors.                                                                                                         1 person/ per week                $1,500
4         Lotus-redo independent redo tool.                                                                                                                                         1 person/ per week                $1,500
5         32G/64G sector redo function test.                                                                                                                                         1 person/week                       $1,500

## Total Budget Requested

Total budget is about $12,000.

## Maintenance and Upgrade Plans

We will keep an eye on Filecoin version updates, and we will provide corresponding maintenance and upgrades.

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

Please describe (in words) your team's relevant experience, and why you think you are the right team to build this project. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc.

## Team code repositories

None.

# Additional Information

None.
