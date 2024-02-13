To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Lotus Farcaster`

**Name of Project:**  `lotus farcaster V3`

**Proposal Category:** Choose one of `app-dev`

**Proposer:** `s0nik42 - Twin Quasar`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

lotus-farcaster V3 brings additionnal functionnalities to lotus farcaster (see tables below).

**Lotus farcaster is used by 400+ miners, was downloaded more than 200 times and get 30+ new users during the last 2 weeks. We want to keep farcaster has one of the main analytics companion of miners by continuously adding features supporting their new challenges. This new release follow Filecoin roadmap and bring storage markets features, bring support to the new lotus split mode architecture and made it reusable for other project by providing all the functions are a python module. This tool is build for the community and we really want to keep it opensource**

Lotus farcaster is a Visualization and Analytics tool for Lotus Filecoin node It leverages Prometheus, Grafana and Python.

We want it to be accessible and designed for any types of miners.
It's designed to manage all type of architecture :
* single miner, 
* single miner with workers
* monolitic and split store architecture (markets node)
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
| Lotus Miner              |          |            |          | Grafana             |          | Web Client |   
| lotus-exporter-farcaster | <------- | Prometheus | <------- | farcaster-dashboard | <------- |            |
 --------------------------            ------------            ---------------------            ------------  
   |        
   |    -------------------------   
   |-> | Lotus Daemon            | 
   |     -------------------------  
   | 
   |    -------------------------  
   |-> | Lotus Markets           | 
        -------------------------  
 
```

### lotus farcaster comes with 2 Components :
* A Grafana dashboard
* lotus-exporter-farcaster a standalone python script executed every minute by the crontab.
It generates metrics that are exposed by node-exporter to prometheus.

### Security
The design and choice of these components, was made to keep a high level of security :
- metrics are pulled from the miner to avoid compromising network or management servers
- lotus-exporter-farcaster doesn't bind any ports to avoid exposing the miner to external threat
- lotus-exporter-farcaster run under unprivileged user (ideally lotus user) to avoid system being compromised
- The global solution doesn't rely on any cloud or remote component. To avoid data leak.

lotus-exporter-farcaster is running locally on the miner without any specific privilege nor access to other servers. 

### It will follow [prometheus guidelines](https://prometheus.io/docs/instrumenting/writing_exporters/) :
* ressources inexpensive
* standard prometheus metrics naming
* compatible with 3rd parties dashboards and exporters

## Benefits
* Support any type of lotus architecture
* Easy to deploy
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
|Deals        | V2          | View of current sealing deals (State/Price/Size/collaterals/From/Is Verified/etc... |
|Gas Fee      | V2          | Realtime gasfee and History (requested by Community) |
|Sectors State| V2          | Identify faulty sectors in deadlines (requested by Community). Helping miners to quickly indentify which sectors to restore |
|Fil+ Datacap | V2          | Fil+ Realtime and Historical view of Datacap allocated to the miner addresses |
|Max Quality Adjusted Power| V2 | A new indicator, showing the maximum power that can be expected from a miner (it's a forecast of the power after the next deadline if the full capacity is proved) |
|Sectors w/ Deals| V2       | Breakdown of sectors in 3 categories : CC / inc. deals / inc. Verified. Current and historical view, helping the miner to understand how he gets is power over time|
|Address lookup | V2        | Allow miners to provide a custom lookup file (Adress=Name/Label) to improve dashboard readability.. The lookup apply to any panels containing adresses (Wallet / Deals / Fil+ / etc...).|
|Farcaster Status | V2      | Farcaster reports any problems when scraping data. Ensuring dashboard is accurate.|
|Deployment toolset | V3    | Provide a deployement script supporting and autodetecting any type of lotus architecture + Docker|
|Full Python Library | V3 | Provides all functionnalities as a Python library.|
|Storage market Proposal | V3 | Provides on-going downloads, pending publishing deals, etc...|
|Sectors lifecycle | V3 | Dashboards helping miners to identify expired sectors correlated with errors to help fast troubleshooting.|


## Roadmap

The planning could be shorted if Protocol Labs for any reasons decide to force miners to switch to splitstore.   

01 sep 2021 : V3 scoping
07 sep 2021 : V3 Development of Design / Specifications / Mockup
30 sep 2021 : First release open to beta tester
15 oct 2021 : Public release of the new farcaster (without the python lib)
15 nov 2021 : Public release of the python lib

| Milestone                                                                              | Hours | Cost     |
| -------------------------------------------------------------------------------------- | ----- | -------- |
| Collect needs from the community, design, planning                                     | 8     | €   576  |
| Studing the new Lotus API and reverse iengineering                                     | 8     | €   576  |
| Exporter development (lotus V3.0)                                                      | 40    | € 2 880  |
| Dashboard development (lotus V3.0)                                                     | 40    | € 2 880  |
| Collect feedbacks from beta user / bug fix and UI                                      | 10    | €   720  |
| Automatic Deployment process + Docker                                                  | 20    | € 1 440  |
| Python library                                                                         | 50    | € 3 600  |
| Launch support (community support / comm / bug fix)                                    | 20    | € 1 440  |
| New Video Tutorial + Documentations (Docstring + Dashboard request)                    | 20    | € 1 440  |
| First year support (up to 8 hours)                                                     | 8     | €   576  |
| **Total Budget Requested**                                                             |       | **€ 16 128** |
|                                                                                        |       |          |
| Option : Additionnal support per major update (start after included support consummed) | 10    | € 720    |

No VAT charged 

## Maintenance and Upgrade Plans

Tools will be updated according to lotus release. Will be glad to work closer with PL team to specify API needs. 

# Team

## Team Members

Julien NOEL - julien.noel@twinquasar.io

## Team Website

`https://twinquasar.io`

## Relevant Experience

Julien is a :
- Filecoin miner, actively helping the filecoin community on slack. 
- Filecoin Notary
- Part of MinerX program
IPFS and Web3 enthousiast, starting being active around filecoin right before Space Race, 
Julien is a computer science engineer, spending 15 years working for Top100 companies providing strategic advice to C-level around new technologies.
