To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Lotus Farcaster`

**Name of Project:**  `lotus farcaster V2`

**Proposal Category:** Choose one of `app-dev`

**Proposer:** `s0nik42`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

lotus-farcaster V2 brings additionnal functionnalities to lotus farcaster (see tables below).

Lotus farcaster is a Visualization and Analytics tool for Lotus Filecoin node It leverages Prometheus, Grafana and Python.

**Lotus farcaster as 20 forks, was downloaded by more than 200 times and get 20+ new users during the last 2 weeks.**

We want it to be accessible and designed for any types of miners.
It's designed to manage all type of architecture :
* single miner, 
* single miner with workers
* multiple miners farm.

We want to move from console based monitoring to a proactive professional monitoring grade. Compared to the existing console tools, users will benefits :
* consolidated information
* data history
* push notification
* Visual monitoring
* Scalable solution
* User management
* Security
* Mobile device accessibility

## How it works

### Architecture
```
 --------------------------            ------------            ---------------------            ------------
| Lotus Miner              | <------- | Prometheus | <------- | Grafana             | <------- | Web Client |
| lotus-exporter-farcaster |           ------------           | farcaster-dashboard |           ------------
 --------------------------                                    ---------------------
```

### lotus farcaster comes with 2 Components :
* A Grafana dashboard
* lotus-exporter-farcaster a standalone and configuration-less python script executed every minute by the crontab.
It generates metrics that are exposed by node-exporter to prometheus.

### Security
The design and choice of these components, was made to keep a high level of security :
- metrics are pulled from the miner to avoid compromising network or management servers
- lotus-exporter-farcaster doesn't bind any ports to avoid exposing the miner to external threat
- lotus-exporter-farcaster run under unprivileged user (ideally lotus user) to avoid system being compromised
- The global solution doesn't rely on any cloud or remote component. To avoid data leak.

lotus-exporter-farcaster is running locally on the miner without any specific privilege nor access to other servers. 

### It will follow [prometheus guidelines](https://prometheus.io/docs/instrumenting/writing_exporters/) :
* configuration-less
* ressources inexpensive
* standard prometheus metrics naming
* compatible with 3rd parties dashboards and exporters

## Benefits

* Easy to deploy
* Configuration less
* Small footprint
* Collect lotus node and miner data
* Only rely on API
* Data are pulled from the Prometheus server (increase security)  
* Deployed on the miner node only
* Run under Unprivileged user

## Dashboard Features

|Feature      |Status       |Comments           |
|-------------|-------------|-------------------|
|Sectors      | V1          |                   |
|Mpool        | V1          |                   |
|Storage Info | V1          |                   |
|Workers Info | V1          |                   |
|Sealing      | V1          |Job + Scheduler    |
|Power        | V1          |                   |
|Wallets      | V1          |                   |
|Chain        | V1          |Head + Sync Status |
|Deadlines    | V1          |                   |

**New Features :**
|Deals        | V2          | View of current sealing deals (State/Price/Size/collaterals/From/Is Verified/etc... |
|Gas Fee      | V2          | Realtime gasfee and History (requested by Community) |
|Sectors State| V2          | Identify faulty sectors in deadlines (requested by Community) |
|Fil+ Datacap | V2          | REaltime and Historical view of Datacap allocated to the miner addresses |
|Max Quality Adjusted Power| V2 | Calculate the max power you can expect from the miner (it's a forcast of how much power you will get after the next deadline is the miner prove all its capacity) |
[Sectors w/ Deals| V2       | Break down of sectors in 3 categories : CC / inc. deals / inc. Verified. Current and historical view |
|Address lookup | V2        | Allow miners to provide a lookup file (Adress=Name/Label) allowing reports to be more readable. The lookup apply to any panels of grafana containing adresses (Wallet / Deals / Fil+ / etc...).
|Farcaster Status | V2      | Farcaster reports any problems in scraping data. To ensure the dashboard is accurate
|Deployment toolset | V2    | provide additionals scripts to simplify farecaster deployment and troubleshooting.


## Roadmap

01 oct 2020 : Project initiated
15 oct 2020 : Design / Specifications / Mockup
20 oct 2020 : Presentation during [Filecoin Liftoff Week](https://www.youtube.com/watch?v=cyer6_gSv78&ab_channel=Filecoin) 
26 oct 2020 : First release open to beta tester
27 oct 2020 : Private GitHub repo, open to beta tester from PL and the community : @benjaminh83, @flyworker, @hsanjuan, @jennijuju, @ribasushi, @RobQuistNL, @std, @stuberman, @whyrusleeping @Patrick - Factor8 Solutions @Phi-rjan 
26 nov 2020 : Support lotus 1.2.1 + automatic installation script
30 nov 2020 : first public release

| Milestone                                                                              | Hours | Cost     |
| -------------------------------------------------------------------------------------- | ----- | -------- |
| Collect needs from the community, design, planning                                     | 16    | € 1 152  |
| Upskill on the different systems                                                       | 16    | Offered  |
| Studing Lotus API and reverse iengineering                                             | 24    | € 1 728  |
| Exporter development (lotus V1.2.1)                                                    | 36    | € 2 592  |
| Dashboard development (lotus V1.2.1)                                                   | 36    | € 2 592  |
| Collect feedbacks from beta user / bug fix and UI                                      | 10    | € 720    |
| Launch support (community support / comm / bug fix)                                    | 20    | € 1 440  |
| Video Tutorial + Documentations (Docstring + Dashboard request)                        | 20    | € 1 440  |
| First year support (up to 36 hours)                                                    | 36    | € 2 592  |
| **Total Budget Requested**                                                             |       | **€ 14 256** |
|                                                                                        |       |          |
| Option : Additionnal support per major update (start after included support consummed) | 10    | € 720    |

No VAT charged 

## Maintenance and Upgrade Plans

Tools will be updated according to lotus release. Will be glad to work closer with PL team to specify API needs. 

# Team

## Team Members

Julien NOEL - online@noelnoel.org

## Team Website

`https://github.com/s0nik42/lotus-farcaster`

## Relevant Experience

Julien is a filecoin miner, actively helping the filecoin community on slack. 
IPFS and Web3 enthousiast, starting being active around filecoin right before Space Race, 
Julien is a computer science engineer, spending 15 years working for Top100 companies providing strategic advice to C-level around new technologies.
