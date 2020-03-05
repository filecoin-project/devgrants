# RFP Proposal: `Consensus Visualization Tool` 

**Name of Project:**
Consensus Visualization Tool

**Link to RFP:** 
[Consensus Visualization Tool](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-consensus-visualization-tool.md)

**RFP Category:** 
`app-dev`

**Proposer:** @sahilnanda1995

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** 
Yes!


# Project Description


The blockchain and crypto ecosystem is already as complex for an average joe to understand. And when the user can’t visualize how things work, they can’t  wrap their heads around the concept. 

Because of the way the human brain processes information, using charts or graphs to visualize large amounts of complex data is more accessible than poring over whitepapers/raw numbers/CLI logs. Data visualization is a quick, easy way to convey concepts. 


This proposal aims to deliver an open-source blockchain consensus visualization tool that demonstrates [Filecoin’s Expected Consensus process](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-consensus-visualization-tool.md#about-expected-consensus-ec) as well as visualizes bad forks occurring in the system. 

#### Outcomes to achieve: 
The tool is aimed to serve the following user-groups:

1. Educate newcomers about the novelty of Filecoin expected consensus. 👶
2. Give powers users means to investigate the organic evolution in network activity.  🕵️‍♀️

## Deliverables

### Main deliverable: 
An interactive visualization of Filecoin expected consensus viewable in web browser. 

### Specific Deliverables: 

#### 1. Visualization Specifics: 

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
    3. Forks: 
        * Natural Forks
        * Bad Forks


3. Show the list of probable miners (according to their storage power)

#### 2. User onboarding + increasing clarity:


1. Landing Page to explain key components of the interactive viz + CTA leading to the viz. 
    * An inspiration is [weth explained](https://weth.io/) by Radar Relay team.
2. A contextualized help button built into the viz:
    * Contextualization based on the product flow and the screen the user is watching. 
    * An inspiration is the ? button in [this tool](http://nba3d.peterbeshai.com/).  

3. A help center that contains the following:  
    * Tutorials with demo usage. 
        * An [example](https://discourse.foam.space/t/introducing-foamviz-foam-developer-grants/1047/4?u=prastut) we have tried with visualization tools.  
    * Glossary of terms.
    * FAQ.

#### 3. Robustness:

1. A well-documented, human-readable codebase.
2. Work with a Filecoin node API starting with the lotus API as recommended. 
3. Well-tested and usable by a large audience during Testnet and Mainnet.

## Development Roadmap

Tentative Start: Feb 1, 2019
### Milestone 1: Get vantage on: 

1. what the viz would look like: 
    * Design sprint kickoff: Get feedback on the direction we want to take from the [low fidelity mockups we have been able to create so far](#1.-Created-Low-Fidelity-Mockups: ) from the Filecoin DevGrants Team. 
    * Low Fidelity to High Fidelity: Integrate feedback -> convert low fidelity prototypes into high fidelity design mockups (shared via Figma prototypes). 
    * Closure on design: Get feedback on the high fidelity mockups developed in point 2. 

2. and how the viz would be built: 
    * Complete data source vantage: [Continue and finish research](https://docs.google.com/document/d/1zaUlGd-gceihqrr1AQ_dEZaTbnTGR6LkAzZICRhIUpo/edit) on the list of API endpoints that will be used. 
    * Architectural Design vantage: tentative stack in mind (subject to change based on constraints identified)
        * Frontend Stack: 
            * Visualization Stack: d3.js or konva.js whichever seems more optimal depending on how custom the design gets. 
            * For managing UI state: React.js
            * For real-time experience: Socket.io
        * Backend Stack: 
            * Web Framework: Express.js
            * DB: MongoDB -> For faster retrieval of blockchain data. 
            * Filecoin Node: to get data that is not accessible by the existing node API endpoints. (will be setting up one ourself)  


People Involved: 
1. Lead Developer. 
2. Designer. 
3. Product Manager. 

Milestone Completion ETA: 22 Feb, 2020
Duration: 3 weeks. 
Funding Required: $6,000 


### Milestone 2: 🏗 stage. 

#### #buidl:
1. Front-End: static components for the viz will be built with mock data. 
2. Back-End: will be completed up to spec in with completed endpoints that will be consumed by frontend. 



#### Integration:
* Both deliverables from the above stage will be integrated. 
* From user onboarding + increasing clarity deliverables, the following will be executed:
    * Contextualized help button. 
    * Help Center. 

People Involved:
1. Lead Developer: working on backend. 
2. Frontend Developer.
3. Designer: interfacing with frontend developer when help needed. 
4. Product Manager. 

Milestone Completion ETA: 1st April, 2020 
Duration: 5 weeks. 
Funding Required: $10,000

Just in time for tentative mainnet launch ([source](https://filecoin.io/blog/roadmap-update-2019-q4/)), will be quite exciting to see when the network activity with real incentives on the viz.  

### Milestone 3: 🎁 stage.

1. Beta release of the interactive viz is deployed live and shared with the community. 
2. Feedback exercise started around the beta release. 
    * Here we will collaborate with Filecoin Dev Grants Team:
        * To give us feedback
        * And point us to people with whom we can schedule user feedback calls with. 
    * These feedback calls will enable us to understand: 
        * kinks in the user experience of the implementation 
        * level of clarity that would be required to write/record explainers and FAQ's . 
    * We are also open to holding 2 community calls (1 community call/week) inviting feedback from the community at large. 

3. Based on the insights gained from the feedback, the remaining user onboarding + increasing clarity deliverables will be executed:
    * Landing Page for the viz. 
    * Additions to Help Center.  

People Involved:
* with getting user feedback and iterating on those feedback: 
   1. Designer.
   2. Product Manager.
 
* executing remaining deliverables: 
   1. Lead Developer. 
   2. Frontend Developer. 

Milestone Completion ETA: 14th April, 2020 
Duration: 2 weeks. 
Funding Required: $2000

### Milestone 4: 🧐 + 🛠 stage. 
* Production deployment.
    * Also includes iteration on feedbacks from Milestone 3.  
* Codebase documentation. 
* Q/A to ensure robustness.  
* Migrate repositories to the Filecoin Shipyard. 


People Involved:
1. Lead Developer. 
2. Product Manager. 

Milestone Completion ETA: 1st May, 2020 
Duration: 2 weeks. 
Funding Required: $1500


## Total Budget Requested


 | Milestone | Budget |
 |-----|---------:|
 | 1 | $6,000 | 
 | 2 | $10,000 | 
 | 3 | $2,000 | 
 | 4 | $1,500 | 
 |**Total**| $19,500 |


Since this will be our first contribution to the Filecoin Community, we are not charging for product management costs in good faith. 

## Maintenance and Upgrade Plans

Maintenance: 

* After project completion, maintaining and iterating on user feedback on the system actively for the T+3 months. That means bug fixes, upgrading API endpoints to keep the viz up and running with the specs mentioned in the current proposal.
* For 1 year: support if the system goes down.

Upgrade Plans: 

We are looking to expand this project by building a bigger umbrella that comprises of potential visualization ideas applicable to the Filecoin network. Some ideas that we have: 
* Visualizing the adoption + evolution of storage market on a planetary scale. 
    * Inspired from this [example.](https://blueshift.io/international-trade.html) 
* Visualize a peer map with density of storage and retrival miners with telemetry data like blocks produced: 
    * Inspired from this [example.](https://telemetry.polkadot.io/#map)
* Visualizing development activity on the Filecoin network. 
    * Inspired from this [example.](https://twitter.com/Superhuman/status/1106583185402417152)

Marketing ideas:

* Twitter Bot: Any significant event on the network can be made into a gif and shared. 
    * Example of tweet:
        * Title: “500 Miners joined the Filecoin network”
        * Body: <gif of the viz from - 5 seconds to + 5 seconds>

# Team

## Contact Info

Email: sahil@thevantageproject.com

## Team Members

* Lead Developer: Sahil
* Designer: Saumya
* Frontend Developer: Dhruv
* Product Manager: Prastut



## Team Member LinkedIn Profiles

* Sahil: https://www.linkedin.com/in/sahil-nanda-8b1b88143/
* Saumya: https://www.linkedin.com/in/skrn/
* Dhruv: https://www.linkedin.com/in/dhruvbhatnagar10/
* Prastut: https://www.linkedin.com/in/prastut/


## Team Website

[BUIDL Labs](https://buidllabs.io/)


## Relevant Experience

Our team comprises of people having background in theory-based visual design and analytical methods. We like to discover and validate insights from data, then translate them into systems, processes, and frameworks that help in mindfully created human-information interactions.

The advent of high technology information, imaging, networking, mobile devices and social media systems has fostered a modern renaissance in visualization. Just as the great artists of the European Renaissance were also designers, inventors, scientists & architects, we think the modern visualizers have an essential role to play in decoding the increasingly complex world and make it accessible to all humans.

Curiosity led us down the blockchain ecosystem rabbit hole. We wanted to analyze the organic activity happening on these public blockchains but the reality is that the format of these public datasets make it very difficult to analyze, understand and then derive insights. 

Hence, we want to build tools that can help in solving this problem and give users means to make informed decisions without relying on any third party. Visualizations are one part of this toolkit. 

Brief info about the team members: 

* Lead Developer: Sahil 
    * Budding Filecoin Researcher + Go Developer. 
    * Built [PolkaViz](https://polkavizproject.surge.sh/). Before that built algorithmic trading strategies for a crypto hedge fund. 
    * [GitHub](https://github.com/sahilnanda1995)

* Designer: Saumya 
    * Currently spending mindspace in solving UX problems in onboarding people to decentralized economic networks. 
    * Previously built and shelved a social network for developers. Led design and product management for it. 
    * [GitHub.](https://github.com/saumyakaran)

* Frontend Engineer: Dhruv 
    * Built [FOAMViz project](https://github.com/thevantageproject/foamviz). Experience with visualizing geo-spatial data and in building for AR applications using Unity and three.js.   
    * [GitHub.](https://github.com/dhruv10)



* Product Manager: Prastut
    * Currently spending mindspace in observing and understanding incentives for participation for core actors involved in upcoming projects that use PoS. Eager to deep dive into Filecoin Expected Consensus in detail during the project.  
    * Have 5+ years of product-dev experience across multiple startups, research labs and companies. Will help the team with nuances on how to best visualize data from end user PoV leveraging the experience picked up through the following projects: 
        * Architected [Polkaviz](http://polkavizproject.surge.sh/) project. 
        * Built the entire frontend data visualization stack for [Centify](https://centify.surge.sh/#/). 
        * Was a data visualization research associate at Information Design Lab, IIT Bombay. [Work documentation.](https://prastut.github.io/dataviz)
    *  [GitHub.](https://github.com/prastut)
       



## Team Projects

Similar projects Github repo links: 

1. [PolkaAnalytics](https://github.com/buidl-labs/PolkaAnalytics)
2. [PolkaViz](https://github.com/buidl-labs/polkaviz)
3. [FOAMViz](https://github.com/buidl-labs/foamviz)

You can check out our[ Github profile](https://github.com/buidl-labs) as well. 

# Additional Information

## Pre-Proposal Stage: 


The critical constraint for the viz is the design i.e how it works. Everything hinges on the design to score well on comprehensibility, utility, user engagement and delight!

Hence our team decided to do homework at our end to be better prepared to handle the project. 

What we have been able to do so far: 
1. Created low fidelity mockups for some parts of the tool. 
2. Started gaining awareness on the list of node API endpoints that will be used to fetch data for the tool. 

#### 1. Ideation + Low fidelity mockups for some parts of the tool: 



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




#### 2. Node API endpoints Research

We are documenting node endpoint research on this [google doc.](https://docs.google.com/document/d/1zaUlGd-gceihqrr1AQ_dEZaTbnTGR6LkAzZICRhIUpo/edit?usp=sharing)

#### 3. Research Dump
Definitions of essential terms that we encountered in deep diving in the Filecoin rabbit hole have been jotted down [here]( https://docs.google.com/document/d/1uxPajf9RtPC_1ANussN84EdaViLbgzFX2JUnko7eAdM/edit?usp=sharing). 


## How do we ensure self-accountability? 
In addition to complying with the 'Acceptance Criteria' , we will share weekly progress documented on a google doc in Filecoin Riot Channel. 

This is how we have kept/keep ourselves accountable in some of the projects we have built: 
* [PolkaViz Proposal Logs](https://docs.google.com/document/d/1IMF_Ik3mLoZrB3eDAhSb88J3aVtllyiy6c5ciNEJjAc/edit?usp=sharing)
* Zcash Service Status Dashboard [Proposal 00](https://docs.google.com/document/d/1Y_quhg9RQxqH3heT5dFd5ZqscPBoLSTt_F6uI6B0Xuc/edit#heading=h.yrqwywr1lqqr), [Proposal 01](https://docs.google.com/document/d/1DocF0E0W9JsnizV99MqNpGdSEjBdFEzM5wSKjSpmnEc/edit)


and the respective community members feedback:
* ![](https://i.imgur.com/j8Qt5JH.png)

* ![](https://i.imgur.com/hp7RCT1.png)
