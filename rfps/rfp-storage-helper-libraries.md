> Proposals for this were funded in Wave 1 but this RFP is still open for additional proposals.

# RFP: Storage Helper Libraries

**Name of Project:** Storage Helper Libraries

**RFP Category:** `devtools-libraries`

**Proposer:** [@mishmosh](https://github.com/mishmosh)

## Project Description

(originally described [here](https://discuss.filecoin.io/t/brainstorming-storage-helpers/423))

The intent of go-filecoin is to handle operations at the detailed, protocol level. However, there’s an emerging body of functions that may be well-suited for libraries, separate from the go-filecoin node but generally reusable across a variety of storage use cases and implementations. They could include:
- **File ingestion + splitting**: generally speaking, this prepares files for storage deals in dag-compatible way. recurse through folders. split files that are larger than selected filecoin sector size into chunks according to dag. et cetera.
- **Storage deal agent**: primary job would be to monitor deals and renew as needed. could also select from miners with the best reputations, desired price range(s), desired geographical distribution
- Your ideas for storage helper tools

This RFP is requesting proposals for storage helper libraries that can bundle useful functions from [`go-filecoin`](https://github.com/filecoin-project/go-filecoin/) and other standard software libraries into a module that is useful for common storage workflows. You can submit a more fleshed out proposal for either of the ideas listed here, or you can propose a new idea for a storage helper library in response to this RFP.

## Deliverables

- An open-sourced, dual-licensed (under MIT and APACHE2) library that performs a useful workflow and can be used modularly by other software applications in the Filecoin ecosystem
	- Can be in any language, but we have a preference for Go
- Documentation of how to use and install this library
- Sample application (can be extremely simple) that uses both this helper library and `go-filecoin` to perform the intended workflow
- Well-documented, human-readable codebase

## Recommended Team

- Protocol developers with lots of experience in Go might be a good fit for this project
- Some familiarity with storage workflows and Filecoin will be extremely useful in coming up with interesting module ideas

## Milestones & Funding

**Total Funding Amount:** $5000

**Milestones:** 

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Storage helper library | $3500 | 2 weeks |
| 2 | All deliverables (codebase, sample application, documentation, testing) | $1500 | 1 week |

## Acceptance Criteria

- The sample application must demonstrate the approved library functionality with no errors
- The sample application must be built on top of both the storage helper library and `go-filecoin`, and it must work as intended
- A developer on our team can install and use this helper library themselves without needing to talk to anyone

## Resources

- [`go-filecoin` CODEWALK](https://github.com/filecoin-project/go-filecoin/blob/master/CODEWALK.md)
- [Discussion forum thread on brainstorming storage helper ideas](https://discuss.filecoin.io/t/brainstorming-storage-helpers/423)
- [Filecoin network stats dashboard](https://github.com/filecoin-project/filecoin-network-stats/), an application built on top of go-filecoin
- [Filecoin protocol specification](https://github.com/filecoin-project/specs/), for a deeper explanation of the Filecoin protocol