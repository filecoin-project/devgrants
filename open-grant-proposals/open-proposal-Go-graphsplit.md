# Open Grant Proposal: `Go-graphsplit`

**Name of Project:** Go-graphsplit

**Proposal Category:** devtools-libraries

**Proposer:** `laurarenpanda`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

[Go-graphsplit](https://github.com/filedrive-team/go-graphsplit) is a tool for splitting large dataset into graph slices fit for making deal in the Filecoin Network, developed by FileDrive Team.

When storing a large dataset in the Filecoin Network, we have to split it into smaller pieces to fit for the size of sector, which could be 32GiB or 64GiB.

At first, we made the dataset into a large tar ball, did chunking this tar ball into pieces, and then used each piece to make deal with storage miners. We did this way for a while until we realized it brought difficulties to retrieval. Even if we only needed to retrieve a small file in the dataset, we had to retrieve all the pieces of the tar ball at first. 

Graphsplit has solved the problem we faced above. It takes advantage of IPLD concepts, following the [unixfs](https://github.com/ipfs/go-unixfs) format datastructures. It regards the dataset or it's sub-directory as a big graph and then cut the big graph into small graphs. The small graphs will keep its file system structure as possible as its in big graph. After that, we only need to organize small graph into a car file according to [unixfs](https://github.com/ipfs/go-unixfs).


## Value

With this tool:
- large data can be split into data pieces fit for the size of sector in the Filecoin Network.
- data piece can keep its file system structure.
- data retrieval can be more efficient.

## Deliverables

The development of this tool has been preliminarily completed, and we will continue to maintain and evolve it.

## Development Roadmap

### Milestone:

* IPLD protocol analysis 
* Architecture design
* Design Doc
* Implementation of Go-graphsplit

__Resources__ :

Developer - 80 hours

## Total Budget Requested

Tool dev:

 | Role | Rate/Hr | HC | Man-Hour | Man-Week | Price |
 |-----|---------|----|-----------|-------------|------|
 | Developers| $50 | 2 | 160 | 2 | $8,000.00 |

Maintenance: $2,000.00 (2 developers)  

Total Budget: $10,000.00 


## Maintenance and Upgrade Plans

Maintenance provided by FileDrive team will include:
- bug fixing;
- upgrades during changes of the Filecoin Network Protocol;
- Documentation updates as tool evolves.

# Team

## Team Members

- Developer: Filex Li, Huanhuan Qian

## Team Member LinkedIn Profiles

- Filex Li: https://www.linkedin.com/in/felixlee20190908/?locale=zh_CN
- Huanhuan Qian: https://www.linkedin.com/in/%E6%AC%A2%E6%AC%A2-%E9%92%B1-455141129/

## Team Website

[FileDrive](https://filedrive.io/)
[Twitter](https://twitter.com/FileDrive1)
[FileDrive Offical WeChat Account](https://mp.weixin.qq.com/mp/profile_ext?action=home&__biz=MzkzMDE4ODg0MQ==&scene=124#wechat_redirect)

## Relevant Experience

FileDrive team is focusing on building storage application based on IPFS/Filecoin. We participated in Slingshot competition from phase 1 to phase 2.3, and stored almost 1 PiB useful data in the Filecoin Network. As a client, we have rich experience in data processing and storage deal transactions.

IPFS relevant resource:
- IPFS: https://ipfs.io/   
- IPLD: https://ipld.io/   
- go-unixfs: https://github.com/ipfs/go-unixfs


## Team code repositories

Project repo: https://github.com/filedrive-team/go-graphsplit
