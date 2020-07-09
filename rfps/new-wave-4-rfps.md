# RFP Ideas for Wave 4

Filecoin will be launching mainnet in about 2 months: [current gantt chart](https://app.instagantt.com/shared/s/1152992274307505/latest).

We are seeking proposals for the following RFPs for Wave 4 of the Dev Grant program.

The deadline for Wave 4 proposals is **July 1st, 2020 at 23:59 PDT** for priority consideration. We will evaluate later proposals submitted after the deadline as capacity allows.

## RFP Ideas

- Priority
  - [go-filecoin Community Maintainership](#go-filecoin-maintainership)
  - [Storage client application with erasure coding and basic PGP](#storage-client-application-with-erasure-coding-and-basic-pgp)
  - [Simple Storage webapps](#simple-storage-webapps)
  - [Windows support for lotus](#windows-support-for-lotus)
  - [Remote HSM Signer support](#remote-hsm-signer-support)
  - [Devnet scripts](#devnet-scripts)
  - [Crosschain integrations](#crosschain-integrations)
  - [Simple lotus block explorer update](#simple-lotus-block-explorer-update)
  - [Shared Blocklists of content CIDs](#shared-blocklists-of-content-cids)

- Other Ideas
  
  (Details on these below can be found in the [Wave 3 RFP list](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md))
 
  - [Storage and Retrieval Market Order Books](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#storage-and-retrieval-market-order-books)
  - [Web archiving browser extension or Twitter bot](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#web-archiving-browser-extension-or-twitter-bot)
  - [S3 (Glacier) API for Filecoin](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#s3-glacier-api-for-filecoin)
  - [FLOPy AWS Snowball-like hard drive service](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#flopy-aws-snowball-like-hard-drive-service)
  - [GraphQL API for lotus-chainwatch](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#graphql-api-for-lotus-chainwatch)
  - [Storage Workflow User Research](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#storage-workflow-user-research)
  - [Snarks as a Service](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#snarks-as-a-service)
  - [VM research - verifiable subsets of WASM-able languages](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#vm-research---verifiable-subsets-of-wasm-able-languages)
  - [VM research - Improving state tries](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#vm-research---improving-state-tries)
  - [Expert use of large data archives](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#expert-use-of-large-data-archives)

We also accept **Open Grant Proposals** where you can suggest your own Filecoin project idea.

*Teams that applied for any of the above RFPs in Wave 3 who did not receive grants will be reconsidered for Wave 4.*

See our [Proposal Guidelines](#proposal-guidelines) below about how to apply.

*Have a question about any of these RFPs? Email devgrants@filecoin.org*

&nbsp;

## *Priority RFP ideas*

&nbsp;

### go-filecoin Maintainership

**Project Description**

We are looking for teams interested in stewarding and improving [go-filecoin](http://github.com/filecoin-project/go-filecoin), one of the [4 current Filecoin implementations](https://filecoin.io/blog/announcing-filecoin-implementations-in-rust-and-c++/). go-filecoin is nearly feature-complete, so you will be starting from a very strong foundation. lotus and go-filecoin achieved interoperability in April 2020, but go-filecoin will need to be updated to bring it back to an interoperable state and to feature-completeness for mainnet launch. 

As the implementation graduates to community maintainership, we are looking for community members able to actively maintain compatibility with the other Filecoin implementations, run and optimize this implementation in live deployments, and ensure go-filecoin continues to be a fully-functional implementation. This is a great opportunity for teams to become strong stakeholders and stewards in the Filecoin ecosystem by building their expertise and engagement. This grant builds on the [previous RFP for protocol implementation teams](https://github.com/filecoin-project/devgrants/issues/43) (see the [full grant specification](https://docs.google.com/document/d/1L7ZZOC4cms3SZNyx7u1Hr0H_XFDUI8FYA2W8dXWBGsY/edit) for details).

In particular, we’re looking for teams that are interested in differentiating the go-filecoin implementation from other Filecoin implementations to drive adoption. Some examples include:
- Making the implementation highly optimized for mining operations
- Building services around the core go-filecoin implementation, e.g. hosting go-filecoin nodes as a service
- Involving the greater Filecoin community in completing the implementation
- We’d love to hear any other direction you think is compelling as well

Please drop any questions in the [go-filecoin maintainership issue](https://github.com/filecoin-project/devgrants/rfp-go-filecoin-maintainership.md).

&nbsp;

### Storage client application with erasure coding and basic PGP

**Project Description**

A storage client application with an easy-to-understand interface and nice UX that has support for basic file encryption and erasure coding to suggest an ideal number of redundant storage deals. The application should allow users to encrypt data, enter into storage deals with several miners, retrieve and decrypt the data.

**Proposed Features**

- encrypts and decrypts a file using basic PGP (e.g. [Keybase example](https://keybase.io/encrypt) or with MetaMask keys or other options)
- calculates recommended redundancy using a good erasure coding library (e.g. [zfec](https://github.com/tahoe-lafs/zfec)) and can reconstruct data if a copy cannot be retrieved
- enters into a recommended number of storage deals
- can range from a simple single-page webapp with a simple drag n’ drop interface to a desktop application
- decentralized application or dapp although it can assume public hosted Filecoin node JSON RPC API endpoints exist
- optionally can also split larger files into smaller pieces
- optionally can also use [this Filecoin signing tools library](https://github.com/zondax/filecoin-rs) or [the Filecoin JS API](https://github.com/filecoin-shipyard/js-lotus-client) (both are currently WIP)

Your proposal should provide examples of applications and user interfaces your team has built and links to their code repositories.

&nbsp;

### Simple Storage webapps

**Project Description**

Single page apps that demonstrate using Filecoin to store and retrieve files. Example workflow: drag + drop a file, pay to store it, retrieve it. Show miner info, CIDs.

One version could eli5 (explain-it-like-I'm-5) to new users as a tutorial or tour.

Your proposal should provide examples of applications and interfaces your team has built and links to their code repos.

Also see [Filecoin community resources](https://github.com/filecoin-project/docs/wiki) for an initial list of Filecoin developer tools.

&nbsp;

### Windows support for lotus

**Project Description**

lotus Filecoin currently supports Arch Linux, Ubuntu, Fedora and MacOS. Golang can also be cross-compiled to Windows, so Windows support for lotus could be added as described in [lotus issue 2133](https://github.com/filecoin-project/lotus/issues/2133). This project would provide basic support for running a full node on Windows. It will also also require compiling the rust-fil-proofs library in Rust.

Use cases to support include reading from the chain, submitting transactions and participating in storage deals. Support for mining on Windows may be more complicated and is not required for to fulfill this RFP.

&nbsp;

### Remote HSM signer support

**Project Description**

A pluggable remote signing module that supports HSMs would allow Filecoin miners to secure their private keys used to participate in block signing and consensus.

[lotus issue 2016](https://github.com/filecoin-project/lotus/issues/2016) describes an API interface for remote signers that can “secure a miner’s worker key, which is required to be used every epoch period (25s) to perform around 5 signing operations.” The API calls listed are currently in the [lotus JSON RPC API](https://github.com/filecoin-project/lotus/blob/master/api/api_full.go#L160), the ExternalBackends endpoint may need to be added to lotus.

*Requirements*

1. Miner worker keys are BLS
2. Slashing checks for not signing blocks at the same height
    - double sign protection in the HSM (e.g. if a node is compromised)
3. Whitelisting withdrawal addresses
4. Load balancer for using multiple HSMs (e.g. multiple USBs)
5. RPC calls
6. VPN / TLS tunnel to the node
7. 5 signatures within a 25s block epoch time / a few signatures per second

*Other notes*
- The Remote Signer module can be a small Docker.
- Node keys for storage deals are out of scope (but could be added).
- [Filecoin signing tools](https://github.com/zondax/filecoin-rs) is an existing standalone library that includes BLS signing and can be a locus for a remote signer / KMS.

Support for a various HSMs will be considered as this increases security biodiversity e.g. Ledger Nano X, YubiHSM2, USB Armory, iMX8, cloud vaults, etc. PCIe and rack HSMs integrations may be considered but they are expensive options for miners.)

&nbsp;

### Devnet Scripts

**Project Description**

A description of how to set up a shared Filecoin Devnet has been shared [here](https://gist.github.com/travisperson/c04b0ed8058a31bc5cc119bde9bac3a3). We are interested in proposals to automate this process so shared Devnets become easier to deploy. Via an open source Kubernetes script or Helm chart would be an ideal automation script.

Basic Devnet features should include setting up a faucet, bootstrapper nodes and a genesis miner, smaller sector sizes to speed up developer workflows and testing, dedicated storage miners, some ideas on how to prevent Devnet attacks.

The intent is to support developers who want to use shared devnets for faster development, testing and collaboration, similar to the various testnets available for live blockchain networks.

&nbsp;

### Crosschain integrations

**Project Description**

We are seeking proposals for infrastructure and dapp demos that can demonstrate early integrations between another blockchain and Filecoin. One example of infrastructure proposed for crosschain integration with Filecoin is a smart contract event listener on another chain + a Filecoin storage or pinning service.

Dapps can directly store to Filecoin at the client dapp level using an existing JS API. For deeper integration, user-defined smart contracts are a roadmap feature in Filecoin, likely for next year, therefore protocol-level cross chain bridges are also roadmap.

To support Filecoin storage at the smart contract level, interim cross chain tooling could be built for now that can help make Filecoin storage programmatic from Substrate smart contracts and runtimes.

*Triggering Storage to Filecoin*

There are currently 3 main ways for developers to use Filecoin:

1. [Filecoin node JSON RPC API](https://lotu.sh/en+api) - requires interacting with the Filecoin storage market and storage deal lifecycle management. A JS convenience library for this is development.
2. [Powergate on top of Filecoin](https://docs.textile.io/powergate/) - a sidecar to a Filecoin node that provides a deal agent, fast retrieval (using IPFS for hot storage), node keys (required for storage deals) mapped to multi-tenant sets of wallets, plus other convenience features for developers so less storage market management is required. Has a JS library as well.
3. [Filecoin-backed IPFS Pinning Services](https://ipfs.io/ipfs/QmeGwRiy1MBiH7vBgvVawpFMc5bWLL1iiqmLmaJp3LyaZ6) - will expose a simplified Pinning API for storing and retrieving data, may use Powergate under the hood. (Currently in development.)

For native IPFS users, Filecoin currently also offers ways to [pull data from remote IPFS nodes](https://github.com/filecoin-project/lotus/pull/1843).

*Examples from Substrate*

Pinning APIs are likely the easiest cross chain infra to start and could be used with a [Substrate Offchain Worker](https://substrate.dev/docs/en/knowledgebase/learn-substrate/off-chain-workers#docsNav) (also see the [offchain Rust IPFS project](https://github.com/w3f/General-Grants-Program/pull/283)). A later step could be a parachain that talks to Filecoin.

*Example from Ethereum*

A prior example is an Ethereum smart contract event listener that triggers an IPFS Pinning API like [Quasar](https://github.com/openworklabs/quasar/blob/primary/docs/howQuasarWorks.md#under-the-hood), a project explored by the Aragon community for IPFS Cluster, or later Aragon integration with an IPFS pinning service.

*Confirming Storage Status*

A [Filecoin data CID checker](https://github.com/filecoin-project/devgrants/blob/master/rfps/wave-3-rfps.md#filecoin-cid-checker-and-storage-oracle) is being built that can serve as a storage oracle via API of the status of a specific data CID on Filecoin, pulled from the latest state.

*Payments*

How crosschain payments should work is an ongoing question. This could be solved by an infrastructure service provider in the near-term. We expect payments and micropayments for infrastructure services to be an interesting area to explore in the future after launch.

&nbsp;

### Simple lotus block explorer update

**Project Description**

Last year, a simple Filecoin block explorer was built for an earlier go-filecoin node implementation. It was updated for the lotus Filecoin node for the 2019 December testnet launch [here](https://github.com/openworklabs/lotus-block-explorer).

We would like to see this simple explorer updated to the current lotus API and testnet / mainnet. Enhancements can be made to improve performance and the information displayed.

This explorer originally presented details about Filecoin actors (current core smart contracts hardcoded in the protocol) such as the Storage Market actor, Miner actors, as well as information contained in blocks. ([Screenshots are available here](https://filecoinproject.slack.com/archives/CFP9A2T7W/p1593095833249300?thread_ts=1593095710.249000&cid=CFP9A2T7W).)

This explorer can make a great tutorial on interacting with the Filecoin JSON RPC API. If interested, please add that to your proposal.

&nbsp;

### Shared Blocklists of Content CIDs

lotus Filecoin has added the ability for miners to create blocklists of content piece CIDs they do not want to store or serve retrieval requests for (See [lotus PR 2069](https://github.com/filecoin-project/lotus/pull/2069)). This may be required for miners to comply with local law enforcement requests (which lists to respect and which items to block are entirely up to the miner operator).

This RFP is for a way for blocklists to be shared by the community, potentially with some basic metadata around the reasons for blocklisting. A way for community members to propose CIDs to blocklist would also be useful.

Related projects in IPFS have proposed a [content-decider framework](https://github.com/ianjdarrow/content-decider) and [DNR lists](https://github.com/ipfs/camp/blob/master/DEEP_DIVES/25-do-not-replicate-lists-dnr.md#do-not-replicate-lists---dnr).



&nbsp;

### Additional RFPs

Additional RFPs can be found in the [Wave 3 RFP list](https://github.com/filecoin-project/devgrants).

&nbsp;

----

## Proposal Guidelines

We generally fund projects that can be built in a 2 month time frame and evaluate proposals based on:

- The quality of the proposal and near-term value to the Filecoin ecosystem
- Your team’s technical experience, open source contributions and interest in diving into how Filecoin works
- Likelihood that your team will continue to support the Filecoin ecosystem long-term and commitment to maintaining your project for one year

Note that all proposals must be open sourced via MIT and Apache2 licenses.


**Proposal Requirements**

Proposals should include a value proposition about how it will benefit the Filecoin ecosystem, technical detail about what your team intends to build and evidence your team is capable of creating good, re-usable open source code, compelling product demos and great documentation, and a reasonable technical development plan broken down into milestones. Here's a [good sample proposal](https://github.com/ipfs/devgrants/blob/master/targeted-grants/IPFS-mobile-design-research.md).

Proposals should include:

1. Project Description
   - Brief description
   - Value to the Filecoin ecosystem
2. Deliverables
   - An explanation of your technical solution and architecture
      - Imagine that an experienced software developer will evaluate your proposal
3. Milestones & Funding requested
   - Most projects have at least 4 milestones
   - Budget and estimated timeframe for each milestone
4. Team
   - Roles and Experience
       - Teams with a history of high-quality open source code repos and live applications and products are preferred.

We also accept **Open Grant Proposals** where you can suggest your own Filecoin project idea. [More info](https://github.com/filecoin-project/devgrants/blob/master/open-grant-proposals/open-proposal-template.md)

To submit a proposal, fork and make [a PR](https://github.com/filecoin-project/devgrants/pulls) to this repo by July 1st 23:59 PDT (for priority consideration. We will evaluate later proposals submitted after the deadline as capacity allows.)

&nbsp;

---

*Have a question about any of these RFPs? Email devgrants@filecoin.org*
