# RFP Proposal: `Filecoin Client Api Helper Libraries`

**Name of Project:** java-filecoin-api-client

**Link to RFP:** [rfp-storage-helper-libraries](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-storage-helper-libraries.md)

**RFP Category:** `devtools-libraries`

**Proposer:** [xjxh](https://github.com/xjxh)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

Filecoin aims to create a global, distributed file storage network that provides decentralized storage services for applications.
The `java-filecoin-api-client` is a very useful tool for the developers who wants to develop applications on the Filecoin storage network.
However, currently there is very few well-wrappered Filecoin client http api libraries developed with Java.
Java has a large number of developers. 
This tool will bring great convenience for Java developers to develop to develop DApps based on Filecoin.

## Deliverables
1. Complete wrapper all the apis of  [api_full.go](https://github.com/filecoin-project/lotus/blob/master/api/api_full.go).
2. Unit test codes of full API function
3. The codebase is open-sourced and dual-licensed under MIT and APACHE2 licenses.
4. Well-documented, human-readable API Instruction and User-Guid

## Development Roadmap

### Milestone 1
1. Project Design: Project architecture, technology selection.
2. Complete wrapping apis for `chain` and `syncer` module.
3. Development: 
 * 1 Arch, 1 Dev
 * 48hrs


### milestones 2
1. Complete wrapping apis for `messages`, `wallet` and `client` module.
2. Development: 
 * 1 Dev
 * 40hrs

### milestones 3
1. Complete wrapping apis for `state` and `payment` module.
2. Development: 
 * 1 Dev
 * 40 hrs

## Total Budget Requested

Total Budget: $6,640.00

 | Role            | Rate/Hr | HC  | Man-Hour | Man-Week | Price     |
 | --------------- | ------- | --- | -------- | -------- | --------- |
 | Arch            | $80     | 1   | 8        | 1        | $640.00   |
 | senior engineer | $50     | 1   | 120      | 3        | $4,800.00 |

## Maintenance and Upgrade Plans

1. If the `Filecoin` API is updated, we will upgrade in time.
2. Bug Fixing on demand.

# Team



## Team Members

- Architect: Lion
- Full-Stack Dev: Rock

## Team Member LinkedIn Profiles
- Lion: [https://www.linkedin.com/in/chan-lion-327b28101/](https://www.linkedin.com/in/chan-lion-327b28101/)
- Rock: [https://www.linkedin.com/in/rockyang/](https://www.linkedin.com/in/rockyang/)

## Team Website

[http://www.xjxh.pro/](http://www.xjxh.pro/)

## Relevant Experience

XJXH is a Cloud Storage Technology Service company based in SHENZHEN China. 
we have focused on Cloud Storage technology for over three years including the standard s3 storage, 
Network shared storage and the decentralized storage. We have a professional
technical R & D and O & M team based in SHENZHEN China, We also have a professional
IDC based in Shandong Province of China. We are committed to providing enterprise-level
decentralized storage services in the future and have always been working hard for this. 


## Team code repositories

* Lion: https://github.com/lionsoul2014
* Rock: https://github.com/yangjian102621
* DongYa: https://github.com/dongyado

# Additional Information

The project `java-filecoin-api-client` is open source in [Filecoin Shipyard](https://github.com/filecoin-shipyard/java-filecoin-api-client).
We had already develop an web wallet with this lib and also open source it.[filecoin-wallet](https://github.com/filecoin-shipyard/filecoin-wallet)   





