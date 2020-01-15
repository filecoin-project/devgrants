# RFP: `Reputation System`

**Name of Project:** Miner Reputation System

**Link to RFP:** 
[Reputation System](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-reputation-system.md#rfp-reputation-system)

**RFP Category:** `app-dev`

**Proposer:** `@sahilnanda1995`


**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** 
Yes!


# Project Description

As the number of storage miners increases on the network, knowing the quality and reputability of miners on the network becomes an unscalable task for any specific participant. 

Understanding the quality of any given miner can be especially important for storage clients, who may have different requirements about the types of miners with whom they might wish to store their data.

To solve the above problem, we envision a platform that lets people make informed decisions for themselves based on high-quality, free, public information. The platform should:
1. standardize miner's subjective reputation and quality into objective variables that can be analysed. The standards will be evolving based on: 
    * storage clients needs and requirements. 
    * market forces. 
2. incentivizes radical transparency from miners. 


This proposal attempts to address a small scope of the above vision by making an MVP of a reputation system -  whereby storage clients and network participants may submit substantiated feedback on storage miners to create a reliable source of truth on the quality of miners offering storage on the Filecoin network. 



## Deliverables
* An service that allows:
    * Storage clients to submit feedback on a miner.
    * The service to validate that feedback against events on the Filecoin network.
* An API for the above service: 
    * conforming to industry best practices.
    * Users to query and consume information about a miner in question.
* A simple web application that uses both this service and go-filecoin to perform the intended workflow.
* Tutorial workflow with demo usage.
* Well-documented, human-readable codebase.


### Specifics of service:


#### /get
The users will be able to query the following for a particular miner: 
* Metrics mentioned in RFP: 
    * Number and % (where applicable) of deals with no penalties
    * Number and % (where applicable) of slashed contracts
    * Number and % (where applicable) of dropped contracts
    * Number and % of failed deals (if possible) -- i.e. the number of deals that were attempted but failed, possibly due to this miner having spotty connectivity
    * % of retrieval requests successfully fulfilled
    * Number of files retrieved
    * Lifetime data stored
    * Lifetime data retrieved
* Metrics that we have thought of: 
    * Collateral: 
        * Reason: Over collateralization may signal more skin in the game fr. 
    * Storage Price (in FIL/byte/block): 
        * % deviation of storage price from: 
            * mean of all storage prices on the network. 
            * median of all the storage prices of the network. 
        * Reason: Some miners may be overpricing/underpricing their storage with respect to the market. 
    * % of miner storage being used.  
        * Formula = used storage/total storage. 
        * Reason: Miners hovering around > 80% consistently may signal more trust-worthyness. 
    * Uptime:
        * Reason: This is a more generic metric to track then failed deals. A miner may be up consistently but not getting any deals do to other reasons. 
    * Miner Proactiveness: 
        * Delta of time since filecoin published a new version and the minder updated itself. 
        * Reason: 
            * Smaller the delta, the more proactive the miner. 
            * Miners who don't update are risky. 


   
### Specifics of web app: 


#### Home page:
Displaying  list of miners currently providing space for allocation with the following info:
* Miner
* Miner Score
* Used Storage
* Available storage
* Storage Price
* Valid till
* Status

 
![](https://i.imgur.com/OsVK6v2.png)

^ Early Prototype. 

<br><br>

#### Miner Individual page:
* Miner stats card containing information:
    * Miner Address
    * Filecoin version
    * Collateral 
    * Miner geographic location
    * Storage Metrics: Used/Available/Total Storage. 

* Miner Score Table: (10 days average):
    * [Final/Average Score](#How-will-scores-be-calculated?)
    * Individual characteristics score:
        * Latency
        * % of successful deals
        *  %  of slashed and dropped contracts
        * etc

* Comparison with storage miners with same score:
    * Storage price
    * Collateral
    * Est. uptime
    * Stored data

* Substantiated feedback:
    * identifying the user:
        * a message-signing-based authentication mechanism with a user's public address as their identifier.
    * identifying the event:
        * enter dealid/(id associated with the event): 
        * Choose check event:
        * Comment/feedback
        * Submit
        * Post if event is verified.


![](https://i.imgur.com/zDz75Bd.png)

^ Early Prototype. 



## Development Roadmap

Tentative Start: Feb 1, 2019
### Milestone 1: Get vantage on: 

1. Scope of the reputation system service: 
    * Collaborate with FileCoin DevGrants team to: 
        * Gain feedback on the metrics we have thought of. How relevant would they be for users now?  
        * Gain awareness on the kinds of objective feedback users will give that can be verifiable from the service.
    * Iron out reputation score logic that will be the single metric that all miners will be ranked upon. 
    * Finalize the reputation system service requirements spec sheet.
     
2. and how the tool would be built: 
    * Syncup process from Filecoin Network to DB. 
    * Architectural Design vantage of the service.   

People Involved: 
1. Lead Developer. 
2. Filecoin Researcher. 
3. Devops Engineer. 

Milestone Completion ETA: 15 Feb, 2020
Duration: 2 weeks. 
Funding Required: $10,000 


### Milestone 2: #buidl-ing the service 

1. Setting up the sync progress from Filecoin Node to DB. 
2. Writing API's + code for users to: 
    * query the miner metrics above.
    * submit claims: 
        * that get verified via data that is contextual to the claim. 
        * if verification succeeds: claims would get stored. 
        * if verification fails: claim context will get stored and relevant response will be sent back. 


People Involved: 
1. Lead Developer. 
2. Backend Engineer
3. Filecoin Researcher. 
4. Devops Engineer. 

Milestone Completion ETA: 15th April, 2020
Duration: 8 weeks
Funding Required: $20,000


### Milestone 3: 🐶-fooding the service: 

via building a simple web app that has the following screens: 
1. Home page: 
    * display tabular list of miners with current reputation score. 
    * able to view, search, filter miners based on reputation score. 
3. Specific Miner Page: querying miner details from the service. 


People Involved:
1. Lead Developer. 
2. Frontend Developer.

Milestone Completion ETA: 7th May, 2020
Duration: 3 weeks. 
Funding Required: $8,000

### Milestone 4: 🧐 + 🛠 stage.
* Production deployment.
* Codebase documentation.
* Q/A to ensure robustness.
* Migrate repositories to the Filecoin Shipyard.

People Involved:
* Lead Developer.
* Filecoin Researcher. 

Milestone Completion ETA: 1st May, 2020 
Duration: 2 weeks. 
Funding Required: $1,500


## Total Budget Requested


 | Milestone | Budget |
 |-----|---------:|
 | 1 | $10,000 | 
 | 2 | $20,000 | 
 | 3 | $8,000 | 
 | 4 | $1,500 |
 |**Total**| $39,500 |



## Maintenance and Upgrade Plans

Maintenance: 
* After project completion, maintaining and iterating on user feedback on the system actively for the T+3 months. Bug fixes if any. 
* For 1 year: support if the system goes down.

Upgrade Plans:

As we approach mainnet launch, real users and their use cases will become more visible. We plan to analyze the network activity and incorporate the highly requested use-cases in the reputation system (service + web-app). 


# Team

## Contact Info

Email: sahil@thevantageproject.com

## Team Members

* Lead Developer: Aviral
* Filecoin Researcher: Sahil
* Backend Developer: Saumay
* Frontend Developer: Bhaskar
* DevOps: JP

## Team Member LinkedIn Profiles

* Aviral: https://www.linkedin.com/in/sriavi/
* Sahil: https://www.linkedin.com/in/sahil-nanda-8b1b88143
* Bhaskar: https://www.linkedin.com/in/bhaskar-singh-55a535b9/
* JP: https://www.linkedin.com/in/jayprakashjp/

## Team Website

[The Vantage Project](https://www.thevantageproject.com/buidl/)


## Relevant Experience

Our team is currently deep diving into understanding incentives for participation for core actors involved in upcoming projects that use PoS. Filecoin is one the biggest projects to launch in this year and would provide a lot of exciting opportunities to understand user adoption and the challenges they face while operating in such a novel paradigm. 

We see this proposal as an opportunity to observe the network evolution more closely by building tools that we ourselves would use + helping the community at large. 

Brief info about the team members: 

* Lead Developer: Aviral 
    * Setup data infrastructure for multiple startups in India in the role of a data engineer. Will be leveraging that experience here.    
    * [GitHub](https://github.com/kebab-mai-haddi), [Website](http://aviralsrivastava.com/).

* Filecoin Researcher: Sahil  
   * Budding Filecoin Researcher + Go Developer. 
   * Built [PolkaViz](https://polkavizproject.surge.sh/). Before that built algorithmic trading strategies for a crypto hedge fund.
   * [GitHub](https://github.com/sahilnanda1995)

* Backend Developer: Saumay
    * Extensive experience in wrangling data and building ETL pipelines. 
    * [Github](https://github.com/Saumay-Agrawal)

* Frontend Engineer: Bhaskar Singh 
    * Worked on [PolkaAnalytics](https://polkanalytics.com/#/dashboard). 
    * Previously built and shelved 2 startups. Led frontend for them. 
    * [GitHub.](https://github.com/bhaskarSingh)


* Devops: JP
    * 10+ years of tech experience. Ex Goldman Sachs, Yahoo. 
    * [GitHub.](https://github.com/jayprakash1)
       


## Team Projects

Similar projects Github repo links: 

1. [PolkaAnalytics](https://github.com/thevantageproject/PolkaAnalytics)
2. [ZCash Service Status Dashboard](https://github.com/thevantageproject/zcash_service_status_dashboard)

You can check out our[ Github profile](https://github.com/thevantageproject/) as well. 

# Additional Information
[Research Document](https://docs.google.com/document/d/119CDu2hU5ArRvdt2rDoqKQAuuux1_37Z4c_lb8OXNak/edit?usp=sharing)

#### How will scores be calculated?
The raw results from the previous 7 days of benchmarks are compared across the results of the rest of the miners to assign a score in different categories: latency, % of successful deals, % of slashed and dropped contracts, etc. Scores in the 0-10 range are assigned as percentiles - this means that the top 10% of storage miners on a category will receive a 10, the next 10% will receive a 9 and so on. The final Average Score is the average of the 3 previous scores.

#### What are stats benchmarks?
A storage miner monitoring system aimed to determine the quality of the service of the miners and detect potential issues in their configuration. This will aspires with it to strengthen the storage network and allowing storage clients to improve the miners selection process.

With attempts to sign contracts/deal with every miner in the network, and if successful, will upload and download a small file every 2 hours to test the miner capabilities. From this data, latency, upload throughput and download throughput can be determined.

#### How is the uptime calculated?
We can determine a storage miner is offline through the following algorithm: every two hours, a file is attempted to be uploaded and downloaded. If the storage miner times out the connection or is unavailable, the test will be repeated 4 additional times separated by 3 minutes each. If the storage miner proves to be unavailable on all of them, the host will be flagged as offline.

When a file contract could not be signed with the storage miner with previously, the host will be flagged as offline.
