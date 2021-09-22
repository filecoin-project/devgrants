# RFP: Social media archiving Web APP

**Name of Project:** Social media archiving Web APP

**Proposal Category:** `app-dev`

**Proposer:** `CoinSummer.io`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `Yes`

# Project Description
- Goals：
	- Protect users' privacy and generated data on various social media
	- Prevent users' own data from force removal due to policy control, restrictions by social media company, etc
	- Provide valuable data set to store on Filecoin network

- Solutions:
	- Through a decentralized, safe and private storage methods, permanently store user generated texts, pictures, videos and other type of data on social media networks in order to solve the security and privacy issues brought by centralized data storage.
	- After logged in via third party authorization provied by social media provider, user is able to selects the data to store on Filecoin Network, submit storage order to miners and pays the corresponding storage fee, and can view and manage his/her data in the web/mobile APP.

- Tech Specs:
  - Backend: NodeJS + PostgreSQL/MySQL + Redis
    - RESTFul APIs
  - Frontend: React + TypeScript
    - Web APP
    - Browser extension

## Deliverables
1. UI/UX design
    - Mockups
    - Product specifications
2. Up-to-date and easy-to-use Lotus JS SDK
    - Implementation + npm package published
    - Documentation
3. Web APP
    - Web APP client
    - RESTFul API backend
    - Documentation and user guide
4. Browser extension
    - Browser extension package

## Development Roadmap
### Milestone 1 - Complete specifications
- Goals:
  - Create UI wireframes and mockups
  - Finalize specs and architecture
  - Validate specs with the Filecoin team
- Deliverables:
  - Application specs and architecture design
  - Development plan for upcoming milestones
  - Zeplin project with high-fidelity design mockups
- Duration: 1 week
- Team: Full-time PM, Part-time UI/UX designer
- Budget:
  - Number of hours: 30h + 30h (design) = 60h
  - Total (USD): $3,600

### Milestone 2 - Lotus JS SDK
- Goals:
  - JS SDK that integration with Lotus full-node
- Deliverables:
  - Backend code
  - NPM package published
  - Documentation
- Duration: 1 week
- Team: Full-time Backend developer
- Budget:
  - Number of hours: 60h
  - Total (USD): $3,600

### Milestone 3 - Social media authorization and upload file workflow
- Goals:
  - Start UI development
  - Integrate Filecoin wallet
  - Connect with social media such as Twitter, Weibo
  - Steps for the full cycle of making a deal in Filecoin
- Deliverables:
  - Frontend and backend code
- Duration: 1 week
- Team: Full-time Frontend developer, Full-time Backend developer, Part-time PM
- Budget:
  - Number of hours: 120h
  - Total (USD): $7,200

### Milestone 4 - List files owned by the user
- Goals:
  - Implement UI for file listing
  - Implement backend and frontend logic
- Deliverables:
  - Backend code with new API endpoints
  - UI listing the files owned by the user along with their basic details such as CIDs and miner info.
- Duration: 1 week
- Team: Full-time Frontend developer, Full-time Backend developer, Part-time PM
- Budget:
  - Number of hours: 100h
  - Total (USD): $6,000

### Milestone 5 - Download file flow
- Goals:
  - Implement UIs
  - Implement backend and frontend logic
- Deliverables:
  - New features in the backend code
  - New features in the frontend code to order download and then notify the user when it is ready for downloading
- Duration: 1 week
- Team: Full-time Frontend developer, Full-time Backend developer, Part-time PM
- Budget:
  - Number of hours: 100h
  - Total (USD): $6,000

### Milestone 6 - QA, deploy and documention
- Goals:
  - Complete automated tests
  - Fix bugs
  - Setup CI server and deploy to production environment
  - Finish writing documentation
- Deliverables:
  - A tested version is running and connected to the Filecoin network
  - API and user guide document
- Duration: 1 week
- Team: Full-time QA engineer, Full-time Devops engineer, Part-time Backend developer, Part-time Frontend developer and Part-time PM
- Budget:
  - Number of hours: 60h
  - Total (USD): $3,600

## Total Budget Requested
|No.| Milestone Description | Funding | Duration |
|:-------:|:------|------:|:------|
|1| Complete specifications | $3,600 | 1 week |
|2| Lotus JS SDK | $3,600 | 1 week |
|3| Social media authorization and upload file workflow | $7,200 | 1 week |
|4| List files owned by the user | $6,000 | 1 week |
|5| Download file workflow | $6 000 | 1 week |
|6| QA, deploy and documention | $3,600 | 1 week |
|| Totally | $ 30,000 | 6 weeks |

## Maintenance and Upgrade Plans
Bugs and feature requests will be created and tracked in the github repository. Critical bugs will be fixed for a period of up to 20 days after delivery. And, we can also consider establishing a monthly retainer to provide post-grant maintenance.

# Team

## Contact info
k@coinsummer.io

## Team Setup
For now, we propose the following profiles for the execution team:

- 1 Lead UI/UX Designer: Responsible for the conception of the proposed use cases and user flows.
- 1 Product Manager: Responsible for product feature design, user interaction design and monitor the project's execution for successful delivery.
- 2 Software Engineers:
  - 1 Lead Software Engineer: In charge of conceiving, implementing and integrating the necessary APIs to communicate with the Filecoin network and social media network.
  - 1 Frontend Engineer: Responsible for the implementation of the UIs as idealized by the Lead UI/UX Designer.
- 1 QA Engineer: Responsible for product functional testing, performance testing.

## Team Website
[https://coinsummer.io](https://coinsummer.io)

## Relevant Experience
CoinSummer team is committed to the major cryptocurrency and blockchain projects, and has developed multiple applications and technical research on Bitcoin/Lightning Network, Ethereum.

- [CoinSummer](https://coinsummer.io): Provide cryptocurrency market insights and reliable data analysis, dedicated to creating a one-stop crypto market research platform. CoinSummer’s products include: crypto market observation, bitcoin analysis, blockchain data.
- [Crypto videos](https://coinsummer.tv): Cryptocurrency industry analysis, regulatory, trend prediction, trading strategy, fundamental analysis, industry technical analysis video, real-time tracking of the latest developments of crypto currency.
- [Lightning Network Payment SDK](https://ln.coinsummer.io): Payment SDK for Bitcoin lightning network.
- [Lightning Network Payment Web APP](https://lapp.coinsummer.io): Web APP for receive small tips and micro-payments across the web, using Lightning Network and Bitcoin.

CoinSummer team support and contribute to Filecoin project and Chinese filecoin commuity：

- [Proof Parameters CDN Download](https://filecoin.coinsummer.io/v26.html): CDN provider for Proof parameters on Mainland China.
- [Datastore mirrors](https://filecoin.coinsummer.io/datastore.html): Download service of Filecoin Blockchain synchronization Datastore backup.
- [Filecoin resources](https://github.com/CoinSummer/filecoin): Filecoin Awesome resources Repo for Chinese commuity. Including common resource links, commonly node operations, common Storage Miner operations, Seal Worker operations, environment variables, debugging, frequently asked questions, etc.

# Additional Information
