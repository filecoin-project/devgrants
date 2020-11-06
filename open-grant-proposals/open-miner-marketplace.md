# Open Grant Proposal: `Miner Marketplace`

**Name of Project:** Miner Marketplace

**Link to RFP’s:**

- https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-5-rfps.md
- https://github.com/filecoin-project/devgrants/blob/a2981ff73ba43fde7e31db9ff9ed0b7ce4e84a14/rfps/new-mining-tools-rfps.md#miner-transaction-history-and-earnings-predictor
- https://github.com/filecoin-project/devgrants/blob/a2981ff73ba43fde7e31db9ff9ed0b7ce4e84a14/rfps/new-mining-tools-rfps.md#miner-hardware-profitability-calculator

**Proposal Category:** `app-dev`

**Proposer:** @Saumay-Agrawal

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes


# Project Description


### Problem Statement: 

Miners are at the heart of the Filecoin's decentralized storage network. They are a representative of the value that Filecoin strives to provide.

Though we feel that problems of information asymmetry and lack of transparency are being faced by the Filecoin miner community - which hinders friction-less onboarding of new miners as well as keeping existing miners peace of mind. 

We believe that Happy Miners = Happy Network! 


#### Questions (by category) that we feel miners find difficult to get answers to:

1. Information asymmetry in understanding returns:
    * What is the yield that I can expect if I run a miner? 
    * What are the overall profits and losses over the past X period since I have been running a miner? 
    * What can be my future returns look like? 
    * Who are the miners who are earning more than me and why?
    

2. Lack of transparency causing risk mitigation problems:
    * How can I make my value prop more trustworthy to potential storage clients?
        * Suppose I am a small miner, how can I compete with larger miners?
 
    * If all things are equal, how do I go about competing with other miners?  

#### Questions (by category) that we feel clients find difficult to get answers to:


1. Information asymmetry in selecting miners: 
    * No standardized and objective way to compare miner's value prop. 
   

2. Lack of transparency causing risk mitigation problems:
    * How can I go about minimizing risk when choosing a miner? 
        * How do I find out how reliable a miner/miner company is?



These above questions are intertwined in their nature as information asymmetry causes lack of transparency and vice versa. 

This cyclic nature of these questions leads to compounding problems.


<br>


### User problem validation from the community: 


