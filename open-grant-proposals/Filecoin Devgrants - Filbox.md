# Open Grant Proposal: Filbox - Storage App built on top of Filecoin and IPFS

‒ Name of Project: Filbox

‒ Proposal Category: `app-devs`

‒ Proposer: `yongxi-liu`

‒ Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?: Yes.

# Project Description

![Filbox-prototype1](https://oss.faycz.com/filbox/fibox1.png)
![Filbox-prototype2](https://oss.faycz.com/filbox/2.png)

‒ Filbox is an open source file storage application built on top of Filecoin and IPFS network. While Filecoin has created an incentivised data storage market, to put it into daily use and realise mass adoption, we need a user friendly entry for people with any  background (technical + non-technical) and resolve the issues that are indeed concerning to them: 1) Data Privacy. Right now, it is possible for miners to stalk user data when they accept a deal request from storage clients.  2) Miner Stability. Although the filecoin economics structure has discouraged much of the malicious acts, there are still malicious miners out there (e.g. reject to accept deals/accept deals but not seal them) who maybe alarming for the data being stored.  3) Adding more fun. We want to add an extra layer of fun/usefulness to the platform.

‒ We've thus created Filbox, where users can 1) Encrypt private data. By deploying the end-to-end encryption functionality, we ensure that users can get their files encrypted easily in the application before the data has been uploaded/transferred to the miner, therefore mitigating the risk of data being exposed to miners/third parties. 2) Choose miners. We will have a rating algorithm based on miner's deal history with the miner's ask price - thus users will be able to get a clearer idea of the miner's credibility and choose the miner with good credit rating and appropriate ask price. 3) Share your work. In the future, we will add the content-sharing feature to our product where users will be freely sharing the work they've created - can be creative writings, videos, etc., It can either be free or has to be purchased, depending on the author.

‒ Happy storing!

# Value

‒ Ultimately, Filbox's aim is to provide a safe, easy to use and stimulating place for users to store their data. For storage users, they can encrypt their data, choose which miner they want to store data with and share valuable contents if they want. For content producers, for example, artists, they can publish their work on the content marketplace and be ready to make profits from it. We will envolve to make more features feasible in the future and hopely to make more contributions to the Filecoin ecosystem.

‒ We are also aware of the challenges that we might be facing:

* Powergate's frequent code update.

Powergate is a great library that provides easy APIs to build on IPFS and Filecoin. Our project is built on Powergate but it's still in pre-release phase and not well-documented. Its code base is changing and iterating quickly and frequently. It's a challenge for our team to keep up with its API update in a limited time frame. To mitigate the risk, we  put quite a lot of efforts in mastering Powergate source code, so that we can reduce responsive time and build stable branch on our own.
Impact: Low

* Sector Size.

Filecoin's target sector size is 32GB and six month deal period which has a gap with our cloud disk scenario.Most of personal files are small which have trouble to fill up an entire 32GB sector. Our project will provide archive feature for users to package files together and store.
Impact: Low

# Deliverables

‒ User Registration/Login; 

‒ User can upload files to IPFS & Filecoin miners; 

‒ User can search & download file with filename or CID;

‒ User can encrypt and upload their file;

‒ User can choose miners to make deals with.

# Development Roadmap

## Milestone1 - Product Design 

‒ Output: Prototype, User Interface, Product Structure, Project Plan

‒ Team: 1 UX, 1 PO, 1 PM

‒ Duration: 2 Weeks

## Milestone2 - MVP Implemententation (Basic Use Case)

‒ Output: User Register/Login, Upload Files to IPFS & Filecoin Miners; Search & Download File with File Name or CID.

‒ Team: 1 UX, 1 PO, 1 PM, 1 UI-dev, 1 Backend Dev

‒ Duration: 3 Weeks

## Milestone3 - Enhanced Use Case

‒ Output: Provide client version; User can encrypt the file to upload; User can choose specific miner to dealwith

‒ Team: 1 Arch, 1 UX, 1 PO, 1 PM, 1 UI-dev, 1 Backend Dev

‒ Duration: 4 Weeks

# Total Budget Requested

| Role | Rate/Hr | HC | Man-Hour | Man-Week | Price |
|-----|-------|----|--------|----------|------|
| Arch | $80 | 1 | 40 | 1 | $3,200 |
| PM | $60 | 1 | 40 | 1 | $2,400 |
| PO | $50 | 1 | 80 | 2 | $4,000 |
| UX | $50 | 1 | 40 | 1 | $2,000 |
| UI-Dev | $50 | 1 | 120 | 3 | $6,000 |
| Backend Dev | $50 | 1 | 120 | 2 | $6,000 |

**Project Duration: 9 Weeks**

**Total Funding: $23,600**

# Maintenance and Upgrade Plans

1. Website Maintenance

  - Continuing optimising use case and user experience;
  
  - Bug fixing on demand;
  
  - Service maintenance.

2. Further Upgrade Plan

  - Add content market features. Filbox users will be able to sell their creations in the content marketplace (a huge project). 

# Team
## Team Members
‒ Yu Li/Arch

‒ Felix Zhou/PO

‒ Lea Shao/PM

‒ Eric Qu/UI/UX

‒ Fay/Frontend Dev

‒ Leo/Backend Dev

‒ Yongxi Liu/Analyst

‒ Qiankun Chen/Test

‒ Kimmy Wen/Brand Mng

## Team Member LinkedIn Profiles

‒ Yu Li:  https://www.linkedin.com/in/savage-li-077a48101/

‒ Felix Zhou: https://www.linkedin.com/in/felix-zhou-2b40b92a/

‒ Kimmy Wen: https://www.linkedin.com/in/kimmy-sijiewen/

## Team Website

https://filbox.keystore.com/home/

## Relevant Experience

‒ Founded in 2018, we (Keystore Group: www.keystore.com) are one of Asia's top crypto asset service provider. We utilise bank-level encryption technology and operate business in internet banking and custody for crypto asset for institutional clients. While the integral part of crypto asset service is data safety, it's intuitive that we take the role of data storage to a further phase. We are also one of the filecoin miners (KeyPool: https://www.keypool.com)   Equipped with profound tech experience in Intel, Marvell, Phillips, TechCrunch, 360yunpan，we are a team committed to continuously envolve and improve the filecoin ecosystem.

## Team code repositories

https://github.com/rleor/filbox

https://github.com/love-fay/fay-sso
