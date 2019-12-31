# Open Grant Proposal: Filecoin Miner Map

**Name of Project:** filecoin-miner-map

**Proposal Category:** `app-dev`

**Proposer:** `kb-filecoin` 

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

<!--
Please describe exactly what you are planning to build. Make sure to include the following:
- Start with the need or problem you are trying to solve with this project.
- Describe why your solution is going to adequately solve this problem.

This section should be 2-3 paragraphs long.
-->

We want to (1) visualize the geographic distribution of miners and the composition of these miners in the ecosystem.  This is important for network stability and comprehensive understanding of node characteristics that will allow development teams in debugging the network.  (2) There are many important characteristics in quality of service (i.e. internet speed, round trip latency, choice of routing intermediate nodes) that can be important but currently not included Filecoin today.  We want to display these information so that users can make more informed decisions when storing or buying dataspace.

This project is the first step towards these goals.  Our project will visualize the location of miners and give comprehensive information about each network node. 

We realize that there is already a RFP related to miner reputation.  However, only referencing prices to match orders from clients and offers from miners might be a drawback rather than a progress, since there are many other issues to consider (i.e. internet speed, latency).  We therefore consider displaying these quality of service and allow users to filter out nodes based on certain criterias they care about in a visualization tool easy to use.

## Value

<!--
Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:
- What are the benefits to getting this right?
- What are the risks if you don't get it right?
- What are the risks that will make executing on this project difficult?

This section should be 1-3 paragraphs long.
-->

1. For a filecoin, which matching engine solely references price, 
  - Miners are assigned or chosen based on price without any other information about the quality of bandwidth/service.
2. For a filecoin, which lacks an effective method to evaluate the internet speed of miners, 
  - Miners will be compelled and happy to control the cost of service by sacrificing the quality of bandwidth/service. 
3. For a filecoin community, where a global distribution and statistics of miners is missing,
  - Miners can not know about their competitors, and the only way to attract clients is to lower the price.

In either case, it is inefficient to attract good service provider and unfair for them to join the game. That eventually hurts the entire ecosystem.

- What are the benefits of the project?
  - Both miners and clients know the storage and price of all the miner nodes in the world.
  - Clients may store files on more stable nodes for the same price.
  - For clients to whom internet speed is a more important issue than storing price, they are enabled to pay for better service.
  - May conceive a more sophisticated matching engine.
  - A historical service track record is displayed to show quality of service on network nodes.

- What are the risks that will make executing on this project difficult?
  - Service-related characteristics cannot be accurately evaluated for miners.

## Deliverables

<!--
Please describe in detail what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished.
-->

- Fully functional miner monitor website, which is accessible via a https://.
  - Mobile-friendly and fast to load
  - Real-time updates based on changes in the network
  - Visual design provided by D3.js or similar packages
- Miner-oriented APIs and well-documented codebase.

In detail, the following information and statistics will be visualized and updated (not limited to what appears in [rfp-reputation-system](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-reputation-system.md) but more than that:

  - Number and % (where applicable) of deals with no penalties, slashed contracts, and dropped contracts.
  - Number and % of failed deals (if possible) -- i.e. the number of deals that were attempted but failed, possibly due to poor network connectivity.
  - Distribution of regions of all failed deals, and % of retrieval requests successfully fulfilled
  - Number of files retrieved, lifetime data stored, and lifetime data retrieved
  - Feedback provided to the network about a specific miner should be substantiated via actions on the network - the proposed solution should verify claims about reputation via queries to the Filecoin Network (e.g. by verifying deal state on the Filecoin network).
  - Calls to this service should be well scoped, such that this service might be easily integrated into other libraries that might more broadly focus on creating a seamless storage experience.
  - Functionality of this service should be thoughtfully integrated into the storage workflow for the Filecoin Network.
  - In addition, this service should be extensible such that additional information about the miner might be captured and included over time.

## Development Roadmap

<!--
Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section).

For each milestone, please describe:
- The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates)
-->

