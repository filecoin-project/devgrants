# Filecoin Devgrants

> **Wave 8 dev grant proposals are due June 30, 2021 for priority consideration. We will continue to evaluate new proposals after that deadline as capacity allows.**

Additional [Wave 8 RFPs](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-8-rfps.md) will be published soon.

> Learn about Waves 4 & 5 projects and Gitcoin Grants for Filecoin here in this [Filecoin blogpost](https://filecoin.io/blog/filecoin-dev-grants-wave-4-5-gitcoin/).

<p align="center">
  <img src="https://github.com/filecoin-project/devgrants/blob/master/img/Filecoin_Grants_illustrations.png" style="width:1300px;>
</p>

> Hello and welcome to the home page of the Filecoin Dev Grants program! If you haven't already checked it out, you can read more about the motivations behind the program on [the Filecoin Foundation website](https://fil.org/grants/). 

> **Note:** The Dev Grants program is administrated by the [Filecoin Foundation](https://fil.org/).

> You can see updates about major project milestones on [the Filecoin blog](https://filecoin.io/blog).

- [Filecoin Devgrants](#filecoin-devgrants)
  - [🥅 Goals of Filecoin Devgrants](#-goals-of-filecoin-devgrants)
  - [🔎 What we fund](#-what-we-fund)
    - [Types of grants](#types-of-grants)
    - [Categories](#categories)
      - [Technical Areas](#technical-areas)
  - [📋 How to apply](#-how-to-apply)
    - [Timing and Deadlines](#timing-and-deadlines)
    - [Eligibility](#eligibility)
    - [Submit a proposal for an RFP](#submit-a-proposal-for-an-rfp)
    - [Submit a proposal for open grants](#submit-a-proposal-for-open-grants)
  - [⌛ After you apply](#-after-you-apply)
  - [🎟️ Submit an RFP](#️-submit-an-rfp)
  - [ℹ️ Help](#ℹ️-help)
  - [License](#license)

> This page is also available in [Chinese (中文)](./README-Chinese.md).

## 🥅 Goals of Filecoin Devgrants

To date, the Filecoin project has focused primarily on research, specification and implementation of a decentralized storage network protocol. Throughout this process we have been fortunate to work with incredible community members and contributors. Some are already building tools on the budding network in active development.

We created the Filecoin Dev Grants program to:
- Reward ongoing & existing contributions that add great value to the Filecoin ecosystem
- Inspire more contributors to solve open problems and engage with the Filecoin project
- Seed the creation of new products, businesses and tools to increase the utility of Filecoin

We’re looking to fund talented and eager teams that want to work with us to build a more robust, efficient, and decentralized web.

## 🔎 What we fund

### Types of grants

We currently offer 3 types of grants:
1. **Requests for Proposals (RFPs)**: RFPs are grants for specific development work. As the name suggests, we are requesting proposals from teams that want to complete the work specified in each RFP. In these grants, we generally have clearly scoped *deliverables, milestones, and funding limits*. Some RFPs will ask you to propose your own milestones and funding needs. While there is some flexibility in RFP deliverables, we expect teams will deliver what is in scope in the RFP. Any deviations from the specified scope must be approved between your team and ours before we can approve funding. See [RFP submission details](#submit-a-proposal-for-an-rfp) for more information on how to apply for RFPs. Relevant proposals will be labeled [`proposal-type:rfp`](https://github.com/filecoin-project/devgrants/labels/proposal-type%3Arfp).
2. **Open grants**: If you have an idea for something that isn't covered by an open RFP, you can submit a proposal to our open grants category! This is where you get to be really creative; we can't wait to see what you propose! We will review these proposals on the same cadence as RFP proposals (i.e. once every quarter, read more about timing in [Timing and Deadlines](#timing-and-deadlines)). See [open grant submission details](#submit-a-proposal-for-open-grants) for more information on how to submit a proposal. Relevant proposals will be labeled [`proposal-type:open`](https://github.com/filecoin-project/devgrants/labels/proposal-type%3Aopen).
3. **Next step grants (Microgrants)**: Grants of $5,000 in FIL are available to support taking the next step after you have created an initial prototype with Filecoin. These grants are intended for independent developers, small studios, non-profits, activists, and researchers. Applicants may be working independently, or as part of a course or hackathon.
Acceptance criteria are very simple, and work is expected to be complete within 2 months. See [next step grant details](https://github.com/filecoin-project/devgrants/blob/master/microgrants/microgrants.md) for more information on how to submit a proposal.
                                                                                                                    
### Categories

All of our RFPs and open grants fund work in a few core categories. Over time, these categories may change/expand, so please keep a watch on this space!

- **Core development**: The Filecoin Project is currently focused on core protocol research, specification, and implementation. Through this program, we may occasionally fund collaborators to tackle core protocol implementation work. Relevant proposals will be labeled [`category:core-dev`](https://github.com/filecoin-project/devgrants/labels/category%3Acore-dev).
- **Application development**: As we continue to build out our developer platform, we would love to work with talented application developers to build useful and delightful applications that utilize Filecoin as the decentralized storage layer. Relevant proposals will be labeled [`category:app-dev`](https://github.com/filecoin-project/devgrants/labels/category%3Aapp-dev).
- **Developer tools and libraries**: We are always looking for ways to make the lives of Filecoin developers easier. This includes developer tools and libraries for both core protocol developers and application developers. Dev tools at all layers of the stack are invaluable! Relevant proposals will be labeled [`category:devtools-libraries`](https://github.com/filecoin-project/devgrants/labels/category%3Adevtools-libraries).
- **Technical design**: The Filecoin protocol will continue to evolve over time. Several planned protocol upgrades are already being researched, but we want to find the best technical designs for these planned upgrades and for ideas that aren't currently on our radar. This type of technical design work can be improvements to our core storage protocol, cryptoeconomics design, and more! Relevant proposals will be labeled [`category:technical-design`](https://github.com/filecoin-project/devgrants/labels/category%3Atechnical-design).
- **Documentation**: Having great documentation is crucial for any open-source project and development platform. This category includes how-to guides, protocol concepts, API docs, and more. If you think we need to create or improve existing documentation, please submit a proposal or apply to one of our open docs RFPs! Relevant proposals will be labeled [`category:docs`](https://github.com/filecoin-project/devgrants/labels/category%3Adocs).
- **Community**: We would like to support community initiatives throughout the global Filecoin ecosystem. We have a standing RFP for hosting community meetups, and are generally excited to hear about all sorts of community initiatives you might have! Relevant proposals will be labeled [`category:community`](https://github.com/filecoin-project/devgrants/labels/category%3Acommunity).
      
#### Technical Areas

<p align="center">
  <img src="https://github.com/filecoin-project/devgrants/blob/master/img/filecoin-stack-devgrant-areas.jpg" width="75%">
</p>


## 📋 How to apply

### Timing and Deadlines

We will start a new grants cycle, or `wave`, every quarter i.e. every 3 months. Therefore, the last day of each quarter is the deadline for all proposals in that wave. 

| Wave No. | Wave Opens | Wave Deadline |
| --- | --- | --- |
| 7 | Jan 15, 2021 | March 31, 2021, 11:59PM PT |
| 8 | April 1, 2021 | June 30, 2021, 11:59PM PT |
| 9 | July 1, 2021 | Sep 30, 2021, 11:59PM PT |
| 10 | Oct 1, 2021 | Jan 15, 2022, 11:59PM PT |
                                                                                                                        

After the wave deadline, we will spend a few weeks reviewing proposals on GitHub, leaving comments, asking questions, and requesting changes. Ultimately, we approve or reject each proposal that was submitted within each wave. Our aim is to do this within a few weeks after each wave deadline. Please note that if your team isn't responsive on GitHub, or doesn't provide the information requested in a timely fashion, your proposal likely will not be accepted. So pay attention to GitHub after you submit your proposal!

Note that there is a chance (but no guarantee) your proposal will be reviewed earlier than the wave deadline. Because grants are awarded on a rolling basis, strong proposals that are submitted early might have a slight advantage on the off-chance we review before the wave deadline. Of course, there is no guarantee that we will review proposals before the deadline, so it's up to you whether you want to submit well before the deadline or not!

### Eligibility

- All projects must be open-sourced
- All projects must be dual-licensed under MIT and APACHE2 licenses
- All teams must be self-managed

### Submit a proposal for an RFP

All of our currently open RFPs are listed in the [`rfps` folder](rfps/).

Here are the steps to submit a proposal against one of the listed RFPs!
1. Select an RFP you would like to apply for.
2. Submit a PR against the [`rfp-proposal-template.md` file](https://github.com/filecoin-project/devgrants/blob/master/rfp-proposals/rfp-proposal-template.md) in the [`rfp-proposals` folder](https://github.com/filecoin-project/devgrants/tree/master/rfp-proposals) of this repo. Make sure to fill in all the categories of the RFP proposal template (incomplete proposals will not be considered). Rename your file `project-title.md`, making sure to replace `project-title` with the name of your project.

**Remember to submit your PR before the wave deadline. PRs submitted after the deadline will be considered in the next wave (at which point, the RFP might be closed).**

### Submit a proposal for open grants

Here are the steps to submit a proposal for the open grant category!
1. Submit a PR against the [`open-proposal-template.md` file](https://github.com/filecoin-project/devgrants/blob/master/open-grant-proposals/open-proposal-template.md) in the [`open-grant-proposals` folder](https://github.com/filecoin-project/devgrants/tree/master/open-grant-proposals) of this repo. Make sure to fill in all the categories of the proposal template (incomplete proposals will not be considered). Rename your file `project-title.md`, making sure to replace `project-title` with the name of your project.


**Remember to submit your PR before the wave deadline. PRs submitted after the deadline will be considered in the next wave (which means a 3-month delay in review for your proposal).**

## ⌛ After you apply

After you submit your proposal -- assuming you get it in by the deadline -- you can expect the following to occur:

- After the wave deadline, we will review all PRs. During our review, we will add comments, questions, change requests, etc, on your team's PR.
- After a few round trips of discussion, our team will make a decision on which proposals to fund and which not to. <!--Accepted proposals will be merged into the appropriate directory, i.e. either [`open-grant-proposals`](https://github.com/filecoin-project/devgrants/tree/master/open-grant-proposals) or [`rfp-proposals`](https://github.com/filecoin-project/devgrants/tree/master/rfp-proposals).-->
- During the discussion and review phase, our team will contact your team for financial and legal follow-ups, such as to confirm milestones and funding, your team's legal structure, etc.
- If your team is accepted, we will ask you to sign our Open Source Software Grant Agreement, which will include a copy of the work plan and funding milestones. Note that if your team does not meet the acceptance criteria for the grant (whether it's an RFP or open grant), we may stop funding your team for further development work.
- We aim to complete all review within a few weeks after the wave deadline, so please stay vigilant on GitHub. If we don't hear back from you when we ask you a question or request changes on your proposal, it's very unlikely that your proposal will be accepted!

## 🎟️ Submit an RFP

> This section only applies to individuals and organizations that are willing to fund RFPs. As a result, this currently applies primarily to Protocol Labs, but we will eventually expand to work with other organizations very soon!

If you would like to propose an RFP for the Filecoin ecosystem, you've come to the right place! Here, we provide instructions for how to submit and iterate on an RFP for the Filecoin Dev Grants program. Note that all proposals submitted to your RFP should be reviewed along the same timeframe as is listed in [Timing and Deadlines](#timing-and-deadlines). If you submit an RFP, you will be responsible for making sure all relevant proposals are reviewed on time. Before you start, make sure you can build a strong case for why this grant will increase the utility of the Filecoin ecosystem. If you're convinced that it will, please proceed!

1. Submit a PR against the [`rfp-template.md` file]() in the [`rfps` folder]() of this repo. Make sure to fill in all the categories of the RFP template, including the source of funding. Name this file `rfp-project-title.md`, replacing `project-title` with the name of the project you'd like to fund.
2. We will review the RFP idea, providing comments and suggestions. If there is an opportunity to cofund the RFP, we will also identify that opportunity (note: not relevant for RFPs suggested by other Protocol Labs projects). Eventually, the RFP idea will either be accepted or rejected.
3. If the RFP idea is accepted, it will be merged into the `rfps` folder, and collaborators can begin submitting proposals. Please remember that there is no obligation to begin reviewing these proposals before the wave deadline. Of course, if you would like to begin reviewing proposals early, you may! However, it IS required for RFP owners to review all proposals within 2-weeks after the wave has closed.
4. Create an issue with the appropriate Category tag and a link to the merged RFP doc. This is where community members will have discussions, ask you questions, and more, so please monitor this thread!
5. Once you have selected your grant winners, you may submit a PR to move the RFP into an `inactive-rfps` folder or keep the RFP open for further submissions.

Please contact `@Sonia John` on Filecoin Slack ([invite](http://filecoin.io/slack)) or email devgrants@fil.org with any questions.

## ℹ️ Help

If you have any questions, please ask them!
- File an issue in this repo
- Join our [community chat](https://github.com/filecoin-project/community#chat)

Additionally, check out [filecoin.io](https://filecoin.io) or the [Filecoin Docs](https://docs.filecoin.io) to learn more about Filecoin.

## License

The Filecoin Project is dual-licensed under Apache 2.0 and MIT terms:

- Apache License, Version 2.0, ([LICENSE-APACHE](https://github.com/filecoin-project/devgrants/blob/master/LICENSE-APACHE
) or http://www.apache.org/licenses/LICENSE-2.0)
- MIT license ([LICENSE-MIT](https://github.com/filecoin-project/devgrants/blob/master/LICENSE-MIT) or http://opensource.org/licenses/MIT)

All Filecoin dev grant projects are open sourced and also use these licenses.
