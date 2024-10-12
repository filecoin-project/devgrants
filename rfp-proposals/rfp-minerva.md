# RFP Proposal: `Minerva`

**Name of Project:** Minerva: 

**Link to RFP:** [new-wave-3-rfps.md](new-wave-3-rfps.md#expert-use-of-large-data-archives)

**RFP Category:** `app-dev`

**Proposer:** `@dbw9580`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

IPFS together with Filecoin provides infrastructure for a data storage market where owners of data pay storage providers to safely store the data for future retrieval. Despite the splendid promise of IPFS, the ecosystem lacks sufficient applications beyond storage and simple sharing.

Minerva is a storage module of [Apache Drill](https://drill.apache.org/) that connects IPFS's decentralized storage and Drill's flexible query engine. Any data file stored on IPFS can be easily accessed from Drill's query interface, just like a file stored on a local disk. Moreover, with Drill's capability of distributed execution, other instances who are also running Minerva can help accelerate the execution: the data stays where it is, and the queries go to the most suitable nodes which store the data locally and from there the operations can be performed most efficiently.

## Value to the Filecoin ecosystem

First, with the help of Filecoin, we see the potential of an open data market that is not only about storing and retrieving data, but also actively provides computational services such as data analysis, data mining and many more.

Second, we have collected about 1TB public datasets from different fields of research and industrial applications, including human genome and blockchain systems, and provide search service based on IPFS. These could be transfered to the Filecoin network.

Third, this proposal also provides a potential decentralized solution for retrieval market of Filecoin. The indice of content stored on Filecoin network can be stored in a database, which itself is stored distributedly on IPFS, and can be easily queried by end users as well as applications incorporating Minerva.


## Technical architecture

> A more detailed explanation of Minerva's architecture can be found in these [slides](https://www.slideshare.net/BowenDing4/minerva-ipfs-storage-plugin-for-ipfs) and this [paper](https://conferences.sigcomm.org/events/apnet2019/posters/7.pdf).

Minerva is a data query engine built upon a combination of three co-operating components: Qri - the data management tool, Drill - the distributedquery engine, and IPFS - the storage backend. Minerva takes advantages of the flexibility of Drill’s query engine and the scalability of IPFS’s decentralized filesystem. Each user of Minerva runs a local node, and the Minerva nodes form a peer-to-peer network. A user who has a particular dataset in her local store is a provider for that dataset, and can accept queries about it from other users in the network.

A dataset is first sliced into a number of chunks and each chunk becomes an object on IPFS. These pieces of data construct a hierarchical tree structure, where all leaf nodes contain the data, and the others record hashes of lower-level nodes, like directories. Each of the intermediate nodes and the root node have its own content identifier (CID), i.e. the hash of the content, and the CIDs serve as the paths to a certain part of or the whole dataset on IPFS, respectively. Users can input standard SQL statements into Drill, specifying as the table name the IPFS path of the part of data they want to query. The query string will look like the following:

```
SELECT ˋidˋ, ˋnameˋFROM ipfs.ˋ/ipfs/QmRhDW...3SVi/employees.jsonˋLIMIT 100
```

After parsing the SQL, Drill builds a distributed execution plan that will be sent to and executed on other nodes of Minerva who are serving the same dataset in the network, according to the DHT of IPFS. 

Drill is aware of data locality and tries to minimize the network cost by delegating computing jobs to the nodes that store particular pieces of data locally. Both decentralized read and write operations are enabled. Furthermore, Drill supports custom SQL functions, which are loaded from .jar files at runtime. Users can implement their conversion rules and analysis algorithms in the form of custom functions for a dataset, and distribute them with the dataset. Future users can benefit instantly by loading the custom functions from IPFS, in the same way as they specify a dataset stored on IPFS.

## Deliverables

* The Minerva IPFS storage module for Apache Drill
* Codebase in Java
* Detailed documentation
* Tutorials on how to set up a Minerva node on IPFS and Filecoin, and how to run a query on a decentralized dataset
* A website demostrating the functionalities of Minerva on Filecoin

## Development Roadmap

Milestone 1:
* Completion and improvement of the Minerva module: enable distributed writes and faster queries
* Deom website: upload public datasets to Filecoin, which is approximately 1TB.
* 4 weeks
* 2 devs
* $500

Before this RFP is made, we currently have implemented the basic functionalities of Minerva as a storage module, including support for IPFS/IPNS scheme name, json and csv formats, distributed execution of read quries, and a preliminary support for write queries. We intend to further polish the code to fully enable write queries, as well as implement several optimizations on query planning to improve performance.

We have also collected about 1TB public datasets from different sources of industrial and acemedic areas, which is currently hosted on a private IPFS cluster. We will transfer the datasets to Filecoin-enabled storage network and deploy a publicly available website that provides access to the datasets through Minerva.

Milestone 2:
* Make it Filecoin ready
* 4 weeks
* 2 devs
* $500

Milestone 3:
* Preliminary public dataset sharing testbed: enable public dataset sharing and trading on top of IPFS and Filecoin
* 4 weeks
* 2 devs
* $500


## Total Budget Requested

A total of US$1500, plus the filecoins for storing 1TB of public data for 1 year.

## Maintenance and Upgrade Plans

We intend to actively maintain Minerva for at least 1 year.

# Team

## Team Members

- Bowen Ding (dbw9580@live.com)
- Liang Wang (wangliang.f@gmail.com)
- Yuedong Xu (ydxu@fudan.edu.cn)

## Relevant Experience

We have been developing Minerva since 2018 primarily as a research project. We published the progress at [APNet 2019](https://conferences.sigcomm.org/events/apnet2019/posters/7.pdf). We are currently working on [merging Minerva into Apache Drill](https://github.com/bdchain/Minerva/issues/2).

## Team code repositories

https://github.com/bdchain/Minerva/


