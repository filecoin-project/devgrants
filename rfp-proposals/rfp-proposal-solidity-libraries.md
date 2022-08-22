# RFP Proposal: `Solidity libraries and pre-compiles for FEVM Smart Contracts`

**Name of Project:** Solidity libraries and pre-compiles for FEVM Smart Contracts

**Link to RFP:**  https://github.com/filecoin-project/devgrants/pull/898

**RFP Category:** `devtools-libraries`

**Proposer:** `ainhoa-a`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes 

# Project Description

In the context of the FVM Early Builder program (Solidity edition), we propose to build a set of tools and libraries to enable Ethereum developers to re-use their existing know-how to develop Filecoin-specific use cases.  
                          
The first goal, which we have defined as Milestone 1 would consist of a feasibility analysis to evaluate if it is worth it to serialize and deserialize data in solidity.     

If the evaluation is successful we would like to continue working on this project, otherwise, a different approach should be investigated. 

## Development Roadmap

### Milestone 1 - Research and feasibility analysis of CBOR in Solidity in terms of FVM gas usage 

Assumptions/ Pre-requirements

_Access to tutorials and existing documentation for the integration is provided. 
Access to async agile communication in the FVM Slack Channel._ 

#### Technical Scope and Timeline

####  Week 1: Ramp-up into FEVM
During the first week we will go through the existing tutorials and documentation, we will identify the gaps that exist to improve this documentation for other developers. 

- Set up a FEVM running environment
- Investigate how to deploy a Solidity Smart Contract in the FVM environment.

#### Weeks 2-3 The deep dive into Solidity 
- Implementation of a smart-contract in solidity that serialises and deserializes data in CBOR including complex types like structs and lists. 
- Benchmarking of gas efficiency.
- Short documentation and preparation of the results for the demo

##  Deliverables

- Smart Contract of the PoC capable of serialising and deserializing data in CBOR.
- Short Documentation (Readme file). 
- Results of the Benchmark.

## Team Members

1.5 FTE

- Technical Leader Engineer
- 1 Support Engineer
- Management POC  

## Estimated Milestone Delivery

4 weeks from kickoff
Assumption: Mid-Late September 

## Milestone Summary

| Milestone No. | Milestone Summary & Staffing | Funding | Estimated Timeframe |
| ------------- | --------------------- | ------- | ------------------- |
| 1             | Results of feasibility analysis for the use of CBOR in Solidity in terms of FVM gas usage  |  28.400,00 $  | Delivery Mid-Late September 2022             |

## Total Budget Requested

Total: 28.400,00- $

## Maintenance and Upgrade Plans

If the research analysis from Milestone 1 provides good results in terms of feasibility for this approach, we would like to continue this project, with Milestone 2, focusing around the Implementation CBOR serde for the common Filecoin data types (Address, Actor ID, Sector Number, etc. – a lot of this is inside fvm_shared) and later a Milestone 3 consisting in the implementation of the actual library. Otherwise, the work around this approach will stop and other approaches should be investigated. 

# Team

## Contact Info

This has been shared per Email.

## Team Members

- Team Member 1 - [Emmanue Murano](https://github.com/emmanuelm41) 
- Team Member 2 - [Lola Rigaut-Luczak ](https://github.com/rllola)
- Team Member 3 - [Ainhoa Aldave](https://github.com/ainhoa-a)

## Team Website

https://zondax.ch/

## Relevant Experience

We have taken par of the FVM Early Builders program and recently delivered an SDK for FVM in Assmblyscript. https://github.com/Zondax/fvm-as-sdk 

We have been collaborating with PL for several years and have/or are currently contributing to the following projects: Signing Tools (WASM/Typescript and FFI support, Secp256k1 and BLS support) Filecoin Indexing, Filecoin GPU Scheduler, Exchanges & Custodian technical support among others.

## Team code repositories

https://github.com/Zondax/