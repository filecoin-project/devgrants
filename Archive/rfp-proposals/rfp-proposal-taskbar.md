# RFP Proposal: `P2P task transcript`
**Name of Project:** `P2P task transcript`
 
**Link to RFP:** [Hedera x Filecoin RFP](https://github.com/filecoin-project/devgrants/blob/master/rfps/hedera-and-filecoin.md)
 
**RFP Category:** `devtools-libraries`
 
**Proposer:**  [victorholo](https://github.com/victorholo) on behalf of Taskbar
 
**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes
# Project Description
 
The underlying project proposes the building of a decentralized storage solution that will enable intermediate use of HFS (Hedera File Service) for temporary storage and simple deletion of temporary/intermediate/unnecessary metadata and based on condition, transfer the transcript file into permanence on IPFS with Filecoin - [web3.storage](https://web3.storage/) and include all the metadata into a Hedera smart contract to facilitate auditing.  

The transcript is used for documenting all the Taskbar gig-economy interactions to facilitate permanent, transparent storage reach respective task and reputational system consequences inside the Taskbar decentralized skills ecosystem. The idea behind the project came from observing early user interactions on the Taskbar gig-economy freelancing platform which require the related data to be retained as permanent proof of reputation and/or in the event of a need to trigger a referral to the DAO (Decentralized Autonomous Organization) dispute resolution process.

Using HBARs for payment of native HFS services such as: FileCreate, FileUpdate, FileAppend; the relevant intermediate metadata will be stored iteratively, documenting all interaction and relevant events for the duration of the task’s lifetime (task creating, bidding, acceptance, payment to escrow, duration of task, final completion or dispute resolution, user reputation adjustment), where HFS data would be deleted in the event that the task is not accepted by both parties, canceled or expired. The final contents of the transcript for a completed task would be uploaded to IPFS using Filecoin web3.storage with its associated metadata being stored on Hedera. (Considering an option for including metadata with 2 privacy levels for transcripts, public or confidential)
 
## Value
The project sets the path for a permanent juxtaposition and intertwining of Hedera and Filecoin ecosystems, where more temporary data is stored intermittently on HFS while encouraging permanent storage of data, especially where the data is linked to user reputation, on IPFS.

And additional value for Filecoin & Hedera would represent the application of this use case across the Taskbar gig-economy, freelancing platform which if successfully implements the project’s full utility, stands to increase in notoriety and use, bringing along more utilization for Filecoin & Hedera protocols.

## Deliverables
A working implementation tailored for the Taskbar P2P task transcript.

The functionality described will be open-sourced as JavaScript/TypeScript as a scaffold service that can be integrated separately in other solutions.
 
## Development Roadmap
Overall development time – 2.5 months split across the following milestones:

- ### Milestone 1 (1 weeks) 
    2000$ - pro-rata at 50\$/hr * 40 hrs + 2500$ Taskbar dev team
    - Finalize the requirements and specifications
    - Formulate all parameters of Transcript file along with their metadata
    - SDK hierarchy and initial setup

- ### Milestone 2 (3 weeks)
    6000$ - pro-rata at 50\$/hr * 120hrs  + 7500$ Taskbar dev team + 1000$ frontend
    - SDK – Hedera HFS integration
    - SDK – Integration with Hedera smart contracts
    - SDK - Integration with Filecoin web3.storage for transcript storage
    - Frontend development
 
- ### Milestone 3 (2 weeks) 
    2000$ - pro-rata at 50\$/hr * 40hrs  + 5000$ Taskbar dev team + 2000$ frontend
    - Webapp template UX design
    - SDK testing
    - SDK integration with frontend
    - Define and implement test suite
    - Website integration & backend support

- ### Milestone 4 (2 weeks)
    2000$ - pro-rata at 50\$/hr * 40hrs  + 5000$ Taskbar dev team
    - Application implementation - fully functional interactive UI according to the UX design local environment & associated testnets
    - Staging deployment
 
- ### Milestone 5 (2 weeks) 
    2000$ - pro-rata at 50\$/hr * 40hrs  + 5000$ Taskbar dev team
    - Regression testing
    - Feedback collection, and potential bug fixes
    - Improvements based on feedback
    - Production deployment
 
## Total Budget Requested
42000 USD
 
## Maintenance and Upgrade Plans
Taskbar FZ-LLC commits to the SDK’s and software’s maintenance for the period of 2 years based on dependent Hedera and Filecoin SDK & API modifications, support in enhancing the solution based on demand.
Taskbar will maintain an open feedback stream to facilitate identification of new features. This process will influence our future development.
 
# Team
### Contact Info

[tudor@mytaskbar.com](mailto:tudor@mytaskbar.com)

[hello@mytaskbar.com](mailto:hello@mytaskbar.com)

## Team Members
1. Victor Holotescu - https://github.com/victorholo
2. Iosif Peterfi - https://github.com/iosifpeterfi
3. Vishal Dharmawat - https://github.com/vshall20
4. Alex Taylor
5. Tudor Holotescu
6. Taskbar development team
 
## Team Member LinkedIn Profiles
1. Victor Holotescu - https://www.linkedin.com/in/victor-holotescu/
2. Iosif Peterfi - https://www.linkedin.com/in/iosifpeterfi/
3. Vishal Dharmawat - https://www.linkedin.com/in/vishaldharmawat/
4. Alex Taylor - https://www.linkedin.com/in/alexpaultaylor/
5. Tudor Holotescu - https://www.linkedin.com/in/tudor-holotescu/      
6. Taskbar Development Team
 
## Team Website:
https://www.mytaskbar.com/

## Relevant Experience
Taskbar has compiled a strong team that has been directly involved in multiple Hedera Hashgraph based projects since 2018 and along with the support of the Taskbar development team that has  experience in delivering end-to-end software solutions.

## Team code repositories
Taskbar source code has yet to have been published but below are the account of some of the team members:
 
1. Victor Holotescu - https://github.com/victorholo
2. Iosif Peterfi - https://github.com/iosifpeterfi
3. Vishal Dharmawat - https://github.com/vshall20
 
# Additional Information

Thank you for the review and consideration.

We stand available to clarify any queries or scope enhancement proposals through our contact info or through our official communication channels listed at mytaskbar.com.

Any delta cost for delivering the project will be insourced by Taskbar.
