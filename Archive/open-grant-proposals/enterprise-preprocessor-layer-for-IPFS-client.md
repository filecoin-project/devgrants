# Open Grant Proposal:  Enterprise preprocessor layer for IPFS client (encryption, compression and other enterprise use cases)

**Name of Project:**  Enterprise preprocessor layer for IPFS client (encryption, compression and other enterprise use cases)

**Proposal Category:** app-dev

**Proposer:** Andy ZHOU

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes



# Project Description

We plan to make a preprocessor gateway for IPFS client with the aim to fulfil common needs and concerns of enterprise users. So as to attract more enterprise users to embrace IPFS in their infrastructure. 

This preprocessor gateway is going to provide ReSTful interfaces over HTTP protocol that is easily accessible by mainstream enterprise applications. Our target audiences will integrate it with the technologies they familiar with.

We plan to carry out our work based on [Go-IPFS project](https://github.com/ipfs/go-ipfs), where we add a standalone preprocessing layer before it. 

This project will start from the very basic features and extend it in the future projects. The initial features include:

1. Encryption and decryption of files
2. Common open-source encryption algorithms will be supported, also leaving the possibility for future extension
3. Compression and decompression of files
4. Common open-source compression algorithms will be supported, also leaving the possibility for future extension
5. Support of AWS KMS and Aliyun KMS, also leaving possibility to plug in services from the other cloud providers
6. Support local key management
7. Develop a file formant that adds metadata over encrypted/compressed file to facilitate indexing and searching
8. Metadata may include filename, mime type, extension, creation time, key words, description, etc
9. Adopter may choose to fill the metadata or leave it out for anonymity reason



## Value

Currently, the cost for a non-blockchain enterprise to adopt Filecoin/IPFS is fairly high, especially the need to understand blockchain architecture, set up FIL wallet, purchase for FIL, set up Filecoin/IPFS node, manage cryptography keys, carry out development projects to fulfil regulation requirements, and etc. All these keep quite a number of potential enterprise users away.

Nevertheless, we foresee that enterprise users will stand a very important role in Filecoin ecology in the future. So we decided to propose this project, with the mission to fulfil the common needs and concerns of enterprise users (encryption, compression, meta data, etc.), letting the enterprise users to embrace IPFS at a marginal cost. 

By lowering the "entrance fee" for enterprise users, there will be more and more of them joining IPFS, in the long run, it is for sure some of them will eventually migrate to Filecoin to pursue for higher quality of service. With the strong payment ability the enterprise users have, we believe they will bring great benefits to Filcoin's incentive economy.



## Deliverables

1.  An IPFS preprocessor gateway exposing ReSTful interfaces over HTTP protocol, that allows enterprise applications to interact with.
2. Documentation



## Development Roadmap

| #    | Milestone                                             | Fund      | Est. time |
| ---- | ----------------------------------------------------- | --------- | --------- |
| 1    | Technical design in detail and prototyping            | US$ 2,000 | 2 weeks   |
| 2    | Code: Encryption, decryption and local key management | US$ 6,000 | 3 weeks   |
| 3    | Code: KMS integration                                 | US$ 4,000 | 2 weeks   |
| 4    | Code: Compression                                     | US$ 2,000 | 1 week    |
| 5    | Code: Metadata and file format                        | US$ 4,000 | 2 weeks   |
| 6    | Integration, clean up                                 | US$ 2,000 | 1 week    |
| 7    | testing, documentation & publish on Github            | US$ 4,000 | 2 weeks   |
| 8    | Maintenance for one year                              | US$ 6,000 | 1 year    |

There will be 2 main developers working on all the tasks throughout the project, and we may put in more resources depending on the situation. There will be 1 developer responsible for maintenance.

p/s: The estimated time could look a bit long, because we mainly contribute to this project off work.



## Total Budget Requested

US$ 30,000



## Maintenance and Upgrade Plans

We will collect feedback and suggestions to keep improving this project.

In case there are resource intensive work, we will consolidate them into a project and apply for a new grant.

In the future, we probably will extend the scope of this project to Filecoin when the time has come.



# Team

## Team Members

- [Andy ZHOU]( https://github.com/ablozhou) - Lead developer
- Cody HUANG - Developer & project manager
- (May assign more developer from our company depending on the situation)



## Team Website

https://www.eidledger.com/



## Relevant Experience

Our company, Beijing Gong Yi Lian technologies limited inc. (北京公易联科技有限公司), is a company providing citizen digital identity authentication services that is anonymous and trustable at the same time. Part of our business focuses on enterprise customers (toB), which gain gain us a lot of experiences on integration with enterprise applications and also we know the concerns of our enterprise customers. 



## Team code repositories

[ChatIt](https://github.com/ablozhou/chatit.git) - A chat room application that supports 100K simultaneous users on a single server

[QuartzCluster](https://github.com/ablozhou/quartzcluster) - Spring boot Quartz cluster




# Additional information

We have integrated IPFS into our infrastructure, nevertheless our work is not open-source-able due to information security policies. Since we find IPFS useful, we decided to give back by starting this project, with the hope that more enterprise users could benefit from IPFS.

Our company is currently leading a project in IEEE standard association, that is [P3210 Standard for Blockchain-based Digital Identity System Framework](https://sagroups.ieee.org/3210/). We see the trend of more and more artists store their NFT masterpieces on Filecoin/IPFS, where they need a way to declare their copyright. With the standard we are working on, the artists will be able to protect their copyright under the identity issued by any regime, thus easily recognized by the law systems. So, we are exploring the possibility to implement such identity standard on Filecoin/IPFS in the future.
