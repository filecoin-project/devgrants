To submit a proposal, please create a PR against this template in this repo. Please title your file `rfp-proposal-title.md`, replacing `title` with the name of your project.

# RFP Proposal: `Telegraf plugin for Lotus & TICK stack setup`

**Name of Project:**

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/new-mining-tools-rfps.md#monitoring-tool-for-miners

**RFP Category:** `mining-tools`

**Proposers:** `vvkio`, `svilenkov` 

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

The objective of this project is to give miners an easy way to set up monitoring and alerting for their clusters. With monitoring in place miners will be able to better understand their resource utilization which could potentially lead to better hardware utilization, also increasing the overall reliability of the setup. 

Some of the metrics we wish to expose:

- Sealing metrics
    - Total sectors in phase (PC1, PC2, etc)
- Storage
    - Storage utilization
    - NVMe cache utilization
    - Chain size, disk space left
    - VRAM
- CPU
    - Core utilization
    - Temperature
- Memory
    - Utilization
    - Swap
    - Pressure
- GPU metrics
- Network
    - Utilization
    - Total daily bandwidth (avoid ISP caps)
- Sync with the network
    - Diff
Alerts:
  - Out of sync
  - Low storage
    - Low space on chain diks
    - Low Storage
    
Also open to suggestions on what else could be useful. 

## Value

By increasing the uptime of the individual miners the network reliability will increase and with that the overall quality of service.

## Development Roadmap

10 Oct 2020: Proposed start date

20 Nov 2020: Proposed finish date

Milestone | Hours | Cost
--- | --- | ---
Setup & planning | 8 | €560
Lotus Telegraf Plugin development | 50 | €3,500.00		
Telegraf host metrics configuration | 50 | €3,500.00
TICK Stack setup and scripts | 20 | €1,400.00
Dashboards configurations | 20 | €1,400.00
Alerts configurations | 20 | €1,400.00
[Optional] Terraform configuration for DigitalOcean deploymennt | 20 | €1,400.00
Documentation and video on how to setup | 6 | €420.00
Blog post on how to setup monitoring | 4 | €280.00

**Total** |  | 	**€13,860.00**


## Maintenance and Upgrade Plans

We are working on a hosted mining managment platform which will leverage some of the work proposed in this project, we plan to keep mantaining this project.

# Team

## Contact Info

vuk@filmine.io

## Team Members 

- [Vukašin Vukoje](http://linkedin.com/in/vvkio/)
- [Igor Svilenkov Božić](https://ipfs.io/ipfs/QmYmxjToxg4fKeTqsXAfWigRTXBJK2YDxxFncVFJLpnxB8)

## Team Website

https://filmine.io/

## Relevant Experience

Former founder and CEO of (Tenderly)[https://tenderly.dev/] a smart contracts development platform where I spent two years developing Ethereum infrastructure that is today helping thousands of Solidity development build smart contracts more effectively with features like monitoring, alerting, gas profiling, contract analytics and debugging. I also competed and won several Ethereum Hackathons like (ETHBerlin 2018)[https://devpost.com/software/smart-alert-s5p1zw] and (ETHParis)[https://devpost.com/software/zippo].
