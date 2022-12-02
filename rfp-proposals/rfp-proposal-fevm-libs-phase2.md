# RFP Proposal: `Solidity libraries for FEVM Phase 2`

**Name of Project:** Solidity libraries for FEVM Smart Contracts

**Link to RFP:**  

**RFP Category:** `devtools-libraries`

**Proposer:** `ainhoa-a`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes 

# Project Description

In the context of the FEVM Early Builder program we propose to build a set of tools and libraries to enable Ethereum developers to re-use their existing know-how to develop Filecoin-specific use cases. 

After validating the research and benchmarking phase, it has been proposed to start the implementation of the actual libraries. This Solidity library is required in order to allow Solidity smart contracts to seamlessly call methods on Filecoin built-in actors, as well as to access Filecoin specific syscalls idiomatically.

## Development Roadmap and Deliverables

## Phase 1  - Research and Benchmarking  (Completed)

Milestone 1 - Research and feasibility analysis of CBOR in Solidity in terms of FVM gas usage 
Milestone 2 - Research and PoC of Pre-compiles for specific built-in actors

*These Milestones have been completed and were part of a previous RFP

##  Phase 2 - Implementation of the Filecoin.sol libraries 

## Milestone 1 - Deep dive into built-in actors and implementation of an MVP 

### Technical Scope and Timeline
#### Week 1: Deep dive into built-in actors and Filecoin.mock.sol library 

During the first week we will deep dive into built-in actors implementation https://github.com/filecoin-project/builtin-actors/ , and implement a mock.sol library with the scope to enable developers to start creating their first FEVM DApps.
This mock version will not actually perform any cross-contract calls or syscalls. It will respond to specific scenarios. The ultimate goal is for devs to be able to replace imports of mocked libraries with the real one and have their contracts connected to the real protocol.

This phase will principally focus on the following actors:

