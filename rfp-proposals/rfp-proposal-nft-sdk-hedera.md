

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
	- buy a NFT with HBAR (or FIL via trustwallet wip).
- Xact Checkout app (https://checkout.xact.ac) integrated with Xact Wallet SDK (https://docs.xact.ac)
	- Users can connect to the dApp through Xact Wallet.
	- Users can view their NFTs.
	- Each NFT’s Preview will be automatically stored on IPFS.
	- Users can sell any of their NFT. A Quantity and a unit price (in HBAR) must be defined.
	- Users can remove from sale their NFT anytime.
	- For each NFT for sale, a public checkout page will be created and be accessible publicly.
	- Users can buy a NFT by scanning a QR Code via Xact Wallet on the checkout page.

## Development Roadmap

First, we want to create a marketplace using multiple cryptocurrencies in the future. But first, we will have to add features to the SDK, for example, scheduled transactions.


|ID and title| Description budget and time | 
|--|--|
| 1 - design work | We will have to create a clean design, yet attractive so users can comprehensively create their NFTs, sell it, buy, bid. $15,000 - 1 month, October 2021
| 2 - integration of Xact Wallet | We will integrate Xact Wallet SDK, in order to use a secure interface with user's account for buying NFTs. $ 2,000 -  2 weeks, September/October 2021
| 3 - adding categories and collections for marketplace | We will add categories for NFTs on the marketplace, collections for artists/seller and filter on NFTs listed. For a better segmentation of available content. Also, we could add a part to showcase the "top" NFTs selling of the week for example. Idea is to present NFTs in an attractive way; $ 10,000 - 1/2 months October / November 2021
| 4 - support of HIP 17.x | We will add HIP 17.x support, to allow artists to add royalties to their NFTs. Crucial to bring artists from other NFT/Chains/Marketplace to HTS/Filecoin marketplace we are willing to build. $ 10,000 - 1/2 months  / November / December 2021
| 5 - auction/bidding system | Allowing users to auction their NFTs with Hedera. This will require a design work as well to optimize the experience for buyers and sellers. $ 15,000 - 2/3 months  /  December 2021
| 6 - more crypto currencies support | Allowing users buy in other cryptocurrencies than HBAR. $ 8,000/10,000 - 2/3 months  /  December 2021

Second, we are willing to develop further checkout.xact.ac app

## Development Roadmap Xact Checkout
Let's defined each features of the application
- Theme Switcher ( Dark and Light theme )
- Ability to connect through the Xact Wallet
- A User can Logout
- Check accountId and balance on the header
- List the NFT on the Home Page
  - If the NFT is an image then show the image
  - If Audio / Video / File / Unknown then show a placeholder image
- Sell a NFT Page
  - List details about the NFT
  - Complete the form in order to process the sale.
  - Wait for Xact Wallet validation before submitting the action.
<ins>Future Development :<ins>
We really want to push the main idea of this app forward. And enrich it with features and gamification. This simplicity in creating QR Codes to interface with Hedera Token Service / Filecoin NFTs allows us to plan the following developments:
<table>
  <tr>
   <td>ID
   </td>
   <td>Title
   </td>
   <td>Description
   </td>
   <td>Funding
   </td>
   <td>Estimated time frame
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>Multiple buy
   </td>
   <td>Ability to buy multiple quantities of a same NFT from checkout page.  \
 \
This will requires for us to change in our app the payment process with our Wallet SDK integration.
   </td>
   <td>$500
   </td>
   <td>2-3 weeks
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td>Design enhancement
   </td>
   <td>Refactor of the NFT listing page (seller view), to better display the NFT media (using masonry grid solution for example). This will require us to remake the CSS of Seller NFT listing page.
<p>
But also, enhancement of the sale form, making it even more user friendly.
<p>
And work on social media cards. (ability for user to setup their social media sharing cards)
   </td>
   <td>$500
   </td>
   <td>2 weeks
   </td>
  </tr>
  <tr>
   <td>3
   </td>
   <td>Create NFT
   </td>
   <td>Ability to directly create a NFT (HTS/Filecoin) from the app and to put it in sale right away.
<p>
We will have to integrate our NFT creation SDK (from Xact Wallet).
<p>
This will require also to integrate the new NFT-Type token introduced by recent HIP.
   </td>
   <td>$500
   </td>
   <td>1-2 weeks
   </td>
  </tr>
  <tr>
   <td>4
   </td>
   <td>Free NFTs give away page
   </td>
   <td>Ability to give NFTs, generating checkout pages with NFTs for free.
<p>
This could be used by artists / brands, to generate a QR code to give away a NFT to their community, securely.
   </td>
   <td>$500
   </td>
   <td>2-3 weeks
   </td>
  </tr>
  <tr>
   <td>5
   </td>
   <td>Adding FIL and other cryptocurrencies for payment
   </td>
   <td>Ability to buy NFT in FIL in addition of HBAR. This will require a FIL address from seller (to be paid in FIL), and a FIL wallet to be integrated for buyer, who will have to specify also a HBAR account id to receive NFT. This is a tricky development, which is needing Design process to be done first to make it simple and comprehensive for users.
<p>
This could require from us to update our Wallet SDK, or to integrate other wallets (trustwallet, coinbase wallet, mathwallet for example)
<p>
We think this would be a big step for a "cross chain" project, bringing people to know Hedera/Filecoin combination in NFT space.
   </td>
   <td>$5,000
   </td>
   <td>1-2 months
   </td>
  </tr>
  <tr>
   <td>6
   </td>
   <td>NFT giveaway on buying, with randomness
   </td>
   <td>Ability for seller to sell NFTs and including a % chance for buyer to win another NFT from the seller. \
 \
This could be done using Hedera Consensus Service, and later, Chainlink combined with Hedera Hashgraph.
<p>
This feature can help sellers to sell more NFTs, by adding a "gamification" side to the buying of their NFTs.
<p>
We would like to make the process friendly, and attractive, for both seller and buyer. So, a design process would be required as well (for styling/animation and for workflow).
   </td>
   <td>$5,000
   </td>
   <td>1-2 months
   </td>
  </tr>
  <tr>
   <td>7
   </td>
   <td>Royalties
   </td>
   <td>Ability to add Royalties for NFT selling (will require HIP 17.3 and some Hedera updates to allow this).
   </td>
   <td>$2,000
   </td>
   <td>1-2 months
   </td>
  </tr>
  <tr>
   <td>8
   </td>
   <td>Seller shops
   </td>
   <td>Ability for sellers to generate their own NFT shop, with all their NFTs currently in sale.
<p>
The "NFT shopify" based on Hedera Hashgraph and Filecoin. With the ambition to help users from other networks crossing the bridge to Hedera/Filecoin NFTs. \
 \
This will require us to make a unique design for the shops but also for the Shops creation process, and adding maybe customization options (different layouts, custom domain integration, ability to choose crypto currencies accepted etc..).
   </td>
   <td>$30,000
   </td>
   <td>2-4 months
   </td>
  </tr>
  <tr>
   <td>9
   </td>
   <td>Multilingual
   </td>
   <td>Adding support of more languages : French, Italian, Portuguese, Spanish, Chinese, Japanese, Russian..
   </td>
   <td>$1,000
   </td>
   <td>1 month
   </td>
  </tr>
  <tr>
   <td>10
   </td>
   <td>Marketing
   </td>
   <td>Marketing campaign setup to startup
   </td>
   <td>$5,000-10,000
   </td>
   <td>1-2 months
   </td>
  </tr>
</table>

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

We worked together for years in the development area. And for 10 months on the Hedera Hashgraph network. More precisely on the NFT area with Hedera Token Service. Very quickly, Hedera Token Service appeared to us to be powerful, inexpensive, and very well thought out. But when it comes to files, the solutions offered by Filecoin appeared to us to be the best. The combination of both networks is meaningful and participating in this RFP was obvious to us. We believe we can bring our creativity, our sense of design and UX to the service of both networks. With our RFP submissions, we want to bring sustainable and practical solutions to developers and users. 

Baptiste Hediard is a web designer working at Sylleb, CEO of this company based in France and established in 2016. With Sylleb, he worked on several App projects like Getsign.io (a e-signature SaaS), livemockups.com (a mockup generator SaaS), Yarea.io (a client portal creator SaaS). Recently, he designed the Xact Wallet App ([https://wallet.xact.ac](https://wallet.xact.ac)). The first Hedera Hashgraph wallet that allows users to preview their NFTs media (including the NFTs media stored on nft.storage/Filecoin storage IFPS) and to safely connect your Hedera Hashgraph account to dApps. This wallet is available on iOS and Android for free. In addition of these works, Baptiste Hediard works on crypto projects for 2 years, including NFT collection minted on Hedera Hashgraph, known as [https://www.hashgraph.cards](https://www.hashgraph.cards) and a NFT marketplace based on Zilliqa network, with NFT media stored also on IPFS, WafuSafu.com project. 

Vincent Schneider is a Freelance Fullstack developer for 7 years, mainly working with NodeJS and JS Frameworks. He worked on many projects, including mobile applications, backend and progressive web applications. He develops Xact Wallet, and it's open source SDK, available for developers willing to securely integrate the Xact Wallet to their dApps in order to accomplish actions such as Login, pay,.. 

## Team code repositories

[[https://github.com/orgs/Xact-Team/](https://github.com/orgs/Xact-Team/)](https://github.com/orgs/Xact-Team/](https://github.com/orgs/Xact-Team/))

# Additional Information

We deployed a version of demo marketplace app at [demo-marketplace.xactnft.io](https://demo-marketplace.xactnft.io/)
