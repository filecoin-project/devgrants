# Developer Tooling Ideas

We are seeking proposals for the following RFPs for various developer tools.

  - [WebRTC Direct libp2p transport productionization and standardization](#webrtc-direct-libp2p-transport-productionization-and-standardization)
  - [Shared Blocklists / Wantlist of content CIDs](#shared-blocklists--wantlists-of-content-cids)
  - [CID Indexing Tool for Miners and Storage Clients](#cid-indexing-tool-for-miners-and-storage-clients)

&nbsp;

*Thanks to @willscott, @daviddias, and @mishmosh for suggesting and giving feedback on all these initial ideas.*

&nbsp;

### WebRTC Direct libp2p transport productionization and standardization

Libp2p has a number of transports, including QUIC, WebSockets, TLS/TCP, and noise/TCP. There have been a couple attempts towards including a WebRTC transport in this category, but thus far these have only yielded limited success. Since the last attempt, there has been maturation both of the libp2p standardization process, and of the quality of WebRTC libraries, especially for golang. We are interested in helping bring a solid, network-ready webrtc transport to fruition, as it can play an important role in libp2p networking going forward.

In particular, WebRTC holds a unique position in its ability to support bridging between long-lived daemons running in a p2p network with more transient browser clients. Browsers are significantly limited in the types of connections they can initiate. Today, the WebSocket transport is the only common libp2p transport that allows browser clients to connect to a node, and unfortunately it cannot be automatically configured since it requires the addition of a dnsname, and a manually acquired TLS certificate for the node operating the WebSocket server to meet the security requirements imposed by web browsers. In contrast, WebRTC is designed as a p2p protocol between two web clients. As such, a WebRTC listener would be able to automatically accept connections from web users without further operator configuration. In cases where devices have globally public IPs, or where operators configure port forwarding on their firewalls, so that the socket listening for inbound connections can be reached globally without NAT hole punching, the WebRTC connection process can be short circuited to match the efficiency of existing transports. This is done by the client creating a synthetic SIP record (“churn”)  to communicate to the transport layer that they have learned from an external signaling source the host and port at which their counterparts are listening. Since this host and port will be communicated through multiaddrs in the libp2p ecosystem, it will already be known at the point of connection, and can allow for efficient connections when the remote party is globally reachable.

The WebRTC transport protocol shares many of the same characteristics as the recently implemented QUIC protocol. Both use UDP at a base layer, and both natively multiplex multiple streams over that UDP connection. In the case of WebRTC this is done by opening data channels over the peer connection. Note that there are situations where creating a WebRTC data channel can trigger renegotiation of the transport. As such, there should be care taken to always keep a data channel open, and either to use an existing libp2p mux for streams within one rtc data channel, or to use the negotiated property on creation to agree on additional stream IDs without potentially re-initiation connection negotiation.

#### Deliverables

- A direct webRTC transport specification for libp2p
- A go-libp2p-webrtc-direct transport, which supports connection establishment and transport of libp2p streams over WebRTC and which:
  - allows connection based on a multiaddr, without the need for a signaling server when the remote address is not behind a NAT
  - Makes use of libp2p-relay as a signaling channel when optimistic direct connection fails
  - Advertises a multiaddr either directly or behind a relay based on local determination of NAT status

#### Additional Resources

- https://github.com/libp2p/js-libp2p-webrtc-direct
- https://github.com/libp2p/go-libp2p-webrtc-direct

&nbsp;
-----
&nbsp;

### Shared Blocklists / Wantlists of Content CIDs

Lotus Filecoin has added the ability for miners to create blocklists of content piece CIDs they do not want to store or serve retrieval requests for (See [lotus PR 2069](https://github.com/filecoin-project/lotus/pull/2069)). This may be required for miners to comply with local law enforcement requests (which lists to respect and which items to block are entirely up to the miner operator).

This RFP is for a way for blocklists to be shared by the community, potentially with some basic metadata around the reasons for blocklisting. A way for community members to propose CIDs to blocklist would also be useful.

Related projects in IPFS have proposed a [content-decider framework](https://github.com/ianjdarrow/content-decider) and [DNR lists](https://github.com/ipfs/camp/blob/master/DEEP_DIVES/25-do-not-replicate-lists-dnr.md#do-not-replicate-lists---dnr).


&nbsp;
-----
&nbsp;


### CID Indexing Tool for Miners and Storage Clients

A CID indexing tool for all sectors that a storage miner has, as software that sits on top of a Filecoin node and sends data to a community aggregator.

Alternatively, a CID metadata index for storage clients to batch and keep track of larger archives stored on Filecoin.

#### Description

Storage miners who offer more information about CID data and sector status are likely to be more attractive to storage clients.

A CID indexer could be run as a sidecar to Lotus to keep track of all sectors a miner has:

- Grabs all the IPLD data structures of the client data
- Understands every CID
- Maps CIDs to sectors and offsets
- Creates a local CID index
- Then storage miners could share their CID index with a aggregator for community visibility

Sectors that miners have can also be observed at https://spacegap.github.io.

Optionally this tool could also map Filecoin pieceCIDs to payload / data CIDs (as used in IPFS) to support Retrieval Miners and Clients. https://github.com/mgoelzer/cid_oracle is another tool that scans the Filecoin blockchain for pieceCID to payload CID mappings.

-----

To apply for any RFPs see our [Proposal Guidelines](#proposal-guidelines) below for how to apply.

*Have a question about any of these RFPs? Email grants@filecoin.org*


-----

### Proposal Guidelines
### Filecoin Dev Grants

We generally fund projects that can be built in a 6 week to 2-3 month time frame and evaluate proposals based on:

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
3. Milestones & Funding requested
   - Budget and estimated timeframe for each milestone
4. Team
   - Roles and Experience

We also accept **Open Grant Proposals** where you can suggest your own Filecoin project idea. [More info](https://github.com/filecoin-project/devgrants/tree/master/open-grants)

To submit a proposal, submit an issue using this [RFP Proposal Template](https://github.com/filecoin-project/devgrants/issues/new?assignees=realChainLife&labels=&template=rfp-proposal.md&title=RFP+Application).

&nbsp;

---

*Have a question about any of these RFPs? Email grants@filecoin.org*
