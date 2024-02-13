# Open Grant Proposal: `OpenRPC pt.2`

**Name of Project:** OpenRPC

**Proposal Category:** `devtools-libraries`, `docs`

**Proposer:** `@belfordz`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** YES

# Project Description

OpenRPC is an API description language built for JSON-RPC. This project is to improve OpenRPC tooling such that filecoin can more easily generate and deploy documentation. As part of a previous devgrant, OpenRPC document generation was added to lotus, and has since been merged and released. 

At the moment, the https://github.com/open-rpc/generator can build documentation, however the depencies it is using need to be updated (new inspector version). We also lack a quick and dirty way to start auto-generating and deploying docs alongside github releases. This has made it a little cumbersome to get open-rpc documentation deployed for lotus. 

The generator also supports generating clients. The generated clients lack the ability to have headers be customizable. This is an issue for filecoin's api, which needs to be able to set the headers for auth. The clients are also cumbersome to generate/release automatically. 

Lastly, OpenRPC needs more depth in its testing tools. It's important to know the performance impact from one change to another, and the current test-coverage tool doesn't currently output any performance data. It lacks documentation / example use cases, making it unclear what to do with it. We are also lacking supporting scripts for such usecases. 

This is primarily to address the issues outlined in (this exploration document:)[https://github.com/protocol/w3dt-sudo/blob/lotus-openrpc/home/olizilla/2021-04-exploration-report-lotus-openrpc.md]


## Value

- What are the benefits to getting this right?

Filecoin will have best-in-slot documentation for its JSON-RPC api. A very large part of what makes it so good is having the inspector right inside the documentation. Also, having generated typescript clients automatically built and released when new lotus changes are released will take a lot of time-burden off the lotus devs. 

As for the testing side, it will become easier to catch large discrepencies in performance in CI. It will also create an easy way for multiple clients to ensure that they adhere to the cannonical OpenRPC document produced by lotus. We will have documentation around the usecases for the testing tool so that it will be clear how to add test cases, as well as how to integrate it within filecoin.

- What are the risks if you don't get it right?

We try again! There isn't anything too extravagant here that can go wrong. All the work involved is purely in complement to what already exists. No core changes will be required for this work.

- What are the risks that will make executing on this project difficult?

There is really very few risks, but if I had to pick one, I'd say the biggest risk would be getting the auth/api key part of the generated clients right. The nice thing is that it's easy to test.

## Deliverables

- Docs Generator
 - Update project dependencies
 - Updated UI (with new inspector, etc)
 - github action for generator:docs
   - configure where to deploy (s3 or gh-pages)
   - example project demonstrating it's use with the stat
   - example scheduled action which generates docs based on rpc.discover results
- Typescript client generator
 - updated deps
 - Support for configurable transports (allow setting of headers)
 - Support for configurable id type
 - github action for generator:client:typescript
- Testing tool
 - Output timing data (min, max, av. api call duration)
 - Documentation for how to use the tool
  - how to add test cases

## Development Roadmap

#### Milestone 1: Generator:Docs 

- Updating all the dependencies of the generated docs to resolve build issues & security updates.
- Generated result is using latest inspector and UI upgrades done for metamask openrpc docs.
- github action to generate docs and deploy them to s3 or gh-pages (with examples).

Estimated Effort: 56 hours, 1 person, 5600 USD

#### Milestone 2: Generator:Client

- Updated deps for ts client
- ability to configure the generated client allowing headers to be configured for filecoin api use
- gh action for typescript client generation & deployment
- copy-pastable code to enable generating and releasing clients when the api changes.

Estimated Effort: 48 hours, 1 person, 4800 USD

#### Milestone 3: Testing tool

- Testing tool
 - Output timing data (min, max, av. api call duration)
 - Documentation for how to use the tool
  - how to add test cases

Estimated Effort: 24 hours, 1 person, 2400 USD

## Total Budget Requested

56 + 48 + 24 = 128 hours, 12800 USD.

I can commit 20-30 hours per week starting 04/19/2021, making this a roughly 6 week project. The estimated completion date given the proposed start date would be 05/24/2021.

All funding will be used to pay the devs at Xops (my company, OpenRPC founders).

## Maintenance and Upgrade Plans

We are working out a way to secure long term funding for the various OpenRPC tools. If a long term agreement, with some sort of SLA/dev support is something that interests you, I'd love to chat about how to structure it best.

Aside from this, OpenRPC is built and maintained as a community and volunteering-lead effort. There is growing adoption of the OpenRPC spec & tools, which will fuel more contribution and maintanence over time. 

# Team

## Team Members

- Zachary Belford (@belfordz)

## Team Member LinkedIn Profiles

 - https://www.linkedin.com/in/belfordz/

## Team Website

 - https://xops.net/

## Relevant Experience

Xops built OpenRPC.

We've been building tooling in the blockchain space for 5 years now, having worked on wallets, dapp developer tools, and for the two years, JSON-RPC api tooling. 

## Team code repositories

all of the repositories under
https://github.com/open-rpc
https://github.com/xops

Many/most of the repositories under 
https://github.com/etclabscore

Most notably:
https://github.com/etclabscore/ethereum-json-rpc-specification

# Additional Information

Hope to talk soon - you can email me via belfordz66@gmail.com 
