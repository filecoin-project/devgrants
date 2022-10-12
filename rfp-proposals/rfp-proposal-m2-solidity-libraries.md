# RFP Proposal: `M2 - Solidity libraries and pre-compiles for FEVM Smart Contracts`

**Name of Project:** Solidity libraries and pre-compiles for FEVM Smart Contracts

**Link to RFP:**  

**RFP Category:** `devtools-libraries`

**Proposer:** `ainhoa-a`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes 

# Project Description

In the context of the FEVM Early Builder program we propose to build a set of tools and libraries to enable Ethereum developers to re-use their existing know-how to develop Filecoin-specific use cases.             
               
After validating the first Milestone, it has been proposed to continue the research to investigate and evaluate pre-compiles for specific built-in actors.  

If the evaluation is successful we would like to continue working on this project, otherwise, a different approach should be investigated. 

## Development Roadmap

### Milestone 1 - Research and feasibility analysis of CBOR in Solidity in terms of FVM gas usage 

*This Milestone has been completed and it was part of a previous RFP: https://github.com/filecoin-project/devgrants/issues/897

### Milestone 2 - Research and PoC of Pre-compiles for specific built-in actors

Assumptions/ Pre-requirements

_Access to tutorials and existing documentation for the integration is provided. 
Access to async agile communication in the FVM Slack Channel._ 

#### Technical Scope and Timeline

Weeks 1-2: Research and development of PoC for specific builtin actors 

The first two weeks will be dedicated to the research and development of a Proof of Concept to evaluate pre-compiles for specific builtin actors. The objective is that pre-compiles will live in the EVM actor. We will modify EVM built-in actor to include pre-compiles, starting with a Multisig Actor. Once we have integrated this we will run a benchmarking to test and compare if we have significant improvements. 

##  Deliverables

- EVM built-in actor with new functionalities (pre-compiles)
- Solidity Smart contract calling the pre-compile feature 
- Benchmarking of gas consumption
- Test suite 
- Short documentation

## Team Members

1.5 FTE

- Technical Leader Engineer
- 1 Support Engineer
- Management POC  

## Estimated Milestone Delivery

4 weeks from kickoff
Assumption: Late October / Early November

## Milestone Summary

| Milestone No. | Milestone Summary & Staffing | Funding | Estimated Timeframe |
| ------------- | --------------------- | ------- | ------------------- |
| 1             | Results of feasibility analysis for the use of CBOR in Solidity in terms of FVM gas usage  |  RFP https://github.com/filecoin-project/devgrants/issues/897   | Already delivered in September 2022             |
| 2             | Results of  Pre-compiles for specific built-in actors  |  16.800,00- $  | Delivery Late Oct / Early Nov 2022   |

## Total Budget Requested

Total: 16.800,00- $

## Maintenance and Upgrade Plans

If the research analysis from Milestone 2 provides good results we would like to continue this project, adapting to the needs of the FVM core team and eventually collaborating in the development of the solidity libraries for built-in actors. 

# Team

## Contact Info

This has been shared per Email.

## Team Members

- Team Member 1 - [Lola Rigaut-Luczak ](https://github.com/rllola) 
- Team Member 2 - [Emmanue Murano](https://github.com/emmanuelm41) 
- Team Member 3 - [Ainhoa Aldave](https://github.com/ainhoa-a)

## Team Website

https://zondax.ch/

## Relevant Experience

We have taken part in the FVM Early Builders program and recently delivered an SDK for FVM in Assemblyscript. https://github.com/Zondax/fvm-as-sdk 

We have been collaborating with PL for several years and have/or are currently contributing to the following projects: Signing Tools (WASM/Typescript and FFI support, Secp256k1 and BLS support) Filecoin Indexing, Filecoin GPU Scheduler, Exchanges & Custodian technical support among others.

## Team code repositories

https://github.com/Zondax/