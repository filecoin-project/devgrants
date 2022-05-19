# FVM Project Ideas

We are seeking proposals for the following RFPs for the Filecoin VM.

#### About the FVM

The Filecoin Virtual Machine is a new and exciting addition to the Filecoin protocol to support user-programmability and EVM-compatibility. ***It is currently in active development.***

The FVM will be added to the live Filecoin network in several milestones.

**Milestone 1** includes the new VM runtime with built-in actors (i.e., smart contracts) and integration of the reference FVM (written in Rust) into Filecoin clients, either via FFI or without. Milestone 1 is currently scheduled to be deployed in mid-June 2022 with mainnet network update v16 Skyr.

**Milestone 2** will introduce user-programmable actors and EVM-compatibility in a phased manner. It is currently scheduled for deployment in September 2022 (estimated).

For more information, visit https://fvm.filecoin.io

-----

Have a question about an RFP? Ask in [Filecoin Slack](https://filecoin.io/slack) in the `#fvm` channel and flag the technical sponsors.

Interested in applying for an RFP below or have a project idea not listed here? See the [FVM Open Tooling & Infrastructure RFP](fvm-open-tools-infra.md) for guidelines on submitting a proposal.

-----

## *FVM Project Ideas*

- [FVM Early Actor Interface & Registry](#fvm-early-actor-interface-and-registry)

*Stay tuned! More RFPs will be posted soon.*

&nbsp;

&nbsp;

### FVM Early Actor Interface & Registry

**Category:** `devtools-libraries`

#### Overview

This project will attempt to create early developer interfaces today using CBOR serialization / de-serialization for early usage and requirements feedback. An FVM Actor Interface Definition Language in IPLD RFP is also upcoming for the longer-term future and will replace this early work when it is complete.

#### Description

We seek proposals for:

1. **Early Actor interface definition metadata** - a standardized form of metadata, such as a simple, functional JSON-based interface definition and schema for messages parameters, return types, and state types, similar to Ethereum ABIs, that can be attached to any Actor on chain to allow Actor message and state introspection. This will allow users to auto-generate clients in JS, and allow chain explorers to decode messages and dive into state.

1. **Early metadata registry for Actors** - after deploying an Actor on chain, this registry can be used to attach a corresponding ABI-like metadata schema to the Actor’s code CID. Chain explorers can also look for updates in this registry Actor when a new record is added and apply it towards interpreting those specific messages. By using code CIDs, any actor that gets deployed with that code CID is guaranteed to have the same schema.

1. **JavaScript/TypeScript libraries to codegen clients** - to generate and parse messages, as well as decode actor state given the actor’s state CID. These libraries would be used by Filecoin webapps, chain explorers, and more.

Note that even though IPLD supports a number of codecs, in reality all of Filecoin uses CBOR and the calling convention for Actors is method number-based. We expect the first wave of native actors to use the same codec and calling convention.

#### Technical Sponsors

@raulk, @eshon

#### Resources

https://github.com/filecoin-project/FIPs/blob/master/FIPS/fip-0030.md#namespace-actor
https://github.com/filecoin-project/builtin-actors


&nbsp;
-----
&nbsp;

<!--

### RFP Idea title

**Category:**

#### Overview

#### Description

#### Technical Sponsors

#### Resources

&nbsp;
-----
&nbsp;

-->
