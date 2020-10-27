# RFP Proposal: `Filecoin video archiver`

**Name of Project:** Filecoin video archiver

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-5-rfps.md

**RFP Category:** `app-dev`

**Proposer:** `mitchellpkt`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `yes`

## Project description:

This project’s is a webapp that will allow users to upload their videos easily to Filecoin. The target audience is Youtube content creators and other videographers, to assist with the challenges and costs of storing hours of raw footage in different codecs and resolutions. Upload & download functionality with Filecoin will be supported by Metamask/FilSnap leveraging Ceramic to upload via Powergate.

Youtube channels of all sizes have to ask themselves, where will they store their videos? This simple web app will solve many problems, including:
+ Maintaining and upgrading massive pre-existing internal storage solutions
+ Inconveniences of starting self-hosting (time, price of storage units, price of extra hardware to support it, research, upgrades & maintenance, networking infrastructure and more)
+ Opt-in privacy for content encryption
+ Convenient recovery access

4K and 8K resolutions use massive amounts of data, which can be unwieldy for videographers to move, store, and archive. Those who rely on third parties (e.g. Youtube) for storage are exposed to several loss vectors - channel deletion, account suspension, failure of hosting company, etc. This is where our app shines, allowing videos to be uploaded to Filecoin and quickly retrieved when needed in the future.

## Deliverables:

Interactive webapp:
+ Introduction to Filecoin and use cases
+ Metamask login and wallet maintenance
+ Guide for downloading videos through Youtube Studio or Google Takeout
+ File selection and downloader (potential metadata: date & time uploaded, length of video, CID?, size of video in bytes)

Advanced options:
+ OAuth for simultaneous upload to Youtube and Filecoin
+ OpenID Connect for a familiar Web2 style of user authentication
+ Power users can set the IP+port to use their own Powergate instance if desired
 
## Development Roadmap

### Milestone 1: Formalize design/specifications

During this initial phase we will formalize design on how to mediate interactions with Filecoin, identity management, and encryption. A tentative architecture is shown below, which will be initially tested and iterated as necessary. While many of the components in the stack are well-defined, we must take care to ensure that identity management, file tracking, and encryption/decryption are clearly (and deterministically) defined to ensure backup robustness.

