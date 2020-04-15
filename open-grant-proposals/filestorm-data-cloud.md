# Open Grant Proposal: `FileStorm Data Cloud Storage`

**Name of Project: FileStorm Data Cloud**

**Proposal Category: `app-dev`**

**Proposer: `fraymond`**

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?: "Yes"** 

# Project Description

FileStorm is implementing a storage client front-end that supports file encryption, redundant storage strategy, and multiple storage platform, including IPFS. The application will allow users to encrypt data, enter into storage deals with several miners, retrieve and decrypt the data. The application will also provide the users with multiple ways to pay for storage services, such as monthly subscription and pay per use.

- Easy to use UI that supports file upload, download, file drag and drop, file management, bulk file maintenance, etc.
- Files are defaulted to be encrypted using users's private key before being uploaded.
- Data is broken into smaller pieces and stored on a global network.
- Data redundancy is calculated and recommended by using erasure coding library such as zfec.
- Data can be reconstruct if a copy cannot be retrieved.
- Support interuptible data transfer and resume using GraphSync.
- Compatible with IPFS.

## Value

Decentralized storage platform is the future, but most web and mobile based applications use centralized cloud services. FileStorm wants to build a bridge for IT users to use decentralized storage as cloud services they are familiar today. The web application and the storage API are the two main product of this project.
- What are the benefits to getting this right?
It will existing technology to transition smoothly from centralized cloud service to decentralized service.

- What are the risks if you don't get it right?
If the project was not implemented correctly, users may hesitate to adopt the new technology.

- What are the risks that will make executing on this project difficult?
Number of users committed to use our data storage services.

We will also implement interuptible data transfer and resume, which is in high priority, so this is a rfp for two items.

## Deliverables

An application that supports the Web, iOS and Android phones for users to store data files.
A payment service API for different file storage options.
A file storage and retrieval service API for other applications.
Documentations for the APIs. 

## Development Roadmap

* Milestone 1
  - UX Design
  - Project manager, UX Designer, Architect
  - Deliverable: Design documentation
  - 3 weeks
  - Cost: $18,000

* Milestone 2
  - Development
  - Architect, front-end developer, back-end developer
  - Deliverable: Web and Mobile Application, API
  - 4 weeks
  - Cost: $24,000

* Milestone 3
  - Testing and Website launch.
  - Architect, Developers x 2, Tester
  - Deliverable: User guide, Documentation
  - 3 weeks
  - Cost: $18,000

## Total Budget Requested

$60,000.

## Maintenance and Upgrade Plans

The team will maintain the package long-term and release new package versions with new FileCoin release.

# Team

## Team Members

[FileStorm team](https://www.filestorm.net/?language=en#team)

## Team Member LinkedIn Profiles

- [Raymond Fu](https://www.linkedin.com/in/raymond-fu-b8138a4/)
Checkout https://www.filestorm.net/?language=en#team for other teammates' info.

- ...

## Team Website

[https://www.filestorm.net/?language=en](https://www.filestorm.net/?language=en)

## Relevant Experience

FileStorm is has already build a storage platform that will connect to multiple distributed storage solutions including Hadoop, Redis and MongoDB.

## Team code repositories

https://github.com/filestorm-fst/go-stormchain

