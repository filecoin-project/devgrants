# RFP Proposal: `Consensus Visualization Tool` (WIP)

**Name of Project:**
Consensus Visualization Tool

**Link to RFP:** 
[Consensus Visualization Tool](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-consensus-visualization-tool.md)

**RFP Category:** 
`app-dev`

**Proposer:** `@thevantageproject`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** 
Yes

**Disclaimer:** Research is still in progress. Will soon be updating after getting more awareness around data.

# Project Description

This proposal aims to deliver an open source blockchain consensus visualization tool that specifically demonstrates Filecoin’s Expected Consensus process.

Specific things we are going to work on:
1) Provide an interactive visualization of Filecoin consensus viewable in web browsers
2) Provide live information updates of the following:
New messages
Blocks
Miners
Tipsets
Ancestors
Forks
3) Visualize the formation of Blocks
4) Visualize the formation of Tipsets
5) Depict miner related information
6) Show the list of probable miners (according to their storage power)

**Context:**


Filecoin is a decentralized storage network that turns cloud storage into an algorithmic market. The market runs on a blockchain with a native protocol token (“Filecoin”) , which miners earn by providing storage to clients. Conversely, clients spend Filecoin hiring miners to store or distribute data.

Filecoin uses the **Expected Consensus** protocol:

Expected Consensus is based on the heaviest weighted chain which tracks the most total storage power.
A miner’s odds of being elected to produce a block in Expected Consensus is proportional to their storage power in the network, or proven storage in active use. As blocks collect transactions and storage proofs are posted to the network, heavier chains track the most proven storage in the network.
Total proven storage in use is how chains are weighted, and the network eventually converges around the heaviest chain.

We aim to visualize what is happening in this process so that it becomes easier for a layman to understand it.

## Deliverables + Mockups(WIP, will soon be updating with the figma prototypes as soon as we final the design)


#### Messages Visualization:
* Whenever a new message arrives, we drop it onto an existing heap of the pending pool of messages.
* The set of messages that form the next block disappear and the remaining heap re-shapes itself, i.e. , remaining blocks fall to take up the empty space (We have the concept of **gravity** in mind !).
* The newly created block is displayed on the side of the heap. It will be interactive, i.e. , its corresponding details would be shown when clicked.
* The block will then get added to the existing blockchain (main chain) which will be displayed on the bottom half.
* If multiple blocks are mined at the same time, a TipSet will be created and all the corresponding blocks will be displayed.
* When a Tipset is created, we will create an alert to display the quantity of blocks in that tipset formed.

