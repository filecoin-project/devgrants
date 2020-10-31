# Open Grant Proposal: `Deplatformer`

**Name of Project:** Deplatformer

**Proposal Category:** `core-dev` (Deplatformer), `devtools-libraries` (Pygate)

**Proposer:** peterVG

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description
**The problem we are trying to solve with this project:** Currently, people across the world are facing a dire choice: continue to buy-in to social media platforms, accepting their ever-changing, draconian terms, along with the secretive sale of your private data to advertisers, **or** lose all your photos, data, and curated content to walled garden lock-in. Our aim is to create a clear use case and application of the Filecoin storage network which will allow users to deplatform and divorce themselves from Facebook and other centralized social networks. 

**What exactly are we planning to build:** Deplatformer will start with a modest goal, which will be to empower users to upload their Facebook content into Filecoin and regain control of their own curated data. Then they will be able to use a mobile application to share their images and videos using other messenger applications on their phone to reach their contacts and friends.

This project will create the foundation for several other related initiatives including self-deplatforming from other silos such Instagram, Google Photos, and iCloud, as well as investigating the ability to apply AI image classification and other methods to enable users to create their own value from their content collections. 

**How our solution is going to adequately solve this problem.** We will minimize risk by focusing on the Facebook export and “Filecoin to Mobile” use case in order to develop the critical Filecoin tooling and workflows. These will be portable beyond the scope of this current project as well as to other projects in the Filecoin ecosystem to establish proven practices for moving cloud and platform data onto Filecoin. Most importantly, this specific focus will help us explore the relative market demand for this class of product.

## Value

**Why this proposal is valuable for the Filecoin ecosystem:** The most recent self-reported 2020 statistics show that Facebook had 2.7 billion monthly active users and Instagram had 1 billion monthly active users. Both Google Photos and iCloud are estimated to have over 1 billion users each. The recent Netflix documentary "The Social Dilemma" illustrated that there is growing concern within this user base about the mental health consequences, social decay, and loss of privacy that these platforms have introduced. Even if Deplatformer manages to convince just a small fraction of this market to give the decentralized storage alternative a try, it will represent a huge on-ramp of early adopter consumers for the Filecoin network.

Additionally the tools and practices we will develop and open-source as part of this project will be portable and greatly beneficial to many other Filecoin projects, specifically the Filecoin Management Service and the ability for mobile application clients to receive data pushed from Filecoin and IPFS.

**The benefits to getting this right:** Deplatformer will establish Filecoin as the go-to platform for repatriating online sovereignty. This is one of the core objectives of the decentralization movement and it will place Filecoin right at the forefront of it.

**The risks of not getting it right:** AI-driven advertising algorithms and feed manipulation logic will continue to improve exponentially as social media networks and centralized storage platforms increase their stranglehold on personal and civic sovereignty. 

**The risks that will make executing on this project difficult:** We must be able to convince a key early adopter community of users that giving Deplatformer a try will be worth it. We also must get Filecoin management right. We have to figure out the right balance between long-term cold-storage on Filecoin and making media available just-in-time to end-users. For example, there are no clear best practices established yet on when, where and how to make retrieval deals or if and when to cache in a hot layer. We have identified these risks and plan to address them head-on as part of our development plan.

## Deliverables

All deliverables will be available for use, download, and use-case validation upon milestone completion.

