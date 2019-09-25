# RFP Proposal: `ars-go-filecoin-storage-helper`

**Name of Project:** go-filecoin-storage-helper

**Link to RFP:** [rfp-storage-helper-libraries](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-storage-helper-libraries.md)

**RFP Category:** `devtools-libraries`

**Proposer:** [@waynewyang](https://github.com/waynewyang)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:**  "Yes"

# Project Description

The project is based on [rfp-storage-helper-libraries](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-storage-helper-libraries.md), We think we're  very clear about the project want to do, our implementation will meet the need of [RFP](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-storage-helper-libraries.md),

We think the keypoint is that client must pay for the metadata, the metadata is used for data retrieval,so the design of the metadata is very important,now we already have the idea.

Besides,we have another idea we'll provide the function in storage helper that metadata encryption.

## Deliverables

- Meet the need of the original RFP,
  - An open-sourced, dual-licensed (under MIT and APACHE2) library that performs a useful workflow and can be used modularly by other software applications in the Filecoin ecosystem
  - Can be in any language, but we have a preference for Go
  - Documentation of how to use and install this library
  - Sample application (can be extremely simple) that uses both this helper library and go-filecoin to perform the intended workflow
  - Well-documented, human-readable codebase.
- Besides, we want to point out as belows
  - Our implementation  will meet any size directory and file upload through the storage helper
  - A large file or directory needs to be split into multiple deals, we'll implement these functions as belows,
    - Deals monitors
    - Callback of deals status and reminder that deadline of the deals
    - Automatically maintain orders after the deadline of the deals reached
  - Metadata encryption

## Development Roadmap


| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Storage helper library | $3500 | 2 weeks |
| 2 | All deliverables (codebase, sample application, documentation, testing) | $1500 | 1 week |


## Total Budget Requested

**Total Funding Amount:** $5000


## Maintenance and Upgrade Plans

- Version maintenance: every time when release a new version of filecoin, we check to see if any new features have been released or changed. And according to the changes of the new version to release our version, to ensure that the functions of our library  perfect available.

- Bug resolution: we will assign a person to focus on the issue of the project on a daily basis, record all issues, and arrange the time according to the severity to solve and submit in the fastest time.

- Communication: developers using this open source project are welcome, and we will be in constant contact with them to hear Suggestions to improve our project

# Team
## Team Members
- [@waynewyang](https://github.com/waynewyang) : arch
- [@johnli-helloworld](https://github.com/johnli-helloworld): developer
- [@magnshen](https://github.com/magnshen): developer

## Team Member LinkedIn Profiles
- [waynewyang](https://www.linkedin.com/in/waynewyang/?locale=en_US)
- [@johnli-helloworld](https://github.com/johnli-helloworld)
- [@magnshen](https://github.com/magnshen)

## Team Website

- https://www.arsyun.com   
- https://github.com/arsyun

## Relevant Experience
- ARS team has rich experience in distributed cloud storage and has deployed practical products. And provides cloud service base on IPFS and filecoin.
  - [Essential-Thinking-of-Blockchain](https://github.com/arsyun/Essential-Thinking-of-Blockchain)
  - [Product:pServer](https://www.arsyun.com/web/index.html)
- [@waynewyang](https://github.com/waynewyang)  is the [Contributor](https://github.com/filecoin-project/go-filecoin/graphs/contributors) of go-filecoin, we can deeply understand the work flow about file coin.
- ARS Team has been attended IPFS camp in berlin and Barcelona, We're very interesting in IPFS and filecoin, and plan to do some application based on IPFS & filecoin.

## Team code repositories

- https://github.com/arsyun.
- https://github.com/arsyun/go-filecoin-api-client
- https://github.com/arsyun/go-filecoin-storage-helper

# Additional Information

- We want to point out the idea about metadata  as below,
  - We'll store the metadata by leveldb
  - Each upload action will use a separate db
  - The key/value of the leveldb as below,
    - 1 ChunkSize : size
    - 2 Type : metadata or db
    - 3 /path/"/a/b/c/foo.txt": size 
    - 4 /chunk/"the path that belongs to"/seq/cid:status

You can refer to the detail [here](https://github.com/arsyun/go-filecoin-storage-helper)