![](https://i.imgur.com/IGbj6jz.jpg)

#### Miner Visualization:
* We will display the list of active miners with the most storage power along with their probability to mine next (Their SP / Total SP).
* We will also display the probability of fork occurrence (Formula proposed in pic).
* We can use circles to depict active miners in decreasing order of their storage powers. Greater the radius of a circle, larger that miner's storage power.
* The next elected miner will be highlighted.
* This would help in visualising the **expected consensus** protocol (Since the miners will be arranged in descending order of their SP, the next probable miner would likely be among these top miners with the most SP).

![](https://i.imgur.com/C6zY27a.jpg)


#### Chain Visualization:
* This page will show the filecoin chain.
* By default, the main chain will be displayed.
* We will add a **zoom slider** which will be used to display the forks created.
* 100% zoom -> main chain
* 80% zoom  -> some of the heavy forks
* 0% zoom -> the complete set of forks (if possible)
* We can also show the forks created by showing the fork links with a different colour.

#### Tipset Visualization:
* We will show the history of the Tipsets created using a list.
* We will also display the 3 latest tipsets with their complete details (height, parent, children, current chain weight).

#### Fork Visualization:
* A simple list of the history of all the forks created(Height, Parent, Children, current weight) will be shown.

![](https://i.imgur.com/ilvGFbb.jpg)
![](https://i.imgur.com/2CU8G8Y.png)


### Show when natural and bad forks occur (e.g. >51% malicous attack)
WIP


Our implementation will:

- have a well-documented, human-readable codebase
- work with a Filecoin node API (lotus* and/or go-filecoin, local or remote) and database or cache if needed to perform the intended workflow (* starting with the lotus API is recommended)
- have tutorials with demo usage
- possibly be in any mainstream language with a preference for ones that ensure easy long-term maintenance
- be well-tested and usable by a large audience during Testnet and Mainnet

#### We will also provide video tutorials explaining different components around the visualization.
(similar to as we did on FOAMVIz : https://discourse.foam.space/t/introducing-foamviz-foam-developer-grants/1047/4?u=prastut)

---



#### Node API endpoints:
https://docs.google.com/document/d/1zaUlGd-gceihqrr1AQ_dEZaTbnTGR6LkAzZICRhIUpo/edit?usp=sharing


## Total Budget Requested

Total Budget: $25,100 - $29,800
 
 | Role | Rate/Hr | HC | Man-Hour | Man-Week | Price |
 |-----|---------|----|-----------|-------------|------|
 | PM | $60 | 1 | 60-80| 2| $3,600 - $4,800|
 | Design | $50 | 1| 30-40 | 1 | $1,500 - $2,000 |
 | Front-Dev | $50 | 1 | 100 - 120 | 3 | $5,000 - $6,000 |
 | Back-Dev| $50 | 2 | 300 - 340 | 4 | $15,000 - $17,000 |
## Maintenance and Upgrade Plans
* Maintaining the system actively for the next 6 months. That means bug fixes if any with the specs mentioned in the current proposal.
* For 1 year: support if the system goes down.


# Team
The Vantage Project

## Contact Info

Email: hello@thevantageproject.com

## Team Projects

![](https://i.imgur.com/bUYotyo.png)

You can checkout all the completed and ongoing projects and project repositories from our [Projects gallery](https://github.com/thevantageproject/web/wiki/Projects)

## Team Website

[The Vantage Proeject](https://www.thevantageproject.com/buidl/)

## Team Members

* Prastut - Currently a partner @ The Vantage Project. Comes from a UX, product management & full stack background.

    * Co-founder, Designer, Frontend Developer for [Centify](https://centify.surge.sh/) (2018). Built the entire frontend data visualization stack. 
    * Data Visualization Research Associate at Information Design Lab, IIT Bombay (2017). [Work documentation](https://prastut.github.io/dataviz ).  
 [Github](https://github.com/prastut), [CV](https://drive.google.com/file/d/15_oS6XtO_DRlITjG6WyTAEavaiSnBsdL/view).

* Aviral - Backend development and Data engineering background. Research Associate(SDE) and Masters (Thesis) Student at Boston University. [Website](http://aviralsrivastava.com/), [Github](https://github.com/kebab-mai-haddi), [CV](http://aviralsrivastava.com/assets/documents/Aviral_Srivastava_CV.pdf).

* Bhaskar - Google Certified Mobile Web Specialist. [Github](https://github.com/bhaskarSingh), [Linkedin](https://www.linkedin.com/in/bhaskar-singh-55a535b9/)

* Sahil - Problem Solver @ The Vantage Project. [Github](https://github.com/sahilnanda1995), [Linkedin](https://www.linkedin.com/in/sahil-nanda-8b1b88143/)

# Additional Information

#### How do we report on project’s progress?
Filecoin Riot/Slack channel. 

---
#### How can we guarantee results? 
In addition to complying with the 'Acceptance Criteria' , we will maintain a progress log using a shared google doc.

We will be updating our progress regularly on that shared doc.

Examples of how we have been keeping ourselves accountable in other communities:
* [PolkaViz Proposal Logs](https://docs.google.com/document/d/1IMF_Ik3mLoZrB3eDAhSb88J3aVtllyiy6c5ciNEJjAc/edit?usp=sharing)
* Zcash Service Status Dashboard [Proposal 00](https://docs.google.com/document/d/1Y_quhg9RQxqH3heT5dFd5ZqscPBoLSTt_F6uI6B0Xuc/edit#heading=h.yrqwywr1lqqr), [Proposal 01](https://docs.google.com/document/d/1DocF0E0W9JsnizV99MqNpGdSEjBdFEzM5wSKjSpmnEc/edit)

and their feedbacks:
* ![](https://i.imgur.com/j8Qt5JH.png)

* ![](https://i.imgur.com/hp7RCT1.png)

---

#### Research : 
https://docs.google.com/document/d/1uxPajf9RtPC_1ANussN84EdaViLbgzFX2JUnko7eAdM/edit?usp=sharing
(This includes the definitions of essential terms)

---
