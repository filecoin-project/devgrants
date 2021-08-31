# Open Grant Proposal: Discovery

**Name of Project:** Discovery

**Proposal Category:** Community

**Proposer:** Cali93

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Getting started in Web3 is hard, because the information is:

- Scattered
- Inaccurrate or not trustworthy
- Censorable

Discovery is a gamified & community driven learning platform that onboards users and developers into Web3.

In order to provide high-quality courses built around open source, trustable and verifiable content,
members of the Web3 projects will collaborate with community experts in various fields such as:

- content creation and research
- development, infrastructure and security

## Value

Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:

- What are the benefits to getting this right?

This would help onboard thousands, if not millions of users and developers into Web3.

All the projects using our Gitbook Github Action would automatically have a change history and a back-up of their docs available in different sources (NFT.storage, Web3.storage) and it would incentivize people to contribute and maintain the documentation.

- What are the risks if you don't get it right?

We would need to do a retrospective on what was wrong, analyze why and come with a decent solution in order to make it right.

- What are the risks that will make executing on this project difficult?

If we had to build the whole infrastructure to achieve what we want it could have been a challenge but as NFT.storage & Web3.storage were released recently we're going to use those great libraries.

## Deliverables

Please describe in details what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished.

- A dApp which allows users to join Discovery, create a project, and upload images for future NFT minting processes.
Any user will be able to link their Github Account to a did.
Project owners will be able to link Gitbook courses to their project.
Contributors will be able to create new courses and quests in addition to update existing content
Learners will be able to browse courses by project or theme and they will be able to mint an NFT once they've successfully completed a quest.
- A Github action, that will upload content of all kinds from a repo (videos, markdown files, images, text, mp4 et al) to web3.storage.
- The metadata from the action, such as the authors, lines of codes/diffs, commitID, reviewers will be stored in NFT.storage and we will pair this with an image selected from prior uploaded images, and then store these on NFT.storage and use the returned URI for our ERC-721 minted token.
- Utilizing off-chain oracles to guarantee the integrity of the minting process, including the security of the NFT image URI and token URI.

## Development Roadmap

Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section).

For each milestone, please describe:

- The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates)

## Milestones

### Milestone 1

We will create a pleasant user interface, which will allow for users to join the Discovery Web dApp. The user will be able to create new "projects" which will entail creating and uploading data to Gitbook. We will create and test a Github Action that can be plugged in any repo (Gitbook or code), which will automatically upload the files of the repo to FileCoin and IPFS through web3.storage.
In addition to the files of the repo, we will have the creator of the project upload images which will be ranked according to rarity. These images will be uploaded to web3.storage and using web3.js on chain we will store in a mapping with the image CIDs linked to the rarity and project name and emit an event of the storage.

- Giovanni - UI/UX Designer and Front-End Developer (Figma/next.js/chakra-ui)
- Cali - Full Stack Developer (Github action/web3.storage/nft.storage)
- Jameson - Backend/Solidity Developer (web3.js/Smart Contracts)

Completed By : October 1st, 2021

Budgetary Needs:
3x $4500/month developer salary = $13,500

### Milestone 2

We will begin to implement and extend the multiple smart contracts needed for our project flow. A Project Factory smart contract will control the access, approvers, and minting of NFTs. This contract will inherit from ERC-721, and will keep track of pending eligible addresses for future minting. We will use Identity-Link Services built on top of IDX and Ceramic (Ceramic and IDX are built on top of IPFS) to link the github account to an ethereum address(es) and DID through the user profile page. Seperately a Course Factory smart contract for contributors to established projects will be created. Within this contract, the Chainlink VRF will be used to add randomness to the minting of the NFT. We will also build a chainlink external adapter which will pass the metadata and the chosen image from the mapping to NFT.storage and return the URI from Nft.storage to the smart contract.

- Giovanni - UI/UX Designer and Front-End Developer (Figma/next.js/chakra-ui)
- Cali - Full Stack Developer (Ceramic/IDX/web3.storage/nft.storage)
- Jameson - Backend/Solidity Developer (Chainlink VRF/Chainlink EA/Smart Contracts)

Completed By : December 1st, 2021

Budgetary Needs:
This milestone will last two months
3x $4500/month developer salary = $13,500/month
Total = $13,500 x 2 = $27,000

### Milestone 3

We will build subgraph that will track the metadata of the project and course NFTs. This will serve as a project registry and will also store the details of the projects. Our front-end will use the nft.storage URIs to display the details about the projects and courses. We will build a smart contract for the quests that users will complete within the courses. The UI will be built for presenting these quests. The smart contract will call a Chainlink External Adapter which will check the ceramic streamID for proof that user completed quest and will also pass metadata to NFT.storage and return URI to contract. This will also utilize the Chainlink VRF contract for randomness according to pre-set thresholds within the smart contract.

