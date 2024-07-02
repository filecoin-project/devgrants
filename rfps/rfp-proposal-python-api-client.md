# RFP: `Python Standard Library & File Storage Tools`

**Name of Project:**

Python Standard Library & File Storage Tools

**RFP Category:** `devtools-libraries` and `app-dev`

**Proposer:** @fern-xian @s1eke

## Project Description

We (KJ Planet) have closely followed the updates of the Filecoin project ever since it first became known to the world.  At present, the core technology of the project is rapidly iterating. We have  noticed that besides the rapidly developing core technology of Filecoin, its ecology is being actively constructed as well. We would love to integrate our resources and contribute to the ecosystem of such a great project.

There are two parts of our proposal which are as the following:

Part 1: We plan to develop a lotus standard library with python, which will be published on github.com under the MIT and Apache open source agreement. This is the most convenient way for Python developers to use Filecoin. Introducing this open source library into the code gives it the ability to call Filecoin functions, including network, storage, wallet, and other Filecoin functions. It must be mentioned that transactions and signatures are important parts of the blockchain system and also a matter of user privacy, so they must be kept private. With that in mind, we will use python to implement a function to build and sign transactions. But this is not a python version of lotus. It still needs to connect to a node to communicate with the Filecoin network.

Part 2: We plan to develop a file storage tool based on the Python standard library of lotus which will be published on github.com under the open source agreement of MIT and Apache. The goal is to make this tool user-friendly and easy to use through the UX interface. The tool supports storage transactions, upload resume through breakpoints, redundant calculations, file encryption, file lists, and file download. Users will be able to access the WEB UI through the browser to log in to this tool and temporarily store their files to the server. After redundancy and encryption process, the data will then be stored in the network through the Filecoin nodes. All operations and privacy are completely in the hands of the users. We do not save any private data of the users and do not enforce encryption of the data. We are exploring a user identification method that does not require registration (to further protect user privacy). The plan is that the users will provide a private key signature as identification. Once a user is identified, a file list will be displayed and a file download function will be provided. Developers can freely modify and deploy this project to add features or meet certain personalized needs.They could also choose to allow or restrict public access.
 
Help needed: since the Filecoin project is still under development, we would need to communicate with your team to understand what changes there might be in the future that could potentially impact the design and definition of storage and user data.

## Value

**Python Standard Library**

python standard library provides a channel for developers in the ecosystem to easily connect to Filecoin. Even for python developers who are not familiar with Golang or in lack of an overall understanding of Filecoin, with the help of this library, they could work on Filecoin without having to spend too much time on basic knowledge. We believe that as Filecoin continuously develops, it will attract more and more python developers to join and grow the ecosystem. Therefore, the python standard library is a must. 

**File Storage Tool**

File storage tool is a client for ordinary users. It creates a convenient and user-friendly file storage channel for users to store data on Filecoin network. Easy operation, rich functions and high-level privacy provides users with safe and reliable services. The tool will be maintained by the development team. Users could also host and make improvements as they feel like.

## Deliverables

**Python Standard Library**

* A complete design document including general module, function design, package, dependencies, roadmap, etc. which will be published on github.com public repository
* Complete function codes, notes and public github repo. Detailed notes on each crucial export function.
* A complete development manual and visual documentation generated based on code comments. Both will be published on github.com public repositary.
* A complete test document including test cases and reports.
* Unit tests with a coverage rate of 85%.


**File Storage Tool**

* A complete system design document including function design, UI design and server-side processing logic.
* A complete UI design document including prototype drawing and effect drawing.
* A complete user manual in PDF and github.com MD format.
* A complete RPC development manual in PDF and github.com MD format.
* Complete codes and public github repository.
* A complete test document including test case and reports.
* Unit tests with a coverage rate of 85%.

## Recommended Team

* **Xiang, Jie**

	Worked on the development of core blockchain projects at OneThingTech, HyperChain and Tecent. He has more than 10 years of experience developing background servers and is proficient in c/c ++, golang, python, lua and other coding languages. Experienced in public chain development based on BTC, ETH, EOS, Dash and BTS.
	
