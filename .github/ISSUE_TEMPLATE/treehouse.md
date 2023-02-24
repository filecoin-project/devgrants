# Open Grant Proposal: `Treehouse`

**Name of Project: Treehouse**

**Proposal Category:** Choose one of `app-dev`

**Proposer:** `jacobleegithub`

**(Optional) Technical Sponsor:** `Sonia`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT, GPL, and APACHE2 licenses?:** "Yes"

# Project Description

## Introduction of Treehouse

Treehouse is the ultimate all-in-one online photo album app designed for modern families. Treehouse app seamlessly combines advanced features like milestone tracking and secure family member sharing with the latest technologies like NFTs and Filecoin storage - all within a convenient and private Web3 world.

As a unique addition, Treehouse now also offers a dynamic Learning Diary function that allows parents, teachers, and students to connect, learn, and track progress in real time. In the Learning Diary, students receive learning hours certificates from their teachers, share photo and video works, and view progress with parents. This feature is perfect for developing new skills and documenting academic portfolios in a safe and secure way.

We believe that preserving your family's memories should be both simple and secure, which is why our app is portable and allows for easy batch photo and video backups, all while saving valuable mobile device storage space.

Join the Treehouse community today and experience the future of online photo album apps - an elegant and streamlined way to document your family's journey.

## Market Problems

Limited options for baby photo album apps. While there are many photo album apps on the market, it is designed for children and their unique needs.

Privacy concerns with centralized platforms. Current market leaders in Asia and other regions are operated by centralized platforms, leaving user data vulnerable to exploitation.

Limited storage on portable devices. The demand for photo and video storage is high, and limited storage on mobile devices can quickly become an issue for families trying to document their child's journey.

## Solutions

### Filecoin Storage

Treehouse uses filecoin decentralized storage technology to ensure the account owner(photo uploader) and authorized family members are the only one who can view the content of the album files. The storage space of the album files is controlled by the user themself. Through the file encryption technology, no company or organization can access content without being authorized by the user. If the Treehouse operator cannot continue the service due to some situations, it will not impact user content or damage the user's content retrieval.

### Security & Privacy Protection
Treehouse uses public-key cryptography with asymmetric encryption to protect user content. When a user uploads a photo album to Treehouse, the upload tool will perform the AES-256 encryption process to encrypt the photo files, ensuring that the uploaded file is encrypted and only the user is able to retrieve and decrypt the files.

When sharing photos with family members, Treehouse uses Elliptic Curve Integrated Encryption Scheme (ECIES) encryption to individually transmit the shared decryption key of AES-256, and does not disclose the user's public key information to avoid the risk of brute force cracking. This ensures that only the intended recipients are able to view the shared photos.

## Treehouse Technology Overview

Treehouse is a secure and privacy-focused online photo album app with learning diary for modern families that combines advanced features like milestone tracking and learning portfolio with the latest technologies such as Filecoin storage & Dapps. The app uses Flutter framework for the frontend, Rust for the backend, and smart contracts to manage NFT creation and learning hours certificate. The system utilizes AES-256 ECM encryption technology and public-key cryptography with asymmetric encryption to ensure the security and privacy of user data.

