To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Project Title`

**Name of Project:**

**Proposal Category  `devtools-libraries`

**Proposer:** `flyworker`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?: Yes
# Project Description

In this project we are creating a way using IPFS/Filecoin data as input for runing computing on filecoin networ. Use can submit tasks to the service provider, aske to provide runing the task for them and store the task result on IPFS.

## Value

Filecoin now has over 8EB storage now, it has over 2700 nodes over the world and contains over 4000 high performance server over the world sealing the data. With those rich resource, Filecoin can do more than just storage. The major cloud provider generally give customer computing+storage service. if we want challgen the centralized cloud, then the coumputing part is important.
One way of using miners compute resource is sharing smart contract,and dockerlized the CPU resource on provider machine.client can create contracts and write task info to the smart contracts. The provide and take task from contract and parsing the task. The data needed for calculation is coming from IPFS or FIlecoin if the cid is not valid any more on the network.

## Deliverables
* user creates a smart contract fot the computing task
* Serive provider gets the task from network
* Provide parses the smartcontract and get the ipfs resource id
* if ipfs resource not exist, the provider will retreave the data from filecoin  network.
* With data needed, service provider complete the calclation 
* Task result save on Filecoin
* Task is marked as completed in smart contract

## Development Roadmap

Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section).

For each milestone, please describe:
- The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates)

## Development Roadmap


Milestone 1- completed the calculation on IPFS:  $20,000

* user creates a smart contract fot the computing task
* Serive provider gets the task from network
* Provide parses the smartcontract and get the ipfs resource id
* With data needed, service provider complete the calclation 
* Task result save on Filecoin
* Task is marked as completed in smart contract


Milestone 2 – UI  tool  10,000
* if ipfs resource not exist, the provider will retreave the data from filecoin  network.

## Total Budget Requested

* Milestone 1: $20,000

* Milestone 2: $10,000


Total: $30,000
.

## Maintenance and Upgrade Plans

We have a dedicated team in Montreal with 10 developer team, since this product has very close relationship with the Storage market project Swan we are building we will keep a code upgrade at weekly bases. Future upgrade can be add S3 compatible file importer service, enhancement of key management, connect to swan project. Etc. 

# Team

## Team Members

- Charles Cao
- Boqian Wang

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/charles-cao-09a79526/

- https://www.linkedin.com/in/boqian-wang-6b0955171/

## Team Website

https://filswan.com

## Relevant Experience

Please describe (in words) your team's relevant experience, and why you think you are the right team to build this project. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc.

We - NBFS Canada participated in SR1, SR2, and cooperation with starling and pinata project. In slingshot 2 we processed over 10,000 deals and over 500 offline deals, talked to 100 miners and actively working data transfer service between Asia and North American users.
Prior to working on Filecoin project, we were working on a decentrilized AI computing platform which using smart contract for data/task transmission to different AI workers, we have in hand experience of handling encryption and data pipeline.

We build the following product

- https://nbai.io GPU cloud computing 
- https://nbfspool.com One of the largest Filecoin mining node in North America
- Https://swan.nbfspool.com A storage market for price decovering and offline trasfer

The team get the following reward and honor.

- The Natural Science and Engineering Research Council of Canada (NSERC) special fund supports research on the direction of video coding.
- Canadian government high-tech research and development grant
- Natural Science Foundation of Canada (NSERC) Blockchain to AI Cloud Computing Research Grant
- Canadian Information Technology and Integrated Systems Mathematical Organization (Mitacs) AI medical identification project grants
- Canadian tax support for scientific research and experimental development
- Quebec e-commerce innovation enterprise support
- CENGN (Canadian Center of Excellence for Next Generation Networks) Research Support Project
- Canadian D3 incubator Hosted Startup support
- Microsoft Entrepreneurship Support Program (BizSpark) Support
- HP Enterprise Supplier Partner, Dell Enterprise Supplier Partner, ASUS Enterprise Service Partner, Amazon Enterprise Partner, NVIDIA Canadian Cloud Computing Supplier


Charles Cao, Founder of Filecoin node NBFS Canada, CEO of Nebule AI inc, previous working for IBM, Autodesk, Exepida and Paysafe. NBFS Canada is working on building an edge cloud computing platform (Project Swan) integrated with Filecoin decentralized storage solution. Project Swan integrates computing, online/offline deal management and storage price discovering in one platform to bring enterprise applications closer to where the data located.

## Team code repositories

https://github.com/nebulaai

# Additional Information

Fronter accelerator participants
