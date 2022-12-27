# Open Grant Proposal: `Treehouse`

**Name of Project:**

**Proposal Category:** Choose one of `app-dev`

**Proposer:** `jacobleegithub`

**(Optional) Technical Sponsor:** `Sonia`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT, GPL, and APACHE2 licenses?:** "Yes"

# Project Description

## Introduction of Treehouse

Treehouse is a convenient and secure online photo album app for baby journeys. Parents can store the baby's daily life with precious living experience in the family's own Web3 world.

Traditional online photo album services are operated by a single platform company, all album content is under the management of the platform operator. Web3 is de-platformed and uses distributed storage technology. These storage spaces are provided by storage space providers around the world as marketplace There is no storage operator that can access your secure album content, ensuring user’s privacy and security.

## Market Problems

The existing Google Photos and Apple Photos are not designed for children. Currently, the baby journey photo album platform with the highest market share in Asia is operated by China based companies and used by tens of millions of people and more.

After analyzing photos and journey diaries of young children, we can understand the health status, life pattern and geographical distribution of young children, as well as family members and their composition, family background, nannies or schools, teachers and other networks. Platform operators are seriously affecting personal privacy, the most worrying of these is most users are unaware of this.
Solutions

## Distributed Storage

Treehouse uses Web3 content storage technology to ensure the account owner(photo uploader) and authorized family members are the only one who can view the content of the album files. The storage space of the album files is controlled by the user themself. Through the file encryption technology, no company or organization can access content without being authorized by the user. If the Treehouse operator cannot continue the service due to some situations, it will not impact user content or damage the user's content retrieval.

## Security & Privacy Protection

Treehouse uses a Public-key cryptography, or asymmetric cryptography service to protect the user's content, and only the user can decrypt the data. Suppose you want to upload your own photo album to Treehouse, the upload tool will help you to perform the AES-256 encryption process when saving the photo file, so the uploaded file is actually encrypted, and only users are able to retrieve and decrypt files. AES-256 is an encryption standard widely used in industry, finance and military. Treehouse does not host the user's password, so there is no possibility of any password leakage.

When you share photos with family members, the system uses p2p encryption to individually transmit the shared decryption key, and does not disclose the user's public key information to avoid the risk of quantum computers doing brute force cracking.
Persistence of file storage

Completely different from platform operators, Treehouse uses Web3 storage technology - IPFS, and these storage spaces are provided by operators of the IPFS protocol all around the world. These services cannot be closed, if the Treehouse App is out of service for some reason, you can still retrieve the album yourself through IPFS protocol.

## Treehouse Technology Overview

The Treehouse service is composed of three major elements.
The first is DID - identity, which creates a representation of users. The second is an integrated API service, which includes internal cloud service for applications and blockchain with decentralized storage service for users.

## Treehouse software stack