![https://i.imgur.com/Neqv2uY.png](https://i.imgur.com/Neqv2uY.png)

_Execution time: 2 weeks. Contributor time: 2 weeks engineer + 1 week infrastructure architect + 0.5 week project manager_

### Milestone 2: Design and implement web page backend
We will set up a barebones single-page front-end to test functionality of Metamask integration, Powergate integration, and upload / download features. FIL and/or ETH wallet will be connected to handle transactions with Powergate. The backend will be written in Golang for widespread adoption within the community and maintenance. 

Uploading at this stage encompasses pushing a local video to Filecoin. Downloading at this stage encompasses pulling a video from Filecoin to your computer. 

_Execution time: 5 weeks. Contributor time: 5 weeks engineer_


### Milestone 3: Refine and refactor front-end for final product UI & UX
There is no official Youtube/Google API for downloading videos, so the webapp will provide a guide for retrieving videos through YouTube studio or Google Takeout. This will include a video and documentation that introduces Filecoin and shows how to use it for video backup. This will cover the potential pricing for upload / download costs in Filecoin. A CSS framework to enhance the user interface (UI) and work on user experience (UI) in both webapp. During this phase we will also implement opt-out privacy features, leveraging existed symmetric encryption libraries for local encryption prior to upload (and decryption after download). Practical key management overhead will be minimized by deterministic generation.

At this stage, the Web 3 side of the project will be functional for local-to-filecoin backups. The next stage expands Web 2 functionality and integration.

_Execution time: 6 weeks. Contributor time: 6 weeks engineer + 1 week infrastructure architect + 1 week project manager_


### Milestone 4: Advanced features for enhancements
During this phase we will implement Youtube login through Google’s OAuth. This would be to allow videographers to upload to Filecoin and Youtube simultaneously, providing web 2 convenience and web 3 censorship resistance. This should attract users from the massive Youtube community. At the same time we can use OpenID Connect (OAuth 2.0 +) for a web2 version of user authentication for login to our webapp. The benefit of this would be to be able to store a list of videos they have backed up and show other information pertinent to them in a more familiar way.

We will implement advanced configuration options for users that wish to connect to their own Filecoin node or Powergate instance. This feature essentially aims to maintain the integrity of decentralized systems, and ensure that the usability and stability of our app is not reliant on any particular powergate provider.

_Execution time: 3 weeks. Contributor time: 3 weeks engineer + 0.5 week infrastructure architect + 0.5 week project manager_

### Milestone 5: Community testing and feedback
User testing the tool with community and production. We will prepare a feedback form to solicit input from developers and other users on features, UX, UI, accessibility, etc.

_Execution time: 2 weeks. Contributor time: 2 weeks engineer + 1 week project manager_

### Milestone 6: Documentation and upstream contribution
Write up documentation, and implement changes based on feedback. All project deliverables are completed and added to https://github.com/filecoin-shipyard or linked there via a new meta repo + README (website, documentation, codebase, tutorial).

_Execution time: 2 weeks. Contributor time: 2 weeks engineer + 0.5 week project manager_


## Maintenance and Upgrade Plans
Maintenance for 1 year guaranteed, including critical bug fixes on demand. We are always open to community suggestions to improve the project.

## Team Contact Info

Point of contact: Mitchell Krawiec-Thayer ([mitchell@insight-infrastructure.com](mailto:mitchell@insight-infrastructure.com))

## Team Members

**Project manager: Mitchell Krawiec-Thayer**
- Led team that built and operates Monero’s Observatory (Monero Archival Project)
- Head of Research, Developers in Residence at [Insight](http://www.insightconsensus.com/)
- Data Science and Protocol SecEng for Monero Research Lab
- Project manager for grants from the Zcash Foundation, Web 3 Foundation, ICON Foundation, Harmony Grants, and Monero CCS
- [GitHub](https://github.com/mitchellpkt/), [Twitter](https://twitter.com/Mitchellpkt0), [LinkedIn](https://www.linkedin.com/in/mitchellpkt/), [Medium](https://medium.com/@mitchellpkt)

**Infrastructure architect: Rob Cannon**
-  Automated deployment expert
-  Infrastructure architect and DevOps engineer
-  GitHub: [https://github.com/robc-io](https://github.com/robc-io)
-  Medium: [https://medium.com/@robcannonxyz](https://medium.com/@robcannonxyz)

**Engineer: Marco Rodriguez**
-  Decentralized Consensus Fellow at Insight
-  Created data collection system for citizen science with IPFS backend ([video](https://fellows.link/marco_video), [code](https://fellows.link/marco_code))
-  Distributed systems expert with Golang experience
-  Github: [https://github.com/mrodriguez3313](https://github.com/mrodriguez3313)

**Engineer: Pranav Thirunavukkarasu**
- Lead Engineer on the [Zcash Observatory](https://fellows.link/ObservatoryRoadmap)
- Blockchain Engineer, Developer in Residence at [Insight](http://www.insightconsensus.com/)
- Built a DevOps tool to spin up various local Lightning Network clusters for development and network testing purposes: [fellows.link/pranav_video](https://fellows.link/pranav_video)
- Developed an Ethereum mobile wallet focused on user experience, wallet security, and network reliability
- Full-stack engineering experience at Hewlett Packard Enterprise, focused on front-end user interfaces and low-level networking

**Other Insight contributors:**
-  DevOps and Data Engineering mentors will advise on system design and implementation strategy.
-  Code & documentation reviewers will be assigned as milestones near completion.
-  Additional thanks to office and administrative staff for creating a productive workspace.

## Team Member LinkedIn Profiles

-  Mitchell: [https://www.linkedin.com/in/mitchellpkt/](https://www.linkedin.com/in/mitchellpkt/)
-  Rob: [https://www.linkedin.com/in/rob-cannon-21571317/](https://www.linkedin.com/in/rob-cannon-21571317/)
-  Marco: [https://www.linkedin.com/in/marco-a-rod/](https://www.linkedin.com/in/marco-a-rod/)
-  Pranav: [https://www.linkedin.com/in/tpranav61/](https://www.linkedin.com/in/tpranav61/)

## Team Website

[https://github.com/insight-infrastructure](https://github.com/insight-infrastructure)

## Relevant Experience

Insight specializes in open-source production-grade infrastructure for distributed systems and blockchain ecosystems. Recent projects involve a distributed network analysis suite ([funded by the Zcash Foundation](https://grants.zfnd.org/proposals/21786689-zcash-observatory)), a blockchain data pipeline and analytics stack ([funded by the ICON Foundation](https://forum.icon.community/t/grant-application-blockchain-analytics-and-data-pipelines/871/3)), load-balanced endpoints ([for Polkadot](https://github.com/insight-w3f/)), and a cryptocurrency security audit ([funded by the Monero community](https://ccs.getmonero.org/proposals/research-post-quantum-monero.html)).

## Team code repositories
-  DevOps tooling: [github.com/insight-infrastructure](github.com/insight-infrastructure)
-  DistSys and Blockchain R & D: [github.com/insight-decentralized-consensus-lab](github.com/insight-decentralized-consensus-lab)
-  R & D for ICON: [github.com/insight-icon](github.com/insight-icon)
-  R & D for Web 3 Foundation: [github.com/insight-w3f](github.com/insight-w3f)
-  Insight Fellows Program: [github.com/insightdatascience](github.com/insightdatascience)

# Additional Information

1 - It would be very helpful to have a technical liaison from Filecoin who is available for brief (weekly?) check-ins throughout the grant execution. It’s valuable to have an available contact who can confirm that we’re on the right track, and producing results that are both representative and useful. 

2 - We are always happy to iterate the proposal based on your priorities and advice. Let us know what you'd like to see modified!

Thanks for your time,

Mitchell, Marco, Pranav, and Rob
