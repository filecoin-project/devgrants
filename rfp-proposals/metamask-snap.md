# RFP Proposal: `Metamask plugin for Filecoin`

**Name of Project:** Filecoin MetaMask snap

**Link to RFP:** [Filecoin Wallet & Tools](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-filecoin-wallets.md)

**RFP Category:** `app-dev`

**Proposer:** [nodefactoryio](https://github.com/NodeFactoryIo/)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Recently most famous Ethereum web wallet [MetaMask](http://metamask.io) has introduced a plugin system called [snaps](https://github.com/MetaMask/metamask-snaps-beta/wiki). Snaps are therefore plugins that can be developed and used by (decentralized) applications with custom MetaMask behavior. This enables a opportunity to connect MetaMask to another blockchain networks such as Filecoin and easily onboard existing Ethereum users into Filecoin. 

We want to build a snap for Filecoin network where existing Ethereum users could get Filecoin addresses and therefore have a wallet that can:

 * generate Filecoin secp256k1 keys per app and possibly support BLS,
 * read and track user's FIL balance,

and have API methods exposed for dapps to be able to:

 * send and receive FIL,
 * sign custom messages,
 * display transactions history,
 * backup private key,
 * display notifications on transactions,
 * set custom remote Filecoin node URL.


## Deliverables

1. MetaMask snap codebase written in TypeScript with unit tests.
2. MetaMask snap build.
3. Documentation on snap.
4. Library for injecting wallet snap
5. Tutorial for app developers how to support snap.
6. Demo app for testing the snap.
7. Demo video.

## Development Roadmap

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | Generating Filecoin compatible keys and implementing read-only actions (display address, balance, transactions, backup) | 14,400$ | 3 weeks |
| 2 | Implementation of sending transactions and signing messages | 9,000$ | 3 weeks |
| 3 | Library release. Other project deliverables are being completed such as demo website, video and documentation.| 7,200$ | 2 weeks |
| 4 | Maintenance and upgrades for Testnet changes and Mainnet launch | 4,400$ | 2 weeks |

For the 1. and 2. milestone there will be 2 persons working full-time (snap developer and frontend developer) together with the project lead. 

For the 3. milestone 1 full-time person (frontend developer) and 1 full-time person (project lead) will be working on finishing all the deliverables.

Lastly, 4. milestone is reserved time for all the upgrades that will happen on Filecoin and possible MetaMask changes. Our goal is to have it working for the Mainnet launch and therefore do any upgrades that could happen by then.

Delivery of the project is planned to happen 2.5 months after the project's starting date, having taken into consideration that there are experimental and changeable APIs on boths sides.

## Total Budget Requested

35,000$

## Maintenance and Upgrade Plans

We are ready to maintain the implementation for this year and prepare for the mainnet launch. It's uncertain how much the MetaMask snap development will go and how many breaking changes to expect, but with the current pace we are positive we can make it.  

# Team

## Contact Info

NodeFactory is a blockchain research and development company based in Zagreb, Croatia. Being mostly fullstack developers and blockchain developers for the last 3 years, we are successfully providing services such as dapp development, infrastructure and tooling.


## Team Members

- [Belma Gutlić](https://www.linkedin.com/in/belmagutlic)
- [Marin Petrunić](https://www.linkedin.com/in/mpetrunic)
- [Mak Muftić](https://www.linkedin.com/in/mak-muftic-763650137)
- [Ivan Rubido](https://www.linkedin.com/in/ivan-rubido-917169151)
- [Nikola Mlinarić](https://www.linkedin.com/in/nikola-mlinari%C4%87-6159b1168)


## Team Website

[https://nodefactory.io](https://nodefactory.io)

## Relevant Experience

We already have experience with building apps on Filecoin as we have been a part of Wave 1 grant program. Project that we have built is Hactar, an analysis tool for miners, and it is currently in production as we have finished our last milestone.

Also, we have experience with MetaMask snaps as recently we've started working on snap for Polkadot network.

## Team code repositories

* [ChainGuardian](https://github.com/nodefactoryio/chainguardian) - Eth 2.0 validator desktop application 
* [Hactar main repo](https://github.com/nodefactoryio/hactar) - Filecoin miner analyzer 
* [js-libp2p-noise](https://github.com/nodefactoryio/js-libp2p-noise) - stream security transport for libp2p that's to be used in Eth 2.0 mainnet
* [MetaMask snap for Polkadot](https://github.com/NodeFactoryIo/metamask-snap-polkadot) - snap for dapps interactions on Substrate based chains