- StorageMarketActor: responsible for managing storage and retrieval deals [[ Market Actor Repo](https://github.com/filecoin-project/specs-actors/blob/master/actors/builtin/market/market_actor.go)]
- StorageMinerActor: responsible to deal with storage mining operations and collect proofs [[ Storage Miner Actor Repo](https://github.com/filecoin-project/specs-actors/blob/master/actors/builtin/miner/miner_actor.go)]

**Deliverable 1:**
* Implementation of mock libraries for the StorageMarketActor and StorageMinerActor including specific and common types. 
* Implementation of example Smart contract test for each actor to demonstrate how to call the mock library. 
* npm package to easily integrate the library.
* Short documentation

#### Week 2-3: MVP of the Filecoin.sol library  
During these 2 weeks we will focus on implementing Solidity library containing the APIs present in the mock version, MarketAPI.sol and MinerAPI.sol. At this stage we will focus on functionality, and gas-consumption and optimizations will be considered in coming stages. 

**Deliverable 2:**
* Implementation of the APIs for StorageMarketActor, StorageMinerActor, StoragePowerActor and Verified Registry (all methods marked sooner or exported (at the day of writing in the document provided by the fvm core team ) including specific and common types. 
* Implementation of example Smart contracts
* npm package to easily integrate the library. 
* Repository documentation and solidity docs 

### Total Milestone estimated effort and delivery

Duration: 3 weeks (for both, deliverable 1 and deliverable 2)
* Deliverable 1: mid November
* Deliverable 2: early December  

Funding for this Milestone: **23.100,00- $**

## Milestone 2  - Reaching Feature completeness 

###  Technical Scope and Timeline

During this Milestone we will complete the implementation of all remaining methods and built-in actors marked as “export” and that are ready to be integrated within the library. We will provide short solidity documentation as we keep integrating APIs. As we build the library we will test real-world smart contracts with the actual filecoin.sol, to evaluate the gas-cost properties and whether they fit into the size limit of 24kB. 

We will provide frequent updates and releases on a weekly basis. The aim of this Milestone consists of having the code ready for auditing. 

#### Deliverables
* Implementation of the remaining methods for CBOR serialization/deserialization
* Implementation of test smart contracts to interact with the library 
* Dispatch API for all methods of all actors marked as “Sooner” or “Export” 
* APIs to access Filecoin-specific precompiles.
* Handler for handle_filecoin_method (handling method numbers other than 2)
Shorthand utility for authenticate message calls via handle_filecoin_method ([FIP-0044](https://github.com/filecoin-project/FIPs/blob/master/FIPS/fip-0044.md)) 
    *  Some S[olidity code already exists](https://github.com/lotus-web3/client-contract/blob/main/src/DealClient.sol#L49-L58), need to harden, test, and integrate into library as utility
* npm package to easily integrate the library. 
* Short documentation of the library so that it can be used by developers.

### Total Milestone estimated effort and delivery

Duration: 5 weeks 
Delivery plan: We plan to deliver this work incrementally, with releases on a weekly basis. Final delivery is planned for early January. 
Funding for this Milestone: **33’000.00 $**

## Milestone 3 - Getting ready for official release: improvements and optimizations  

###  Technical Scope and Timeline

During this milestone we will keep optimizing the library, and making improvements as we receive feedback from external security audits, fvm core team and developers. We will also complete documentation of the library, and add additional methods that were not were not ready to be exported at an earlier stage. The scope of this milestone includes:

* Implementation of any required additional  methods: at the day of writing many methods are not available to be exported yet.  
* Optimizations covering:
    *  Have a gas consumption estimation for each method: this will allow us to have a general feeling about how the library does in terms of performance. 
    * Create CI benchmarks to be able to account for improvements in gas consumption as we apply changes on code.
    *  Review CBOR serialization process to optimize the gas consumption it generates. As it is the main reason for overhead in gas, it is important to spend time trying to optimize them. This will have an impact on all the actors and methods.
    *  Review CBOR deserialization process to optimize the gas consumption it generates. As it is the main reason for overhead in gas, it is important to spend time trying to optimize them. This will have an impact on all the actors and methods.
    * Review callactor process to optimize the gas consumption it generates.
* Documentation of the library 

### Total Milestone estimated effort and delivery
Duration: 3 weeks
Estimated Delivery: Late January/Early Feb
Funding for this Milestone: 19’800.00 $


## Milestone Summary

| Milestone No. | Milestone Summary & Staffing | Funding | Estimated Timeframe |
| ------------- | --------------------- | ------- | ------------------- |
| 1      | Deep dive into built-in actors and implementation of an MVP   |  23.100,00 $  | Early December 2022             |
| 2      | Reaching Feature completeness   |  33.000,00 $  | Early January  20223            |
| 3      | Getting ready for official release: improvements and optimizations    |  19.800,00 $  | Late January/Early Feb 2023   |


## Total Budget Requested
Total: **75.900,00- $**


# Team
We will allocate 2 x Sr. engineers that will be available full time to work on this project. Additionally, we will have another engineer that will be available if needed to support them, in order to meet delivery times. A project manager will be assigned to make sure deliveries are met on time and quality. 

2 x Sr. Developer 
1 x Software Developer 
Project Management 

# Notes
Security Audit Request: This work does not involve a security assessment/audit in any of the milestones, whether that is cryptographic analysis, workflows, etc. We expect the client to commission and fund an adequate security audit before releasing this to the general public.

License: Source code will be delivered as under Apache 2.0. 

## Contact Info
This has been shared per Email.

## Team Website
https://zondax.ch/

## Relevant Experience
We have taken par of the FVM Early Builders program and recently delivered an SDK for FVM in Assmblyscript, and previous research work for FEVm and precompiles. 

We have been collaborating with PL for several years and have/or are currently contributing to the following projects: Signing Tools (WASM/Typescript and FFI support, Secp256k1 and BLS support) Filecoin Indexing, Filecoin GPU Scheduler, Exchanges & Custodian technical support among others.

## Team code repositories
https://github.com/Zondax/