# Open Proposal: `FILViz - Phase 1`

**Name of Project:**
FILViz - Phase 1

**Proposal Category:**
`app-dev`

**Proposer:** `@prastut`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:**
Yes!

# Project Description

Filecoin is becoming a fascinating playground for people collaboratively coming to consensus around a public decentralized censorship-resistant storage market by turning cloud storage into an algorithmic market.

Our team feels that an average joe (not familiar with blockchains) is not aware of the impact Filecoin is going to generate. And we want to share our enthusiasm with the community at large.

Noticing the above undercurrent, we feel the need to create experiences that give a feeling akin to the [feeling one get's when watching a rocket launch](https://www.youtube.com/watch?v=nqOU2CGeAvk) 🚀

Therefore, we propose to build an umbrella project that deals explicitly with visualization tools over Filecoin that let's end users sit back and glimpse through the new universe of markets and applications that are getting created with/on Filecoin.

This proposal is Phase 1 of the umbrella project that focuses on kickstarting the macro and micro visualization of the Filecoin network.

#### Outcomes to achieve:

The tools we build in the first phase of the project are aimed to serve the following user-groups:

1. Educate newcomers about the markets starting to form on top of Filecoin. 👶
1. Give powers users means to investigate the organic evolution in network activity. 🕵️‍♀️

## Deliverables

The proposal is structured into two broad categories of deliverables:

1. Visualization deliverables.

   1. Visualizing macro-evolution of Filecoin Miner ecosystem on planetary scale.
   2. Visualizing micro-evolution of Filecoin Miner ecosystem in specific areas of the world.

2. Marketing and Education deliverables.
   1. FILViz bot: A twitter bot that acts as a snapshot service over the above visualizations. It will relay essential updates on the Filecoin network to Twitter.
   2. Glossary/Help Guides: written from a perspective of the average joe with the vision to spark curiosity and lead that curiosity to the Filecoin rabbit hole.

### Deliverables in depth:

#### Visualization Deliverables:

##### 1. Visualizing macro evolution of Filecoin Miner ecosystem on planetary scale:

Recently new Filecoin website designs were shared with the commmunity:
![](https://i.imgur.com/5BvdK4Y.jpg)
![](https://i.imgur.com/ZSrrhsN.jpg)

We want to make a visualization that pipes in real data from the network and plot it on a planetary scale to see the evolution in realtime. An [example](https://foamviz.surge.sh/#/data-globe) of how it would look like in motion is shown below:

![](https://i.imgur.com/SNbTpgz.jpg)

The bar's height is scaled to represent the power of the miner.

Insights for end-users at a glance:

1. Which geography has the most activity?
2. Patterns across the world.
3. Evolution of Filecoin miner ecosystem in the time leading up to mainnet launch.

##### 2. Visualizing micro-evolution of Filecoin Miner ecosystem in specific areas of the world:

View specific areas in the world and analyze them.

- The difference is that the earth shows a macro view but doesn't show specifics from UX perspective.
- The specific view helps you get into the nitty-gritty analysis.
- This is similar to zooming in google earth and viewing specific areas for network analysis.

An [example](https://foamviz.surge.sh/#/poi-analytics) of how it would look like in motion is shown below:

![](https://i.imgur.com/9ucXx6y.jpg)

Notes:

- The bars height are scaled to represent the power of the miner.
- The tool will also ask for permission for viewer location. If given access, the viewer will be able to scan network activity around their locality.

#### Marketing and Education deliverables:

##### 1. FILViz bot:

Features:

- A twitter bot that acts as a snapshot service over the above visualizations.
  - Snapshot can be in the form of picture/gif ([eg](https://twitter.com/simongerman600/status/1195986266216681472?s=20)).
- Relays important updates on the Filecoin network to Twitter.
- Envisioned flow:
  1. A pre-set list of triggers coded out.
  2. Whenever event triggers -> bot relays data on Twitter.

Benefit:

- Help in onboarding + adoption by leveraging Twitter's network effects.
- Incentivizing mimetic effects: newcomers will become curious about what’s happening in the Filecoin community as the bot’s efforts starts compounding over time.
- Social Validation for top miners:
  _ How?: the bot will post profile links of top miners ranked by various metrics to give a feeling of a leaderboard on Twitter.
  _ Frequency: daily/weekly basis to give top miners a platform to show-off their efforts. \* Data collection: Will circulate a form in Filecoin Slack to link Twitter handles of the miner with their miner address.

To demonstrate how impactful this approach for marketing can be, attached below is a screenshot of analytics of a twitter bot we created to post updates about the Polkadot Network. Notice that it received over 34,000+ organic impressions in 1 Month.

NOTE: The bot went live in late December, 2019. As with any social media effort, it takes time to build compounding returns:

![](https://i.imgur.com/i7uXXII.png)

##### 2. Glossary/ Help Guides:

All tools will be documented with help sections and written from a perspective of the average joe. The attempt will be to make somebody curious (with the viz) and lead that curiosity to the Filecoin rabbit hole.

## Development Roadmap

### Milestone 1: finalization of scope:

1. what the visualizations would look like:

   - Design sprint kickoff: Get feedback on the direction we want to take from the Filecoin DevGrants Team.
   - Low Fidelity to High Fidelity: Integrate feedback -> convert low fidelity prototypes into high fidelity design mockups (shared via Figma prototypes).
   - Closure on design: Get feedback on the high fidelity mockups developed in point 2.

2. and how the viz would be built:
   - Complete data source vantage: Finish research on the list of API endpoints that will be used.
   - Architectural Design vantage: tentative stack in mind (subject to change based on constraints identified)
     - Frontend Stack:
       - Visualization Stack: Deck.gl
       - For managing UI state: React.js

People Involved:

1. Lead Frontend Developer (full time).
2. Product Manager (part time).

Duration: 1 week.
Funding Required: \$1,800

### Milestone 2: #buidl-ing out visualization deliverables:

#### #buidl-ing:

1. Front-End: static components for the visualizations will be built with mock data.
2. Back-End: will be completed up to spec in with completed endpoints that will be consumed by frontend.

#### Integration:

Both deliverables from the above stage will be integrated.

People Involved:

1. Lead Frontend Developer (full-time)
2. Backend Developer (full-time)
3. Product Manager (part-time)

Duration: 2 weeks (1 visualization/week).
Funding Required: \$5,520

### Milestone 3: #buidl-ing out marketing and educationa deliverables:

#### #buidl-ing:

1. Execute FilViz Twitter bot
2. Execute Glossary + Help Section:
   - Contextualized help button.
   - Help Center.

#### Beta release

1. Beta release of the visualization tools are deployed live and shared with the community.
2. Feedback exercise started around the beta release
   - Here we will collaborate with Filecoin Dev Grants Team:
     - To give us feedback
     - And point us to people with whom we can schedule user feedback calls with.
   - These feedback calls will enable us to understand:
     - kinks in the user experience of the implementation
     - level of clarity that would be required to write/record explainers and FAQ's .
   - We are also open to holding 2 community calls (1 community call/week) inviting feedback from the community at large.
3. Based on the insights gained from the feedback, the remaining user onboarding + increasing clarity deliverables will be executed:
   - Landing Page for the viz.
   - Additions to Help Center.

People Involved:

- with getting user feedback and iterating on those feedback:

  1.  Lead Frontend Developer (full-time).
  2.  Product Manager (part-time).

- executing remaining deliverables:
  2.  Frontend Developer (full-time).

Duration: 2 weeks.
Funding Required: \$5,520

### Milestone 4: 🧐 + 🛠 stage.

- Production deployment.
  - Also includes iteration on feedbacks from Milestone 3.
- Codebase documentation.
- Q/A to ensure robustness.
- Migrate repositories to the Filecoin Shipyard.

People Involved:

1.  Lead Frontend Developer (full-time).

Duration: 1 week.
Funding Required: \$1,800

## Total Budget Requested

| Milestone No. | Milestone Description                                 | Funding  | Estimated Timeframe |
| ------------- | ----------------------------------------------------- | -------- | ------------------- |
| 1             | finalization of scope                                 | \$1,800  | 1 week              |
| 2             | #buidl-ing out visualization deliverables             | \$5,740  | 2 weeks             |
| 3             | #buidl-ing out marketing and educationa deliverables: | \$5,740  | 2 weeks             |
| 4             | Documentation + Testing and Adjustments               | \$1,800  | 1 week              |
| **Total**     |                                                       | \$14,640 | 6 weeks             |

## Maintenance and Upgrade Plans

Maintenance:

- After project completion, maintaining and iterating on user feedback on the system actively for the next 3 months. Bug fixes, if any.
- For 1 year: support if the system goes down.

Future Plans:

- Visualizing deal flow on planetary scale.
  - Inspired from this [example](https://blueshift.io/international-trade.html).
- Visualizing development activity in the Filecoin ecosystem:
  - Inspired from this [example](https://twitter.com/Superhuman/status/1106583185402417152).

# Team

## Contact Info

Email: prastut@buidllabs.io

## Team Members

- Lead Frontend Developer: Bhaskar
- Backend Developer: Sahil
- Product Manager: Prastut

## Team Member LinkedIn Profiles

- Bhaskar: https://www.linkedin.com/in/bhaskar-singh-55a535b9/
- Sahil: https://www.linkedin.com/in/sahil-nanda-8b1b88143
- Prastut: https://www.linkedin.com/in/prastut/

## Team Website

[BUIDL Labs](https://buidllabs.io/)

## Relevant Experience

Our team comprises of people having background in theory-based visual design and analytical methods. We like to discover and validate insights from data, then translate them into systems, processes, and frameworks that help in mindfully created human-information interactions.

The advent of high technology information, imaging, networking, mobile devices and social media systems has fostered a modern renaissance in visualization. Just as the great artists of the European Renaissance were also designers, inventors, scientists & architects, we think the modern visualizers have an essential role to play in decoding the increasingly complex world and make it accessible to all humans.

Curiosity led us down the blockchain ecosystem rabbit hole. We wanted to analyze the organic activity happening on these public blockchains but the reality is that the format of these public datasets make it very difficult to analyze, understand and then derive insights.

Hence, we want to build tools that can help in solving this problem and give users means to make informed decisions without relying on any third party. Visualizations are one part of this toolkit.

Brief info about the team members:

- Lead Frontend Engineer: Bhaskar Singh

  - Worked on [PolkaAnalytics](https://polkanalytics.com/#/dashboard).
  - Previously built and shelved 2 startups. Led frontend for them.
  - [GitHub.](https://github.com/bhaskarSingh)

- Backend Engineer: Sahil

  - Budding Filecoin protocol researcher + Go Developer.
  - Built [PolkaViz](https://polkavizproject.surge.sh/). Before that built algorithmic trading strategies for a crypto hedge fund.
  - [GitHub](https://github.com/sahilnanda1995)

- Product Manager: Prastut
  - Currently spending mindspace in observing and understanding incentives for participation for core actors involved in upcoming projects that use PoS. Eager to deep dive into Filecoin in detail during the project.
  - Have 5+ years of product-dev experience across multiple startups, research labs and companies.
  - Will help the team with nuances on how to best visualize data from end user PoV leveraging the experience picked up through the following projects:
    - Architected [Polkaviz](http://polkavizproject.surge.sh/) project.
    - Architected [PolkaAnalytics](https://polkanalytics.com/#/dashboard) project.
    - Architected [YieldScan](https://github.com/buidl-labs/Web3-collaboration/blob/445e0a071cb6860a15fa974137ee013029a93111/grants/speculative/YieldScan.md) project.
    - Architected [Crypto Code School](https://github.com/buidl-labs/zombies-in-the-room) for Tezos.
    - Built the entire frontend data visualization stack for [Centify](https://centify.surge.sh/#/).
    - Was a data visualization research associate at Information Design Lab, IIT Bombay. [Work documentation.](https://prastut.github.io/dataviz)
  - [GitHub.](https://github.com/prastut)

## Team Projects

Similar projects Github repo links:

1. [PolkaAnalytics](https://github.com/buidl-labs/PolkaAnalytics)
2. [PolkaViz](https://github.com/buidl-labs/polkaviz)
3. [FOAMViz](https://github.com/buidl-labs/foamviz)

You can check out our[ Github profile](https://github.com/buidl-labs) as well.
