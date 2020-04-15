# RFP Proposal: `Filecoin as a storage layer for Substrate`

**Name of Project:** Filecoin as a storage layer for Substrate

**Link to RFP:** [new-wave-3-rfps.md](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#cross-chain-integrations)

**RFP Category:** `app-dev`

**Proposer:** [Cdot network](https://github.com/cdot-network)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description
Cdot network team intends to build a [Substrate](https://github.com/paritytech/substrate) runtime module (pallet) and a relayer to enable Filecoin as storage layer for any blockchain developed by Substrate. In addition to pure file storage, a preliminary implementation that enables storing smart contract code in Filecoin and executing the code upon request will also be developed.

## Value to the Filecoin ecosystem
Currently, storing some states (or files) on a public blockchain like Ethereum only costs a transaction fee. Although storing huge files is super expensive and sometimes impossible (due to the block gas limit), due to the free rent, the state of these public blockchains are becoming a burden for full nodes. There are researches about charging rent fees, and current rent-free model won't last long.

Actually, it is common sense in the community that only a few essential things should be stored on a public blockchain. Other storage task should utilize a network (storage layer) that is specialized for storage. That is Filecoin if the storage should keep decentralized. We thing this approach conforms with Filecoin's Philosophy of the future Web3 world.

These days, Parity's Substrate framework is becoming the top choices to build a new blockchain. With its stabilization and more real use cases of Substrate, this trend is only accelerating. Therefore a easy access from Substrate based blockchain to Filecoin as storage layer will become a must for the whole ecosystem. And the implementation can demonstrate the idea of using Filecoin as storage layer with other blockchains.

In addition to merely storing some large files in Filecoin for a Substrate chain, enabling smart contracts that are rarely run to be stored in Filecoin is a more challenging and interesting topic. In Substrate, a smart contract is stored as a WASM blob on the chain, which may require continuously paying storage fees. Storing these smart contracts on the storage layer and fetching and executing them only when necessary will not only reduce the cost of contract deployer, but enhance the whole network's performance as well. Besides, the implementation will become a first trial towards the possibility for similar scenarios on other blockchains.

## A bit more details about the implementation
The current cross chain model, which relies a relayer to interact between Substrate and Filecoin, is close to using Witness model. This is currently enough since the file's hash (CID) is recorded on the Substrate chain so the only issue is about the liveness. Therefore the system assume that at least one honest relayer exists. Actually the relayer can also be integrated into the user client.

1. User attempts to upload a huge WASM blob (or file) to Substrate chain. Because of its large size, only its hash (CID in Filecoin) is recorded on Substrate chain, while the file itself is stored in Filecoin. User interacts directly through the frontend (or with the relayer), that will handle both Substrate and Filecoin side.
2. When Substrate chain needs to execute this WASM blob (or retrieve the file for further operations), the cross-chain protocol fetches the WASM blob from Filecoin to Substrate chain, following by the execution. First, a retrieving intend is triggered by a user transaction, which will be heard by the relayer. Next, the relayer will retrieve the file through the retrieval market and submit it to the Substrate node, to an external call that is waiting for the file. Finally, the file is operated according the specified rule on Substrate runtime. For the WASM blob case, this means execution of the WASM blob.

 To enable more advanced cross chain features, a SPV model is needed. The experience gained through this implementation will give team more ideas and thoughts toward the SPV model design.

## Deliverables
* A relayer to interact between Substrate and Filecoin
* A reusable Substrate runtime module (pallet) that enables interaction with Filecoin
* A Rust RPC client that enables basic file storage and retrieval. This may become the first step for a fully functioning rust RPC client implementation.
* A Substrate node that enables preliminary WASM call inside runtime
* Full documentation about the relayer and the pallet
* A deployed web front end that enables the public to try this system and its corresponding tutorial
* A demo video
* Articles about Filecoin and about what we have learned through the implementation in the (especially Chinese) community 


## Development Roadmap
**Total Funding Amount:** $35000

**Milestones:** 
| Milestone No. | Milestone Description                           | Funding | Timeframe |
|---------------|-------------------------------------------------|---------|-----------|
| 1             | Substrate pallet and basic relayer              | $10000  |  3 weeks  |
| 2             | Advanced Substrate and full functioning relayer | $16000  |  5 weeks  |
| 3             | Frontend website, documentations and testing    | $9000   |  3 weeks  |

### Milestone 1: Substrate pallet and basic relayer
Specifics:
- Substrate pallet that manage the life cycle from user uploading file to retrieving file.
- Relayer can interact with both Filecoin and a Substrate chain, which involves making transactions and hearing events from Substrate chain, and Storing and retrieving file. This will includes interaction between Go (Filecoin) and Rust (Substrate RPC) Code.

People Involved:
2 Development Engineer, 1 Product Manager

### Milestone 2: Advanced Substrate and full functioning relayer
Specifics:
- Substrate runtime can jump to execute some specific WASM blob (smart contract) uploaded
- Relayer can call relevant functions and hear and parse the returned events on the Substrate side, and can store and retrieve file on the Filecoin side, with correct communications.
- Relayer's Filecoin side is implemented as a Rust RPC client that enables file storage and retrieval. Therefore, the relayer's implementaton can be pure Rust.

People Involved:
3 Development Engineer

### Milestone 3: Frontend website, documentations and testing
Specifics:
- A deloyed frontend website that allows user to upload a WASM blob through Substrate to Filecoin, executes it upon request and displays the result.
- Full documentations, tutorials
- Integration test of the whole system

People Involved:
1 Development Engineer, 1 Test Engineer, 1 Product Manager

## Maintenance and Upgrade Plans

The team will maintain the software and website long-term and upgrade them according to Filecoin and Substrate upgrade.

# Team

## Contact Info
John Wu: john@cdot.network

## Team Members
* Louis Liu: Master at Tsinghua University. 20 years R&D experience in IT, telecommunication and big data industry at HP and China Mobile. Influential evangelist of Web3.0, blockchain technology, crypto capital market and cryptoeconomics in China.
* John Wu: Doctor of science at University of Tokyo. 3 years of smart contract and blockchain R&D experience. Former blockchain tech lead at LOTS, and lead blockchain engineer at ARPA. Polkadot and Cosmos ecosystem contributor. Polkadot technical ambassador. Hackathon winners. Teaching assistant of several courses including Ethereum, Substrate and Blockstack. 
* Yuanchao Sun: Rust enthusiasm. Abundant experience of networking, operating system and distributed system development. Lead software architect and developer in several startups. Cosmos IBC spec 2nd contributor and Chinese version translation community organizer.
* Mike Tang: Co-founder of Rust.cc, the largest Chinese Rust community. 13 years experience in software engineering development including embedded system and web service, and 5 years experience in Rust development. Currently focus on consensus protocol implementation in Rust.

## Team Member LinkedIn Profiles
* Louis Liu: https://www.linkedin.com/in/yi-liu-1b35892b/
* John Wu: https://www.linkedin.com/in/john-wu-72960586/

## Relevant Experience
The team has abundant experience on Substrate and cross-chain related implementation, has won several Hachathons on these topics. Besides, the team also has a lot of contributions to blockchain and rust communities in China, and has given a talk at 2019 Web3 Summit with topic "The present and the future of Web3.0 in China". The experience includes but is not limited to:
* The first Substrate IBC [implementaion](https://github.com/cdot-network/substrate-ibc) with working [demo](https://github.com/cdot-network/ibc-demo)
* [IBC protocol](https://github.com/cosmos/ics) 2nd contributor
* [IBC Chinese version translation](https://github.com/cosmos/ics/tree/master/translation/zh-CN) community organizer 
* Polkadot ecosystem (Polkadot/Substrate) codebase contributions, especially familiar with the Substrate RPC client [Subxt](https://github.com/paritytech/substrate-subxt) (2nd contributor)
* 2019 DeFi Hackathon in San Francisco the best 5: cross-chain (BIC based) MakerDao like collateralized stable coin system: https://github.com/en/defi-hackathon-2019   
* 2019 Polkaworld 1st Substrate Hackathon 3rd prize: Uniswap like DeFi system built on Substrate: https://github.com/polkaworld-org/superfluid
* 2019 Shanghai International Blockchain Week Hackathon 2nd prize: Dynamic price parking lot system built on Substrate: https://github.com/Satoshi-Kusumoto/WanxiangHackathon, https://github.com/Satoshi-Kusumoto/WanxiangHackathonFrontEnd

## Team code repositories
[Cdot network](https://github.com/cdot-network)
