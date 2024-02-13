# RFP Proposal: Chainlink x Filecoin: Use Filecoin for Ethereum zk-Rollup storage

**Name of Project:** filecoin-rollup

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/chainlink-and-filecoin.md

**RFP Category:** `technical-design`

**Proposer:** `@weikengchen`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

## Project Description

Today, the dominating cost of zk-Rollup is related to data availability. Putting data on layer-1, which is the standard solution for data availability, is very expensive. Several companies working in zk-Rollup have been thinking about their own ways of escaping from storing data on Ethereum (e.g., zkPorter, https://blog.matter-labs.io/zkporter-a-breakthrough-in-l2-scaling-ed5e48842fbf).

Given that Chainlink x Filecoin is going to provide an external adapter, assuming at least there is a data feed for the latest block hash or state tree hash, it is possible to enable running a light client inside the zkSNARK circuit, and therefore, the layer-2 can prove to everyone that the data has been reliably stored on Filecoin. 

This project is to explore the technical designs for it. The goal is to enable a zk-Rollup layer-2 to prove that certain data has been stored on Filecoin. The design needs to be efficient, which involves the technical details of zkSNARK and Filecoin's design. Note that Filecoin is using a number of cryptographic primitives that could make the light client in zkSNARK challenging. They will be the focus of this research.

In summary, we want to check if the external adapter would be sufficient, or needs changes, for proving Filecoin storage inside zkSNARK.

## Examples of technical challenges:
The CIDv1 uses multihash to compute the digest of the file. By looking at the existing standards, it seems that `poseidon-bls12_381-a2-fc1` would be suitable to make the file zkSNARK-friendly. We may want to see if there are ways to check file consistency with a lower cost (e.g., by the use of Reed-Solomon code), and how `poseidon-bls12_381-a2-fc1` is supported in current platforms.

The curve used for zkSNARK proofs in Filecoin, BLS12-381, is notorious for the difficulty to verify its proof inside zkSNARK, because BLS12-381's Fq has a two-arity of 1, prohibiting a large number of proof systems based on FFT.
- Needs to check whether it is possible to not verify any proof while having the security guarantees, assuming Chainlink's oracle is perfectly secure.
- Needs to examine how to bring the proof back to the curve of BN254. This may involve the use of nonnative arithmetics (https://github.com/arkworks-rs/nonnative).
- Needs to examine whether Starkware's FRI is better suit for this purpose.  

## Value

This is an important application that seems to be originally a reason behind the collaboration of Chainlink x Filecoin. 

If Filecoin can interpolate with Ethereum, it can provide Ethereum layer-2 with lower cost, and it can also increase the demands of storage in the Filecoin network, which benefits the coins, miners, and the ecosystem in general.

This research is better done sooner than later, as if any protocol change is indeed necessary for this purpose, it is better to be known soon. 

## Deliverables

- A summary of the Filecoin infrastructure that is related to this application, given that Filecoin has a big spec
- Discussion on how to handle the file hash
- Discussion on how to enable a light client to find state information
- Discussion on what the light client in the zkSNARK circuit needs to verify
- Discussion on how to efficiently wrap it into a BN254 proof or a Keccak-based FRI proof
- Discussion on what protocol changes of Filecoin or the Chainlink x Filecoin oracle may benefit such applications
- Proposals for next steps (what to develop, likely in the form of dev apps proposal)

## Development Roadmap

In total 14 weeks, slightly exceeding 3 months.

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Summary of relevant Filecoin infrastructure | $1K | 2 weeks |
| 2 | Discussion on file hash | $1K | 2 weeks |
| 3 | Discussion on state retrieval | $1K | 2 weeks |
| 4 | Discussion on proof requirements | $1K | 2 weeks |
| 5 | Discussion on proof wrapping | $1K | 2 weeks |
| 6 | Recommended protocol changes | $1K | 2 weeks |
| 7 | Next steps proposals | $1K | 2 weeks |

The deliverables would sufficiently cover the state-of-the-arts techniques regarding zk-Rollup and zkSNARK, so it can serve as a good systematization of knowledge. 

Specifically, 
- the file hash should cover how to extend the current CID/multihash to support zkSNARK-friendly hash functions if needed
- the state retrieval protocol should work with today's Filecoin protocol
- the proof requirements need to explore potential storage fault and slashing
- the proof wrapping should explore both curve-based solutions, including non-FFT proof systems, and FRI-based solutions
- the recommended protocol changes should be reasonable changes and be valuable to improve the efficiency 
- the next-step proposals should be a sound plan for a dev app that can implement the design, assuming Chainlink's oracle for Filecoin is already there

## Total Budget Requested

Since this does not involve app developers but mostly research, $7K is sufficient. See above for a breakdown.
FIL coins are clearly preferred for this project.

## Maintenance and Upgrade Plans

We believe that the proposals for the next steps would be valuable. 

# Team

## Team Members

More members may be added later.

- Weikeng Chen

## Team Member LinkedIn Profiles

- [Weikeng Chen](https://www.linkedin.com/in/chenweikeng/)

## Relevant Experience

Weikeng is a PhD student at UC Berkeley working on zero-knowledge proofs and secure multiparty computation, a co-maintainer of the arkworks-rs library (https://github.com/arkworks-rs/), and he is a former intern at a16z-backed blockchain startup Aleo Systems Inc. 

In one of his work "Reducing Participation Costs via Incremental Verification for Ledger Systems" (with Alessandro Chiesa, Emma Dauterman, and Nicholas P. Ward, https://eprint.iacr.org/2020/1522.pdf), which is very closely related to zk-Rollup today, verifying a universal-setup zkSNARK proof inside zkSNARK is done for the first time, which has become a crucial component of Aleo's DPC implementation.

## Resources

https://github.com/filswan/flink (This is an external adapter)

https://github.com/filecoin-project/specs/issues/68

https://github.com/ipfs/specs/issues/130

https://github.com/multiformats/go-multihash/tree/master/multihash

# Additional Information

This project requires information about the external adapter that Chainlink and Filecoin are working on.
