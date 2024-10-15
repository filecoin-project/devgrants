# RFP Proposal: Filecoin-snowball FLOPy AWS Snowball-like hard drive service

**Name of Project:** `FilecoinSnowball`

**Link to RFP:** [Filecoin-snowball FLOPy AWS Snowball-like hard drive service](https://github.com/storswiftlabs/devgrants/blob/master/rfps/new-wave-3-rfps.md#flopy-aws-snowball-like-hard-drive-service).

**RFP Category:** `technical-design`

**Proposer:** `coder-lb`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Please respond with either "Yes" or "No"

# Project Description

In scientific and archival data communities, it is often more efficient to physically ship datasets via hard drives than send it over the Internet. [AWS Snowball](https://aws.amazon.com/snowball/) is an example service. In Filecoin offline deals are possible, where drives are shipped to miners via prior arrangement in an appropriate format and imported upon physical receipt as a new storage deal.

Then We design a solution to synchronize large data sets to Filecoin easily. It includes two important parts:  
1. A simple online trading system. Data providers and miners can agree on the large-scale data migration business on this system and confirm orders.
2. A storage system just like AWS snowball which can migrate data easily. Usually people store large data sets with commercial NAS or SAN, just like the storage system of Dell EMC or Huawei. And they may also store data based on an open source distributed storage system such as Lustre, Ceph or GlusterFS. It's not feasible for them to pull out the hard drives and ship them to the miner. It is also inconvenient for them to find some hard drives to copy out some of the data that needs to be backed up separately. So a very simple solution to backup data is necessary.


## Deliverables

1. The architecture and design of large-scale offline data order transaction matching platform. We will also implement a simple version of this system to show the proof of concept.  
2. The architecture and design of snowball-like NAS device. It is easy to setup with web-based GUI, and can provide NFS interface (for Linux/UNIX) and SMB interface (for Windows) to backup data. It also integrates Filecoin client module in order to submit orders to storage miners easily. We will give the reference hardware & software configuration, NAS UI design and the reference implementation of some software modules.

## Development Roadmap

### Milestone 1

- Propose the architecture and design specification of large-scale offline data order transaction matching platform.
- Porpose the hardware and software specification of snowball-like NAS device.
- Find a specific data provider who will cooperate us in the test.

Resource requirements:  
- 1 architect, 1 designer
- 2 weeks

### Milestone 2

- Implement a simple version of offline data order transaction matching platform. It can show the proof of concept.
- Develop the corresponding software modules (NAS services, Filecoin clients, and Web UI) of snowball-like NAS device.  

Resource requirements:  
- 1 architect, 2 developers
- 3 weeks

### Milestone 3

- Test the data migration process with a data provider.

Resource requirements:  
- 2 developers, 2 test engineers
- 1 week


## Total Budget Requested

Total Budget: $12,000.00

| Milestone | Budget |
|------|--------|
| 1 | $4000 |
| 2 | $5000 |
| 3 | $3000 |

## Maintenance and Upgrade Plans

Improve the design and implementation after Filecoin spec is updated. Further improve this service based on the feedback of data providers and miners.

# Team

StorSwift team focuses on scale-out enterprise storage system development, deployment and maintenance.

## Contact Info

Please email lengbo@storswift.com.

## Team Members

- Architect: Leng Bo
- Developers: Wan Lei, Macro

## Team Member LinkedIn Profiles

- Leng Bo: [https://www.linkedin.com/in/%E6%B3%A2-%E5%86%B7-b302a5b1/](https://www.linkedin.com/in/%E6%B3%A2-%E5%86%B7-b302a5b1/)
- Wan Lei: [https://www.linkedin.com/in/%E7%A3%8A-%E4%B8%87-a46b451a6/](https://www.linkedin.com/in/%E7%A3%8A-%E4%B8%87-a46b451a6/
)

## Team Website


- [https://storswift.com](https://storswift.com) 

## Relevant Experience

We develop distributed enterprise storage systems, and build large data solutions for enterprises. Especially for video surveillance, broadcasting, education, HPC and AI industries, we have our completed large capacity storage solutions. For example, Mellanox and StorSwift build HPC storage solution together based on our distributed storage system and Mellanox high performance network devices:
https://www.mellanox.com/related-docs/solutions/SB_Mellanox_Storswift_HPC_Storage.pdf  

We have also participated in some large projects and provided our storage solutions. For instance, we provided storage software to set up a 30PB storage cluster for Yinchuan smart city (project in Ningxia, China). Recently, we provide RDMA-based storage servers to accelerate AI computing for several Chinese universities. We are also actively building large-scale archive data storage solutions for marine farms.

Core members of StorSwift come from Rasilient Systems, a U.S. company which develops large scale storage system especially for the video surveillance industry.

## Team code repositories

- [Hive interface based on ipfs-cluster](https://github.com/elastos/Elastos.NET.Hive.Cluster)
- [https://github.com/storswift](https://github.com/storswift)   
- [https://github.com/storswiftlabs](https://github.com/storswiftlabs)  
- https://github.com/coder-lb

# Additional Information

We are very interested in all aspects of creating Filecoin storage for large-scale data, and we will do our best in this ecosystem.