1. Information asymmetry:
    * Faced by Miners: 
        * ![image](https://user-images.githubusercontent.com/10279686/98396712-2c8ad500-2084-11eb-99b5-3ba53cb5d441.png)

    * Faced by Miners and Clients both: 
        * ![image](https://user-images.githubusercontent.com/10279686/98397017-b20e8500-2084-11eb-947d-d59178dd5f7f.png)

<br>
<br>

2. Lack of transparency causing risk mitigation problems:
   * Faced by miners: 
       * ![image](https://user-images.githubusercontent.com/10279686/98396882-78d61500-2084-11eb-8ed0-b2607690591a.png)
       * Marketing get's lost in the void like this: ![image](https://user-images.githubusercontent.com/10279686/98397403-51337c80-2085-11eb-84a4-a8516164647d.png)

   * Faced by clients: 
       *  ![image](https://user-images.githubusercontent.com/10279686/98397085-ce122680-2084-11eb-9770-77e2d3065c96.png)









<br>
<br>
<br>
<br>

## Solution: 

We want to build a resource center platform focusing on miners information that aims to: 
* provide quantitative and qualitative data about miners’ performance. 
* standardizes the above information so they are sortable and filterable. 

We believe that this platform will kickstart helping the community answer the questions we had mentioned above. 


We call this platform FindSignal (tentatively) - an open miner marketplace. 
 

FindSignal will have these key components:

1. Standardized listing of all miners - 
    - that can be sorted and filtered by different attributes.
    - Search via address

2. Miner Profile - that contains various details about the miner.
    - A miner can update their profile to boost their transparency. 
    - A miner can at a glance see overall profits, losses. 

3. Calculator View - that abstracts away network economics and provides miner key insights into profitability. 
 
<br>
<br>

### Components in Detail: 

#### 1. Standardized listing of all miners: 
- On the lines of how bakers of Tezos are listed on [Baking Bad](https://baking-bad.org/)
- A filtering mechanism similar to Baking Bad to empower community members to find high signal miners. 
    - ![](https://i.imgur.com/TGY2a2a.png)
- Global search via address
- Click to view miner profile. 


The following image is of one of our team's flagship product YieldScan and this is how we envision the listing: 

![image](https://user-images.githubusercontent.com/10279686/98402108-b9d22780-208c-11eb-9ea5-e32653f6bde5.png)



<br>
<br>

#### 2. Miner Profile: 

A miner profile contains all possible information that can inform client about how the miner is performing. 

We also envision miner using their **FindSignal profile links to market themselves on social media.**

It would contain various details about the miner like:

- Generic information about the miner. Eg:

  - Name
  - Bio,
  - Contact details like email, twitter handle etc (based on miner’s discretion)

- Kind of service (or a combination of services) being provided by the miner:

  - Storage
  - Retrieval
  - Others characteristics like “repair” (when added in the future)

- Attributes measuring miner’s skin in the game

  - Committed capacity
  - Locked funds

- Attributes measuring miner’s performance in the network

  - Number of times miner went offline
  - Block reward collection
  - Storage power
  - Number of storage deals made over a period of time

- Attributes that signal trust of the miner:

  - How many clients have trusted the miner with their data.
  - How much volume per client has been entrusted with the miner.
  

- Miner Transaction History:

  - A clean no-brainer jargon-free transaction history.
      - We are inspired by Zerion style clean history which humanizes historical transaction flow. ([Sample](https://app.zerion.io/0x5b3ce67ebc795fe7e709815bc49d4300898e1b7b/history
))
     - It will help a miner understand the history of all their incoming and outgoing transactions in terms of collateral pledged, rewards, penalties, gas costs ( over time). 
  - Tactical Features:  
      - Aggregated earnings and losses over past X period. 
          - No running through logs of transactions to understand what a miner is making. 
          - This will also act as an attribute to the standardized listing. 
      - UX that helps explain where miner's funds are going so a miner can follow through easily and troubleshoot their setup if needed. 

  - Ref this [RFP](https://github.com/filecoin-project/devgrants/blob/a2981ff73ba43fde7e31db9ff9ed0b7ce4e84a14/rfps/new-mining-tools-rfps.md#1-miner-transaction-history) for more detail on the problem we intend to solve. 


- Miner Earnings Predictor: 
    - Devising an algorithm to predict miner's earning over course of time. 
        - Using history from on-chain data. 
        - Baseline assumptions will be taken to give a speculative view.
 
    - Ref this [RFP](https://github.com/filecoin-project/devgrants/blob/a2981ff73ba43fde7e31db9ff9ed0b7ce4e84a14/rfps/new-mining-tools-rfps.md#2-earnings-predictor) for more detail on the problem we intend to solve. 
 


- Miner Transparency Score. 
    - This is a gamification feature to incentivize miners to add more details to their profile. 
    - The higher the transparency score, the higher you can get to rank in the overall listing. 


- Other attributes
  - Location
  - Support for offline data transfer
  - Average client rating
  - Powergate Reputation Score
      - Ref: Reputation Module [here](https://docs.textile.io/powergate/)
 
<br>
<br>

The following image is of our flagship product YieldScan. 

* We intend to have a miner profile as close to this:
    * ![Dashboard - Validator Profile](https://user-images.githubusercontent.com/10279686/94892491-63c4ff80-04a2-11eb-8529-6d2f5ca8302e.png)

* Addition of incentivisations for miners: 
    * We’ll develop a “transparency score” based on the amount of information (both on-chain and off-chain) that’s shared by the miners to promote transparency in identities. 
    * Updating each attribute like display name, legal name, twitter handle, etc. will carry some points, which will be added to the transparency score (sample shown below)
    * <img width="858" alt="Screenshot 2020-10-02 at 10 04 36 AM" src="https://user-images.githubusercontent.com/10279686/94892500-6b84a400-04a2-11eb-9947-8e1b508c8548.png">


<br>
<br>

Note: 
* The above list of attributes is not precise. 
* Basis how we get data from the chain and getting a better understanding of what would be valuable to a miner, we will optimize accordingly. 
* Requesting the Filecoin Foundation for flexibility to allow us to design a superior end experience. 



<br>
<br>



#### Calculator View

* This view will abstract away problems statement listed in this [RFP](https://github.com/filecoin-project/devgrants/blob/a2981ff73ba43fde7e31db9ff9ed0b7ce4e84a14/rfps/new-mining-tools-rfps.md#miner-hardware-profitability-calculator). 
* The idea is to give a human friendly calculator that: 
    * strips away all jargon. 
    * connected to real-time on-chain data. 
    * helps user enter data basis $ and calculate net return on investment in $. 
        * Similar to what ETH2 ecosystem has done with this [spreadsheet](https://docs.google.com/spreadsheets/d/15tmPOvOgi3wKxJw7KQJKoUe-uonbYR6HF7u83LR5Mj4/edit#gid=842896204). 
 

These images are from one of our team's flagship product YieldScan and this is how envision solving this problem: 
 * ![image](https://user-images.githubusercontent.com/10279686/98402312-159cb080-208d-11eb-84a0-6a890470c3b6.png)
 * ![image](https://user-images.githubusercontent.com/10279686/98402599-9491e900-208d-11eb-9a4e-755e6b9cb30b.png)



<br>
<br>
<br>
<br>

## Development Roadmap

### Milestone 1 - Basic Miner Profile Live (4 weeks)

The end outcome that the team will be working towards would be to: 
1. render a frontend where you can **view basic miner profile** using the following methods: 
    * Enter any address via a search bar to go to miner profile 
    * or use findsignal.in/filecoin/miner/:address:
2. algorithm spec for: 
    * filtering and sorting mechanism. 
    * processing all transaction history to output a clean, logically grouped list. 
    * what attributes when filled increase transparency score and by how much. 


This will give us awareness on the: 
 * kind of data challenges we will face. 
 * kind of stability challenges we will face. 
 
<br>

Deliverables listed in a tabular form: 

| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1.  | Backend Setup  | Backend Setup comprises of: <ul><li>Chain Indexer - for fetching on-chain data</li><li>Database - for storing on-chain/off-chain data and aggregating results for the platform </li><li>API layer</li></ul> For chain indexers, we will be going through and basis what fits our usecase either work with the team or fork the project: <ul><li>https://github.com/filecoin-project/sentinel-visor</li><li>https://github.com/filecoin-project/filscan-backend</li><li>https://github.com/renproject/account-chain-indexer</li></ul> Database: Postgres (tentaively) |
| 2. | Miner Profile | Basic profile rendered with: <ul><li>On-chain data</li><li>Other objective metrics</li><li>Transaction History</li><li>Aggregated profit and losses</li></ul> |
| 3. | Algorithms Spec| Research team works on designing the following algorithms and publishing it's spec: <ul><li>Miner Filter and Sorting mechanism - on what attributes should the standardized list be filtered, what attributes would the user want to join and filter etc. </li><li>Miner Transaction History Processor - outputs a clean history that groups things logically</li><li>Miner Transparency Score - reward points weight to each attribute</li></ul> |

<br>

Resources that will be working + time allocation: 


| Resource | Working Days | 
| ------------- | ------------- |
| Project Mananger | 8  | 
| Full Stack Developer | 24  | 
| Research/Lead Developer| 24  | 





<br>
<br>


### Milestone 2 - Spectacular Miner Profile + Standardized Listing (4 weeks)

The end outcome that the team will be working towards would be to: 
1. finish high fidelity of miner profile. 
3. finish the standardized listing with filter mechanism.  
4. algorithm spec for: 
    * predicting miner earnings. 
    * profitability calculator basis hardware specs



<br>

Deliverables listed in a tabular form: 
 Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1.  | High Fidelity Miner Profile Design + Implementation  | Design team will work on:  <ul><li>fork designs from YieldScan and tailor the experience to needs of the Filecoin community. </li><li>Design the aggregated viewing of on-chain data</li></ul> Dev team will work on: <ul><li> integrating auth for miner to add subjective metrics </li><li>adding subjective metrics to the profile</li></ul> |
| 2.  | Standardized Listing + Filter Mechanism  | Design team will work on:  <ul><li>fork designs from YieldScan and tailor the experience to needs of the Filecoin community. </li><li>Design the UX of using multiple filters</li></ul> Dev team will work on: <ul><li> integrating standardized listing with miner profile</li></ul> |
| 3. | Algorithms Spec| Research team works on designing the following algorithms and publishing it's spec: <ul><li>Miner Earnings Predictor - ingests on-chain data for the miner and outputs a speculative view on future earnings</li><li>Hardware Profitability Calculator</li></ul> |


<br>

Resources that will be working + time allocation: 

| Resource | Working Days | 
| ------------- | ------------- |
| Project Mananger | 8  | 
| Design Technologist | 24  | 
| Full Stack Developer | 24 | 
| Research/Lead Developer| 24  | 


<br>
<br>


### Milestone 3 - Calculator View + Q/A (4 weeks)

The end outcome that the team will be working towards would be to: 
1. finish incorporating predictive earnings about miner to the miner profile. 
2. finish the calculator view.  
3. Q/A


<br>

Deliverables listed in a tabular form: 
 Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1.  | Integrating Miner Earnings into the Miner Profile   | Design and dev teams collaborate on the spec given by research team. |
| 2. | Implementing Calculator View| Design and dev teams collaborate on the spec given by the research team |
| 3. | Q/A| Stress testing + internal beta testing of the entire platform. |


<br>

Resources that will be working + time allocation: 

| Resource | Working Days | 
| ------------- | ------------- |
| Project Mananger | 8  | 
| Design Technologist | 24  | 
| Full Stack Developer | 24 | 
| Research/Lead Developer| 12  | 


<br>
<br>

### Milestone 4 - Beta Launch (2 weeks)

The end outcome that the team will be working towards would be to: 
1. onboarding miners with the help of the Filecoin community. 
2. publishing launch collaterals to market the product. 
3. integrating product feedback and solving bugs with the community. 


Resources that will be working + time allocation: 

| Resource | Working Days | 
| ------------- | ------------- |
| Project Mananger | 6  | 
| Design Technologist | 6 | 
| Full Stack Developer | 6 | 



<br>
<br>

## Total Budget Requested

Sent via Google doc to the team. 

<br>

## Maintenance and Upgrade Plans

**Maintenance**

- After project completion, maintenance or bug fixes if any.
- For next 6 months: support if the system goes down.

**Support**

- We will be available to provide guidance and troubleshooting assistance to
  - any user facing hassle in the UI

**Upgrade Plans**

- Implementing support for storage clients: 
    - there profiles. 
    - a recommendation system that takes into input client's desires with the deal they want to make and suggests them miners to store with. 
    - also helps making storage deal inside the platform itself. 

- Integration of https://sourcecred.io/ to measure and reward value creation among participants.

<br>

# Team

## Contact info

saumay@buidllabs.io

## Team Members

- Design Technologist: Abhinav

  - Designer and Frontend developer
  - Designed YieldScan for Polkadot ecosystem chains and Crypto Code School for Tezos.
  - Have experience in designing HCI solutions especially in the domain of data analytics.

- Researcher/Lead Developer: Rajdeep
  - Worked on infrastructure tools for various open source communities
  - Wrapping up the execution of Demux

- Full Stack Developer: Sahil 
    - Lead Backend dev for YieldScan. 
    - Previously built strategies for algorithmic crypto hedge fund. 

- Project Manger: Saumay
  - Has 3+ years of product-dev experience across multiple startups, research labs and companies
  - Extensive experience in wrangling data and building ETL pipelines, Go Developer.
  - Successfully executed Demux sprint.

## Team Member LinkedIn Profiles

- Abhinav - http://abhinavthukral.in/
- Rajdeep - https://github.com/rajdeepbharati
- Sahil - https://github.com/sahilnanda1995
- Saumay - https://www.linkedin.com/in/saumayagrawal/

## Team Website

https://buidllabs.io/

## Relevant Experience

Our team has solved similar information asymmetry problems for other networks:

- Livepeer pricing tool
  - Though still in its MVP stage, Livepeer pricing tool enhanced the visibility into off chain pricing data of Orchestrators (akin to Miners) in the Livepeer network
- YieldScan
  - Solves the problem of information asymmetry between the validators and nominators in the Polkadot network.

Besides this, our team has also been actively working on a project in the Filecoin ecosystem

- Demux
  - an API gateway between Livepeer and Filecoin for facilitating decentralised streaming services.

## Team code repositories

- Livepeer pricing tool - https://github.com/buidl-labs/livepeer-pricing-tool
- YieldScan - https://github.com/buidl-labs/YieldScan
- Demux - https://github.com/buidl-labs/Demux
