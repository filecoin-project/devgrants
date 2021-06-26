To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `XDV`

**Name of Project:** `XDV node`

**Proposal Category:** `app-dev`

**Proposer:** `@molekilla`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** yes

# Project Description


**XDV Protocol** objective is to make any document or metadata, linked data or linked tokens, verifiable within decentralized blockchain stores like Filecoin, decentralized content network like IPFS or hybrid decentralized content network with blockchain features like Swarm Bee. `Verifiable Documents` can be a verified credential as proposed by the Verifiable Credentials model, an ERC-721 standard NFT (Non Fungible Token), a PKCS#11 or PKCS#12 signed document verifiable with government mandated smart cards or as simple as any binary data signed with a DID that can be authenticated and verified with a `proof` (eg proof of residence from a `KYC Know Your Customer`).

### Previous Work

XDV initially focused on wallets and having those wallets be able to sign documents with government mandated smart cards.
A second feature came later where the document was `anchored` to a blockchain. XDV worked with Swarm V1, which eventually shutdown and went to focus on Swarm Bee. XDV project team moved to IPFS while the new Swarm Bee blockchain was under construction. 

One feature requested was to preserve privacy, encryption or zero knowledge technologies were required. After looking for previous work, we stumble upon `Ceramic` blog and found [How to Store Signed and Encrypted Data On IPFS](https://blog.ceramic.network/how-to-store-signed-and-encrypted-data-on-ipfs/).

We took that paper as base layer for our implementation with a few twists:

- **No server changes**: Customized IPFS implementation are difficult to maintain.
- **Keep it simple**: `dag-cbor` instead of `dag-jose`.
- **Delegate missing features to other stacks**: Subscriptions, events and encryption can be done by other complementary APIs.

Another previous work that we manage to create innovation around it is `did-jwt`. We forked `did-jwt` and created `did-jwt-rsa`, which is a DID JWT that signs and verifies RSA Signatures. By accomplishing that, we practically gain DID compatibility with PKCS#11/PKCS#12, which in most governments around the world are required for legal document signing.

And then we asked ourselves, **what if you could do a RSA Signature enabled blockchain**? We found out that there is actually one project, `NDID` blockchain from Thailand, which is developed with `Tendermint`. 

## Enter XDV: The need for custom tailor made blockchain

Initially, Substrate was the top pick, but after much research about market conditions (right now is pretty difficult to find Rust engineers) and current team knowledge, we went with Cosmos SDK and Starport. 

Most of the APIs required to build XDV Protocol are in `Go`. A first protocol draft must contain the basic primitives, and further protocol versions must be able to build on previous work.

Considering that signature is just one of the many use cases, and that disparate data sources and structures will be more common in the future, XDV Protocol `lingua franca` is based in `IPLD Schemas` from Protocol Labs.

Thus, the current XDV Protocol Specification:

### Primitives

- **Files**: Decentralized content storages
- **Documents**: Document anchoring
- **NFT**: NFT (Tokenized Metadata or Non Fungible Token)
- **OffchainDataSources**: An ODBC inspired oracle based connection

### Smart Data Contracts 

- **Smart Data Contracts** uses the underlying primitives as API to build next generation ETL / Map Reduce like functions, where every data node is linkable and verifiable. 

### RBAC And ACL  (Role Based Access and Access Control Lists)

Allows to configure access controls on data nodes and sources.

## Value

Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:
- What are the benefits to getting this right?
it could replace oracles gen 1, where every data feed requires extensive development time

- What are the risks if you don't get it right?
none

- What are the risks that will make executing on this project difficult?
finding knowledgable IPLD engineers



## Deliverables

Please describe in details what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished.

## Development Roadmap

Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section).

For each milestone, please describe:
- The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates)

## Total Budget Requested

Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds.

## Maintenance and Upgrade Plans

Specify your team's long-term plans to maintain this software and upgrade it over time.

# Team

## Team Members

- Team Member 1
- Team Member 2
- Team Member 3
- ...

## Team Member LinkedIn Profiles

- Team Member 1 LinkedIn profile
- Team Member 2 LinkedIn profile
- Team Member 3 LinkedIn profile
- ...

## Team Website

Please link to your team's website here (make sure it's `https`)

## Relevant Experience

Please describe (in words) your team's relevant experience, and why you think you are the right team to build this project. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc.

## Team code repositories

Please provide links to your team's prior code repos for similar or related projects.

# Additional Information

Please include any additional information that you think would be useful in helping us to evaluate your proposal.