* **Sean Fang**

	Senior DevOps, responsible for CI/CD pipeline. Has a rich experience in python and golang development and an in-depth understanding of distributed file system.


## Detailed Requirements & Constraints

**Python Standard Library**

Python standard library is a package for lotus' HTTP interface. Developers are faced with python functions that call filecoin functions in the simplest way. The lotus standard library follows the RPC standard request mode of filecoin. The parameters of the function are passed to the lotus node through HTTP Post requests and wait for the data returned by the node.

Module List

* General public modules including http client, logs, common error handling and other tool definitions.
* Comm API:common APIs are defined corresponding to lotus api_comm.
* Full API:the APIs of a full node is defined corresponding to lotus api_full and are used to perform the funtions of a full node. They can be used to develop softwares related to blockchains, wallets and trasactions.
* Storage API: the APIs of storage miner are defined corresponding to api_storage and are used to perform the functions of storage miners. They can be used to develop APPs on miner management, operation and maintenence and other monitoring softwares.
* Construction of signing of storage trades: this module will not depend on the functions of lotus node. Instead, complete trades will be constructed and then broadcast over Filecoin network through lotus nodes.
* General configuration

Items:

* API permission control including read, write and admin.
* Lotus node token
* Lotus node address

**File Storage Tool**

User client

* WEB UI for PCs: supports mainstream browsers(Chrome，Firefox，Safari and Edge). Maintain a uniformed interface and easy to use.
* WEB UI for mobiles: supports iOS and Android system. Maintain a uniformed interface and easy to use.
* Both client ends include 4 pages：registration, log in, home and settings.

Funtion list

* User verification, currently we are considering using a private key signature to verify a user's identity and to obtain the user's file list and other data. At the same time, if the user login function is turned on, each user only needs to complete the signature verification at the very first time.
* User registration：disabled by default
* User login: login with valid user name and password. disabled by default. This function is designed for those who would like to make a private/limited service with this tool instead of making it public. For example, an enterprise might set up this tool and only provide the service to its staff and clients. Anyone without an assigned and valid account will not be able to access the service. 
* User registration restriction: service providers could decide to enable or disable new user registration function. 
* User login restriction: service providers could decide to enable or disable user login function. 
* Remember Me: users could choose to record encrypted local data in the browser and recover the data through certain forms of password(such as public key, user address, etc) so that users do not have to provide identity verification data repeatedly in a rather short time period. 
* File upload: users select the files they would like to be stored from the current device and click the upload button to transfer the data to the server. It supports the file breakpoint resume function to avoid repeated transmission of large files due to network failure or other possible reasons.
* List of stored files: shows the files that the current user has stored on Filecoin network including key information such as file name, size, storage duration, cost, redundancy method, encryption method, etc.
* The list of unstored files: shows the list of files currently stored in the server but not yet stored on the filecoin network, including key information such as file name, size, and temporary storage period.
* File storage: upon users' choice, the system will divide, encrypt, and calculate redundantof their files. A storage trade will be initiated based on the storage agreement reached by filecoin storage miners. The temporary files will be deleted from the file system according to the configuration parameters after the storage trade is verified to be valid. A storage operation may generate multiple storage transactions and match one or more miners. The storage operation may take a few minutes or longer, so we need another program to monitor whether all storage transactions have been completed to ensure that the files are correctly stored on the filecoin network.
* File download: provides direct download links and for files that have been stored on the filecoin network. The server obtains the stored data fragments from the filecoin network and transfers them to the users after restoration calculation. The restoration process may include redundant restoration, decryption, and combination to obtain the original file. The process may vary since users might have made different choices while making the storage trade.
* File deletion: deletes temporary files that users do not wish to be stored on the filecoin network from the server. This function cannot delete files that are already stored on the filecoin network.
* File encryption: our current plan is to support PGP, ECDSA asymmetric keys and symmetric encryption methods such as AES.
* File redundancy: supports zero redundancy, backup redundancy and erasure code redundancy.
* Miner price: obtain the storage price of miners from the storage market and calculate the optimal storage plan to reach a storage agreement.
* Cost calculaton: estimate the users' payment for storage based on encryption method, redundancy mode, and miner price selected by the user.