### 1. Pygate gRPC python client for Textile Powergate
- Continue maintenance of [Pygate](https://github.com/pygate/pygate-gRPC), the Python gRPC client, for the wider benefit of the Filecoin and Powergate community.  
- Make new Pygate enhancements to meet Deplatformer requirements.
### 2. End user Filecoin and content management Web Application
- Provide automated parsing, extraction, and upload of profile information and content collection from social media export files to Filecoin network. 
- Provide a web interface to manage uploaded Facebook content and view Filecoin CID, replication, deal and wallet information.
### 3. Filecoin Management Service 
- Manage Filecoin wallets, retrievals, hot cache layer management and pushing content to mobile apps, including a daily feed based on calendar date posts (e.g. “Your Memories”).  
### 4. Mobile application
- A thin client to receive and re-push content from the Filecoin Management Service.

### Use Case Demonstrations:
1. Download the Facebook data backup.
2. User will utilize the web application to migrate their data to Filecoin. 
  * Upload the Facebook data backup.
  * Web application parses metadata, extracts images and videos, and enhances Facebook data.
  * Web application builds / updates local database from Facebook data.
  * Web application encrypts uploaded content using local key.
  * Web application uploads content and index database to Filecoin.
  * Web application updates Filecoin service with metadata for use by mobile client.
3. User will connect the mobile client to the Deplatformer Filecoin Management Service and fetch their metadata.
  * The Filecoin Management Service will provide information based on a QR code or typed code which will “unlock” the metadata.
  * The encryption keys will be cached on the mobile application in secure storage.
4. User will receive files from the Filecoin network on their mobile client.
  * Filecoin Management Service will set encrypted files for download to IPFS.
  * Filecoin Management Service will pin files on behalf of the user.
5. User will utilize the mobile application (iOS and Android) to share images to their existing social network (Whatsapp, iMessage, Facebook Groups, etc)
  * Mobile client will download files and content metadata directly from IPFS.
  * Mobile client will decrypt files using encryption keys.
  * User will trigger sharing with their network via the mobile client.


## Development Roadmap

### Milestone 1:
Software functionality:  
A. User will utilize the web application to migrate their platform data to Filecoin.
  * Extract and parse information from Facebook export file.
  * Create user databases and store information locally.
  * Provide web interface to browse and manage deplatformed content.  

B. Deploy and maintain the web application servers.  

Resources:  

| Person                                                | Funding                 | Time               |
|-------------------------------------------------------|-------------------------|--------------------|
| Peter Van Garderen (Soft Dev, Sys Admin, Project Mgt) | 20 hours/week @ $75/hr  | 3 weeks duration   |
| Art Richards (Soft Dev, Sys Admin, Project Mgt)       | 20 hours/week @ $75/hr  | 3 weeks duration   | 
| Antreas Pogiatzis (Soft Dev, Sys Admin)               | 20 hours/week @ $75/hr  | 3 weeks duration   |  
|                                                       | **$13,500**             | 3 weeks from start | 

### Milestone 2:
Software functionality:

A. User will utilize the web application to migrate their data to Filecoin.  
  * Encrypt information. 
  * Upload images, video and metadata to Filecoin.
  * Update Filecoin Management Service with metadata for use by mobile client.  
  
B. Develop Filecoin Management Service to: 
  * Create wallets for users.  
  * Receive wallet deposits. 
  * Report wallet balances.
  * Maintain list of trusted, verified miners, regional preferences.
  * Maintain market pricing information.
  * Determine replication policy 
  * Report on expiring storage deals and enable auto-renew.  
  
C. Deploy and maintain Filecoin Management Service.

Resources:  

| Person                                                | Funding                 | Time               |
|-------------------------------------------------------|-------------------------|--------------------|
| Peter Van Garderen (Soft Dev, Sys Admin, Project Mgt) | 20 hours/week @ $75/hr  | 6 weeks duration   |
| Art Richards (Soft Dev, Sys Admin, Project Mgt)       | 20 hours/week @ $75/hr  | 6 weeks duration   | 
| Antreas Pogiatzis (Soft Dev, Sys Admin)               | 20 hours/week @ $75/hr  | 6 weeks duration   |  
| Developer X (Soft Dev)                                | 20 hours/week @ $75/hr  | 6 weeks duration   |  
|                                                       | **$36,000**             | 9 weeks from start | 


### Milestone 3:
Software functionality:

A. UX / UI for mobile client application (iOS & Android)

B. User will connect the mobile client to the Deplatformer Filecoin Management Service and fetch their metadata.  
  * The service will provide information based on a QR code or typed code which will “unlock” the metadata.
  * The encryption keys will be cached on the mobile application in secure storage.
   
Resources:  

| Person                                                | Funding                 | Time                |
|-------------------------------------------------------|-------------------------|---------------------|
| Peter Van Garderen (Soft Dev, Sys Admin, Project Mgt) | 20 hours/week @ $75/hr  | 5 weeks duration    |
| Art Richards (Soft Dev, Sys Admin, Project Mgt)       | 20 hours/week @ $75/hr  | 5 weeks duration    | 
| Antreas Pogiatzis (Soft Dev, Sys Admin)               | 20 hours/week @ $75/hr  | 5 weeks duration    |
| Developer X (Soft Dev)                                | 20 hours/week @ $75/hr  | 5 weeks duration    |  
|                                                       | **$30,000**             | 14 weeks from start | 



### Milestone 4:
Software functionality:

A. User will receive files from the Filecoin network on their mobile client application.
  * The Filecoin Management Service will retrieve files from Filecoin using a location optimized retrieval strategy.
  * The Filecoin Management Service will set encrypted files for download to IPFS.
  * The Filecoin Management Service will pin files on behalf of the user.
  * The Filecoin Management Service will push files to mobile phone gallery.
   
Resources:  

| Person                                                | Funding                 | Time                |
|-------------------------------------------------------|-------------------------|---------------------|
| Peter Van Garderen (Soft Dev, Sys Admin, Project Mgt) | 20 hours/week @ $75/hr  | 5 weeks duration    |
| Art Richards (Soft Dev, Sys Admin, Project Mgt)       | 20 hours/week @ $75/hr  | 5 weeks duration    | 
| Antreas Pogiatzis (Soft Dev, Sys Admin)               | 20 hours/week @ $75/hr  | 5 weeks duration    |
| Developer X (Soft Dev)                                | 20 hours/week @ $75/hr  | 5 weeks duration    | 
| Developer Y (Soft Dev)                                | 20 hours/week @ $75/hr  | 5 weeks duration    | 
|                                                       | **$37,500**             | 19 weeks from start | 



### Milestone 5:
Software functionality:

A. User will utilize the mobile client application on iOS or Android to share images to their network using off channel tools.
  * Mobile client application will receive files directly from IPFS.
  * Mobile client application will decrypt files using encryption keys.
  * Mobile client application will enable a "Share To" functionality.
  * The Filecoin Management Service will push files to mobile phone gallery.
  
B. Mobile application distribution channels.
   
Resources:  

| Person                                                | Funding                 | Time                |
|-------------------------------------------------------|-------------------------|---------------------|
| Peter Van Garderen (Soft Dev, Sys Admin, Project Mgt) | 20 hours/week @ $75/hr  | 7 weeks duration    |
| Art Richards (Soft Dev, Sys Admin, Project Mgt)       | 20 hours/week @ $75/hr  | 7 weeks duration    | 
| Antreas Pogiatzis (Soft Dev, Sys Admin)               | 20 hours/week @ $75/hr  | 7 weeks duration    |
| Developer X (Soft Dev)                                | 20 hours/week @ $75/hr  | 7 weeks duration    | 
| Developer Y (Soft Dev)                                | 20 hours/week @ $75/hr  | 7 weeks duration    | 
|                                                       | **$52,500**             | 26 weeks from start | 


## Total Budget Requested

| Milestone   | Duration      | Participants | Personnel    | Servers     | Total        |
|-------------|---------------|--------------|--------------|-------------|--------------|
| Milestone 1 | 3 weeks       |  3           | $13,500      | $1,500      | $15,000      |
| Milestone 2 | 6 weeks       |  4           | $36,000      | $3,000      | $39,000      |
| Milestone 3 | 5 weeks       |  4           | $30,000      | $2,500      | $32,500      |
| Milestone 4 | 5 weeks       |  5           | $37,500      | $2,500      | $40,000      |
| Milestone 5 | 7 weeks       |  5           | $52,500      | $3,500      | $56,000      |
|             |               |              |              |             |              |
|             | **26 weeks**  |              | **$169,500** | **$13,000** | **$182,500** |

* Note that Personnel costs are inclusive of project management, administration, and public relations.

## Maintenance and Upgrade Plans
Our goal is to transform into an open organization focused on providing the online world the ability to deplatform themselves from incumbent social media. Our plan is to use this amazing Filecoin open grant opportunity to launch and grow a free and  open sourced suite of Filecoin based tools and services. 

While our objectives are ambitious, we believe that by bootstrapping on the same networks we are liberating users from, and by providing them with a straight-forward user experience, we will be able to grow a critical mass of early adopters. The end-user web and mobile applications will remain free. However, we believe that after an initial period of subsidized Filecoin storage, whereby our users will gain increasing exposure and trust of the service, they will be willing to pay a small monthly subscription, on par or less than Google Drive or Apple iCloud storage. These fees will fund their Filecoin storage and the fractional micropayments we will charge to use the Deplatformer Filecoin Management Service. We will make all Filecoin storage, retrieval, and processing fees visible via reports in the web application so that users become educated and empowered users of the Filecoin network and the Deplatformer service.

In short, our long-term objectives to fund ongoing maintenance and upgrades include leveraging the initial product to begin collecting monthly service fees and transaction micropayments. We will also seek additional investments or assistance from cryptocurrency venture capitalists and grant programs.

As an additional benefit to the Filecoin community, we will also continue to maintain and develop the Pygate gRPC client to deliver the Deplatformer tools. This will keep the door open to the Filecoin world for the world's substantial and influential community of Python developers.

# Team

## Team Members

1. Peter Van Garderen
2. Art Richards
3. Antreas Pogiatzis
4. Hector Monsegur (provisional Developer X)
5. Tony Wooster (provisional Developer Y)


## Team Member LinkedIn Profiles

1. https://www.linkedin.com/in/petervangarderen/ 
2. https://www.linkedin.com/in/richardsart/
3. https://www.linkedin.com/in/a-pogiatzis/
4. https://www.linkedin.com/in/hxmonsegur/
5. https://www.linkedin.com/in/tonywooster/

## Team Website

* https://deplatformer.io
* https://deplatformer.substack.com/
* https://open-images.deplatformr.com/about 

## Relevant Experience
Our team was chosen as one of ten finalists from over 130 projects in this past summer’s HackFS event. We developed Pygate, the Python gRPC client and reference web application for Textile’s Powergate API to the Filecoin network. It is now being actively used by other Filecoin projects that prefer to work in Python. Peter Van Garderen gave a developers’ introduction to Pygate during Build day at the Filecoin Liftoff event. We continue to maintain Pygate for community benefit and we will enhance it as we use it to build out the Deplatformer web application and Filecoin Management Service.

Our team gained further experience developing Filecoin solutions by participating in the Gitcoin Apollo mentorship process as well as the Filecoin Slingshot competition. Our Deplatformer prototype was selected as one of the finalists in Apollo Demo Day and we were active, positive contributors in both the #powergate-users and #slingshot Slack channels during Slingshot Phase 1.

Our team includes deep technical expertise in blockchain, archiving, encryption technologies, and artificial intelligence research, as well as many years practical experience in systems administration, software development and IT community leadership.

***Peter Van Garderen*** is a highly respected domain expert in the field of digital preservation. He is well known within the global community of heritage institutions as the founder of Artefactual Systems Inc. and the creator of the free and open source Archivematica digital preservation system and AtoM archival cataloging application. AtoM is the most widely used product in this market by archival institutions worldwide. Peter has the practical experience of launching and maintaining free open source products and services and building a sustainable business around them. He stepped back as company president a few years ago to free up time for more product development and research and development activities. His interest and early contributions to the Filecoin ecosystem are an extension of this work. Peter sees the Deplatformer tools and experience as a stepping stone to introducing institutional heritage institutions and their invaluable public collections to Filecoin storage.

***Art Richards*** is an experienced founder, entrepreneur, project manager and product manager. He has significant experience in IT solutions for IoT, Energy, Logistics, Mobility, E-commerce, and Sales. Art has led several multi-disciplinary teams to launch customer-focused products. He consults with startups to help them improve their processes and teamwork to deliver better products.  He is an advisor to Blockchain Logistics Forwarding platform DexFreight. In 2014, Art founded the BlockTrade cryptocurrency exchange, one of only two at the time to maintain a money transmitter license in the US. Art is an experienced leader of several startups, including a Logistics Mobile App, TruckIN which was sold to a major industry player, a Building Management IoT Platform, Envio Systems, currently finalizing its series B investment round, and a Voter Engagement System, Ride.vote, currently providing free rides to voters in counties like Miami-Dade, Harris County (Houston) and Los Angeles County for the 2020 elections.  

***Antreas Pogiatzis*** is a professional software engineer holding an integrated Masters Degree from the University of Glasgow. He is currently pursuing a part-time PhD in Privacy Preserving technologies in the context of Big Data from the University of Greenwich. At the same time, he is working as a KTP Associate in a healthcare data analytics provider (Transforming Systems Ltd) in a research-oriented collaboration with University of Greenwich. Antreas is the founder of three startups (DermaTrack, NodeDistrict, Bifrost) and has led innovative initiatives like establishing a Fintech Society at the University of Glasgow and launching his own cyber security community/ctf team (CYberMouflons). Antreas' work experiences span a wide variety of working cultures, from small startups to multinational corporations, highlighting his adaptiveness and caliber. He is passionate about cyber-security, distributed ledger technologies, fintech and data science. Antreaa acquired his professional software engineering experience from companies like Airpoint Ltd, JP Morgan and LookingGlass. 

Our provisional developers **Hector Monsegur** and **Tony Wooster** are senior software engineers with many years experience developing and deploying complex web and mobile applications. Most recently they collaborated with Art Richards to launch the innovative Ride.vote service.

## Team code repositories

* https://github.com/pygate
* https://github.com/deplatformer
* https://github.com/artefactual/archivematica
* https://github.com/artefactual/atom 

# Additional Information
Our project members have a long history with blockchain technology and are passionate about the decentralization movement. We've gelled into a cohesive, effective team over the course of HackFS, Gitcoin Apollo and the Slingshot Space Race. Our skills and personalities are very complementary and we enjoy each other's company. We balance technical expertise with strong organizational skills to achieve our goals on time and within scope. Breaking down complex problems and then executing on them is our strong point, which is why the milestones above are both ambitious as well as realistic.  

As noted in the Development Roadmap, we plan on expanding our core team of three to include the help of two experienced developers who will help us push our project past the finish line. The wider Filecoin community stands to benefit from our project deliverables irrespective of the relative success of the Deplatformer vision. However, We are confident that we will see Deplatformer come out of this seed phase with a concrete FOSS product suite that we will successfully launch and evolve through active engagement with our user base and sponsors. We will deplatform social media captives and lead the exodus to Filecoin decentralized storage!
