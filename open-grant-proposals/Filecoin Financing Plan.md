To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Filecoin Financing Plan`

**Name of Project: Filecoin Financing Plan**

**Proposal Category:** core-dev

**Proposer:** catthehunter

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Please describe exactly what you are planning to build. Make sure to include the following:
The proposal would address the issue of high threshold to participate Filecoin. For instance, the cost of the hardware and collateral for a mining pool with 1P power will be more than 3 million RMB (about $462,000). We hope that through the Filecoin financing plan, users with 
hardware and mining pool can publish financing plans to the entire network. 
Filecoin financing plans will include the total financing amount, the timeline, the usage plan, repayment amount (yield indicator) and repayment plan(installment). Anyone can make an investment by transferring FIL to the financing plan address, and financing repayment will be returned to the transfer account. 
To secure the benefit of the investors, the financing plan itself shows investors the credit information of the financier. At the same time, the logic of freezing financing fund and income automatic repayment of the financing plan will be implemented in the lotus-miner, and to freeze financing fund will guarantee that the financing fund can only be used to increase the mining pool power. The Automatic income repayment will guarantee that the investors' income is not subject to the individual intentions of the financier. 

## Value

Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:
- What are the benefits to getting this right?
A: The project can spread the pressure of high cost to join Filecoin, to reduce the risk for individuals to participate, to lower the cost threshold for Filecoin participation, and to attract more users to get involved.
- What are the risks if you don't get it right?
A: If we didn't get it right, the investors may lost their capital.
- What are the risks that will make executing on this project difficult?
A: The credit rating of financiers is not comprehansive or accurate enough, and that makes investors afraid to invest. 

## Deliverables

1. deliver the lotus-miner implementation code for financing plan
2. deliver the web browing portal (financing plan explorer) code for financing plan and access services.

## Technical Breakdown

Filecoin financing plan detailed process:
1. Add two control address types for miner, which means on the basis of the worker/owner address, we add the financing address and the repayment freeze address.
2. A sealing sector first determines whether the financing address has some balance, If the address has, the sector will use the balance; if not, the sealing sector will follow the original logic to process.
3. A financing plan includes features below:
Financing address
Financing start time
Financing end time
Financing total amount (At the financing end time, if financing total amount has not yet met, the financing plan will be canceled automatically.)
Repayment total amount
Repayment start time
Repayment end time
Repayment period
Repayment period option (3 options: month, week, day)
4. During the repayment time, the miner balance is frozen to pay for the current repayment. When the added-up balance meets the repayment limit, the balance will be automatically transferred to the repayment freeze address.
5. Only when the balance in the freeze repayment address has met the repayment amount, the miner’s balance can be withdrew and used. 
6. When repayment time is about to end, repayment freeze address will automatically transfer the scheduled repayment amount into the financing investment address.

## Development Roadmap

No.     Milestone                                                                                                           time                         budget   
1       Implement the creation of the financing plan and release basic features.                                            3 persons/ per week          $4,800
2       Implement the financing plan explorer, provide the user portal for the whole network's investor financing plan      3 persons / per week         $4,800
3       Implement the lotus-miner's financing plan execution guarantee logic, financing fund freeze, and income will be automatically repayed as scheduled promised repayment plan of the financing plan.                                                                                                      15 persons / per week        $24,000

## Total Budget Requested

Total budget is about $33,600.

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

As we mentioned in the last proposal (Sector Repair Tool), we have our own lotus version which has been maintaining all the time. Its features include:
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
