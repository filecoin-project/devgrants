## **RFP ideas for Wave 5**

Filecoin will be launching mainnet throughout the week of October 18th - 23rd: [current gantt chart](https://app.instagantt.com/shared/s/1152992274307505/latest). 

We are seeking proposals for the following RFPs for the Wave 5 of the Dev Grant program. For more ideas see the [Wave 4 grant list here](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-4-rfps.md).

The priority deadline for Wave 5 proposals has now passed however we will continue to evaluate later proposals submitted as capacity allows. Also please keep in mind that **ideas are always rolling and if you are not considered for Wave 5 in-time your application will be rolled over to Wave 6.**

We also accept Open Grant Proposals where you can suggest your own Filecoin project idea.

See our [Proposal Guidelines](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-4-rfps.md#proposal-guidelines) below about how to apply.

Have a question about any of these RFPs? Email devgrants@filecoin.org

##

**Youtube archiving tool**

A storage client application with an easy to understand interface and UX for YouTube content creators - so they can back up all their videos to Filecoin. This could be a webpage but also a browser plug in. 

##

**Governance / voting tool**

Voting interface that allows the creation of polls and can collect and verify responses by requiring key signatures from a Filecoin wallet. Responses can be weighted on any available on-chain metric, e.g. number of FIL or storage power held by a miner.

Use cases include soliciting social consensus around FIPs, help create a miner reputation system (by allowing addresses to vote), or allow transparent voting for really any other proposal put forward by the Filecoin community.

Below are some links to similar systems:



*   [https://snapshot.page/#/](https://snapshot.page/#/)
*   [https://proposals.decred.org/](https://proposals.decred.org/) 
*   [https://commonwealth.im/edgeware](https://commonwealth.im/edgeware) 

##

**Miner marketplace + social network**

A marketplace style website that shows all of the Filecoin miners, their locations, storage quality statistics, and added services. Miners could control some of the information in their listing.

This could be expanded to a social network that also includes verification and a public forum that can help miners and clients find each other - and uses [https://sourcecred.io/](https://sourcecred.io/) to measure and reward value creation among participants. 

##

**Hardware ROI calculator for miners**

A general calculator for Hardware Setup Costs and how that impacts Sealing Rates. 

An overall ROI calculator for Filecoin would consider investments in Hardware as well as Collateral (pledges, rewards, penalties, etc.). For this RFP we are interested mainly in the  Hardware portion. (A separate calculator for Collateral analysis will be started by another team.)

Many miners also consider their sector Sealing Rate when analyzing their hardware configurations.

For all calculations, parameters may change but it helps to have the formulas in place and variables can be filled in later.

An example reference architecture for a medium-to-large miner is also available here: [https://filecoin.io/blog/filecoin-guide-to-storage-mining/](https://filecoin.io/blog/filecoin-guide-to-storage-mining/)**.**

##

**Backup your blockchain to Filecoin**

Build tooling to import other blockchains into Filecoin and store them. Ideally the tool would feature a standardized way of grabbing chain data from nodes (VulcanizeDB / IPLD) and segmenting into pieces for storage in Filecoin (e.g. every 1GB or 10 GB). 

This can be implemented for e.g. Bitcoin, Ethereum or Zcash, and should also include methods for retrieval. 

##

**Patreon for Data**

Web platform that allows interested parties to campaign for important data sets to be preserved using Filecoin. The platform should have an easy to understand interface and UX, allowing non-technical communities to participate also. 

##

**Gas Station Tool or Explainer**

A tool to explain and analyze gas including base fees, fee cap (for each Tipset) and average gas premiums could be helpful to community members along with a schedule of costs for various transaction types. [Eth Gas Station]([https://ethgasstation.info/](https://ethgasstation.info/)) is one example resource but what specific tool is built to explain this topic is open.

Modeling current average gas costs can also help miners and developers better understand the current Mpool and why their transactions are not being mined, especially if their gas is too low compared to the network average.

The EIP-1559 Gas Model was implemented in Filecoin [Changelog](https://github.com/filecoin-project/lotus/blob/efd2dff0cac40934ec5b4472e48887ecbb2efe44/CHANGELOG.md#gas-changes). A Lotus JSON RPC API call to estimate gas in Lotus is a todo [Issue 3326](https://github.com/filecoin-project/lotus/issues/3326) and there is a [Gas Estimation function in Lotus here]([https://github.com/filecoin-project/lotus/blob/18c025f10e99b35cf7cd2eebe10de5163280378e/node/impl/full/gas.go#L189).

##

**CID Indexing Tool for Miners**

A CID indexing tool for all sectors that a storage miner has, as software that sits on top of a Filecoin node.

Storage miners who offer more information about data and sector status are likely to be more attractive to storage clients. A CID indexer could be run as a sidecar to Lotus to keep track of all sectors a miners has. It could: \




1. Grabs all the IPLD data structures of the client data
2. Understand every CID
3. Map CIDs to sectors and offsets
4. Create a local index
5. Then storage miners could share their CID index with a aggregator for community visibility

Sectors miners have can also be observed at [spacegap.github.io](https://spacegap.github.io).

Optionally this tool could also map pieceCIDs (used in CommP) to payload / data CIDs to support Retrieval Miners and Clients. [https://github.com/mgoelzer/cid_oracle](https://github.com/mgoelzer/cid_oracle) is a tool that scans the Filecoin blockchain for pieceCID to payload CID mappings.

##

**State Trie Explorer**

A tool to walk the Filecoin State Tree, explain its structure and what data it keeps track of.

Options:

1. A Simple Block Explorer

    In 2019, a [simple Filecoin block explorer](https://github.com/filecoin-project/filecoin-explorer) was built for an earlier go-filecoin node implementation. It was updated for the lotus Filecoin node for the 2019 December testnet launch [here](https://github.com/openworklabs/lotus-block-explorer).

    We would like to see this simple explorer updated to the current Lotus API and testnet. Enhancements can be made to improve performance and the information displayed.

    This explorer originally presented details about Filecoin actors (current core smart contracts hardcoded in the protocol) such as the Storage Market actor, Miner actors, as well as information contained in blocks. ([Screenshots](https://filecoinproject.slack.com/archives/CFP9A2T7W/p1593095833249300?thread_ts=1593095710.249000&cid=CFP9A2T7W).)

2. or Build any tool with a current State Tree HAMT library

	A tool based on the current Filecoin State Trie is [spacegap.github.io](https://spacegap.github.io) which can show all sectors a miner currently has and proving deadlines.

    The State Tree is represented by a [HAMT](https://en.wikipedia.org/wiki/Hash_array_mapped_trie). There are currently 2 libraries that walk the HAMT to explore the Filecoin State Tree:

    -  A JS tool here: [https://github.com/keyko-io/filecoin-verifier-tools/blob/master/hamt/hamt.js](https://github.com/keyko-io/filecoin-verifier-tools/blob/master/hamt/hamt.js)

    - A Go state _diff_ tool here: [https://github.com/filecoin-project/statediff/](https://github.com/filecoin-project/statediff/) ([live demo here](https://node.glif.io/space07/statediff/rpc)) and used by spacegap.github.io


    **_We are interested in other explorers or visualizations using these libraries because they are an interesting alternative to looping thru Node API calls for every miner or chain databases._** For example, you could track the status of miners and their current Storage Power or the status of all CIDs being stored on Filecoin. 


    Ethereum blocks can also be explored at [https://explore.ipld.io/](https://explore.ipld.io/) and a similar IPLD-inspired tool for Filecoin blocks is possible. Exploring the Filecoin blockchain this way would also be an interesting experiment.


    Goals of the tool - help users:

	-   Explore Filecoin data structures
	-   How the Filecoin blockchain is set up
	-   Dive into Actors and Actor States
	-   What’s happening under the hood
	-   Offer users links like “Check out the state of this Actor right now”
	-   Have the ability to click thru different data structures
	-   Explore every block because in Filecoin it’s IPLD renderable as JSON
