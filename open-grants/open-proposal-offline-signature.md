# Open Grant Proposal: Offline signature in using Owner wallet

**Name of Project:** Offline Signature Commands of Owner Wallet

**Proposal Category:** `devtools-libraries`

**Proposer:** marco-swift

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Please respond with either "Yes"

# Project Description
The owner wallet is the most important wallet in Filecoin. It must be kept securely. If it is lost or changed illegally, the storage provider will get nothing. All FILs including available, vesting, the expected future rewards, and pledged will be out of control. So it is NOT recommended to import the owner key into a lotus daemon node. People MUST NOT keep the owner key in an IDC, and it's not a good idea to keep it in an office computer. The best way is to use a multisig wallets, or some cold wallet solutions. If you think those methods are complicated and want to use a simpler solution, then using offline signature commands is also a good choice.  
  
We provide an set of interactive commands that allow the user to do owner tasks in the local shell without importing the owner key into lotus daemon.  Messages are packaged locally and sent to a remote FullNode for message processing.


We implement these commands:  
- actorSetOwnerCmd  -- change the owner key
- mpoolReplaceCmd   -- replace the message in mpool with more GAS；
- sendCmd           -- send message from the owner wallet
- withdrawCmd       -- withdraw available balance
- actorControlSet   -- set the control addresss；
- actorProposeChangeWorker  -- propose to change the worker address
- actorConfirmChangeWorker  -- confirm to change the worker address

## Value
- Improve the security of the private key of the owner wallet  

## Deliverables
Around 6 weeks  

## Development Roadmap

- Week 1 Complete the formal specification
- Week 2 Design API and start development
- Week 3 Development
- Week 4 Test, Fix bugs and Do some optimization
- Week 5 Test more and Submit it for official review
- Week 6 Release

## Total Budget Requested

$20000 
The funds will be earmarked for the development of Offline Signature Commands of Owner Wallet.


## Maintenance and Upgrade Plans

We plan to continue supporting and maintaining the off-line Signature program for at least the next two years (24 months);  
At the same time, we also pay attention to the new requirements of the community for offline Signature and continue to improvement.

# Team

## Team Members

marco-swift  
coder-lb  
kaola526  

## Team Website

- [https://storswift.com](https://storswift.com) 


## Relevant Experience

Our team start to research and develop for Web3 two years ago. We have implemented the optmized version of PoREP/PoST code, worker task secheduling code, devops management system, and so on. From the very beginning, we have been focused on Filecoin security solutions. We research offline signature, cold wallet and multisig solutions. We also develop a framework to ensure the security of devops for Filecoin clusters.

## Team code repositories

- [https://github.com/storswift](https://github.com/storswift)   
- [https://github.com/storswiftlabs](https://github.com/storswiftlabs)  

# Additional Information

We believe Web3 is the future. The best way to predict the future is to create the future.
