# RFP Proposal: `Hedera/Filecoin NFT SDK`

**Name of Project:** `Hedera/Filecoin NFT SDK`

**Link to RFP:** [`Hedera x Filecoin`](https://github.com/filecoin-project/devgrants/blob/master/rfps/hedera-and-filecoin.md)

**RFP Category:** `devtools-libraries`

**Proposer:** [`SukuLab`](https://github.com/SukuLab), point of contact: [`lucashenning`](https://github.com/lucashenning)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `Yes`

# Project Description

This proposal addresses the scope of the [`Hedera x Filecoin`](https://github.com/filecoin-project/devgrants/blob/master/rfps/hedera-and-filecoin.md) request for proposals (RFP). The goal of this proposal is to build a decentralized storage Software Development Kit (SDK) that enables the seamless creation of Non-Fungible-Tokens (NFTs) based on [Hedera Token Service (HTS)](https://hedera.com/token-service) and Filecoin.

The SDK will be written in TypeScript and expose functionality to seamlessly access non-fungible tokenization that can be used to NFT-enable any sort of file (e.g digital art, music, JSON metadata, etc.). The SDK will interact with a Filecoin node and store files on the FileCoin/IPFS network. It will support storing very large files (up to 1 TiB). It may use a third-party library like [NFT.storage](https://nft.storage/) to facilitate FileCoin interaction.

One of the design goals is to use a standardized JSON Metadata Schema as described in [HIP-10](https://github.com/hashgraph/hedera-improvement-proposal/blob/master/HIP/hip-10.md). Metadata will be stored on Filecoin/IPFS and linked in the `tokenSymbol` of the HTS token. 

## Deliverables

The described functionality will be implemented as a JavaScript/TypeScript SDK that will be open source and shared via NPM. Additionally, this proposal aims to provide a backend service that makes the functionality accessible via a REST API. 

1. Filecoin & Hedera SDK delivered as NPM package for seamless integration into JavaScript/TypeScript projects.
2. Documentation of SDK functions, input parameters, and examples. Hosted as a github website based on a documentation framework (e.g. [Docsify](https://docsify.js.org/#/))
3. NodeJS sample app that leverages the SDK to expose its functionality via HTTP REST API. 
4. [OpenAPI Specification (OAS)](https://swagger.io/specification/) documentation for the REST API. 
5. Open source marketplace integration based on [Svelte](https://svelte.dev/) - This will show how this project can be used in a production environment, leveraging an injected wallet provider like [IV Wallet](https://github.com/nsjames/iv-extension).

## Development Roadmap

### Milestone 1: SDK
Timeline: `4 weeks`, Budget: `$40,000`, Team: `3 FullStack Engineers`
- Design and implementation of functionality for FileCoin and Hedera interaction, exposed as well-documented SDK functions, shipped as NPM package
- Typescript type definitions for all parameters and return values
- Unit tests written in Jest
- Integrate with third party services like [NFT.storage](https://nft.storage/) to facilitate FileCoin interaction.

### Milestone 2: API
Timeline: `3 weeks`, Budget: `$35,000`, Team: `3 FullStack Engineers`
- RESTful backend service that exposes the SDK functionality via API, written in TypeScript, based on [Nest.JS](https://nestjs.com/) 
- [OpenAPI Specification (OAS)](https://swagger.io/specification/) documentation for the REST API, including every endpoint, examples, and descriptions. 
- [Postman](https://www.postman.com/) collection to make integration easier, including test scripts

### Milestone 3: Real World Application - NFT Marketplace
Timeline: `5 weeks`, Budget: `$50,000`, Team: `3 FullStack Engineers, 3 UI Engineers`
- OpenSource NFT marketplace application that uses the SDK and API provided in milestones 1 and 2, based on [Svelte UI](https://svelte.dev/)
- External wallet integration with browser injected Hedera wallet for fund and NFT storage. This delivarable will leverage an injected wallet provider like [IV Wallet](https://github.com/nsjames/iv-extension).


## Total Budget Requested

`$125,000` in project funding divided into 2 sections as described in the RFP.

1. Total budget request for the first part of the RFP, including milestones 1 and 2 as described in [Decentralized Storage SDK](https://github.com/filecoin-project/devgrants/blob/master/rfps/hedera-and-filecoin.md#1-decentralized-storage-sdk-for-hedera--demo-application): `$75,000`
2. Total budget request for the second part of the RFP described in milestone 3 and requests in [Real-world Application](https://github.com/filecoin-project/devgrants/blob/master/rfps/hedera-and-filecoin.md#2-real-world-applications): `$50,000`


## Maintenance and Upgrade Plans

This SDK will be maintained and upgraded by SUKU INFINITE's development team, consisting of 10 FullStack engineers. 

It will be used in production for NFT Marketplaces built by INFINITE, including but not limited to http://infiniteworld.com

# Team

## Contact Info

Please contact [`lucashenning`](https://github.com/lucashenning) (lucas@suku.world)

## Team Members

- Lucas Henning, Technical Lead, [`lucashenning`](https://github.com/lucashenning), [LinkedIn](https://www.linkedin.com/in/luhenning/)
- Martin Kaczynski, Project Lead, [`mkaczynski11`](https://github.com/mkaczynski11), [LinkedIn](https://www.linkedin.com/in/martinkaczynski/)
- Matt Zamora, UI/UX Engineer, [`MattZ-2051`](https://github.com/MattZ-2051), [LinkedIn](https://www.linkedin.com/in/matt-zamora-95b38316b/)
- Joel Del Cueto, UI/UX Engineer, [`wayfaringjou`](https://github.com/wayfaringjou), [LinkedIn](https://www.linkedin.com/in/joel-del-cueto/)
- Federico Alvarez, UI/UX Engineer, [`federico710`](https://github.com/federico710)
- Will Olivera, Full Stack Engineer, [`wolivera`](https://github.com/orgs/SukuLab/people/wolivera)
- Gonzalo Torterolo, Full Stack Engineer, [`gonzatorte-infuy`](https://github.com/gonzatorte-infuy)
- Pedro Mauricio, Full Stack Engineer, [`pedromauricio07`](https://github.com/pedromauricio07)
- Gaston Nieves, Full Stack Engineer, [`gnieves-zircontech`](https://github.com/gnieves-zircontech)


## Team Website

https://suku.world/

## Relevant Experience

Our [team](https://suku.world/about-us) has been building a decentralized supply chain ecosystem that leverages DeFi protocols to enable transparency for conscious consumers over the past 4 years. In addition, we have created our own NFT marketplace which runs on Hedera’s hashgraph.  

As one of [Hedera's official partners](https://hedera.com/users/infinite-by-suku) and the creators of the largest NFT marketplace on Hedera, our team has the necessary experience and expertise to execute and deliver on a large project like this. With our team of experienced software engineers, we are ready to build a well-written and performance-optimized SDK that other projects can rely on. We accept HBAR as a payment option within our platform.  We want all of our partners in our ecosystem to benefit from our technical expertise and efficiency. 

Our team has delivered many software solutions for global clients such as [Cencosud](https://www.coindesk.com/new-blockchain-based-system-will-track-steers-from-hoof-to-plate), the largest grocery chain in South America. Additionally, we have exclusive partnerships with some of the world's most important players in their respective industries, like [Avery Dennison](https://rfid.averydennison.com/en/home/news-insights/press-releases/traceability-software-solution-from-suku-and-avery-dennison.html).

## Team code repositories

Repos: https://github.com/SukuLab

Documentation Sample: https://sukulab.github.io/documentation/#/

# Additional Information

We are looking to use the result of this project as part of  the foundation for the NFT marketplaces built on [INFINITE](http://infiniteworld.com). If this grant is approved, INFINITE and our other whitelabel marketplaces built on top of our NFT marketplace framework will be using this SDK (incl. FileCoin) to mint NFTs. We have significant traction with the business development opportunities for our NFT platforms, and the approval of this grant would create real world value for the Filecoin and Hedera communities. 

We estimate that each of our platforms will have at least tens of thousands of users, and generate tens of millions of dollars in primary and secondary sales. 

