# RFP Proposal: `NFT market built on Filecoin and Hedera Hashgraph`

**Name of Project:** NFT browser using HTS and Filecoin’s decentralized storage service

**Link to RFP:** [Hedera x Filecoin RFP](https://github.com/filecoin-project/devgrants/blob/master/rfps/hedera-and-filecoin.md)

**Proposal Category:** `app-dev`

**Proposer:** `Hashgraph-Exchange`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `Yes`

# Project Description

We've designed an SDK that integrates the Filecoin storage service and Hedera Token
Service (HTS). This allows users to create non-fungible tokens (NFTs) with the ability to
store larger files (images, videos, JSON metadata, etc.) associated with HTS tokens on
the Filecoin network.

The proposed project will make it easier for developers to create Dapps without having
to do a deep-dive into the concepts of Filecoin and Hedera services, in-turn increasing
uptake and making implementation easier and efficient.

Hedera’s native file service (HFS) is inefficient for storing large files. The maximum file
size in HFS is only 1,024 KB and the overall limit of a transaction is only 6 KB, files
have to be broken into smaller chunks and multiple append calls have to be made to
store it on chain. This limitation made the process of creating NFTs using Hedera's HTS
and HFS time consuming and exorbitant.

To solve and overcome this, the project integrates Hedera Token Service(HTS) and
NFT.storage, which is a service backed by Protocol Labs and Pinata specifically for
storing NFT data.

NFT.storage provides an abstraction to simplify Filecoin integration. It can store NFT’s
up to 32GB in size and the process is naturally a lot faster than using HFS. Therefore in
using this approach we get more storage space and less time to upload files.
We believe that this will provide a fantastic user experience for creating NFTs on
hashgraph network, and due to this, once it becomes available, become a leading
provider in this technology space within a short period of time.

## Deliverables

We create a demo application that uses this SDK to build an open source end-to-end
NFT marketplace demo application that
1. Showcases the functionality of the Decentralized Storage SDK.
2. Can be used by other developers in the community as a reference architecture.
The demo application includes:
* NFTs created on Hedera.
* Multimedia associated with the NFT stored on Filecoin.
* JSON metadata schema associated with those NFTs on Filecoin.
* Accepting HBAR and FIL (at a minimum) for payment of NFTs.

Demo link: https://chrome.google.com/webstore/detail/hex/kiaflfdgfekdlghbhkimfmgdkmccoekm/related?hl=en

Instructions to Create NFT using Demo: 
1. `Create/Import` your Wallet
2. Click `Token` and select `Create Token` from the drop down
3. Select `Non Fungible Token` from the drop down
4. Select the necessary file and fill in the fields
5. Click `Create` and check the details in the dialog shown and Click `Confirm`
6. The file will be uploaded to the selected storage type.
7. The symbol for the Token will be FileId for Hedera or CID for Filecoin and you will be provided with a Hedera Token Id.
## Development Roadmap

Milestones:

M1 (Week 1 to 2) 
 * 3 developers
 * Requirements finalization
 * Initial SDK setup
 * SDK - Integrating Nft.storage to store metadata and file
 * SDK - Integrating HTS to issue NFT
 * Budget requested: $20,000
 * 
M2 (Week 3) 
 * 2 developers
 * SDK - Support for checking status of NFTs
 * SDK - Support for HEX extension
 * SDK Testing
 * Budget requested: $15,000

M3 (Week 4)
 * 2 developers
 * Demo Marketplace Application setup
 * Front-end for the demo marketplace application
 * Integrating the sdk with Front-end application
 * Demo marketplace Application Testing
 * Budget requested: $20,000

M4 (Week 5) 
 * 2 Developers
 * Regression testing
 * Bug fixes and Improvements
 * Deploying Demo Application
 * Budget requested: $20,000
## Total Budget Requested

$75,000

## Maintenance and Upgrade Plans

HEX is responsible for coordinating the continuous maintenance of the DAPP
components developed within the project, preserving at the same time their stability in
terms of interface and behavior, so that higher-level frameworks and applications can
rely on them.

Once a year the HEX team will produce a major release, characterized by a well defined
interface and behavior for each of its components. Interface and behavior are allowed to
change within a major release only in a backwards-compatible way.

Component releases are classified in major, minor, revision and emergency, based on
the impact of the changes on the component interface and behavior.

Requests for Change will be managed adopting a priority-driven approach, so that the
risk to compromise the stability of the software deployed in a production environment is
minimized. Requests for Change will also be properly monitored across the different
trackers adopted by the HEX team.

HEX is also responsible for coordinating the support to users of the DAPP components
developed within the project.

Both the Software Maintenance and the User Support are monitored through Key
Performance Indicators, outlined below -

* Automatic upgrades to the most up-to-date versions of the software, including major
releases and patches.
* Early access to Beta versions and the opportunity to test and suggest new features
before they are included in the final release.
* Premium technical support and prioritized incident management, including first
response to your issues within 1 business day, and usually much faster than that.
* Special promotions and discounts.

# Team

## Contact Info
jim@myhex.net

## Team Members

- Jim Gao
- Xavier Praveen
- Alex Peshevski
- Simon Jackson

## Team Member LinkedIn Profiles

- [Jim Gao](https://www.linkedin.com/in/jim-gao-a93369207/)
- [Xavier Praveen](https://www.linkedin.com/in/xavierpraveen/)
- [Alex Peshevski](https://www.linkedin.com/in/alzoo/)
- [Simon Jackson](https://www.linkedin.com/in/simon-jackson-72856aa3/)

## Team Website

https://myhex.io/

## Relevant Experience

Involved with Hedera since 2018, the Hashgraph Exchange (HEX) team worked on
world’s first hashgraph-based DEX, and launched its alpha version during Hedera’s
Open Access (OA) on 9/16/2019. After the inception of Hedera’s token service in Q1 of
2021, the HEX team completely revamped the design and architecture of its DEX, and
won the third place in Hedera21 hackathon.

We are among the first teams in the Hashgraph ecosystem to:

  * Enable users to create an account on Hedera mainet without going through KYC;
  * Enable users to create, add, send and receive HTS based tokens (both fungible
    and non-fungible) through their Hedera accounts.
  * Swap between hbars and HTS tokens
  * Implementing the bridge between Hedera and the Ethereum network
  * Enabling hbar custody solution by implementing a functional hardware wallet

## Team code repositories

[https://github.com/Hashgraph-Exchange/NFT-Browser](https://github.com/Hashgraph-Exchange/NFT-Browser)

# Additional Information

You can try out the latest version of the Chrome based DEX at 
[https://chrome.google.com/webstore/detail/hex/kiaflfdgfekdlghbhkimfmgdkmccoekm/related?hl=en](https://chrome.google.com/webstore/detail/hex/kiaflfdgfekdlghbhkimfmgdkmccoekm/related?hl=en)
