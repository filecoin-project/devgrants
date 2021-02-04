To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Launderette Tracker`

**Name of Project: Campus Laundry Customer Usage Tracking Application**

**Proposal Category:**  `app-dev`

**Proposer:** `Vidhyanandcs`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?: Yes** 

# Project Description

Introduction

Kirei Launderette Solutions is a  campus laundry service provider based of India. We serve in 5 Universities across India.  We operate in self service model and full -service model as per the requirement of the university. Self-service model requires students to use machines by themselves. Full service model is where the clothes are washed and dried by the employees of the facility using the machines available. The payment for the services provided is done quarterly by universities based on the wash cycles used up by students. The estimated number of wash cycles for the year 2021 -22 will be around 200,000. As the wash cycles are increasing year on year, the firm is planning to introduce a mobile application for tracking wash cycles and quality control.

Problem

1)Kirei Launderette Solutions is looking for a storage of  data on a trusted, immutable  network which then can be verified by the university officials before disbursing the payment. 
2)Damaged or lost clothes in case of full service model were  560 cases in the year 2018-19 and 723 cases in the year 2019-20. Resolving these issues amicably is time consuming as Kirei Launderette Solutions does not store any evidence of clothes brought into their store for washing  and taken out of their store after washing by the customers.

Solution

1)Kirei Launderette Solutions would like to use a decentralized cloud storage powered by filecoin to store the student details and wash cycles. As the details are stored in a decentralized storage, it increases the trust and security for the data. This will make sure that sensitive information like student data is not leaked by hackers (which can adversely effect the reputation of the firm). Also University officials can be sure that wash cycle data they are checking is not tampered with.
2) The images of the clothes will be taken at the time of weighing(when customer brings in the soiled clothes) and also at the time of delivery.  This will be stored in filecoin decentralized storage. These images can be used as a reference when students claim lost or damaged clothes.


## Value

Benafits 

1)Kirei Launderette Solutions will be able to create a customer centric application which is stored in a decentralized and competitively priced storage system.
2)The use of decentralized storage will increase the trust on the data stored .
3)The competitive pricing of cloud storage will help to reduce the fixed cost associated with application maintenance.  
4)File coin community will be benefited as we will keep our project as open source. The project can be used as a reference by the community in building future applications and use cases.

Risks

1)If the storage is not reliable Kirei Launderette Solutions would have to switch to costly servers provided by AWS or Azure for development and expansion of the application.
2)The firm may lose valuable data if the storage miner or retrieval miners are reluctant to honor the deal. 

Difficulties

1)Beta testing of the application will depend on  when the collages will be reopening (currently closed due to covid-19 pandemic).

## Deliverables

1)Create a mobile application for tracking customer usage.
2)Deploy it using filecoin storage.
3)Implement the application in one of the  campuses were Kirei Launderette Solutions operates.

## Development Roadmap

Milestone 1 : Develop the android application UI , DB and APIs.

Platforms to be used

1)Flutter for User Interface
2)Go for API development 
3)Etcd for creating database

Manpower to be consumed

1)Flutter UI developer :  Vidhyanand CS (Front end developer)

2)Go APIs and DB developer: Deepk S (Software Engineer and Backend Developer)


Development details

The application will have three type of users:

1)Administrator: 

    The administrator account will be handled by the owners of the firm. This account will have the following capabilities.
    a)Adding a new campus to the app.
    b)Block or give access to a particular student’s account.
    The account will have access to following information:
    a)Campus wise total wash cycles consumed in the year.
    b)Student wise wash cycles consumed in the year(for each campus).

2)Students:

    Each student will have 20 wash cycles per year. Each time a student comes to the facility the following steps have to be followed.
    Step1:  Student takes images of the clothes using application.
    Step2:  Student handover the clothes to operator.
    Step3:  Student marks in the application that clothes are deposited 	in the facility.
    Step4:  Student comes back to take his clothes. He/she takes one more photo of the clothes using application and scans the QR code 	marking delivery of clothes.

3)Campus Admin:

    Campus admin will be the account of the concerned person from the campus administration.
    The account will have access to the following:
    1)Total number of students who used the facility.
    2)The total cycles each student have used.
    3)Grand total number of wash cycles consumed per year.

Funding Required:

    The projected funding requirement for milestone 1 will be 700 FIL 

Time taken:

    The estimated time taken for the development of application will be 45 days (01/05/2021 to 16/06/2021)

Milestone 2: Deploy the application in filecoin storage.

Platforms to be used: 

1)Lotus for storage and retrieval of information. 


Manpower to be consumed:

1) Deepk S (Software Engineer and Backend Developer)

Data stored and retrieved:

The following data will be stored and retrieved from filecoin cloud.
1)Campus account details and credentials.
2)User details and credentials.
3)Updated wash cycle balance each time user avail service.
4)Photos of clothes before and after wash.

Funding Required:

The projected funding requirement for milestone 2 will be 200 FIL 

Time taken:

The estimated time taken for the development of application will be 5 days (17/06/2021 to 21/07/2021)

Milestone 3: Use the application in one campus where laundrette operates.

Manpower to be consumed

1)Prasad S (Facility Manager, Kirei Launderette Solutions, Hyderabad central University Campus)

The application will first used by students of Hyderabad central university where Kirei Launderette Solutions operates. The store manager will be given the task of asking students to install the application and use them. The data and performance from the application will be monitored for 10 days and necessary changes will be made. 

Time taken

The estimated time taken for the development of application will be 10 days (22/06/2021 to 31/08/2021)

## Total Budget Requested

Total budget requested is 900 FIL.  This includes 700 FIL for application development and 200 FIL for deployment into filecoin storage.

## Maintenance and Upgrade Plans

Kirei Launderette Solutions has plans to implement the stable version of this application in all 5 campuses where it operates. It also will be adding a facility manager module  for each campus through which facility manager can have access to relevant data of students. This will help in faster grievance redressal.
The application will be maintained by the same team which is building it. 

# Team

## Team Members

    Vidhyanand CS
    Deepak S

## Team Member LinkedIn Profiles

    https://www.linkedin.com/in/vidhyanand-c-s-57344672/

    https://www.linkedin.com/in/dpaks/

## Team Website

    https://launderetteindia.com/

## Relevant Experience
Vidhyanand CS has been developing UI for web and mobile applications for past 5 years.
Deepak S has completed his M.Tech in computer science and is working as senior software engineer 
The team  has prior experience in building decentralized applications. SecureCerts ( https://securecerts.in/) has been built by the team on algorand blockchain network. This dApp is helping issuers in issuing and verifying immutable certificates.

## Team code repositories

https://github.com/securecerts/scui 

https://github.com/securecerts/dapp

(Access to these private repositories can be given on request)

# Additional Information

Please include any additional information that you think would be useful in helping us to evaluate your proposal.