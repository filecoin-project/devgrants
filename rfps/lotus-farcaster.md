
# Open Grant Proposal: `Monitoring Tool for Miners`

**Name of Project:** `Lotus-farcaster`

**Proposer:** `s0nik42`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

lotus-farcaster is a Visualization and Analytics tool for Lotus Filecoin node It leverages Prometheus, Grafana and Python.
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
|Sectors      | OK          |                   |
|Mpool        | OK          |                   |
|Storage Info | OK          |                   |
|Workers Info | OK          |                   |
|Sealing      | OK          |Job + Scheduler    |
|Power        | OK          |                   |
|Wallets      | OK          |                   |
|Chain        | OK          |Head + Sync Status |
|Deals        | V2          |                   |
|Deadlines    | V2          |                   |
|Gas Price    | V2          |                   |
|Won Blocks   | Roadmap     |                   |

## Roadmap

01 oct 2020 : Project initiated
15 oct 2020 : Design / Specifications / Mockup
20 oct 2020 : Presentation during [Filecoin Liftoff Week](https://www.youtube.com/watch?v=cyer6_gSv78&ab_channel=Filecoin) 
26 oct 2020 : First release open to beta tester
27 oct 2020 : Private GitHub repo, open to beta tester from PL and the community : @benjaminh83, @flyworker, @hsanjuan, @jennijuju, @ribasushi, @RobQuistNL, @std, @stuberman, @whyrusleeping

30 nov 2020 : first public release

Milestone                                           |Hours| Cost
--------------------------------------------------- | --- | ---
Collect needs from the community, design, planning  | 16  | €1,180.00
Upskill on the different systems                    | 16  | € offered
Studing Lotus API and reverse iengineering          | 4   | €  295.00
Exporter development V1.0                           | 16  | €1,180.00		
Dashboard development V1.0                          | 16  | €1,180.00
Collect feedbacks from beta user  / bug fix and UI  | 5   | €  378.75
V2.0 (Exporter + Dashboard)                         | 10  | €  737.50
Launch support (community support / comm / bug fix  | 10  | €  735.50
First year support + new features                   | 20  | € offered
**Total Budget Requested**                          |     | **€ 5678.00**

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
