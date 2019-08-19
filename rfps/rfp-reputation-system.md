# RFP: `Reputation System`

**Name of Project:** Reputation System

**RFP Category:** `app-dev`

**Proposer:** [@jnthnvctr](https://github.com/jnthnvctr)

## Project Description

As the number of storage miners increases on the network, knowing the quality and reputability of miners on the network becomes an unscalable task for any specific participant. Understanding the quality of any given miner can be especially important for storage clients, who may have different requirements about the types of miners with whom they might wish to store their data.

To address this open challenge, we seek proposals for the development of a reputation system - whereby storage clients and network participants may submit substantiated feedback on storage miners to create a reliable source of truth on the quality of miners offering storage on the Filecoin network.

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
  - Successful deals with no penalties
  - Number of slashed contracts
  - Number of dropped contracts
- Feedback provided to the network about a specific miner should be substantiated via actions on the network - the proposed solution should verify claims about reputation via queries to the Filecoin Network. 
- This service should be accessible via a CLI commands, thoughtfully integrated with the workflow required by the go-filecoin network for storage of data.
- In addition, this service should be extensible such that additional information about the miner might be captured and included over time.

## Recommended Team

- Protocol developers with lots of experience in Go might be a good fit for this project.
- Familiarity with storage workflows on the Filecoin protocol highly recommended. 

## Milestones & Funding
Total Funding Amount: TBD. Please propose a budget in your proposal.

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Workflow design and architectural scoping | TBD | 2 weeks |
| 2 | Service implementation | TBD | 6-8 weeks |
| 3 | Sample web application demonstrating interoperability of go-filecoin and the proposed service | TBD | 2-4 weeks |
| 4 | All project deliverables (website, documentation, codebase) | TBD | 2-3 weeks |

## Acceptance Criteria

**Acceptance criteria for workflow design and architectural scoping**:
- These designs and architecture must represent the final design of the service and its intended interoperability with the go-filecoin commands. 
- The workflow design should address the core challenge proposed in the description of this brief, with a focus on the storage client experience.

**Acceptance criteria for service implementation**:
- The service must enable the functionality specified in Milestone 1 in at least one mainstream language.
- Utilization of the service must be enabled for at least commands via the CLI.
- A functioning demo of the service to be presented and testable by the PL team.

**Acceptance criteria for sample application**:
- The sample application must use the proposed service and go-filecoin network to present a view of miners and their current reputation scores. 
- The sample application must to view, search, and filter miners based on their reputation scores. 

**Acceptance criteria for All project deliverables**:
- All of the criteria above have been met.
- A developer on our team can use and test the functionality of this service themselves without needing to talk to anyone.
