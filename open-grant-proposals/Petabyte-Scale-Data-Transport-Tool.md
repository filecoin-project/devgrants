To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Petabyte-Scale Data Transport Tool`

**Name of Project:**

**Proposal Category:**  `app-dev` 

**Proposer:** `flyworker`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** 
Yes

# Project Description

Please describe exactly what you are planning to build. Make sure to include the following:
- Start with the need or problem you are trying to solve with this project.
- Describe why your solution is going to adequately solve this problem.

This section should be 2-3 paragraphs long.

According to document https://docs.filecoin.io/store/lotus/very-large-files the offline deal sealing process performed a very important role for clients transfer files large than 1TB. 

However, the current way how client send create and send deals are very complicated, clients need to type lots of commands and do lots of calculation. There are no standard process/tools for how the export/import data worker, it also lacks validation and failure/error handling. The client data is not encrypted during the export and import.

In order to commercialize the edge storage market as AWS snowball, we are going to build an integrated tool to automate the packaging process while provide more validation, error handling and analysis service. 

In order to solve the problem, we will provide two tools in one software kit, client exporter and miner importer. The client exporter provides a command line interface to provider choices like, generate card file with specific size, batch proposal with selected miners, deal status checking panel. Encryption with AES and asymmetric encryption tools will also provide.

Miners tool provides scheduling import to his node according to his sealing capability for achieve the maximum importing speed. If the car files are transferred from web server, miners build a pipeline from downloading to sealing. When import failed, miners can easily click reset button on a web UI to restart the import process. Decryption tool is also part of the tool set.

Ideally the export and import service should be a fully automatically process with minimal human interaction. It can be packaged as a commercial tool for Petabyte-scale data transport.


## Value

Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:
- What are the benefits to getting this right?
- What are the risks if you don't get it right?
- What are the risks that will make executing on this project difficult?

This section should be 1-3 paragraphs long.

Once the solution is built, the tool can be used in several scenarios.
-	Slingshot users: It can reduce the effort slingshot participants for packaging data and sending deals, so they can focus on data analyse
-	Filecoin plus: Notaries and clients need a tool securely transfer large data set for review
-	Enterprise user: for enterprise user who want to save data to Filecoin node, they need data encryption to make sure they fit the compliance during the data transmission, import/export process.
If we do not have this tool in place, it will delay the entire ecosystem to get big enterprise data owner involved, it will also raise concerns in privacy protection law like GDPR.

We as the developer have risk in the implementation of the data encryption, some code maybe required auditing before deliver to enterprise user.

## Deliverables

Please describe in detail what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished.

The software suit has two components: Client-side tools and server-side tools

On client side: 
User can download the curated dataset using integrated downloading tool, it provides 
-	A pragmatical way of defining input/output directory
-	Batch split big files to small files
-	MD5 file generation
-	File uploading transfer server
-	Merge small files to big file.
-	Database for persistent sending history.
-	Automatically generate car file
-	Local miners reachable
-	Price list of miners
-	One key generates car file 
-	Batch send deals to multiple miners
-	AWS/asymmetric tool
-	Generated CSV for sending to miners, CSV for users. 
-	Dashboard of reporting of daily usage, average price spent, average sealing time, highest success miners, past deals. 

Miner side: 
-	Dashboard of accepted deals
-	Current deal status. 
-	Md5 validation
-	File downloading manager for retry and transmission resume
-	AWS/asymmetric decryption tool
-	Deal Log tracking tool
-	Auto import car file from directory with CSV provide by client.
-	Csv exported for analyse.


## Development Roadmap

Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project but aim for around 2 pages for this section).

For each milestone, please describe:
- The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates)

Milestone 1- Slingshot tool  $20,000
Client side 

-	A pragmatical way of defining input/output directory 
-	Batch split big files to small files
-	MD5 file generation
-	Merge small files to big file.
-	Automatically generate car file
-	Local miners reachable
-	Price list of miners
-	One key generates car file 
-	Batch send deals to multiple miners
-	Generated CSV for sending to miners, CSV for users. 

Miner side: 
-	Dashboard of accepted deals status
-	Current deal status. 
-	Md5 validation
-	File downloading manager for retry and transmission resume
-	Auto import car file from directory with CSV provide by client.
-	Csv exported for analyse.


Milestone 2 – Filecoin Plus tool  10,000

Client side
-	File uploading transfer server
-	Database for persistent sending history.
-	AWS/asymmetric tool
-	Dashboard of reporting of daily usage, average price spent, average sealing time, highest success miners, past deals. 

Miner side: 
-	AWS/asymmetric decryption tool
-	Local file index for review
-	Database for persistent processing history.
-	Dashboard of deal status success rate and log tracking tool


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
- Fei Yan
- Boqian Wang

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/charles-cao-09a79526/
-  https://www.linkedin.com/in/feiya200/

- https://www.linkedin.com/in/boqian-wang-6b0955171/

## Team Website

https://swan.nbfspool.com

## Relevant Experience

Please describe (in words) your team's relevant experience, and why you think you are the right team to build this project. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc.

We - NBFS Canada participated in SR1, SR2, and cooperation with starling and pinata project. In slingshot 2 we processed over 5000 deals and over 1000 offline deals, talked to 100 miners and actively working data transfer service between Asia and North American users.
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
