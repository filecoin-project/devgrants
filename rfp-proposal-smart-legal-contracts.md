
# RFP Proposal: `Smart Legal Contracts`

**Name of Project:** Smart Legal Contracts

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/hedera-and-filecoin.md

**RFP Category:** `app-dev`

**Proposer:** `niallroche`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description
This project will add support for smart legal contracts, sometimes referred to as smart legal agreements, to the Hedera platform by leveraging FileCoin's content addressable distributed storage mechanism to store the legal agreements as an NFT. The legal documents will be represented in standard approaches such as the proposed https://legalschema.org and represented using the Accord Project https://accordproject.org.

The project will use a real-world example use case involving a Digital Bill of Lading represented as an NFT, as outlined in the legal schema whitepaper https://technation.io/wp-content/uploads/2021/06/LegalSchemaFinal.pdf. This project has support from LawtechUK https://technation.io/lawtechuk/ and will build upon prior work of the Law Commission https://www.lawcom.gov.uk/ to support the mainstream adoption of digital documents (including smart contracts) as outlined in https://s3-eu-west-2.amazonaws.com/lawcom-prod-storage-11jsxou24uy7q/uploads/2020/12/Smart-Contracts-summary.pdf.

## Deliverables

The final deliverable for this project will be a digital legal document, represented in a schema defined by legalschema.org with smart clauses implemented in the Accord Project represented as an NFT, stored in Filecoin using the NFT.storage API with a demonstrator application.

## Development Roadmap

### Timeline
The timeframe is proposed to be a three month period starting in October 2021 (M1) to December 2021 (M3)

### Milestone 1 - Digital Document Schema Definitions
- __definition:__
Defining a master schema built on top of https://legalschema.org to represent a digital document with the initial use case being proposed to be a Digital Bill of Lading as outlined in https://github.com/legalschema/templates/blob/main/src/bill-of-lading/text/grammar.tem.md with a sample example at https://github.com/legalschema/templates/blob/main/src/bill-of-lading/text/sample.md.   

- __resources required:__
This milestone will require input from both legal engineers and lawyers from LegalSchema and MDRxTech and LawTechUK to ensure that the digital representation of the document is sufficient to meet the requirements of a real-world transaction and to be compliant with various legal regulations and practices in the UK, including data protection.

- __duration:__ 1 month
- __timeline:__ M1
- __cost estimate:__ USD 8,000

### Milestone 2 - Digital Document represented as a NFT stored on Filecoin
- __definition:__
Modification of the existing proofs of concept from LegalSchema.org that are currently using OpenSea as a marketplace https://github.com/legalschema/nft-metadata-api and Ethereum https://github.com/legalschema/nft-contracts to be associated with the NFT JSON metadata schema stored on Filecoin by using the NFT.storage API and Hedera Token Service, or potentially other alternative toolchains that will arise from the RFP for Decentralized Storage SDK for Hedera & Demo Application.

- __resources required:__ Team Lead & DLT Engineer
- __duration:__ .5 month
- __timeline:__ M1
- __cost estimate:__ USD 14,000

### Milestone 3 - Integration of Smart Legal Contract Stack with Hedera
- __definition:__
This will require integration of parts of the https://github.com/accordproject components with https://github.com/hashgraph/hedera-sdk-js to manage the integration between the Smart Legal Contract Layer and the DLT Smart Contract Layer.

Potential Integration options for this stage include:
1. relay of on-chain events into instances of accord project hosted in an off-chain deployment similar to the example in https://github.com/accordproject/aws-qldb-lambda or as hosted by https://clause.io/smart-agreements

2. Porting the output of the compiled Smart Legal Contract from https://github.com/accordproject/cicero, https://github.com/accordproject/concerto and https://github.com/accordproject/ergo which cross compile into JavaScript and embed on-chain using https://github.com/hashgraph/hedera-sdk-js

- __resources required:__ Team Lead & DLT Engineer
- __duration:__ 1.5 month
- __timeline:__ M1 M2
- __cost estimate:__ USD 19,000

