# RFP Proposal: `Consensus Visualization Tool` (WIP)

**Name of Project:**
Consensus Visualization Tool

**Link to RFP:** 
[Consensus Visualization Tool](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-consensus-visualization-tool.md)

**RFP Category:** 
`app-dev`

**Proposer:** `thevantageproject`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** 
Yes

**Disclaimer:** Research is still in progress. Will soon be updating after getting more awareness around data.

# Project Description

This proposal aims to deliver an open source blockchain consensus visualization tool that specifically demonstrates [Filecoin’s Expected Consensus process](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-consensus-visualization-tool.md#about-expected-consensus-ec) as well as visualizes bad forks occurring in the system. 

#### Outcomes to achieve: 
The tool is aimed to: 
1. educate newcomers about the novelty of Filecoin. 👶
2. give powers users means to investigate the organic evolution in network activity.  🕵️‍♀️

## Deliverables

Main deliverable: Provide an interactive visualization of Filecoin consensus viewable in web browser that achieves the [above mentioned outcomes](https://hackmd.io/9NyGrfzXRfGU-VTpjPaLqw?both#Outcomes-to-achieve). 



Specifics: 


### 1. Visualization Specifics: 

    1. Provide live information updates of the following:
        1. New messages
        2. Blocks
        3. Miners
        4. Tipsets
        5. Ancestors
        6. Forks

    2. Visualize the formation of: 
        1. Blocks
        2. Tipsets. 
        3. Forks. 

    3. Show the list of probable miners (according to their storage power)

### 2. Support User's Journey:

Provides explainers for what is happening and a glossary of terms by providing users: 
1. Website with an FAQ section. 
2. Tutorials with demo usage. An [example](https://discourse.foam.space/t/introducing-foamviz-foam-developer-grants/1047/4?u=prastut) we have tried with visualization tools.  

### 3. Reduce cognitive load for Filecoin community
We will try our best to keep these metrics a priority + work with Filecoin core team to do what's best for the community: 

1. A well-documented, human-readable codebase
2. work with a Filecoin node API starting with the lotus API as recommended. 
3. well-tested and usable by a large audience during Testnet and Mainnet

## Development Roadmap

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Finalize scope, a list of node API endpoints to be used, UI mockups + feedback rounds with the Filecoin DevGrants team, architectural design | TBD | 2-3 weeks |
| 2 | Implementation interoperable with a Filecoin node and User tested | TBD | 4 weeks |
| 3 | All project deliverables are completed and added to the [Filecoin Shipyard](https://github.com/filecoin-shipyard) (website, documentation, codebase) | TBD | 2 weeks |
| 4 | Maintenance and Upgrades during Testnet and Mainnet | TBD | 2 weeks |


Specifics details: 

### Milestone 1: Finalize Scope. 
We imagine an extensive collaborative exercise between FileCoin Dev Grants team and our team. 

We will try to ensure that we ask researched questions and reduce cognitive load for your team. 

Specifics: 

1. Get feedback on the direction + [low fidelity mockups we have been able to create so far](https://hackmd.io/9NyGrfzXRfGU-VTpjPaLqw?both#Fork-Visualization). 
2. Integrate feedback -> converted low fidelity prototypes into high fidelity design mockups in Figma which will be shared. 
3. Again get feedback. 
4. After closure on design, our team will continue our research in getting further clarity on where the data will come for to render the design. 

People Involved: 
1. 
Timeline: 2-3 weeks. 

### Milestone 2: 🏗 stage. 

#### #buidl:
1. Front-End: static components containing all the specs will be developed.
2. Back-End: will be be completed up to spec in with completed endpoints in consume by the front-end team. 


#### Integration:
Both deliverables from the above stage will be integrated. 



### Milestone 3: 🎁 stage.

1. MVP deployed live and shared with the community. 
2. Feedback excersise started around the MVP. 
    * Here we will involve Filecoin Dev Grants Team to give us feedback + point us to people with whom we can schedule user feedback calls with. 
    * These feedback calls will enable us to understand kinks in the user experience of the implementation as well as the level of clarity that would be required to write/record explainers and FAQ's . 


### Milestone 4: 🧐 + 🛠 stage. 
Q/A to ensure robustness.  



## Pre-Proposal Stage: 

We believe that the outcome of the first milestone is to gain clarity on scope and get Filecoin Dev Grants team and our team on the same page of what would be the tool look like. 

What we have been able to do so far: 
1. Created low fidelity mockups for some parts of the tool. 
2. Started gaining awareness on the list of node API endpoints that will be used to fetch data for the tool. 

### 1. Created Low Fidelity Mockups: 
Note: We will soon be updating with the figma prototypes as soon as we finalize the design on our end. 


##### Fork Visualization:
* A simple list of the history of all the forks created(Height, Parent, Children, current weight) will be shown.

![](https://i.imgur.com/ilvGFbb.jpg)
![](https://i.imgur.com/2CU8G8Y.png)

##### Messages Visualization:
* Whenever a new message arrives, we drop it onto an existing heap of the pending pool of messages.
* The set of messages that form the next block disappear and the remaining heap re-shapes itself, i.e. , remaining blocks fall to take up the empty space (We have the concept of **gravity** in mind !).
* The newly created block is displayed on the side of the heap. It will be interactive, i.e. , its corresponding details would be shown when clicked.
* The block will then get added to the existing blockchain (main chain) which will be displayed on the bottom half.
* If multiple blocks are mined at the same time, a TipSet will be created and all the corresponding blocks will be displayed.
* When a Tipset is created, we will create an alert to display the quantity of blocks in that tipset formed.

![](https://i.imgur.com/IGbj6jz.jpg)

##### Miner Visualization:
* We will display the list of active miners with the most storage power along with their probability to mine next (Their SP / Total SP).
* We will also display the probability of fork occurrence (Formula proposed in pic).
* We can use circles to depict active miners in decreasing order of their storage powers. Greater the radius of a circle, larger that miner's storage power.
* The next elected miner will be highlighted.
* This would help in visualising the **expected consensus** protocol (Since the miners will be arranged in descending order of their SP, the next probable miner would likely be among these top miners with the most SP).

![](https://i.imgur.com/C6zY27a.jpg)


##### Chain Visualization:
* This will show the filecoin chain.
* By default, the main chain will be displayed.
* We will add a **zoom slider** which will be used to display the forks created.
* 100% zoom -> main chain
* 80% zoom  -> some of the heavy forks
* 0% zoom -> the complete set of forks (if possible)
* We can also show the forks created by showing the fork links with a different colour.

##### Tipset Visualization:
* We will show the history of the Tipsets created using a list.
* We will also display the 3 latest tipsets with their complete details (height, parent, children, current chain weight).



##### Show when natural and bad forks occur (e.g. >51% malicous attack)
WIP


### 2. Node API endpoints Research

We are documenting our endpoint research on this [google doc.](https://docs.google.com/document/d/1zaUlGd-gceihqrr1AQ_dEZaTbnTGR6LkAzZICRhIUpo/edit?usp=sharing)


<br><br>

## Maintenance and Upgrade Plans
* Maintaining the system actively for the next 3 months. That means bug fixes if any with the specs mentioned in the current proposal.
* For 1 year: support if the system goes down.




## Total Budget Requested

Total Budget: $15,500 - $19,000
 
 | Role | Rate/Hr | HC | Man-Hour | Man-Week | Price |
 |-----|---------|----|-----------|-------------|------|
 | Design | $50 | 1| 30-40 | 1 | $1,500 - $2,000 |
 | Front-Dev | $50 | 1 | 80 - 100 | 3 | $4,000 - $5,000 |
 | Back-Dev| $50 | 2 | 200 - 300 | 4 | $10,000 - $12,000 |


Since this will be our first contribution to the Filecoin Community, in a gesture of good faith project management costs would be free of charge.

Also, after research we noticed that currently there is no working filecoin api client which can be used by developers to build applications on Filecoin. Let us know if this is something community needs help with. 

# Team
The Vantage Project

## Contact Info

Email: hello@thevantageproject.com

## Team Projects

![](https://i.imgur.com/bUYotyo.png)

You can checkout all the completed and ongoing projects and project repositories from our [Projects gallery](https://github.com/thevantageproject/web/wiki/Projects)

## Team Website

[The Vantage Project](https://www.thevantageproject.com/buidl/)

## Team Members

About our team: 


* Back-Dev: Sahil [Github](https://github.com/sahilnanda1995)
* PM- Prastut [Github](https://github.com/prastut)
* Back-Dev: [Aviral](http://aviralsrivastava.com/) [Github](https://github.com/kebab-mai-haddi)
* Design: Saumya [Github](https://github.com/saumyakaran)
* Front-Dev: Bhaskar [Github](https://github.com/bhaskarSingh) 

## Team Member LinkedIn Profiles

* Sahil: https://www.linkedin.com/in/sahil-nanda-8b1b88143/
* Prastut: https://www.linkedin.com/in/prastut/
* Aviral: https://www.linkedin.com/in/sriavi/
* Saumya: https://www.linkedin.com/in/skrn/
* Bhaskar: https://www.linkedin.com/in/bhaskar-singh-55a535b9/



## Additional Information

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
