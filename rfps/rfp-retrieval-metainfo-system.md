# RFP: `Retrieval Metainfo System`

**Name of Project:** Retrieval Metainfo System

**RFP Category:** `app-dev`

**Proposer:** [@askender](https://github.com/askender)

## Project Description

Many public dataset is stored in the filecoin network and ipfs, and there are nearly no meta information can be found about these data.  We need a Retrieval Metainfo System which make data and it's meta information can be easily searched and found.
To address this open challenge, we seek proposals for the development of a retrieval metainfo system.
In your proposal, please specify how you would approach building this sort of project, i.e. general architectural choices, feature scope, and other related details.

Please fill in details about this project. What are you asking for someone to build? What is the purpose/context for this project? What are the high-level requirements for the project?

This section should be 2-3 paragraphs long.

## Value

Please describe why the work that will come out of this RFP is valuable for the Filecoin ecosystem.

## Deliverables

- An open-sourced, dual-licensed (under MIT and APACHE2) service that allows:
  - Storage clients to submit meta information on the system.
  - Users to query the meta informationrmation of dataset.
- A web application (can be extremely simple) that show the meta infomation.
- Tutorial workflow with demo usage. 
- Can be in any language, preference for Go. 
- Well-documented, human-readable codebase.
- A incentive mechanism for meta information provider (optional).


## Recommended Team

- Developers with experience in javascript/python/go might be a good fit for this project.
- Familiarity with storage workflows on the Filecoin protocol highly recommended. 


## Detailed Requirements & Constraints

Total Funding Amount: TBD. Please propose a budget in your proposal.

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Finalize scope, workflow design, and architectural design | TBD | 2 weeks |
| 2 | Service implementation | TBD | 6-8 weeks |
| 3 | Sample web application | TBD | 2-4 weeks |
| 4 | All project deliverables (website, documentation, codebase) | TBD | 2-3 weeks |


## Milestones & Funding

**Total Funding Amount:** List the total proposed funding amount (currently in USD, eventually can be a distribution between USD/FIL)

**Milestones:** Make sure that the values in the Funding column add up to the Total Funding Amount listed above.

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Example milestone | $X | Y weeks |
| 2 | Example milestone | $X | Y weeks |
| 3 | Example milestone | $X | Y weeks |

## Acceptance Criteria


**Acceptance criteria for: Finalize scope, workflow design, and architectural design**:
- This milestone's deliverables must represent the final design of the service.
- The workflow design should address the core challenge proposed in the description.

**Acceptance criteria for service implementation**:
- The service must enable the functionality specified in Milestone 1 in at least one mainstream language.
- Utilization of the service must be enabled for at least commands via the CLI.
- A functioning demo of the service to be presented and testable by the PL team.

**Acceptance criteria for sample application**:
- The sample application must use the proposed service to get the meta information. 
- The sample application must be able to view, search, and filter meta information. 

**Acceptance criteria for All project deliverables**:
- All of the criteria above have been met.
- A developer on our team can use and test the functionality of this service themselves without needing to talk to anyone.


## Resources

- https://slingshot.filecoin.io/