### Milestone 4 - Deployment and testing of Smart Legal Contract Stack with Hedera Nodes in AWS
- __definition:__
Deployment of the Smart Legal Contract Layer and the DLT Smart Contract Layer environments using CI/CD such as Terraform or AWS CloudFormation into an AWS environment either running or interacting with Hedera Nodes via a third party provider

- __resources required:__ Team Lead & DLT Engineer
- __duration:__ 1.5 month
- __timeline:__ M3
- __cost estimate:__ USD 5,500

### Other costings
Depending on Implementation options and Node Hosting, the hosting costs are anticipated to be in the region of $700-$1,200 AWS Hosting fees per month and are only included for the initial three months of the project, while additional transaction fees are predicted they are not considered here for simplicity.  

## Total Budget Requested

Total costs are expected to be in the region of $48,600


## Maintenance and Upgrade Plans

The core MDRxTech team are looking to support a number of projects involving Smart Legal Contracts across a number of DLT solutions, the team have been involved in the Accord Project for almost 3 years and are active members of the Technical Steering Committee and are founders of Real Estate and Construction Working Groups. Members of the core team are members of the UCL CBT and Construction Blockchain Consortium (CBT) and other OSS projects such as https://raphtory.github.io/ and therefore they have long-term plans to maintain this software and upgrade it over time.

# Team

## Contact Info

niall.roche@mishcon.com

## Team Members

- __Niall Roche__ - Head of Distributed Systems Engineering @ Mishcon de Reya (MDRxTech), member of UCL Centre for Blockchain Technology, Construction Blockchain Consortium (CBC), member of Technology Working Group Accord Project
- __Tom Grogan__ - Lawyer, emerging technology, AI/ML and blockchain @ Mishcon de Reya, Head of MDRxTech
- __Alastair Moore__ - Head of Analytics and Machine Learning @ Mishcon de Reya (MDRxTech), member of UCL Centre for Blockchain Technology, Construction Blockchain Consortium (CBC), Head of Real Estate and Construction Working Groups in the Accord Project
- __Walter Hernandez__ - DLT Software Engineer @ Mishcon de Reya, member of Accord Project

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/niallroche/
- https://www.linkedin.com/in/tomgroganmdr/
- https://www.linkedin.com/in/alastairmoore/
- https://www.linkedin.com/in/walterhernandez/

## Team Website

https://mdrx.tech/team/

## Relevant Experience

The MDRxTech team have participated in hackathons involving responsive smart legal contracts that adapt based on data provided from oracles and stored in IPFS and Ocean Protocol, with notable entries in the Global Legal Hackathon (https://challenge.globallegalhackathon.com/project/5ea96739a463460045ccd9ee) and also winning 3rd place in the innovation category of COVIDathon (https://www.mishcon.com/news/legal-engineering-team-a-winner-at-devposts-covidathon. The team published a paper on their work (http://blockchain.cs.ucl.ac.uk/wp-content/uploads/2020/07/UCLCBT_DiscussionPaper_Q22020_V2.pdf) and continue to actively develop this approach with new data sources and oracles.

The team have previously published their work in a Proof of Concept Real Estate DLT project with the UK Land Registry (HMLR) https://www.mishcon.com/news/hm-land-registry-towards-a-distributed-ledger-of-residential-title-deeds-in-the-uk and also have contributions in two chapters (Oracles and Real estate) of a recent book 'Enabling the Internet of Value - How Blockchain Connects Global Businesses' https://www.springer.com/gp/book/9783030781835.

The MDRxTech team will continue to work closely with the LegalSchema and Accord Project teams to work on the integration and with the Hedera product team.

The team have also previously spoken to Protocol Labs around various legal issues involved in decentralised storage, in particular, with relation to data protection concerns such as GDPR, to ensure the final prototype is compliant by design with the relevant data protection legislation.

## Team code repositories

https://github.com/niallroche/covidhack-oracle-provable
https://github.com/walter-hernandez
https://github.com/latticecut

# Additional Information

The team have a track record in taking on real-world challenges to drive innovation in the DLT and Legal sectors and look forward to making this project a success and a building block for others to leverage to expand the ecosystem.