| Milestone No. | Milestone Description                                       |    Funding | Estimated Timeframe |
|---------------|-------------------------------------------------------------|-----------:|--------------------:|
| 1             | Node Discovery and Crawler setup                            | 45,000 USD |             2 month |
| 2             | Frontend client                                             | 45,000 USD |             2 month |
| 3             | Network analysis and visualization of infrastructure        | 45,000 USD |             2 month |
| 4             | Run separate services for both Mainnet and Testnet          |  5,000 USD |              1 week |
| 5             | All project deliverables (website, documentation, codebase) | 10,000 USD |             2 weeks |

Expected software functionalities after each milestone:
- Milestone 1.
  1. kafka- or celery-supported QoS detection tasks;
  2. miner list and their QoS statistics, report, and QoS analysis;
  3. periodically updated miner QoS information;
- Milestone 2.
  1. a lightweight hybrid miner/client node, which collects and evaluates QoS of other mines;
  2. monitor nodes deployed;
  3. dynamic site and real time updates;
- Milestone 3.
  1. redis-based aggregator infrastructure, which dynamically updates site contents;
  2. infrastructure dockerization;
  3. visualization of miner distribution, geographic information, bandwidth, etc.

## Total Budget Requested

<!--
Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds.
-->

As shown in the previous section, summing up to 150,000 USD.

## Maintenance and Upgrade Plans

<!--
Specify your team's long-term plans to maintain this software and upgrade it over time.
-->

We are excited with the Filecoin ecosystem and want to start this project as the first step to join the community. Maintenance and upgrade plans are to be determined after the project is reviewed.

# Team

## Team Members

- Gavin Yeung (blockchain entrepreneur)
- Charles Zhang (CTO)
- Yanhao Zhang (Blockchain engineer)
- Terence Ma (Blockchain and math)
- Sofia Lee (UI & UE)

## Team Member LinkedIn Profiles

- [Gavin Yeung](https://www.linkedin.com/in/gavin-yeung-3a32141/)
- [Charles Zhang](https://www.linkedin.com/in/charles4zzhang/)
- [Yanhao Zhang](https://www.linkedin.com/in/%E8%A8%80%E8%B1%AA-%E5%BC%A0-5ba646169/)
- [Terence Ma](https://www.linkedin.com/in/terencema1023/)
- [Sofia Lee](https://urilee.hashbase.io/) (personal site)

## Team Website

<!--
Please link to your team's website here (make sure it's `https`)
-->

- [www.koinbros.com](http://www.koinbros.com)
- [www.cryptomover.com](https://www.cryptomover.com/)

## Relevant Experience

<!--
Please describe (in words) your team's relevant experience, and why you think you are the right team to build this project. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc.
-->

Our founder Gavin Yeung is a seasoned entrepreneur.  Prior to founding Koinbros, he worked in a bulge bracket bank for a number of years.  Gavin has an MBA from the University of Chicago and Computer Science Master and Bachelor degrees from the University of California, Los Angeles.

Our CTO, Dr. Charles Zhang, was a Computer Science Professor in the Chinese Academy of Sciences.  He was CTO in two prior startups in Beijing and has experience in managing high achieving engineering teams.  Charles has a Ph.D. in Computer Science from Hong Kong University and Master and Bachelor degrees from Tsinghua University in Beijing, China.


Our software engineer, Yanhao Zhang, is a graduate of the Polytechnic University of Hong Kong, studying Master of Science in Information technology.

Our Business Operations Manager, Terence Ma, is a graduate of the London School of Economics, studying Bachelor of Science in Maths and Economics.

Our advisors include a tenure financial statistics Professor from Hong Kong University of Science and Technology (Dr. Ying Ying Li, University of Chicago, Statistics Ph.D. 2008), a hedge fund manager (Richard Warfield, HBS, EECS Berkeley) and a successful entrepreneur (Gigi Wang, Stanford).

## Team code repositories

<!--
Please provide links to your team's prior code repos for similar or related projects.
-->

- [Stellar Rails](https://github.com/cryptomover-software/stellar-rails-wallet) - an open source web browser based Stellar wallet

# Additional Information

<!--
Please include any additional information that you think would be useful in helping us to evaluate your proposal.
-->