- Giovanni - UI/UX Designer and Front-End Developer (Figma/next.js/chakra-ui)
- Cali - Full Stack Developer (Ceramic/IDX/web3.storage/nft.storage/subgraphs)
- Jameson - Backend/Solidity Developer (Chainlink VRF/Chainlink EA/Smart Contracts)

Completed By : February 1st, 2022

Budgetary Needs:
This milestone will last two months
3x $4500/month developer salary = $13,500/month
Total = $13,500 x 2 = $27,000

## Total Budget Requested

Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds.

Total = $67,500
This total is for 3 developers' salaries working full time over a 5 month period.

## Maintenance and Upgrade Plans

Specify your team's long-term plans to maintain this software and upgrade it over time.

Our team will update any library that we use on a continual basis. We will provide maintenance for the overall availability and security of the dApp. This will include bug fixes, monitoring, upgrades to major versions of tools such as Chainlink v2, new web3.storage releases, et al. We will also always be looking for ways to enhance our existing features.

# Team

## Team Members

- Cali "Huxwell" - Brussels, Belgium, Europe

  Software Engineer with a devSecOps mindset.
  [https://www.linkedin.com/in/cali-armut/](https://www.linkedin.com/in/cali-armut/)
- Jamie "JPick713" - Florida, USA

  Solidity & Back-end Developer with a mechanical engineering background.
  [https://www.linkedin.com/in/jameson-pickett-889b42162/](https://www.linkedin.com/in/jameson-pickett-889b42162/)
- Giovani "NoName" - Italy, Europe

  Front-end developer and UI/UX designer
  [https://www.linkedin.com/in/giovannifulin/](https://www.linkedin.com/in/giovannifulin/)

## Team Website

We're currently building our website but you can take a look at this page meanwhile
[https://showcase.ethglobal.co/hackfs2021/discovery](https://showcase.ethglobal.co/hackfs2021/discovery)

## Relevant Experience

Please describe (in words) your team's relevant experience, and why you think you are the right team to build this project. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc.

- **Jamie** has multiple years experience within data analysis and web2.0 programming, particularly within python and JS. He has been working with Solidity and web3 with hackathons including multiple winning submissions on gitcoin and HackFS, and really loves the possibilities Filecoin, IPFS, web3.storage, and nft.storage provide to take web3 dApp development to the next level
- **Giovanni** is passionate about new technologies and has working experiences with software development from freelancing and as an engineer for a software house. 
During the past years, he won several hackathons and Startup competitions in Italy.

    ### Skills:

    - **UI Design:** (Figma), No-code tools(Webflow, Bubble)
    - **Front-End:** (NextJS, Chakra-UI), Back-End(NodeJS, GraphQL, REST API)
    - **Web3:** (Hardhat, ethers, solidity)
- **Cali** has 4 years of professional experience in full stack development and his hobbies are primarily around learning security, devops/infrastructure and sharing knowledge.
His side projects were primarily focused on education so he though that expending on Gitcoin quests by combining it with open source & decentralized content could be a nice hack.
That’s why we've been working on Discovery for 2 hackathons in a row (3 weeks each with a lot of research and brainstorm in between, not to mention that we've started from scratch for each hackathon)

    ### Skills:

    - **Front-end** : HTML, CSS/SASS/JSS, JS, TS, React, NextJS, emotion & styled-components, State management libraries, Apollo
    - **Back-end** : NodeJS, NoSQL/SQL, REST APIs, GraphQL, Serverless Framework, NestJS, TypeORM, Sequelize, Mongoose, PostgreSQL
    - **Web 3**: Hardhat, Web3.js, Ceramic, IDX, Solidity, ipfs-js, Web3.storage, NFT.storage, Chainlink & Subgraph development basics
    - **DevOps**: AWS EC2/Lambda/S3/RDS, GCP, Terraform, GitLab CI, Docker

## Team code repositories

[https://github.com/Discovery-Labs/knowsis/tree/main/src/services](https://github.com/Discovery-Labs/knowsis/tree/main/src/services)
[https://github.com/Discovery-Labs/Discovery](https://github.com/Discovery-Labs/Discovery)

Please provide links to your team's prior code repos for similar or related projects.

[https://github.com/jpick713/Web3StorageNFTTest](https://github.com/jpick713/Web3StorageNFTTest)
[https://github.com/Cali93/discovery-hack-money-2021](https://github.com/Cali93/discovery-hack-money-2021)

# Additional Information

Please include any additional information that you think would be useful in helping us to evaluate your proposal.

[HackFS 2021 Finalists - Live Demo](https://www.youtube.com/watch?v=UGJA6eahQBg)
