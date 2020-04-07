> This Wave 1 RFP is open to additional proposals.

# RFP: `Reputation System`

**Name of Project:** Reputation System

**RFP Category:** `app-dev`

**Proposer:** [@jnthnvctr](https://github.com/jnthnvctr)

## Project Description

As the number of storage miners increases on the network, knowing the quality and reputability of miners on the network becomes an unscalable task for any specific participant. Understanding the quality of any given miner can be especially important for storage clients, who may have different requirements about the types of miners with whom they might wish to store their data.

To address this open challenge, we seek proposals for the development of a reputation system - whereby storage clients and network participants may submit substantiated feedback on storage miners to create a reliable source of truth on the quality of miners offering storage on the Filecoin network. In your proposal, please specify how you would approach building this sort of project, i.e. general architectural choices, feature scope, and other related details.

## Deliverables

- An open-sourced, dual-licensed (under MIT and APACHE2) service that allows:
  - Storage clients to submit feedback on a miner.
  - The service to validate that feedback against events on the Filecoin network.
  - Users to query and consume information about a miner in question.
- Sample web application (can be extremely simple) that uses both this service and go-filecoin to perform the intended workflow.
- Well-documented api for the service conforming to industry best practices. 
- Tutorial workflow with demo usage. 
- Can be in any language, preference for Go. 
- Well-documented, human-readable codebase.

## High Level Requirements

While we aim to leave the specifics of the reputation system to the reputation system, proposals in this space should conform to the following high level requirements: 

- Network participants should be able to query available miners and get back a response that includes (but not limited to): 
  - Number and % (where applicable) of deals with no penalties
  - Number and % (where applicable) of slashed contracts
  - Number and % (where applicable) of dropped contracts
  - Number and % of failed deals (if possible) -- i.e. the number of deals that were attempted but failed, possibly due to this miner having spotty connectivity
  - % of retrieval requests successfully fulfilled
  - Number of files retrieved
  - Lifetime data stored
  - Lifetime data retrieved
- Feedback provided to the network about a specific miner should be substantiated via actions on the network - the proposed solution should verify claims about reputation via queries to the Filecoin Network (e.g. by verifying deal state on the Filecoin network).
- Calls to this service should be well scoped, such that this service might be easily integrated into other libraries that might more broadly focus on creating a seamless storage experience.
- Functionality of this service should be thoughtfully integrated into the storage workflow for the Filecoin Network.
- In addition, this service should be extensible such that additional information about the miner might be captured and included over time.

## Recommended Team

- Protocol developers with lots of experience in Go might be a good fit for this project.
- Familiarity with storage workflows on the Filecoin protocol highly recommended. 

## Milestones & Funding
Total Funding Amount: TBD. Please propose a budget in your proposal.

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Finalize scope, workflow design, and architectural design | TBD | 2 weeks |
| 2 | Service implementation | TBD | 6-8 weeks |
| 3 | Sample web application demonstrating interoperability of go-filecoin and the proposed service | TBD | 2-4 weeks |
| 4 | All project deliverables (website, documentation, codebase) | TBD | 2-3 weeks |

## Acceptance Criteria

**Acceptance criteria for: Finalize scope, workflow design, and architectural design**:
- This milestone's deliverables must represent the final design of the service and its intended interoperability with the go-filecoin API and functionality.
- The workflow design should address the core challenge proposed in the description of this brief, with a focus on the storage client experience.

**Acceptance criteria for service implementation**:
- The service must enable the functionality specified in Milestone 1 in at least one mainstream language.
- Utilization of the service must be enabled for at least commands via the CLI.
- A functioning demo of the service to be presented and testable by the PL team.

**Acceptance criteria for sample application**:
- The sample application must use the proposed service and go-filecoin network to present a view of miners and their current reputation scores. 
- The sample application must be able to view, search, and filter miners based on their reputation scores. 

**Acceptance criteria for All project deliverables**:
- All of the criteria above have been met.
- A developer on our team can use and test the functionality of this service themselves without needing to talk to anyone.
