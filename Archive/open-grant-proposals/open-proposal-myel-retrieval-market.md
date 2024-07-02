# Open Grant Proposal: Bootstrapping a secondary retrieval market 
- Name of Project: Hop Exchange
- Proposal Category: core-dev
- Proposer: @tchardin
- Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:  Yes
# Project Description
- From our own use of the Filecoin network, and from interviews with many Filecoin community members we have found that retrieving content from Filecoin is slow and complicated. 
- Currently, Filecoin users need to run a lotus node or a full Powergate service which have burdensome compute requirements. To enable fast retrieval, miners also need to store a duplicate copy of the content, effectively doubling storage requirements. Finally, managing and collecting payment channels can be challenging for those not familiar with the process.
- As a result, retrieval can be a daunting process for new developers. Because of this, very little content is retrieved from the Filecoin network at the moment and Filecoin is peceived as a cold storage solution.
- Our solution is a bytes exchange for IPFS, that works as a wrapper or replacement for the default Bitswap interface and allows for go-ipfs nodes to participate as content retrieval providers for Filecoin. 
   - The exchange relies on direct messaging for provisioning and GossipSub for querying blocks. 
   - We use the go data transfer protocol with custom vouchers for transferring the blocks.
   - We rely on a remote lotus node to interact with the Filecoin chain.
   - The solution is composable and can be easily integrated with Lotus nodes and Powergate services as well.
