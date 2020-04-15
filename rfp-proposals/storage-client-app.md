# RFP Proposal: `Storage client application with erasure coding and basic PGP`

**Name of Project:** Store Decentralized app

**Link to RFP:** [New RFP Ideas for Wave 3](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#storage-client-application-with-erasure-coding-and-basic-pgp)

**RFP Category:** `app-dev`

**Proposer:** [nodefactoryio](https://github.com/NodeFactoryIo/)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Web application that should enable users to encrypt data, share it with someone else and store it in decentralized way with several miners. User has also the ability to retrieve and decrypt the data. Also, the app would suggest an ideal number of redundant storage deals using erasure coding. Should be easy to use and mobile friendly.

The goal is not only to create an app where user can store own files but also that user can send another user an encrypted file. This can be done in multiple way, but we opted for existing solutions that are already familiar to crypto users - Keybase and MetaMask. Using Keybase user would login using existing Keybase account, while using MetaMask users would first need to "register" (generate PGP keys) inside the app. Registration part would include 3box profile where we could store public PGP key info.

This app is intended for end users that can be either Filecoin newcomers or existing Filecoin users. Therefore, we will have strong focus on the UX and configuration flexbility for advanced users. Planned features are:

 * generate wallet or connect to existing
 * upload a file (use IPFS as hot storage)
 * encrypt and decrypt a file for a file owner
 * encrypt and decrypt a file for an another user using PGP keys (from Keybase or generated using MetaMask)
 * retrieve stored file (using shared link) and decrypt it 
 * calculate recommended redundancy so data can be reconstructed if a copy cannot be retrieved
 * list available miners 
 * enter into a multiple number of storage deals
 * list stored files with deals details
 * connecting to a public Filecoin node API

This is planned to be a single web app made in a decentralized way without any extra backend infrastructure. However, there is a possibility to have some workarounds until that is achieved depending on the rest of Filecoin infrastructure development.


## Deliverables

1. Frontend application codebase built using React, TypeScript
2. Documentation
3. UI and UX design

## Development Roadmap

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Research. Created clear specification and functional requirements document. Responsive UI and UX design. Integration of the design in the React app. | 4,200$ | 3 weeks |
| 2 | Integrating the flow of listing miners, recommending and making deals, creating redundancy, making payment, file uploading, storing and retrieving. | 21,000$ | 4 weeks |
| 3 | Integration of encryption using MetaMask and 3box.| 7,200$ | 2 weeks |
| 4 | Integration of encryption using Keybase.| 3,600$ | 1 week |
| 5 | Maintenance. Upgrades for Testnet changes and Mainnet launch and keeping up with other used libraries. | 3,000$ | 1 year |

For the 1. there will be 2 persons working full-time (project lead and frontend developer) together with the UI/UX designer. The output of this milestone is to have a clear understanding of how app will look like and to have clear understanding on how it will be integrated. This also includes a research on things that we want to achieve, testing signing transactions and file transfers.

For the 2. milestone the goal is to have the whole flow done for the storage of unencrypted files. There will be 2 developers working full-time on this milestone with the help of a senior lead. This is the milestone where most of the work will be done in terms of development, integration and research. 

For the 3. and 4. milestone 2 full-time developers will be working on file encryption services. The goal of this milestone is to have the possibility to encrypt own files or share it encrypted with someone else. This includes handling PGP keys for the user.

Lastly, 5. milestone is reserved time for all the upgrades that will happen on Filecoin and potentially (most probably) other dependencies. 

For the project development, deployment, QA and final delivery we estimate it will take 2.5 months.

## Total Budget Requested

39,000$

## Maintenance and Upgrade Plans

The app shouldn't have much infrastructure is that part won't need much effort to handle. Frontend app will be deployed using IPFS. Also, this is not our only Filecoin app so we have no problem keeping up to date with Filecoin network updates and tools.

# Team

## Contact Info

NodeFactory is a blockchain research and development company based in Zagreb, Croatia. Being mostly fullstack developers and blockchain developers for the last 3 years, we are successfully providing services such as dapp development, infrastructure and tooling.


## Team Members

- [Belma Gutlic](https://www.linkedin.com/in/belmagutlic)
- [Marin Petrunic](https://www.linkedin.com/in/mpetrunic)
- [Mak Muftic](https://www.linkedin.com/in/mak-muftic-763650137)
- [Ivan Rubido](https://www.linkedin.com/in/ivan-rubido-917169151)
- [Nikola Mlinaric](https://www.linkedin.com/in/nikola-mlinari%C4%87-6159b1168)


## Team Website

[https://nodefactory.io](https://nodefactory.io)

## Relevant Experience

We already have experience with building apps on Filecoin as we have been a part of Wave 1 grant program. Project that we have built is [Hactar](https://www.hactar.app), an analysis tool for miners, and it is currently in production - [https://analytics.hactar.app](https://analytics.hactar.app).

## Team code repositories

* [ChainGuardian](https://github.com/nodefactoryio/chainguardian) - Eth 2.0 validator desktop application 
* [Hactar main repo](https://github.com/nodefactoryio/hactar) - Filecoin miner analyzer ([Hactar design](https://www.figma.com/file/2BthZmt2srozgShWtOdSe3/Hactar-Copy?node-id=182%3A39))
* [js-libp2p-noise](https://github.com/nodefactoryio/js-libp2p-noise) - stream security transport for libp2p that's to be used in Eth 2.0 mainnet

# Additional Information

For the development of this project we'd like to use as many as possible existing tools and libraries from the Filecoin ecosystem such as [signing library](https://github.com/zondax/filecoin-rs), [JS lotus client](https://github.com/filecoin-shipyard/js-lotus-client) and [wallet provider](https://github.com/openworklabs/filecoin-wallet-provider). This would save us time by not reinventing the wheel and supporting other projects with feedback. 

Since there is currently no JavaScript libraries that deal with storage and deal management, we might contribute in that area and extract some pieces into the open source library.
