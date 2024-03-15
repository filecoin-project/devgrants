# Open Grant Proposal: `CID Commenting`

**Name of Project:** CID Commenting

**Proposal Category:** `app-dev`

**Proposer:** [@siman](https://github.com/siman)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes, but we preffer GNU GPL v3.

# Project Description

The goal of this project is to create a decentralized platform on top of Substrate and IPFS that allows community to share interesting/important CIDs and comment on them. Think of it as a decentralized Reddit or Hacker News for IPFS.

Additionally it would be cool to show replication factor of the CID content and this stats can be part of the feed algorithm for "trending" or something like this. Maybe we can make the interesting pages with the content sorted in descending order by replication factor. In this way people will see some most used or needed content in IFPS.

## Value

Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:
- What are the benefits to getting this right?
- What are the risks if you don't get it right?
- What are the risks that will make executing on this project difficult?

This section should be 1-3 paragraphs long.

## Deliverables

- An open-sourced, dual-licensed (under MIT and APACHE2).
- Working decentralized web app to manage share and comment CIDs.
- Well-documented API for the service conforming to industry best practices. 
- Video-tutorial with demo usage. 
- Use Substrate and Rust on back-end and TypeScript on front-end.
- Well-documented, human-readable codebase.

## Development Roadmap

WIP... more details soon.

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
