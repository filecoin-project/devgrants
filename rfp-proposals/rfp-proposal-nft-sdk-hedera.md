

# RFP Proposal: NFT creation SDK and Demo Application

Name of Project: NFT creation SDK and Demo Application

Link to RFP: [https://github.com/filecoin-project/devgrants/blob/master/rfps/hedera-and-filecoin.md](https://github.com/filecoin-project/devgrants/blob/master/rfps/hedera-and-filecoin.md)

1 - Decentralized Storage SDK for Hedera & Demo Application

RFP Category: devtools-libraries, docs

Proposer: Xact-Team

Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?: Yes

# Project Description

We are building a Marketplace Demo Application with Open source SDK for creating NFT on Hedera Token Service and using Filecoin nft.storage API for storing files. The goal of the project is to provide for developers a practical SDK that use both Hedera Token Service and Filecoin Storage.

[https://github.com/Xact-Team/xact-sdk-js](https://github.com/Xact-Team/xact-sdk-js)  
[https://www.npmjs.com/package/@xact-wallet-sdk/client](https://www.npmjs.com/package/@xact-wallet-sdk/client)
[https://npmjs.com/package/@xact-wallet-sdk/nft](Xact Wallet SDK with Create NFT and much more which depends on third party API of Xact Wallet)
[https://github.com/Xact-Team/nft](Create NFT on Hedera Token Service/Filecoin)

We have built this SDK with Typescript.
  
[https://github.com/Xact-Team/demo-marketplace](https://github.com/Xact-Team/demo-marketplace)  
[https://github.com/Xact-Team/demo-marketplace-api](https://github.com/Xact-Team/demo-marketplace-api)

Marketplace demo application is using HTML/CSS and Tailwind CSS framework for styling, VueJS for front-end, Laravel (PHP) for backend.

## Deliverables

Deliverables are:
- a SDK for:
	-  create a token using Hedera Token Service and Filecoin nft.storage service (IPFS) for file storing,
- Integration of Xact Wallet SDK (https://docs.xact.ac) for:
	- associate a token,
	- transfer a token,
	- buy and sell a token in HBAR or FIL
- a SDK documentation for the NFT creation SDK ;
- a demo marketplace app, with:
	- homepage listing NFT in sale,
	- login,
	- create a NFT page, with a comprehensive workflow to create a token using HTS and Filecoin service,
	- sell a NFT,
	- buy a NFT with HBAR or FIL.

## Development Roadmap

We want to create a marketplace using multiple cryptocurrencies in the future. But first, we will have to add features to the SDK, for example, scheduled transactions.


|ID and title| Description budget and time | 
|--|--|
| 1 - design work | We will have to create a clean design, yet attractive so users can comprehensively create their NFTs, sell it, buy, bid. $15,000 - 1 month, October 2021
| 2 - integration of Xact Wallet | We will integrate Xact Wallet SDK, in order to use a secure interface with user's account for buying NFTs. $ 2,000 -  2 weeks, September/October 2021
| 3 - adding categories and collections for marketplace | We will add categories for NFTs on the marketplace, collections for artists/seller and filter on NFTs listed. For a better segmentation of available content. Also, we could add a part to showcase the "top" NFTs selling of the week for example. Idea is to present NFTs in an attractive way; $ 10,000 - 1/2 months October / November 2021
| 4 - support of HIP 17.x | We will add HIP 17.x support, to allow artists to add royalties to their NFTs. Crucial to bring artists from other NFT/Chains/Marketplace to HTS/Filecoin marketplace we are willing to build. $ 10,000 - 1/2 months  / November / December 2021
| 5 - auction/bidding system | Allowing users to auction their NFTs with Hedera. This will require a design work as well to optimize the experience for buyers and sellers. $ 15,000 - 2/3 months  /  December 2021
| 6 - more crypto currencies support | Allowing users buy in other cryptocurrencies than HBAR. $ 8,000/10,000 - 2/3 months  /  December 2021



## Total Budget Requested

$75,000

## Maintenance and Upgrade Plans

The maintenance of this software is planned to be maintained by Vincent Schneider and Baptiste Hediard. The upgrades have been defined above and will be processed through the year but can require extra time and some hiring. We thrive to listen for feedback and new features to add. This will for sure influence our development. For that matter we have created a page on Frill to collect feedback.

# Team

## Contact Info

-   [baptiste@hediard.io](mailto:baptiste@hediard.io)
    
-   [vincent.sder@gmail.com](mailto:vincent.sder@gmail.com)
    

## Team Members

-   Vincent Schneider (33 years old)
    
-   Baptiste Hédiard (31 years old)
    

## Team Member LinkedIn Profiles

-   Baptiste Hédiard : [https://www.linkedin.com/in/baptiste-hediard/](https://www.linkedin.com/in/baptiste-hediard/)
    

## Team Website

Our team is independant but, website of Baptiste Hediard company is https://www.sylleb.io

## Relevant Experience

We work together for years in the development area. And for 10 months on Hedera Hashgraph network. More precisely on NFT area with Hedera Token Service. Very quickly, Hedera Token Service appeared to us to be powerful, inexpensive, and very well thought out. But when it comes to files, the solutions offered by Filecoin appeared to us to be the best. The combination of both networks is meaningful and participating to this RFP was obvious to us.

We believe we can bring our creativity, our sense of design and UX to the service of both networks. With our RFP submissions, we want to bring sustainable and practical solutions to developers and users.

Baptiste Hediard is a web designer working at Sylleb, CEO of this company based in France and established in 2016.

With Sylleb, he worked on several App projects like Getsign.io (a e-signature SaaS), livemockups.com (a mockup generator SaaS), Yarea.io (a client portal creator SaaS).

Recently, he designed the Xact Wallet App ([https://wallet.xact.ac](https://wallet.xact.ac)). The first Hedera Hashgraph wallet allowing you to preview your NFTs medias (including the NFTs media stored on nft.storage/Filecoin storage IFPS) and to safely connect your Hedera Hashgraph account to dApps. This wallet is available on iOS and Android for free.

In addition of these works, Baptiste Hediard works on crypto projects for 2 years, including NFT collection minted on Hedera Hashgraph, known as [https://www.hashgraph.cards](https://www.hashgraph.cards) and a NFT marketplace based on Zilliqa network, with NFT media stored also on IPFS, WafuSafu.com project.

Vincent Schneider is a fullstack developer for X years, mainly working with NodeJS and Y.

He worked on many projects, including mobile applications XYZ, and on Vefa.io project, a progressive web application. He develops Xact Wallet, and its opensource SDK, available for developers willing to integrate securely the Xact Wallet to their apps to accomplish actions such as Login, pay,.. This SDK has been enriched especially for this RFP, by adding the possibility of creating an NFT on Hedera Token Service with media on IPFS, transfering a NFT with scheduled transaction, associating NFT… A documentation is available at [https://docs.xact.ac](https://docs.xact.ac) and a dev center is available at [https://dev.xact.ac](https://dev.xact.ac) for this SDK.

## Team code repositories

[[https://github.com/orgs/Xact-Team/](https://github.com/orgs/Xact-Team/)](https://github.com/orgs/Xact-Team/](https://github.com/orgs/Xact-Team/))

# Additional Information

We deployed a version of demo marketplace app at [demo-marketplace.dev.xact.ac](http://demo-marketplace.dev.xact.ac/)
