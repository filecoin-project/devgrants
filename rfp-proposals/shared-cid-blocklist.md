# RFP Proposal: `Shared Blocklists of Content CIDs`

**Name of Project:** Shared Blocklists of Content CIDs

**Link to RFP:** [Shared Blocklists of Content CIDs](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-4-rfps.md#shared-blocklists-of-content-cids)
`
**RFP Category:** `app-dev`

**Proposer:** [@siman](https://github.com/siman)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes, but we preffer GNU GPL v3.

# Project Description

The goal of this project is to create registry for sharing CID block lists on Substrate.

We are going to keep the list of blocked CIDs in Substrate runtime storage.
This will allow blockchain logic of Substrate modules (pallets) and smart contracts access the block lists
and make their own decision whether they want to accept the CIDs that are blocked here or there.

Such blocking functionality need specific extrinsics (transaction functions in terms of Substrate) to manage the lists of CIDs:
- block_cids(space_id, cids)
- unblock_cids(space_id, cids)
- how many times has CID been blocked?
- get the list of space ids that blocked this CID

Additionally I would implement a management of trust list of CIDs.
For example there could be some authorities that represent law enforcement of a country
and maybe they will come up with decisions on some controversial CIDs.
Then they would be able to add those CIDs to their space and others could refer to the trust lists when they are unsure about the CID.

I would also make it possible to use an enum to specify a block reason: Spam, Child abuse, Hate speech, etc.
Only having this info about trusted/blocked CIDs on chain would allow to use them in blockchain logic or in smart contracts on Substrate.

Also we have created flexible Roles and Permissions modules where the space owner can specify what account could manage block lists. This is also an essential feature because it allows to create for example "Content Moderator" role, grant it to some accounts and they will be able to block and/or unblock and/or make trusted CIDs.

## Deliverables

- An open-sourced, dual-licensed (under MIT and APACHE2).
- Working decentralized web app to manage CID blocklists.
- Well-documented API for the service conforming to industry best practices. 
- Video-tutorial with demo usage. 
- Use Substrate and Rust on back-end and TypeScript on front-end.
- Well-documented, human-readable codebase.

## Development Roadmap

WIP... will commit a bit later.

## Total Budget Requested

$20000

## Maintenance and Upgrade Plans

We will maintenance and upgrade the solution such as we are planning to use it in Subsocial protocol.

# Team

## Team Members

**Alex Siman** – Software Architect and Project Manager at Subsocial. Alex is a Polkadot Ambassador, a founder of “Polkadot Ukraine”. He has been building complex web apps since 2008. In 2017, he started to write smart contracts on Solidity and integrate them with dapps. Since 2019 he has been developing Substrate modules and building custom UIs for them with Polkadot API. Links: [GitHub](https://github.com/siman).

**Oleg** – Front-end Developer (TypeScript, React). Oleg develops UI for Subsocial. His main contribution to this project can be found in Subsocial UI repo:
https://github.com/dappforce/dappforce-subsocial-ui/commits?author=mell-old

**Vlad** – Back-end Developer (Rust, C++). Vlad writes SRML and tests for Subsocial. His main contribution to this project can be found in Substrate runtime repo:
https://github.com/dappforce/dappforce-subsocial-runtime/commits?author=F3Joule

## Team Member LinkedIn Profiles

[Alex Siman](https://www.linkedin.com/in/alexsiman/)

Oleh and Vlad don't have LinkedIn accounts.

## Team Website

[DappForce dev team](https://github.com/dappforce)

## Relevant Experience

Alex Siman (the author of this proposal) is a founder and CTO of [Subsocial](http://subsocial.network/) – an open protocol for decentralized censorship-resistant social networks built with Substrate and IPFS. Our development is supported by **Web3 Foundation** grants program and we are particiapant of **Substrate Builders Program** from Parity. We already use IPFS in our architecture: when people write posts and comments, first, their content get stored in IPFS and then we create the entry for every post/comment in Substrate with provided IPFS CID of their content.

## Team code repositories

[DappForce](https://github.com/dappforce)

# Additional Information

[Subsocial protocol](http://subsocial.network)