Module list:

* User module: includes user verification, user registration and login.
* File module: includes file upload and download and initiate stroage trades.
* Trade module: to construct storage trades and trasactions and sign.
* Redundancy module: used for erasure code processing and redundancy cost calculation.
* Encryption module: used for symmetric and asymmetric encryption modules.
* Miner price tasks: automatically update the price of miners. Obtain miner information and prices  from the storage market and Filecoin network and update to the database.
* File monitoring tasks: automatically monitor files that have temporarily expired and are deleted from the file system.
* Transaction monitoring tasks: automatically monitor the latest status of initiated but unfinished stored transactions. Call the Python standard library to obtain the storage transaction credentials from the lotus node and update to the database.
* RPC module

Configuration:

* File temporary storage period: the value is a positive integer with the default value of 0. Set the time limit for files to be temporarily stored on the server. A value of 0 means never delete, otherwise the temporary files will be automatically deleted after they are stored on the filecoin network for a certain time period, eg. days (d), hours (h), and minutes (m). 
* File temporary directory: the value is a string of the file system directory. The directory where the files are temporarily stored on the server can be set as a local hard disk directory or a distributed file system mount directory.
* Whether or not to initiate user login function: the value could be "true/false". The default value is "false". When the value is "true", only valid logged-in users could use the functions of the tool.
* Whether or not to initiate user registration function: the value could be "true/false". The default value is "false". When the value is "true", new users could register.


## Milestones & Funding

**Total Funding Amount:** $43480

Total Budget Requested for Part 1:

| Role| Rate/Hr | Man-Hour | Man-Week | Price |
| --- | --- | --- | --- | --- |
| Arch | $60 | 64 | <2 | $3840 |
| Dev | $40 | 360 | 9 | $14400 |

Total Budget Requested for Part 2:

| Role| Rate/Hr | Man-Hour | Man-Week | Price |
| --- | --- | --- | --- | --- |
| Arch | $60 | 160 | 4 | $9600 |
| UX | $25 | 40 | 1 | $1000 |
| Front-end Dev | $35 | 80 | 2 | $2800 |
| Back-end Dev | $40 | 560 | 14 | $22400 |
| Test | $20 | 120 | 3 | $2400 |



**Milestones:** 

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | completion of design document | 20% | 3 weeks |
| 2 | completion of python standard library | 25% | 4 weeks |
| 3 | completion of file storage tool development | 40% | 6 weeks |
| 4 | Final delivery| 15% | 2 weeks |
## Acceptance Criteria

**Acceptance criteria for milestone 1:completion of design document**

* python design document
* design document of file storage tool
* UI prototype drawing and effect drawing of file storage tool
**Acceptance criteria for milestone 2:completion of python standard library**

* complete source codes; open-source github repository
* Unit tesets with a coverage rate of 85%


**Acceptance criteria for milestone 3:completion of file storage tool development**

* complete source codes; open-source github repository
* A complete test document including test cases and reports.


**Acceptance criteria for milestone 4:final delivery**

* A complete development manual of python standard library.
* Complete test cases and reports of python standard library.
* A complete users' manual of the file storage tool in the formats of PDF and github.com MD.
* A complete RPC development manual of the file storage tool in the formats of PDF and github.com MD.
* Complete tese cases and reports of the file storage tool.

## Resources

* [https://www.tiobe.com/tiobe-index/](https://www.tiobe.com/tiobe-index/)
* [EOS side chain](https://github.com/BankLedger/safecode.contracts/tree/v1.7.0-safecode.f3sf5)
* [hard-fork public chain based on dash](https://github.com/BankLedger/safe)
* [A decentralized exchange based on bts](https://github.com/knowhowchain/knowhowchain-core)