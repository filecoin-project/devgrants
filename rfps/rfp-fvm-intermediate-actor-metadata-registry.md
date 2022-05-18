# RFP: `FVM Early Actor Interface & Registry`

**Name of Project:** FVM Early Actor Interface Definitions &  Registry

**RFP Category:** `devtools-libraries`

**Proposer:** @raulk

## Project Description

We seek proposals for:

1. **Early Actor interface definition metadata** - a standardized form of metadata, such as a simple, functional JSON-based interface definition and schema for messages parameters, return types, and state types, similar to Ethereum ABIs, that can be attached to any Actor on chain to allow Actor message and state introspection. This will allow users to auto-generate clients in JS, and allow chain explorers to decode messages and dive into state.

1. **Early metadata registry for Actors** - after deploying an Actor on chain, this registry can be used to attach a corresponding ABI-like metadata schema to the Actor’s code CID. Chain explorers can also look for updates in this registry Actor when a new record is added and apply it towards interpreting those specific messages. By using code CIDs, any actor that gets deployed with that code CID is guaranteed to have the same schema.

1. **JavaScript/TypeScript libraries to codegen clients** - to generate and parse messages, as well as decode actor state given the actor’s state CID. These libraries would be used by Filecoin webapps, chain explorers, and more.

Note that even though IPLD supports a number of codecs, in reality all of Filecoin uses CBOR and the calling convention for Actors is method number-based. We expect the first wave of native actors to use the same codec and calling convention.

This project will attempt to create early developer interfaces today using CBOR serialization / de-serialization for early usage and requirements feedback. An FVM Actor Interface Definition Language in IPLD RFP is also upcoming for the longer-term future and will replace this early work when it is complete.

&nbsp;

#### About the FVM

The Filecoin Virtual Machine is a new and exciting addition to the Filecoin protocol to support user-programmability and EVM-compatibility. ***It is currently in active development.***

*“The FVM is a WASM-based polyglot execution environment for IPLD data. It is designed to support native Filecoin actors written in languages that compile to WASM, as well as smart contracts written for foreign runtimes including the Ethereum Virtual Machine (EVM), Secure EcmaScript (SES), and eBPF.”*

The FVM will be added to the live Filecoin network in several milestones.

**Milestone 1** includes the new VM runtime with built-in actors (i.e., smart contracts) and integration of the reference FVM (written in Rust) into Filecoin clients, either via FFI or without. Milestone 1 is currently scheduled to be deployed in mid-June 2022 with mainnet network update v16 Skyr.

**Milestone 2** will introduce user-programmable actors and EVM-compatibility in a phased manner. The first phase of Milestone 2 will likely be available for bounties in June / July before it is deployed to mainnet in Summer 2022 (estimated).

For more information, visit https://fvm.filecoin.io

## Technical Sponsors

@raulk


## Milestones & Funding

Please describe targeted deliverables for this project in several milestones along with expected budget and timeframe for each milestone as in the [RFP template here](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-template.md#milestones--funding).


## Resources

https://github.com/filecoin-project/FIPs/blob/master/FIPS/fip-0030.md#namespace-actor
https://github.com/filecoin-project/builtin-actors
