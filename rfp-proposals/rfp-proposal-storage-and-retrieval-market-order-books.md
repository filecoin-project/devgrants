# RFP: `Storage and Retrieval Market Order Books`

**Name of Project:** Storage and Retrieval Market Order Books

**Link to RFP:**
[Storage and Retrieval Market Order Books](https://github.com/filecoin-project/devgrants/blob/89d4a4284675120bfff84da844027ff674bcc313/rfps/new-wave-3-rfps.md#storage-and-retrieval-market-order-books)

**RFP Category:** `app-dev`

**Proposer:** `@sahilnanda1995`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:**
Yes!

# Project Description

Although storage deals are on chain, storage market asks in which miners create price offers for their storage are off chain in Filecoin.

We want to build a single operator service that will aggegrate data around storage and retrival asks helping the storage clients seeking to make deals and increase global awareness around pricing.

## Deliverables

- A service that:

  - queries all Storage Miner Actors for their current `StorageAsk`.
  - Aggegrates the above data to create historical records.

- An API for the above service:

  - conforming to industry best practices.

- A user interface for the above endpoints:

  - Home Page:
    - Table displaying Storage Miner storage ask + various analytics.
  - Specific Storage Miner `StorageAsk` history:
    - Clicking on a particular storage miner entry on the home page opens this page.
    - Shows trends in `StorageAsk` fluctuation of the particular storage miner.

- Tutorial workflow with demo usage.
- Well-documented, human-readable codebase.

## Development Roadmap

### Milestone 1: Getting vantage 🤔

1. Scope of service:

   - Finalizing API Spec Sheet.

2. and how to go about building the service:
   - Architectural design vantage of the service.

People involved:

- Lead Developer (full-time).
- Filecoin Researcher (full-time).

Duration: 1 week
Funding Required: \$3,840

### Milestone 2: #buidl-ing the service

1. Building indexer to query StorageAsk from Filecoin node.
2. Writing an API wrapper on the above indexer.

People Involved:

- Lead Developer (full-time).
- Filecoin Researcher (part-time).

Tech Specs:

- Backend scripts written in Go
- SQLite3 as database

Duration: 2 weeks
Funding Required: \$5,740

### Milestone 3: 🐶-fooding the service:

A StorageAsk Insight UI for the above endpoints:

1. Home Page:
   - Table displaying Storage Miner storage ask + various analytics.
2. Specific Storage Miner `StorageAsk` history:
   - Clicking on a particular storage miner entry on the home page opens this page.
   - Shows trends in `StorageAsk` fluctuation of the particular storage miner.

People Involved:

- Lead Developer (part-time).
- Frontend Developer (full-time).

Tech specs:

- Reactjs
- [ChakraUI](https://chakra-ui.com/) for UI framework
- [Victory](https://formidable.com/open-source/victory/) for charting.

Duration: 1 week
Funding Required: \$1,920

### Milestone 4: 🧐 + 🛠 stage.

- Production deployment.
  - Publish the code repository
  - Finish writing documentation
    - Detailed readme explaining how to run, test and deploy the application.
- Codebase documentation.
- Q/A to ensure robustness.
- Migrate repositories to the Filecoin Shipyard.

People Involved:

- Lead Developer (full-time).
- Filecoin Researcher (part-time).

Duration: 1 week
Funding Required: \$1,920

## Total Budget Requested

| Milestone No. | Milestone Description                   | Funding  | Estimated Timeframe |
| ------------- | --------------------------------------- | -------- | ------------------- |
| 1             | Getting vantage 🤔                      | \$3,840  | 1 week              |
| 2             | Backend API service                     | \$5,740  | 2 weeks             |
| 3             | Basic UI                                | \$1,920  | 1 week              |
| 4             | Documentation + Testing and Adjustments | \$1,920  | 1 week              |
| **Total**     |                                         | \$13,420 | 5 weeks             |

## Maintenance and Upgrade Plans

Maintenance:

- After project completion, maintaining and iterating on user feedback on the system actively for the next 3 months. Bug fixes, if any.
- For 1 year: support if the system goes down.

Upgrade Plans:

As we approach mainnet launch, feedback from storage clients will help us better tailor the pricing proposal. We plan to analyze the network activity and incorporate the highly requested use-cases in the tool.

# Team

## Contact Info

Email: sahil@buidllabs.io

## Team Members

- Filecoin Researcher: Sahil
- Backend Developer: Saumay
- Frontend Developer: Bhaskar
- DevOps: JP

## Team Member LinkedIn Profiles

- Sahil: https://www.linkedin.com/in/sahil-nanda-8b1b88143
- Saumay:
- Bhaskar: https://www.linkedin.com/in/bhaskar-singh-55a535b9/
- JP: https://www.linkedin.com/in/jayprakashjp/

## Team Website

[BUIDL Labs](https://buidllabs.io/)

## Relevant Experience

Our team is currently deep diving into understanding incentives for participation for core actors involved in upcoming projects that use PoS. Filecoin is one of the most ambitious projects to launch in this year and would provide a lot of exciting opportunities to understand user adoption and the challenges they face while operating in such a novel paradigm.

We see this proposal as an opportunity to observe the network evolution more closely by building tools that we ourselves would use + helping the community at large.

Brief info about the team members:

- Filecoin Researcher: Sahil

  - Budding Filecoin protocol researcher + Go Developer.
  - Built [PolkaViz](https://polkavizproject.surge.sh/). Before that built algorithmic trading strategies for a crypto hedge fund.
  - [GitHub](https://github.com/sahilnanda1995)

- Backend Developer: Saumay

  - Extensive experience in wrangling data and building ETL pipelines, Go Developer.
  - Finishing up building: [Livepeer Pricing Tool](https://github.com/buidl-labs/livepeer-pricing-tool)
  - [Github](https://github.com/Saumay-Agrawal)

- Frontend Engineer: Bhaskar Singh
  - Worked on [PolkaAnalytics](https://polkanalytics.com/#/dashboard).
  - Previously built and shelved 2 startups. Led frontend for them.
  - [GitHub.](https://github.com/bhaskarSingh)

* Devops: JP
  - 10+ years of tech experience. Ex Goldman Sachs, Yahoo.
  - [GitHub.](https://github.com/jayprakash1)

## Team Projects

Similar projects Github repo links:

1. [Livepeer Pricing Tool](https://github.com/buidl-labs/livepeer-pricing-tool)
2. [PolkaAnalytics](https://github.com/buidl-labs/PolkaAnalytics)
3. [Zcash Service Status Dashboard](https://github.com/buidl-labs/zcash_service_status_dashboard)

You can check out our[ Github profile](https://github.com/buidl-labs) as well.

# Additional Information

[Research Document](https://docs.google.com/document/d/1UcloC-7_kIOxaK63g00Iu9POsltMeqyxfVd8YGVtQBc/edit?usp=sharing)
