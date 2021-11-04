# RFP Proposal: `PriStorage`

**Name of Project:** `PriStorage`

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/near-and-filecoin.md

**RFP Category:** `app-dev`

**Proposer:** `@manhnvan`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Everything on IPFS or Filecoin network is public and anyone can access it if they know the CID. Our project **PriStorage** is an application for users who want to store their files in private on the decentralized network, every data uploading by **PriStorage** is encrypted, and only shared users can decrypt it. This project is a web application, similar to Google Drive but using IPFS/Filecoin as a cloud storage system and everything related to user management and data sharing based on NEAR smart contracts. Therefore, this application is fully decentralized, different from traditional centralized file storage applications and no one or organization can touch your files without permission.

## Value
* This project helps to extend the use case of IPFS/Filecoin for data storage, not only storing public data like before, but now with the PriStorage application, users can confidently upload their confidential data without fear of prying eyes and able to share their files with those they want.
* Contributing application using the technology of both blockchain platforms, NEAR and Filecoin, helps users benefit from the advantages of these two platforms such as cheap transaction fees and data storage fees compare to traditional data storage services.

## Deliverables

* A user-friendly web application that makes it easy for users to upload and share encrypted files, folders on the public decentralized storage network like IPFS/Filecoin using [Web3.Storage](https://web3.storage/) service.
* NEAR smart contract helps manage and share encrypted files, folders between users using **PriStorage** application.

## Development Roadmap

### 1. Development of NEAR smart contract

The NEAR smart contract written in Rust to provide the following functionality:

* Create folder, shared folder objects:
    * Folders are organized in the form of a tree to ensure flexible and convenient organization of files and folders for users.
    * With shared folders, the folder will be initialized with a password used to encrypt all files in the folder, so that when sharing the folder, the shared person can decrypt all files in the folder using the password.
    * With a common directory, each uploaded file will be encrypted with a randomly generated password from the web client, this password will be encrypted with the user's public key and stored on chain, this ensures that each file has its own decryption password and the decryption password of one file cannot be used to decrypt another file.
* Create file information objects:
   * File before being uploaded to IPFS/Filecoin will be encrypted with AES encryption algorithm. With files imported into a shared folder, the file will be encrypted with the password of the root folder of that shared folder. With files imported into a common folder, the web client will generate a random password and encrypt the file with that password, then the password will be encrypted with the user's public key and saved to NEAR storage.
* Retrieves file, folder infomation objects:
    * Return to web client an object when request with the file or folder id.
* Create shared file, shared folder objects:
    * Client retrieves file/shared folder information object and shared person's information is stored in NEAR storage, then encrypts secret information (password) and creates a shared object on NEAR storage with ecrypted private information that only shared person can decrypt it.

**Team:**

* Manh Nguyen Van - primary development
* Tuan Pham Minh - support engineering and code review

**Milestone budget:** $5,000

**Timeline:** ~15 days (~Nov 1 - Nov 15)

### 2) Development of `PriStorage` web application

This deliverable will create a web application by using [`create-near-app`](https://www.npmjs.com/package/create-near-app), and will provide the following functionality:

* File encryption and decryption: 
   * The web client uses AES encryption and decryption algorithms along with information obtained from NEAR storage to encrypt and decrypt files.
* Private information encryption and decryption: 
    * The web client uses the RSA asymmetric encryption algorithm to encrypt confidential information before creating a storage request.
* Preview: 
    * The web client decrypts the file, then creates a preview for the user instead of downloading the file to the device
* Download:
    * The web client retrieves file information object from NEAR storage, decrypts the secret information of object, then decrypts the file with the password from the decrypted object, finally downloads the file to your computer.

**Team:**

* Manh Nguyen Van - primary development
* Tuan Pham Minh - support engineering and code review

**Milestone budget:** $10,000

**Timeline:** ~15 days (~Nov 16 - Nov 30)

### 3) Deploy and operating `PriStorage` web application

This deliverable will create an deployment pipeline for `PriStorage` web application:

* Deploying smart contracts to the NEAR mainnet.
* Dockerize `PriStorage` web application and set up cloud hosting.
* Setup CI/CD and monitoring system for `PriStorage` web application.

**Team:**

* Manh Nguyen Van - primary development
* Tuan Pham Minh - support engineering and code review

**Milestone budget:** $5,000
**Timeline:** ~15 days (~Dec 1 - Dec 15)

## Total Budget Requested

Sum up the total requested budget across all milestones, and include that figure here. Ensure that it does not exceed the total funding limit on the RFP.

**Total:** $20,000

## Maintenance and Upgrade Plans

Our team has been developing this project for almost a month, and will continue to maintain this project for a long time, as long as the project is funded and continues to grow.

# Team
## Team Members

* Manh Nguyen Van
  * Email: manhnv@giong.network
  * Github: https://github.com/manhnvan
* Tuan Pham Minh
  * Email: tuanpm@giong.network
  * Github: https://github.com/iamvon

## Team Member LinkedIn Profiles

* [Manh's LinkedIn profile](https://www.linkedin.com/in/nguy%E1%BB%85n-m%E1%BA%A1nh-a55639224/)
* [Tuan's LinkedIn profile](https://www.linkedin.com/in/tuanpmhd)

## Team Website

* PriStorage Testnet Demo: https://pristorage.surge.sh

## Relevant Experience
* **Manh Nguyen Van**: Software engineer at Stringee JSC, Vietnam. Experience in working with libraries, SDKs, socket and services of blockchain flatforms like Ethereum, NEAR, IPFS, Filecoin.
* **Tuan Pham Minh**: Software engineer at Merchize HQ, Vietnam. Experience in working with libraries, SDKs, and services of blockchain platforms like Ethereum, NEO, Chia, IPFS, Filecoin.

## Team code repositories

* [PriStorage Repo](https://github.com/manhnvan/Pristorage)

# Additional Information
None