![treehouse_software_stack](https://user-images.githubusercontent.com/14127551/209586900-6e045740-ce71-418c-aa96-5ea4cb744f11.png)

## Treehouse architecture

![treehouse_architecture](https://user-images.githubusercontent.com/14127551/209587164-108a1f1d-d5ae-485f-aa8c-90dd04e1fadc.png)


## Value

Increased security: Provide greater security for users owned photos compared to traditional centralized storage solutions.

Lower costs: Because Filecoin utilizes a decentralized network of storage providers, it can often offer lower storage costs compared to centralized solutions. This could make it more cost-effective for users to store their photos on Filecoin.

<!-- - What are the risks that will make executing on this project difficult? -->

Performance: Decentrolized storage performance may not be as good as some centralized solutions. This could make it challenging to provide a user experience that is fast and reliable enough for a photo storage app.

Complexity: Building an app on top of a decentralized storage protocol like Filecoin can be complex, this could make it difficult to find and hire the necessary talent to execute on the project. The integrated third party API like web3 storage can be options.

User adoption: Finally, there is a risk that users may not be interested in using a decentralized photo storage app, or may not understand how it works. This could make it difficult to gain traction and achieve widespread adoption for the app.

<!-- This section should be 1-3 paragraphs long. -->

## Deliverables

<!-- Please describe in details what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished. -->

## Treehouse Apps on iOS store and Android play store 

## Treehouse App Features

Secure key online photo/video album
Use AES-256 encryption technology to ensure privacy and security. All uploaded photos and videos are protected by encryption technology.

Photo/video file management
Original image quality storage, extending the space of mobile phone albums to the unlimited cloud.

Add family members account
Add sub account and share photo with family members

Baby diary
Combine photo and diary functions to keep every precious moment

Reminder cards
Write down what you have to do, automatically remind you, and use points to keep progress

Make photos or blessing into NFTs
Easy to mint your own NFT in every special moments, and give it to family or friends


## Development Roadmap

<!-- Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section). -->

<!-- For each milestone, please describe: -->
<!-- - The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables. -->
<!-- - How many people will be working on each milestone and their roles -->
<!-- - The amount of funding required for each milestone -->
<!-- - How much time this milestone will take to achieve (using real dates) -->

## Milestone 1 Treehouse Prototyping
Estimated Duration: 2 month
UX/Product Designer x 1, UI/ART Designer x 1
Costs: 8,000 USD

Item of Deliverable

01 Treehouse app wireframe (Design Document)
02 Treehouse app use cases sequence diagram (Design Document)
03 Treehouse functional requirements Document (Design Document)

## Milestone 2 Wallet & NFT
Estimated Duration: 2 month
FullTimeEngineer x 2, QA/QC x 1, UX/Product Designer x 1
Costs: 16,000 USD

Item of Deliverable

01 User wallet module
 - Generate user wallet
 - Receive tokens
 - Query transactions
 - Send tokens

02 NFT mining module
 - Select type of NFT to mint
 - Mint NFT
 - Select users who can receive NFT
 - Generate secret code for receive NFT

03 Test guide
 - Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests.
Document

## Milestone 3 API & Security & Photo
Estimated Duration: 2 month
FullTimeEngineer x 3, QA/QC x 1, UX/Product Designer x 1
Costs: 20,000 USD

Item of Deliverable

01 API Document
02 API Service
03 Security module
 - Generate User ID on web client
 - Add family members on web client
 - Encrypted photo files and upload to ipfs storage
 - Retrieve encrypted photo files from ipfs storage
 - Photo file decryption
 - Encrypted Photo files sharing with family members
 - Family members view shared photo
04 Photo module
 - Add photos/videos
 - Add albums
 - List albums
 - Delete albums
 - Query photos/videos
 - Delete photos/videos
 - Browsing photo/videos
05 Test guide
 - Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests.

## Milestone 4 Treehouse Diary & Reminders modules
Estimated Duration: 2 month
FullTimeEngineer x 2, QA/QC x 1, UX/Product Designer x 1
Costs: 16,000 USD

Item of Deliverable

01 Diary module
 - Add records
 - Query records
 - Modify records
 - Delete records
 - Security module integration
02 Reminder cards module
 - Add reminder card
 - Query reminder cards
 - Add point to cards
 - Delete card of point
 - Delete reminder card
 - Security module integration
03 Test guide
 - Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests.


## Total Budget Requested

<!--Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds. -->

Total requested budget across all milestones: 60,000 USD
Our budget is entirely made up of salary and labor costs, with no additional expenses

## Maintenance and Upgrade Plans

<!-- Specify your team's long-term plans to maintain this software and upgrade it over time. -->

Treehouse charges account users subscription fee and baby goods suppliers account sponsors to support business in the long term.

1. Business model to support long-term plan & maintainess
 - Storage space subscription fee per account. According to market surveys to online photo album storage service providers, parents are willing to pay for the online storage space of a baby photo album, it’s around US$30 to US$60 annual fee.
 - NFT Mining fee. Treehouse charges NFT mining fees to users to support business

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
