> This Wave 1 RFP is open to additional proposals.

# RFP: RSA-based Vector Commitments

**Name of Project:** RSA-based Vector Commitments

**RFP Category:** `core-dev`

**Proposer:** [@pooja](https://github.com/pooja), [@nicola](https://github.com/nicola)

## Project Description

(Originally posted on the [Filecoin Research repo](https://github.com/filecoin-project/research/issues/119))

A Vector Commitment (VC) is a *position binding* commitment and can be opened at any position to a unique value with a short proof (sublinear in the length of the vector). The Merkle tree is a VC with logarithmic size openings.

Recent work on RSA-based VC ([Boneh et al. 2019](https://eprint.iacr.org/2018/1188.pdf)) allows for constant size openings as well as aggregatable proofs, making RSA-based vector commitments appealing for several decentralized applications (stateless blockchains, proof of storage). The Filecoin Research team is working on improving the current Filecoin protocols to make them more efficient and to construct succinct Proofs of Storage based on RSA-based VC.

In this RFP, we are looking for teams that can take our latest research and implementation work on RSA-based VC and implement a modular VC library that can be used by the Filecoin Research team and others. Current implementations include:
- [Cambrian Labs](https://github.com/cambrian/accumulator)
- [@dignifiedquire's implementation](https://github.com/dignifiedquire/rust-accumulators)

## Value

Successful completion of this work will allow us to have much more succinct Proofs of Storage, making our blockchain more efficient and ultimately helping us improve scalability of the protocol. A successful implementation could be used in future upgrades of the Filecoin protocol. This has enormous implications for the world of decentralized storage. Improving scalability of the protocol means a reduction in the barriers to entry for users that want to use the network for its utility without having to deal with the particulars of setting up a complicated node with a long, slow blockchain. This all gets us closer to our ultimate vision of a truly decentralized storage market that powers the web.

## Deliverables

- An open-sourced, dual-licensed (under MIT and APACHE2) library that correctly implements RSA-based vector commitments and can be used modularly by other software projects in the Filecoin ecosystem
	- Can be in any language, but we have a preference for Go and Rust
- Documentation of how to use and install this library
- Sample application (can be extremely simple) that consumes this library as a dependency along with another Filecoin module
- Well-documented, human-readable codebase

## Recommended Team

This project likely requires:
- Expertise in Rust/Go
- Protocol development experience
- Cryptography background
- Deep understanding of vector commitments and RSA

## Milestones & Funding

**Total Funding Amount:** TBD

**Milestones:** Make sure that the values in the Funding column add up to the Total Funding Amount listed above.

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | RSA-based VC library | TBD | 8 weeks |
| 2 | All deliverables (codebase, documentation, application) | TBD | 3 weeks |

## Acceptance Criteria

**Acceptance criteria for milestone 1: RSA-based VC library:**
- Codebase is open-sourced and dual-licensed
- Codebase has a correct and efficient implementation of RSA-based VC (further refinement of this criterion is needed)

**Acceptance criteria for milestone 2: All deliverables:**
- Sample application correctly demonstrates that RSA-based VCs are implemented and can be used with other libraries in a useful workflow
- RSA-based VC library can be used by someone on Filecoin Research or rust-fil-proofs just by using the documentation

## Resources

TODO