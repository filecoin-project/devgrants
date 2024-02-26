# Filecoin Open Grant Proposal: `Scaling out ipfs-search.com along with IPFS`

**Name of Project:** Scaling out ipfs-search.com along with IPFS

**Proposal Category:** `app-dev`

**Proposer:** @dokterbob

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes.

# Project Description
We are the team behind ipfs-search.com. For the past 5 years, we have been providing search for the IPFS. Now we see that the IPFS ecosystem is growing. We want to grow along with it.

Our goal for this grant will be to take ipfs-search from beta to web-scale production. We want to make our engine powerful enough to integrate with meta-search engines like DuckDuckGo and SearX as well as browsers like Brave and Opera.

We have received information that DuckDuckGo is interested in search for IPFS, but will require an API capable of handling 1000 hits per second. That is the scale we want to land at with this grant.

To prepare, we will need to increase the scalability of the engine, both the size of the index as well as the number of queries it can handle.

We recently received a [grant](https://nlnet.nl/project/IPFS-search/index.html) from the EU within the [Next Generation Internet (NGI)](https://www.ngi.eu/) fund through [NLNet](https://nlnet.nl/), for doing the architecture of the scale-up. We still have to secure funding for the infrastructure and the implementation. This is why we turn to you.

## Value
We are an existing, Open Source application that delivers search for the IPFS. We solve the problem of "how do I find things on  IPFS". With support from Filecoin, we can share the wealth of content on IPFS with the world.

Currently, we are seeing that the amount of content on the IPFS is exploding and that public interest is taking off. We want to develop the service we offer to the users of IPFS. The scale-up is a vital part of this.


With this scale-up, we will be able to offer our engine as a service to other parties. This can serve as a platform from which we can continue to develop services for the distributed web in the years ahead.

While search is a tough domain to crack (due to the fierce competition) we believe a service not driven by user surveillance is a valuable part of the Filecoin ecosystem, one that we would love to maintain and develop in the years ahead.

## Deliverables

1. We will have our search engine running over 100 machines (75 search nodes, 15 auxiliary).
2. We will be able to handle 1000 hits/s of search traffic.
3. We will share the [deployment setup](https://github.com/ipfs-search/ipfs-search-deployment) (Ansible) dual-licensed under MIT and APACHE2.
4. We will create reusable, well-documented and production-grade ansible roles for IPFS and ipfs-cluster, and if possible other components.
5. We will propose integration of ipfs-search.com in DuckDuckGo, Startpage, Brave, Opera, Firefox and/or Chrome.
6. We will publish at least 3 posts on [our blog](https://blog.ipfs-search.com/), detailing our approach, objectives and progress scaling out our deployment.

## Development Roadmap

### Phase 1: scale-out from a 5 to a 15-node cluster

#### Milestones
1. Deployment setup for a 15-node cluster
2. Reusable Ansible role for IPFS
3. Extended benchmarking/reports on stability and performance of both crawler and search
4. Blog post describing work done

#### Timespan
July 1st - August 31

#### Budget
Devops operations: 6 weeks x 8 hours x € 75 = € 3600
Server costs: 15 x [Hetzner AX61-NVME](https://www.hetzner.com/dedicated-rootserver/ax61-nvme) bare metal server @ € 89 x 2 months + 10 x signup costs € 89  = € 3 560
Blogpost: 6 hours x € 75 = € 450

Subtotal: € 7610
Coordination: 15% of € 7610 = € 1141.50

**Total: € 8751.50**

### Phase 2: scale-out from a 15-node cluster to a 50-node cluster

#### Milestones
1. Deployment setup for a 50-node cluster
2. Reusable Ansible role for ipfs-cluster
3. Extended (visual) reports on stability and performance of both crawler and search
4. Blog post describing work done

#### Timespan
September 1st - October 31

#### Budget
Devops: 7 weeks x 16 hours x € 75 = € 8400
Server costs: 50 x [Hetzner AX61-NVME](https://www.hetzner.com/dedicated-rootserver/ax61-nvme) bare metal server @ € 89 x 2 months + 35 x signup costs € 89  = € 12015
Blogpost: 6 hours x € 75 = € 450

Subtotal: € 20865
Coordination: 15% of € 20865 = € 3129.75

**Total: € 23994.75**

### Phase 3: scale-out from a 50-node cluster to a 100-node cluster

#### Milestones
1. Deployment setup for 100-node cluster
3. Extended (visual) reports on stability and performance of both crawler and search
4. Blog post describing work done
5. We will propose the integration of ipfs-search.com in DuckDuckGo, Brave, Firefox and Chrome.

#### Timespan
November 1 - December 31

#### Budget
Devops: 7 weeks x 32 hours x € 75 = € 16800
Server costs: 100 x [Hetzner AX61-NVME](https://www.hetzner.com/dedicated-rootserver/ax61-nvme) bare metal server @ € 89 x 2 months + 50 x signup costs € 89  = € 22250
Blogpost: 6 hours x € 75 = € 450
Outreach to DuckDuckGo, Startpage, Brave, Opera, Firefox and/or Chrome: 24 hours x € 75 = € 1800

Subtotal: € 41300
Coordination: 15% of € 39500 = € 6195

**Total: € 47495**

## Total Budget Requested

€ 80241.25

### Breakdown
|             Task                | Phase 1     | Phase 2      | Phase 3     | SUM          |
|---------------------------------|-------------|--------------|-------------|--------------|
| Devops                          |    3600     |     8400     |   16800     |    **28800** |
| Server costs                    |    3560     |    12015     |   22250     |    **37825** |
| Blogpost                        |     450     |      450     |     450     |     **1350** |
| Outreach to DuckDuckGo (et al.) |             |              |    1800     |     **1800** |
| Overhead                        |  1141.5     |  3129.75     |    6195     | **10466.25** |
| **SUM** (EUR)                   |  **8751.5** | **23994.75** |   **47495** | **80241.25** |

## Maintenance and Upgrade Plans
Our goal for this grant is for the project to generate significant traction. This will allow us to attract the funds required for regular maintenance, upgrades, as well as the depth investment required to reach our ultimate goal: fully decentralized search, forever.

On shorter notice, independently from but simultaneous with the scale-out, we will be working towards domain-specific search (e.g. for music and/or video) based on our existing backend infrastructure. Imagine [Youtube Music](http://music.youtube.com/) or [Soundcloud](https://soundcloud.com/) for IPFS.

# Team

Mathijs de Bruin is the founder, team lead and CEO. Rooted in the Dutch hacker scene, he published his first Open Source project at 14. He co-founded the cooperative [Visualspace](https://www.visualspace.nl/) in Amsterdam as well as [Ecoaldeia Silverto](https://silverto.pt), the first Smart Village in Portugal (where he is currently residing), and the [Sol Nascente](https://solnascente.eu/) foundation for regenerative agroforestry.

Kees van Drongelen, a seasoned entrepreneur and UX/design lead. He founded his first design studio in 1993. He is co-founder and CEO of Visualspace. He teaches coding and design at the Hague Royal Academy of arts.

Aad Versteden is the Founder and CEO of redpencil.io. He has extensive experience leading the development of successful Open Source products.

Lars Magne Tungland has recently joined the project. He has a broad role, including project coordination and looking for ways to grow ipfs-search.com.

## Team website
https://blog.ipfs-search.com/

## Team code repositories
https://github.com/ipfs-search

## Team Member CVs/LinkedIn Profiles

- https://dokterbob.github.io/cv/
- https://www.linkedin.com/in/keesvandrongelen/
- https://www.linkedin.com/in/aad-versteden/
- https://www.linkedin.com/in/larstungland/

# Additional Information

Funds to realize the architecture of the scale-out has already been procured through a continuation grant within the previous NLNet/NGI0 fund.

This grant merely concerns itself with the operations of DevOps and hosting.
