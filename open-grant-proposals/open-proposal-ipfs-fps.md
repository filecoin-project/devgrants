To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `IPFS-FPS`

**Name of Project:** uP2P

**Proposal Category:** `devtools-libraries`

**Proposer:** `leon-do`

**Contact:** `dlabs(at)email.com`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes" 

# Project Description

[IPFS-FPS](https://ipfs-fps.com) is now under the umbrella of [Underscored Labs](https://underscoredlabs.com) (_dLabs). This proposal will build the third and final piece of the vision. 

- 1st piece: How to host completely decentralized game on IPFS. https://twitter.com/_slate/status/1342170045561012226
- 2nd piece: A plug and play SDK for crypto games. https://twitter.com/Filecoin/status/1344085868324286465
- 3rd piece: A plug and play SDK for p2p multiplayer games.  Using Unity and libp2p

There is currently no SDK for peer to peer browser games. All libraries go through a centralized server, even if the game is as simple as tic-tac-toe. This SDK will connect users without the need for centralized parties, lower the cost of infrastructure (no servers) and decrease development time.

As a proof of concept, I built and wrote a piece on how to create a multiplayer game for Unity using webrtc: https://leondo.medium.com/multiplayer-unity-game-webrtc-in-5-minutes-71971be769d1. The feedback was overwhelming.

## Value

Within a day, developers was messaging me on where and how to use the tool. What's interesting is this demographic is unaware of the web3 ecosystem. If tools like libp2p are packaged right, it can be huge in the multiplayer gaming industry. I've spoken with Juan B, Colin Evran and Mike Goelzer about this idea and I truly believe there's potential.

There is also a movement in lightweight games. Unity has created a toolkit called [project tiny](https://unity.com/solutions/instant-games) which is a gaming engine made specifically for light mobile and web games. But this is only one part of the equation. The engine only supports single player. No multiplayer support. This propsal will be the missing piece.

## Deliverables

- Source code using libp2p - MIT License
- A `uP2P.unitypackage` that bundles the source code. Double click to import into any project.
- Video explaining setup (example below)
[![](https://user-images.githubusercontent.com/19412160/104258887-57135880-544e-11eb-8be6-43fdcab81df0.png)](https://www.youtube.com/watch?v=be9VtUymNPs)

## Development Roadmap

### Milestone 1: 
- Complete alpha version of uP2P: A peer to peer multiplayer SDK for Unity using libp2p.
- Video demo
- Leon Do - founder
- 4 weeks

### Milestone 2
- Full documentation on the tech stack (blogs)
- Full documentation on how to use it (website)
- Integrate into underscored labs SDK (parts 1 & 2)
- Main launch
- Leon Do - founder
- 2 weeks

### Milestone 3
- Business development: Partner with game developers
- Marketing: Partner with game publishers to promote value of the product.
- Leon Do - founder
- 2 weeks

## Total Budget Requested

|  Milestone  | Work Time | Duration | Budget  |
|-------------|-----------|----------|-------- |
| Milestone 1 | 120 hours | 8 weeks  | $10,000 |
| Milestone 2 | 60 hours  | 2 weeks  | $5,000  |
| Milestone 3 | 60 hours  | 2 weeks  | $5,000  |
| Total       | 240 hours | 12 weeks | $20,000 |

If necessary, this budget will accommodate up to 2 additional developers.

## Maintenance and Upgrade Plans

Specify your team's long-term plans to maintain this software and upgrade it over time.

We want to create software that will last. _dLabs and the community will to continue maintain the project as long as developers are still interested. The project will evolve but will maintain the vision of `a plug and play SDK for p2p multiplayer games`.

# Team

## Team Members

- Leon Do

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/leon-do/

## Team Website

http://underscoredlabs.com/

## Relevant Experience

Leon was a software engineer at ShapeShift, Binance and is an active contributor at IPFS. Having been a pure blockchain researcher, implementing cross chain atomic swaps, dexes and bitcoin lighting he decided to focus more on bridging web3 tech with the web2 world.

## Team code repositories

https://github.com/underscoredLabs

# Additional Information

- Part of Tachyon's Launchpad Accelerator - Underscored Labs
- Protocol Labs HackFS winner for IPFS-FPS
- Unstoppable Domains HackFS winner for IPFS-FPS
- Pinata HackFS winner for IPFS-FPS
- Fleek HackFS winner for IPFS-FPS