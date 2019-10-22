# RFP Proposal: `Reputation System`

**Name of Project:** Reputation System

**Link to RFP:** [Reputation System](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-reputation-system.md)
`
**RFP Category:** `app-dev`

**Proposer:** [@deaswang](https://github.com/deaswang)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

a reputation system include:

- web site:
  - show list of miners order by its reputation.
  - miner detail information include:
    - Network participants should be able to query available miners and get back a response that includes (but not limited to): 
    - Number and % (where applicable) of deals with no penalties
    - Number and % (where applicable) of slashed contracts
    - Number and % (where applicable) of dropped contracts
    - Number and % of failed deals (if possible) -- i.e. the number of deals that were attempted but failed, possibly due to this miner having spotty connectivity
    - % of retrieval requests successfully fulfilled
    - Number of files retrieved
    - Lifetime data stored
    - Lifetime data retrieved
    - etc
  - Storage client Feedback.
  - filter miner with location, reputation, price range, storage capacity etc.

- Database
  - all structure chain information.
  - storage client feedback.
  - miner detail history information.

- BackEnd
  - provide all need information from database to frontend.
  - sync all structure chain information.
  - collect and calculate miner detail information from chain information.
  - calculate reputation result from miner detail information and feedback.

## Deliverables

- An open-sourced, dual-licensed (under MIT and APACHE2) service that allows:
  - Storage clients to submit feedback on a miner.
  - The service to validate that feedback against events on the Filecoin network.
  - Users to query and consume information about a miner in question.
- Sample web application (can be extremely simple) that uses both this service and go-filecoin to perform the intended workflow.
- Well-documented api for the service conforming to industry best practices. 
- Tutorial workflow with demo usage. 
- Use Golang.
- Well-documented, human-readable codebase.

## Development Roadmap

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Finalize scope, workflow design, and architectural design | 10000 | 2 weeks |
| 2 | Service implementation | 30000 | 6-8 weeks |
| 3 | Sample web application demonstrating interoperability of go-filecoin and the proposed service | 10000 | 2-4 weeks |
| 4 | All project deliverables (website, documentation, codebase) | 10000 | 2-3 weeks |

## Total Budget Requested

$60000

## Maintenance and Upgrade Plans

We will maintenance and upgrade with go-filecoin upgrade.

# Team

## Team Members

- Frank(@deaswang)
-
-
- 

## Team Member LinkedIn Profiles

- https://github.com/deaswang
- 
- 
- 

## Team Website

[FilCloud](https://github.com/filcloud)

## Relevant Experience


## Team code repositories

[FilCloud](https://github.com/filcloud)

# Additional Information