- This project will serve as a building block for [Myel](https://myel.network), a community powered content delivery network (CDN) and other CDN services out there.
## Value
- What are the benefits to getting this right?
   - This project will:
      - Improve the developer experience for uploading and retrieving content from Filecoin and drive more adoption.
      - Increase the value of Filecoin as the token will be needed to pay for retrieval deals.
      - Generate many insights on how to improve performance of retrieval on Filecoin with different degrees of decentralization.
       - Drive improvement of state actors related to payment channels as usage increases
       - Bring new members to the Filecoin community to mine retrieval deals. This gives an alternative to those who are put off because of heavy hardware requirements.
- What are the risks if you don't get it right?
   - Expensive retrieval deals may scare away some developers.
   - Clients or providers may waste FIL if data transfers aren't properly executed.
   - A failed attempt at developing a successful retrieval market may decrease the community's confidence in Filecoin becoming a major storage solution.
   - Bad architecture decisions may lead us into dead ends, wasting time and running out of funds to finish the project.
- What are the risks that will make executing on this project difficult?
   - This is a complex technical project with many moving parts. The proposed architecture isn't proven to be the best one but we need to start somewhere and iterate in order to figure it out.
   - The go-ipfs release cycle can be pretty slow so any issue that require making changes to the repo may not make it into an official release in time for compatibility with this plugin.
## Deliverables
- go-hop-exchange: a go package usable as library or as standalone IPFS node:
   - The Exchange enable both client and provider roles.
      - As a Provider it can:
         - Handle incoming messages over a custom stream protocol announcing new content to the network.
         - Decide to retrieve and store incoming content from a client with a data transfer pull request if there is enough available local storage capacity and if there is a valid storage deal on chain. The latter condition prevents peers from bloating the network with bad blocks.
         - Subscribe to a 'query' GossipSub topic and listen for content request messages encoded in CBOR.
         - Send a deal proposal through a messaging stream protocol using CBOR encoding.
         - Execute a data transfer pull request, validate vouchers and send the requested blocks.
         - Access or generate a key in the local keystore to sign vouchers. (i.e. provided by IPFS node Datastore)
         - Send chain messages to a remote lotus node RPC.
         - Manage the lifecycle of payment channels, store vouchers locally.
         - Settle payment channel automatically.
         - Collect payment channel after the wait period.
         - Garbage collect stored blocks when they haven't been requested after a set time period. Blocks provided for retrievals should be tagged in a cid set to be differentiated by the garbage collector.
         - Keep a manifest of the most requested blocks currently stored as well as requested blocks it received queries for but couldn't provide.
         - Regularly seek to improve the local block collection to maximize the number of retrieval deals it will provide. This is achieved by messaging close peers and exchanging manifests to identify and retrieve popular blocks it is not storing already.
       - As a Client it can:
         - Create a storage deal with a Filecoin storage provider.
         - Directly message connected peers until at least 6-12 have synced the content from the storage deal they have created.
         - Initiate a query for a node and a selector, published to the 'query' GossipSub topic. If none of the retrieval providers respond after a period of time we request it from the storage peer itself.
         - Set different strategy levels for selecting providers including:
            - First response with given price ceiling.
            - Cheapest price in given time period.
         - Access or generate a key in the local keystore to sign a new payment channel message.
         - Send chain messages to a remote lotus node RPC.
   - The exchange can run as standalone lightweight client without an IPFS node in which case we set default libp2p host, blockstore, datastore and graphsync instances.
   - We are also providing a basic standalone wallet interface to interact with the local keystore and send messages to a remote lotus node RPC in order to transfer funds in and out of the node's wallet. However, the focus of the deliverables will not be on the wallet experience.
 - Dynamic pricing strategy for providers, more requests per epoch for a given CID triggers price increase while less to no requests lower the pricing to a minimum provided floor. This incentivizes providers to join the network during request peaks and seek out to store more popular content.
 - Basic unit test coverage where relevant.
 - Basic testground test plans for testing the architecture at scale.
 - Benchmarks and observability. Enable the capture of proper metrics so we know what to improve from the start.
 - Godocs, onboarding documentation and examples.
## Development Roadmap
Each release will be usable and tested with the community allowing us to iterate and course correct any design flaws. Our release cycles aim for speed of iteration though we can break them down in 3 phases:

### 03/05/2021 - Content Exchange Protocol
> The bulk of this milestone is a usable version of the exchange protocol to prove out the architecture and API.
- **0.1.0**: Interface prototype and basic data transfer flow to validate the overall architecture. 
   - First usable version with free retrievals.
   - Peer management, stream and GossipSub messaging.
   - Initiate a sync request to publish a query to the 'query' GossipSub topic and retrieve blocks from retrieval providers.
   - Light wallet interface to interact with the local keystore and send messages to a remote lotus node RPC in order to transfer funds in and out of the node's wallet. 
   - Use, import or generate Secp256k1 keys and address
- **0.2.0**: Basic payments
   - Access a key in the local keystore to sign a new payment channel message.
   - Send chain messages to a remote lotus node RPC.
   - Manage the lifecycle of payment channels, store vouchers locally.
- **0.3.0**:  Filecoin Storage deals
   - Create a storage deal with a Filecoin storage provider.
   - Retrieve content from a Filecoin storage provider.
- **0.4.0**:  Settle payment channels 
   - Settle payment channel automatically.
   - Automatically collect payment channel after the wait period.
### 04/02/2021 - Routing Optimizations
> This milestone should improve the performance of content distribution and retrieval by laying the groundwork for optimizing
> the way content is propagated across the network
- **0.5.0**: Block provisioning
   - Maintain a log of all request to rank
   - Ability to sync provided blocks with a neary peer when joining the network for the first time.
   - Publish to a 'provision' GossipSub topic to announce to the network a content ID it will need to retrieve later.
   - Decision mechanism for deciding whether to store an incoming block or not.
   - Validating the incoming block has a valid storage deal.
   - Priority cue to garbage collect content that hasn't been retrieved over a given time period.
- **0.6.0**: Provider selection
   - Set different strategy levels for selecting providers including:
      - First response with given price ceiling.
      - Cheapest price in given time period.
   - Keep track of previous successful providers to increase speed of provider selection.
- **0.7.0**: - Testground test plans & Benchmarks
   - Add observability and benchmarks to retrieval operations.
   - Test the architecture with a large amount of node to find performance bottlenecks.
   - Address any potential issues in the assumptions we made designing this architecture.
### 04/20/2021 - ~~Economics~~ Stability and usability
> ~~This milestones aims at unlocking further incentives for providers to increase the number of providers~~
> In order to provide more value to the community I decided to focus on making data transfers more robust before moving to economic incentives. This milestone improves stability and usability of nodes for real world applications.
- **0.8.0**: Node CLI and HTTP Gateway
   - Implements CLI convenience methods for managing the node and provider business logic.
   - Expose HTTP GET and POST endpoints for uploading and loading content from Web applications.
   - Implements smart garbage collection mechanism to maintain optimal local storage usage.
- **0.9.0**: Testing with real world content
   - Support UnixFS DAG chunking and importing.
   - Support import from CAR files.
   - Deploy geographically distributed nodes and test transfer of NFT files.
- **1.0.0**: - Bug fixes and Documentation
   - Godocs, onboarding documentation and examples.
   - Roadmap update, define learnings and where to go from there.
## Total Budget Requested
- Budget will cover 1 engineer living expenses for the duration of the project
   - $10K per phase
- Also includes infrastructure for running multiple Filecoin test nodes
- Total: **$30,000**
## Maintenance and Upgrade Plans
- This interface will power the Myel CDN so we will be maintaining and improving it in the long term.
# Team
## Team Members
- Thomas Chardin
## Team Member LinkedIn Profiles
- https://www.linkedin.com/in/tchardin/
## Team Website
- https://myel.network
## Relevant Experience
- I was a fellow at IDEO CoLab building early prototypes with IPFS back in 2017, won the PL prize at MIT Bitcoin Hackathon 2018. This year I won the HackFS networking prize and the ETHOnline Filecoin prize as part of Myel, a company I co-founded.
- I have also been hacking and getting very familiar with the Filecoin architecture since June to figure out the best approach for executing on secondary retrieval markets.
## Team code repositories
- Project repo: https://github.com/myelnet/go-hop-exchange
- Experiment with some lotus parts: https://github.com/myelnet/go-myel-network
# Additional Information
- Once this module is out we will be able to design and implement smarter strategies for routing content to relevant peers. This will be the following step on our roadmap.