## Treehouse software stack
![treehouse_software_stack](https://user-images.githubusercontent.com/14127551/221176851-6cfddf43-29d9-449d-a66a-e78b724b7a82.png)


## Treehouse architecture
![treeHouse_architecture](https://user-images.githubusercontent.com/14127551/221176890-740fde87-a711-4064-a5ac-867986a9d9d3.png)


## Value

The value of Treehouse lies in its ability to help parents, teachers, and students capture and preserve the precious moments of a child's journey in a secure and private way. It allows users to create a comprehensive learning diary that tracks a child's academic progress and provides a safe platform for parents and teachers to connect and collaborate.

By using advanced encryption technology and Filecoin storage, Treehouse ensures that user data is kept private and secure. This provides peace of mind for parents and helps build trust in a world where data breaches and privacy violations are becoming increasingly common.

In addition to the practical benefits, Treehouse also provides a meaningful way for families to celebrate and share special moments through the creation of NFTs. This feature allows users to easily mint their own NFTs to commemorate important milestones in a child's life, creating a unique and lasting digital memory.

The social impact of Treehouse is significant, as it helps promote and support a culture of lifelong learning. By making it easy to document and track progress, parents and educators can better understand a child's learning journey, identify areas of improvement, and celebrate their achievements. This has the potential to positively impact a child's academic success and overall well-being, helping to build a brighter future for generations to come..

<!-- - What are the risks that will make executing on this project difficult? -->

Performance: Decentrolized storage performance may not be as good as some centralized solutions. This could make it challenging to provide a user experience that is fast and reliable enough for a photo storage app.

Complexity: Building an app on top of a decentralized storage protocol like Filecoin can be complex, this could make it difficult to find and hire the necessary talent to execute on the project. The integrated third party API like web3 storage can be options.

User adoption: Finally, there is a risk that users may not be interested in using a decentralized photo storage app, or may not understand how it works. This could make it difficult to gain traction and achieve widespread adoption for the app.

<!-- This section should be 1-3 paragraphs long. -->

## Deliverables

<!-- Please describe in details what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished. -->

## Treehouse Apps on iOS store and Android play store 

## Treehouse App Features

- Secure Online Album
Protect your family's memories with AES-256 ECM encryption technology, ensuring your photos and videos are always kept private and secure.

- Batch Management
Store your original quality photos and videos in unlimited filecoin storage, extending the storage space of your mobile device.

- Easy Family Sharing
Easily share your photos with family members by adding sub-accounts and assigning photo permissions.

- Learning Diary
Combine photo and diary functions to create a comprehensive learning diary that captures every precious moment and records progress.

- NFT Creation
Easily mint your own NFTs to commemorate special moments, making it easy to share and cherish those memories with family and friends.

## Development Roadmap

<!-- Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section). -->

<!-- For each milestone, please describe: -->
<!-- - The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables. -->
<!-- - How many people will be working on each milestone and their roles -->
<!-- - The amount of funding required for each milestone -->
<!-- - How much time this milestone will take to achieve (using real dates) -->

## Milestone 1 - Treehouse Prototyping & Photo/Video Batch Management
Estimated Duration: 2 month
FTE x 4
- UX/Product Designer x 1
- UI/ART Designer x 1
- Flutters Engineer x 1
- System Engineer x 1
Costs: 16,000 USD
Item of Deliverable

|Item|Deliverable                            |Specification                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |Verification                     |
|----|---------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------|
|1   |License                                |Apache 2.0 / MIT / Unlicense                                                                                                                                                                                                                                                                                                                                                                                                                                                              |Statement                        |
|2   |Design document                        |We will provide UI Wireframe and a basic tutorial that explains how a user can play, which will show how the functionality works.                                                                                                                                                                                                                                                                                                                                                         |Document                         |
|3   |Functional Requirements with Test guide|Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests.                                                                                                                                                                                                                                                                                                                           |Document                         |
|4   |Docker                                 |We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone.                                                                                                                                                                                                                                                                                                                                                                             |Docker                           |
|5   |Photo/Video Batch Management module    |This milestone will focus on implementing the batch management feature for photo and video upload/download. The deliverables for this milestone include:  Frontend development with Flutter Framework:  Implement a batch upload/download feature in the Treehouse app to allow users to upload/download multiple photos and videos simultaneously.   Backend API Service:  Develop the backend API service using Java(or Rust) programming language to handle batch uploads and download.|Proof of design on android or ios|


## Milestone 2 Secure data sharing
Estimated Duration: 2 month
FTE x 5
- UX/Product Designer x 1
- QA/QC x 1
- Flutters Engineer x 1
- System Engineer x 2

Costs: 24,000 USD

Item of Deliverable

|Item|Deliverable                            |Specification                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |Verification                     |
|----|---------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------|
|1   |License                                |Apache 2.0 / MIT / Unlicense                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |Statement                        |
|2   |Functional Requirements with Test guide|Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |Document                         |
|3   |Docker                                 |We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |Docker                           |
|4   |Photo management module                |Implementing the photo album management, include:  Frontend development with Flutter Framework: Add photos/videos  - Add albums - List albums - Delete albums - Query photos/videos - Delete photos/videos - Browsing photo/videos                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |Proof of design on android or ios|
|5   |Secure photo sharing module            |Implementing the easy family sharing feature, allowing users to easily share their photos with family members. <br></brThe>The deliverables for this milestone include:<br>  Frontend development with Flutter Framework:<br>  - Implement a family sharing feature in the Treehouse app, allowing users to add sub-accounts and assign photo permissions to specific family members. <br> - Develop the UI and UX of the family sharing feature to be intuitive and user-friendly. <br> - Implement Elliptic Curve Integrated Encryption Scheme (ECIES) encryption technology to ensure secure and private transmission of shared photos. <br>  Backend API Service: <br> - Develop the backend API service using Java programming language to handle family sharing requests. <br> Smart Contract: <br> - Develop a smart contract using Solidity to handle family sharing requests.<br>  - Implement smart contract functionality to verify user identity and provide access to sharing privileges.|Proof of design on android or ios|



## Milestone 3 Learning Diary
Estimated Duration: 2 month
FTE x 5
- UX/Product Designer x 1
- QA/QC x 1
- Flutters Engineer x 1
- System Engineer x 1

Costs: 16,000 USD

|Item|Deliverable          |Specification                                                                                                                                                                                                                                                                                                                          |Verification                     |
|----|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------|
|1   |License              |Apache 2.0 / MIT / Unlicense                                                                                                                                                                                                                                                                                                           |Statement                        |
|2   |Test guide           |Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests.                                                                                                                                                                                      |Document                         |
|3   |Docker               |We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone.                                                                                                                                                                                                                          |Docker                           |
|4   |Learning Diary Module|Frontend:<br>  Allow users to create learning cards, tagging photos, videos, and inviting Issuers to issue hours certificates.<br>   Dapps: <br> We will implement a smart contract for users to create learning cards and receive certificate hours from Issuers.<br>   Frontend developed by Flutter framework. Smart contract developed by Solidity.|Proof of design on android or ios|



## Milestone 4 Precious moment with NFT
Estimated Duration: 2 month
FTE x 4
- UX/Product Designer x 1
- QA/QC x 1
- Flutters Engineer x 1
- System Engineer x 1

Costs: 16,000 USD

Item of Deliverable

|Item|Deliverable               |Specification                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |Verification                     |
|----|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------|
|1   |License                   |Apache 2.0 / MIT / Unlicense                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |Statement                        |
|2   |Test guide                |Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |Document                         |
|3   |Docker                    |We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |Docker                           |
|4   |Precious moment NFT Module|Frontend development with Flutter Framework:  Implement the NFT Creation feature in the Treehouse app, allowing users to easily mint their own NFTs.   Backend API Service:  Develop the backend API service using Java programming language to handle the NFT Creation feature.    Implement a storage system that can store NFTs using Filecoin technology.   Implement file encryption using AES-256 ECM encryption technology to ensure user privacy and security.   Smart Contract:  Develop a smart contract using Solidity to handle NFT minting requests. Implement smart contract functionality to verify user identity and provide access to the NFT Creation feature.|Proof of design on android or ios|



## Total Budget Requested

<!--Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds. -->

Total requested budget across all milestones: 72,000 USD
Our budget is entirely made up of salary and labor costs, with no additional expenses

## Maintenance and Upgrade Plans

<!-- Specify your team's long-term plans to maintain this software and upgrade it over time. -->

Treehouse charges account users subscription fee and baby goods suppliers account sponsors to support business in the long term.

1. Business model to support long-term plan & maintainess
 - Storage space subscription fee per account. According to market surveys to online photo album storage service providers, parents are willing to pay for the online storage space of a baby photo album, it’s around US$30 to US$60 annual fee.
 - Subscription model that includes access to different levels of features, including the learning diary and NFT creation.

2. Promotion Strategy
 - Treehouse will be corporate with baby goods suppliers and care service providers to maximize market penetration. Develop with a local agency, referral program with community.


# Team

## Team Members

Jacob Lee, Project Team Lead 
Brady Liu, Project Tech Lead

## Team Member LinkedIn Profiles

<!-- - Team Member 1 LinkedIn profile -->
https://www.linkedin.com/in/jacob-lee-aa435916/
<!-- - Team Member 2 LinkedIn profile -->
https://www.linkedin.com/in/brady-liu-734a27106/
<!-- - Team Member 3 LinkedIn profile -->
<!-- - ...

## Team Website

<!-- Please link to your team's website here (make sure it's `https`) -->
https://trpma.org.tw/eng

Note: TRPMA team will be major project team of Treehouse.

## Relevant Experience

<!-- Please describe (in words) your team's relevant experience, and why you think you are the right team to build this project. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc. -->

Team's experience

The team has been working on blockchain applications since 2014, we have done many projects from digital identity, defi to healthcare related industry projects and government projects.

Project records reference:

2017 phrOS (Personal Health Records Operating System) reference report
https://www.ledgerinsights.com/blockchain-health-records-taiwan/
https://medium.com/dtco/blockchain-enabled-personal-health-record-os-challenges-opportunities-in-health-care-55161e3a5a32
Forum Video Clips
https://www.youtube.com/watch?v=Uheah_33qd8

## Team code repositories

<!-- Please provide links to your team's prior code repos for similar or related projects. -->

All prior project code can be verified on gitlab. Treehouse will be on github.

# Additional Information

<!-- Please include any additional information that you think would be useful in helping us to evaluate your proposal. -->

## Future consideration

Filecoin Virtual Machine (FVM) Perpetual storage integration.
Automate renewal of photo storage deals in perpetuity, without having to run infrastructure to manage repair or renewal of deals.

