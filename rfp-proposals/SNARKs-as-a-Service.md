# RFP Proposal: `SNARKs-as-a-Service (Wave 3/4 RFP)`

**Name of Project:** SNARKs-as-a-Service

**RFP Category:** `core-dev`

**Proposer:** `hellosupranational`

## Project Description

This proposal seeks to develop and operate a free and public 'SNARK-as-a-service' on the Filecoin mainnet for at least 6 months. The goal of this service is to enable users to store and prove data on devices with limited compute capabilities. The initial implementation of the service will support the 32GB WindowPoSt SNARK and will be based on open-source (Apache 2 or MIT) SNARK proving software. The service will provide an API that consumes SNARK inputs (e.g. public inputs, witness) and returns a SNARK proof to the user that may then be submitted to the Filecoin network. The following activities will be completed as part of this grant:

1. Identification of a cost-efficient SNARK proving hardware and hosting environment.
2. Development of a 'scale-out' SNARK proving infrastructure.
3. Development and documentation of the SNARK-as-a-Service REST API, including authentication and authorization functionality.
4. Design and develop SNARK-as-a-Service integration into Lotus client.
5. SNARKs-as-a-Service operation and metrics collection for six months.

While initially the service will support only 32GB WindowPoSt. Future improvements may include support for other sector sizes, as well as support for other SNARKs on the Filecoin network including Proofs-of-Replication or WinningPoSt. After the conclusion of six months and a report out of the metrics to Protocol Labs, there are a variety of options to continue the service including:

* Community supported through donations
* Pay-per-SNARK basis using FIL or traditional payment methods
* Continued support by the Filecoin grants program

## Value
While sealing data and generating PoRep SNARKs are computationally expensive, once this operation is done the sealed sectors can be maintained by devices with less compute power. Furthermore, by offering SNARKs-as-a-service, we are able to amortize the cost of the hardware across many miners, ensuring the hardware is more fully utilized and therefore reducing the cost of each SNARK. The service will initially support up to 200 WindowPoSt per day, but will be built to be horizontally scalable. This initial capacity is enough to support over 10PB of storage at full utilization. Longer-term, the goal of this project is to begin partitioning the computational components required by the Filecoin network so that the appropriate hardware can be selected for each, and the efficiency of the network can be improved. By offering some of these computations 'as-a-service', we are able to reduce the hardware requirements for a miner and enable them to choose between operational and capital expenses. 

## Deliverables

1. Development and documentation of SNARK-as-a-Sevice platform
2. Proposed SNARK-as-a-Service integration into Lotus or rust-fil-proofs
3. Operation of SNARKs-as-a-Service for six months
4. Final report-out including learnings and metrics from service operation

## Team

*Supranational Team*
* Sean Gulley and Simon Peffers are former Principal Engineers at Intel’s Data Center Innovation Group. They have worked for over two decades on algorithmic acceleration, including cryptography.
* Erdinç Öztürk is an assistant professor at Sabanci University and has published numerous papers on hardware acceleration of cryptography.
* Kelly Olson is a former director in the Security Division at Intel Corporation and has served on the Technical Steering Committee and Governing Board of the Linux Foundation's Hyperledger project.

## Detailed Requirements & Constraints

This section was not provided in the Wave 3/4 RFP proposal. It can be discussed and updated as needed following Protocol Labs feedback.

## Milestones & Funding

**Total Funding Amount:** $55,000

**Milestones:**

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Project kickoff and capacity procurement | $10,000 | 2 weeks |
| 2 | SNARK-as-a-Service capability integrated into Lotus or rust-fil-proofs | $15,000 | 6 weeks |
| 3 | SNARK service publicly available | $15,000 | 12 weeks |
| 4 | SNARK service operational for 6 months | $15,000 | 24 weeks |

## Acceptance Criteria

| Milestone No. | Milestone Description | Acceptance Criteria |
| --- | --- | --- |
| 1 | Project kickoff and capacity procurement | Project kickoff meeting held with Protocol Labs team
| 2 | SNARK-as-a-Service capability integrated into Lotus or rust-fil-proofs | Capability integrated into client
| 3 | SNARK service publicly available | Sign-ups for service publically available
| 4 | SNARK service operational for 6 months | Final report detailing service learnings and usage over six months

## Resources

N/A



