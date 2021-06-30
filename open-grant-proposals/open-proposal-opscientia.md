
# Open Grant Proposal: `Opscientia - proposal for research and technical design into hosting large neuroscience datasets on IPFS`

**Name of Project: Opscientia - proposal for research and technical design into hosting large neuroscience datasets on IPFS**

**Proposal Category:** `technical-design`

**Proposer:** `XandraMcC`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

<!-- - Start with the need or problem you are trying to solve with this project.
- Describe why your solution is going to adequately solve this problem. -->

Our team were ETHGlobal Web3Weekend finalists with our Open Science (Opsci) Data Wallet. We also won the Textile.io prize and IPFS blog recognised us as a project that most inspired them. This proposal is to carry on with this idea and research the backend of how we would handle large terabytes of data on IPFS and how we can integrate that into our data wallet.

We are partnering with DANDI (Distributed Archives for Neurophysiology Data Integration) at MIT which is funded by the US government BRAIN initiative (set up by the Obama administration) to test if IPFS can successfully support 2.5 terabytes of brain data. This data is currently non-human and is stored centrally on AWS. However, when human brain data starts being collected by DANDI, and other neuroscience laboratories, there is an inherent ethical risk of storing human data with Big Tech companies. This is where decentralised data storage comes in and we would like to work with IPFS to help verify and build a solution that helps scientists to store their data in an ethical manner.

#### Milestones for this project:
1. Build on initial user-research with users (neuroscientists)
2. Validate and design the backend of our data wallet to be able to host large datasets
3. Build *open science data wallet v1*
4. User-requirement design
5. Validate *open science data wallet v1* with users (neuroscientists)

#### Relevant links:
- DANDI - https://www.dandiarchive.org/

## Value

<!-- Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:
- What are the benefits to getting this right?
- What are the risks if you don't get it right?
- What are the risks that will make executing on this project difficult?

This section should be 1-3 paragraphs long. -->

We will carry out a thorough evaluation of IPFS for large volumes of scientific data. This design is grounded in research, ethics and the end user is at the heart of what we are building. If we get this right it will be the first and largest validation of scientific data being hosted on IPFS. This will provide proof that large amounts of sensitive data can be stored in a decentralised manner and will provide the validation needed for institutions such as MIT to start moving away from centralised storage systems.

What are the risks if you don't get it right?

What are the risks that will make executing on this project difficult?

Mobile is especially important to the wider distribution of IPFS and user base growth. IPFS could, with focused study on use cases and behaviours of mobile users for instance with sharing content and media, be an easier jump to using P2P in their daily lives. For instance, a solid and enjoyable IPFS mobile experience might allow perhaps skipping the desktop experience altogether for users coming to the platform.

The question of scope is constant in defining projects and areas of study. While the scope of this may initially be quite wide and shallow, this could be advantageous in setting up the groundwork for additional studies which would further refine thinking and recommendations as the field progresses. The value lies in making forays into the space, researching and designing that which has not been done to date, and creating a way to learn where to refine and redefine how IPFS is brought to more and more users.

## Deliverables

<!-- Please describe in details what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished. -->

At the end of these 6 weeks we will have:
- Designed the backend of our *open science data wallet*
- Developed version 1 - *open science data wallet v1*
- Designed feature requirements for future product development
- Validated our product with end-users

## Development Roadmap

<!-- Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section).

For each milestone, please describe:
- The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates) -->

### Key questions to address through the overall project:
1. Can researchers upload data to our wallet?
2. Can researchers access uploaded data?
3. Can researchers "do science" on uploaded data?
4. How do latencies compare to centralised storage (i.e. S3 buckets)?
5. How will it integrate and perform with *Neuroglancer* (WebGL-based visualisation tool)?
6. How does data pinning work?


### Milestone 1: Build on initial user-research with users (neuroscientists) - 2 weeks (30 August - 10 September)

**Aim:**
User research with target audience (Distributed Archives for Neurophysiology Data Integration (DANDI) lab researchers) to understand data needs.

**Method:**
In dept 1:1 interviews with DANDI members (n=5)

**User research protocol:**
- Obtain info about researcher (e.g. career level, experience with Web3 tools, etc) - these will be used to build user personas
- Ask user to outline current journey for uploading and accessing DANDI data
- Enquire about pain points in current process (including sources of friction, points of risk for error, latencies)
- Ask user to explain needs once data is uploaded (e.g. cleaning/processing (including "pinning"), visualisation, analysis, sharing, and current tools for this)
- Explain basic data wallet steps and identify initial thoughts, concerns and questions

**Outputs:**
User personas, current state user journey map, feature requirements for POC, user FAQs

**Team members:**
- Shady - user-researcher focusing on institutions
- Sarah - user-researcher focusing on scientists

### Milestone 2: Research and design the backend of *open science data wallet v1* (working group feasibility research) - 2 weeks (30 August - 10 September)

**Team members:**
- Shady - product owner
- Alexandra - technical architect
- Achintya - technical researcher
- Kinshuk - technical researcher

### Milestone 3: Build *open science data wallet v1* - 2 weeks (13 September - 24 September)

**Team members:**
- Shady - product owner
- Alexandra - full-stack engineer
- Achintya - full-stack engineer
- Kinshuk - full-stack engineer

### Milestone 4: User-requirement design - 2 weeks (13 September - 24 September)

**Team members:**
- Sarah - technical designer

### Milestone 5: Validate *open science data wallet v1* with users (neuroscientists) - 2 weeks (27 September - 15 October)

**Aim:** 
User research with target audience (DANDI lab researchers) to gather feedback on POC.

**Method:** 
1:1 user testing with DANDI members (n=5; recruit same group as before where possible)

