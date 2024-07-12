# Fil+ Notary Leaderboard

*We're seeking proposals for the development of a Filecoin Plus Notary leaderboard* 

The purpose of the Filecoin Plus Notary leaderboard is to have a public facing site that displays the Fil+ Notaries ranked by overall average of key attributes. 
Those attributes will be a collection of data points such as Time to Data, Datacap allocated in the last 30 days, and participation in community events. This 
dashboard should display the Notaries in a ‘scorecard' tile layout and highlight requirements set below in deliverables. For a reference on ideal format layout, 
please reference: https://stewards.eth.limo/

## Deliverables
1. Dashboard of scorecards in a easy to view and visually appealing layout
  * P1 - View of notaries ranked by overall averages
  * P2 - Ability to rank by other attributes, including
    - Amount of DataCap allocated in the last 4 weeks,
    - Total amount of DataCap allocated,
    - LDN Stats
    - Community Participation
  * P3 - Tier and stack rank the Notaries based on performance
    - *These functions will be based on engagement levels

2. Notary scorecard view
Ability to view all of the Notaries (around 30 as of Dec 2021) as scorecard titles on the dashboard. The initial datasets to be integrated and tile cards created 
from:

* Notary info
  - P0 - Name, Organization, GitHub handle, GitHub profile picture
  - P0 - Region of operation
  - P2 - Notary since (epoch when they were approved on chain → date)

* Manual verification stats
  - P0 - Average TTD
  - P0 - Number of previous Approvals
  - P0 - All apps (TTD → time to decision)
  - P0 - Time to first response for due diligence
  - P0 - Amount of DataCap allocated in the last 4 weeks
  - P1 - Average number of comments on GitHub issue before allocation decision (issue is closed)
  - P2 - Number of clients DataCap allocated to directly
  - P2 - Amount of DataCap available
  - P2 - Amount of DataCap allocated
  - P2 - Amount of DataCap allocated used in deals by clients

* LDN stats
  - P0 - TTD for LDN DataCap allocations
  - P1 - Total number of LDN DataCap allocations signed
  - P1 - Number of unique clients LDN allocations signed
  - P1 - LDN DataCap allocations signed in the last 4 weeks
  - P2 - Total amount of DataCap allocated through LDNs
  - P2 - Average number of comments on LDN applications
  - P2 - Transitions into # of flags raised by FraudWatcher being addressed

* Governance
  - P0 - Number of Github Discussions created
  - P1 - Number of Notary calls attended
  - P1 - Discussions participated on
  - P2 - Percentage rating of "participation: high/medium/low" (based on % of attendance against peers)

## Development Roadmap

For the above functionalities, 1 to 2 months of development is forecast.
Milestones will be set by the developer and communicated to the Filecoin Foundation via a bi-weekly 30minute update meetings.
You'll be working closely with Kevin Wray, Fil+ Community Engagement: Kwray@fil.org

## Proposal Guidelines

Proposals should include a value proposition about how it will benefit the Filecoin ecosystem, technical detail about what your team intends to build and 
evidence your team is capable of creating good, re-usable open source code, compelling product demos and great documentation, and a reasonable technical 
development plan broken down into milestones. 

Proposals should include:

1. Contact info
2. Team members, and linkedIn profiles
3. Team website
4. Relevant experience
5. Team code repositories
6. Additional information

To submit a proposal, submit an issue using this [RFP Proposal Template](https://github.com/filecoin-project/devgrants/issues/new?assignees=realChainLife&labels=&template=rfp-application.md&title=RFP+Application).
