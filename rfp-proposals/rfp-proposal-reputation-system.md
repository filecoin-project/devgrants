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
| 1 | Finalize scope, workflow design, and architectural design | TBD | 2 weeks |
| 2 | Service implementation | TBD | 6-8 weeks |
| 3 | Sample web application demonstrating interoperability of go-filecoin and the proposed service | TBD | 2-4 weeks |
| 4 | All project deliverables (website, documentation, codebase) | TBD | 2-3 weeks |

## Total Budget Requested

TBD

## Maintenance and Upgrade Plans

We will maintenance and upgrade with go-filecoin upgrade.

# Team

## Team Members

- Team Member 1
- Team Member 2
- Team Member 3
- ...

## Team Member LinkedIn Profiles

- Team Member 1 LinkedIn profile
- Team Member 2 LinkedIn profile
- Team Member 3 LinkedIn profile
- ...

## Team Website

Please link to your team's website here (make sure it's `https`)

## Relevant Experience

Please describe (in words) your team's relevant experience, and why you think would do a great job with this RFP. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc.

## Team code repositories

Please provide links to your team's prior code repos for similar or related projects.

# Additional Information

Please include any additional information that you think would be useful in helping us to evaluate your grant application.