**User-research protocol:**
- Show solution to user and provide brief instructions
- Provide a series of scenarios plus detailed documentation to the user: 1. upload dataset, 2. process/visualise/analyse uploaded data, 3. download data, 4.share/permission data
- User completes each scenario while narrating thoughts to interviewer 
- Ask user for thoughts, concerns and questions on the experiences

**Outputs:**
Validation of whether each feature (and documentation) meets user's needs, identification of areas for further improvement/iteration

**Team members:**
- Shady - user-researcher focusing on institutions
- Sarah - user-researcher focusing on scientists
- Alexandra - technical researcher focusing on technical feedback from institutions & scientists

## Total Budget Requested

**Total: USD$ 17,600**

We are budgeting for 6 weeks of work to research, design, develop *open science data wallet v1*, and validate with users. This will also enable us to carry out significant user-reseach to  develop a clear roadmap to further build on v1.

#### Milestone 1: Build on initial user-research with users (neuroscientists) - 2 weeks (30 August - 10 September)
|Team members required: | rate (per hour) | time (hours) | total |
|-----------------------|-----------------|--------------|-------|
| Shady | USD$20 | 40 | USD$800 |
| Sarah | USD$20 | 80 | USD$1600 |
| | | | **USD$2400** |

#### Milestone 2: Research and design the backend of *open science data wallet v1* (working group feasibility research) - 2 weeks (30 August - 10 September)
|Team members required: | rate (per hour) | time (hours) | total |
|-----------------------|-----------------|--------------|-------|
| Shady | USD$20 | 40 | USD$800 |
| Alexandra | USD$20 | 80 | USD$1600 |
| Achintya | USD$15 | 80 | USD$1200 |
| Kinshuk | USD$15 | 80 | USD$1200 |
| | | | **USD$4800** |

#### Milestone 3: Build *open science data wallet v1* - 2 weeks (13 September - 24 September)
|Team members required: | rate (per hour) | time (hours) | total |
|-----------------------|-----------------|--------------|-------|
| Shady | USD$20 | 80 | USD$1600 |
| Alexandra | USD$20 | 80 | USD$1600 |
| Achintya | USD$15 | 80 | USD$1200 |
| Kinshuk | USD$15 | 80 | USD$1200 |
|   |   |   | **USD$5600** |

#### Milestone 4: User-requirement design - 2 weeks (13 September - 24 September)
|Team members required: | rate (per hour) | time (hours) | total |
|-----------------------|-----------------|--------------|-------|
| Sarah | USD$20 | 80 | USD$1600 |
| | | | **USD$1600** |

#### Milestone 5: Validate *open science data wallet v1* with users (neuroscientists) - 2 weeks (27 September - 15 October)
|Team members required: | rate (per hour) | time (hours) | total |
|-----------------------|-----------------|--------------|-------|
| Shady | USD$20 | 40 | USD$800 |
| Sarah | USD$20 | 80 | USD$1600 |
| Alexandra | USD$20 | 40 | USD$800 |
| | | | **USD$3200** |

## Maintenance and Upgrade Plans

<!-- Specify your team's long-term plans to maintain this software and upgrade it over time. -->

The long term plan is to 

# Team

## Team Members

- Shady El Damaty PhD
- Sarah Hamburg PhD
- Alexandra McCarroll MSc
- Achintya Kumar
- Kinshuk Kashyap
<!-- - Daniel Byington MSc MBA -->

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/seldamat/
- https://www.linkedin.com/in/sarah-hamburg-phd-9510a910a/
- https://www.linkedin.com/in/alexandra-mccarroll-469108133/
- https://www.linkedin.com/in/achintya-kumar1/
- https://www.linkedin.com/in/kinshuk-kashyap-32a4747b/
<!-- - https://www.linkedin.com/in/daniel-byington-964a35a4/ -->

## Team Website

https://opscientia.com/

## Relevant Experience

We are a highly educated, cross-functional, global team with a clearly shared vision to develop a community-owned neuroscience ecosystem that unlocks data silos, reolutionises collaboration, and democratises funding. Our team spans the globe from India, the U.K, the U.S., Spain, Egypt, and Hong Kong.

Shady El Damaty, PhD, is our founder and product manager. He has an extensive quantitative background contributing to methods development and digital infrastructure for neuroscience research.

Sarah Hamburg, PhD, is our product strategist. She is a neuroscientist with years of experience in human neuroimaging, user experience research, and product development.

Alexandra McCarroll, MSc, is our full-stack software engineer and technical architect with experience as both a software and data engineer. In her past she has worked with both big institutions and FinTech startups.

Achintya Kumar, is Opscientia's Open Web Fellow, who is applying his web development skills to build the decentralised science stack. He is our front-end enthusiast and resident DID expert.

Kinshuk Kashyap, is Opscientia's Google Summer of Code Fellow, who was awarded a competitive summer fellowship. He is our resident IPFS expert with a passion for decentralised neuroscience data.

<!-- Daniel Byington, MSc MBA, is our business development expert and is in charge of our non-technical communications. He has a rich background in market and scientific research for pharmaceutical drug development. -->

## Team code repositories
- Opscientia GitHub organisation - https://github.com/opscientia
- Shady - https://github.com/seldamat
- Sarah - https://github.com/shamburgularara
- Alexandra - https://github.com/XandraMcC
- Achintya - https://github.com/Ackintya
- Kinshuk - https://github.com/kinshukk
- Our Web3Weekend Hackathon showcase page - https://showcase.ethglobal.co/web3weekend/open-science-opsci-data-wallet

The data wallet code - https://github.com/opscientia/web3weekend-hackathon

# Additional Information

<!-- Please include any additional information that you think would be useful in helping us to evaluate your proposal. -->