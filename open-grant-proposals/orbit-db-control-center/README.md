# Open Grant Proposal: `OrbitDB Control Center UI: PowergateIO Integration`

**Name of Project:** `OrbitDB Control Center UI: PowergateIO Integration`

**Proposal Category:** `app-dev`

**Proposer:** `@aphelionz` on behalf of `@eqlabs`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and
APACHE2 licenses?:** Yes

# Project Description

[OrbitDB](https://github.com/orbitdb/orbit-db) is a distributed, multi-model database engine that
stores its data on IPFS as Conflict-free Replicated Data Types (CRDTs). OrbitDB has a number of
prominent users including [Metamask](https://metamask.io), [bitcoin.com](https://bitcoin.com),
[3Box](https://3box.io/), [AvionDB](https://dbdb.io/db/aviondb),
and [BitcoinCash](https://www.bitcoincash.org/).

In an effort to respond to our community's desire for reliable pinning, we recently delivered
[`orbit-db-powergate-io`](https://github.com/orbitdb/orbit-db-powergate-io), which greatly
simplified the pinning and storage of OrbitDB database snapshots on Filecoin, via Textile's
[Powergate](https://github.com/textileio/powergate).

To further improve the user experience of this process, we would like to incorporate the
[OrbitDB Control Center](https://github.com/orbitdb/orbit-db-control-center) UI. OrbitDB Control
Center is a GUI for managing databases, running in the browser. The user can intuitively create,
replicate and work with their database instances. (Notably, it also works in the mobile phone
browsers)

Since OrbitDB itself is isomorphic between the browser and node.js, as well as js-ipfs and go-ipfs,
this interface would work with all of the above, and end up being a high-visibility tool for both
the user community as well as the organizations involved: Protocol Labs, Textile, and Equilibrium.

Our [previous grant](https://github.com/filecoin-project/devgrants/pull/147) included a provision
for an addendum, and this proposal invokes that provision. If this addendum is funded, we will
deliver an updated version of the OrbitDB Control Center which makes storing and retrieving
OrbitDB databases on Filecoin intuitive and simple.

![OrbitDB Control Center Screenshot - Database Section](https://raw.githubusercontent.com/orbitdb/orbit-db-control-center/master/screenshot1.png)
![OrbitDB Control Center Screenshot - Database Details](https://raw.githubusercontent.com/orbitdb/orbit-db-control-center/master/screenshot2.png)

## Value

Our [previous grant](https://github.com/filecoin-project/devgrants/pull/147) stated that our
Powergate integration would provide visibility and user feedback to Filecoin, and thus transitively
improve the ecosystem. The rationale for this claim was that OrbitDB itself had a similar effect
on the IPFS ecosystem.

It may be too early to tell, but by participating in the APOLLO event in a mentoring capacity,
the team was able to get immediate feedback with users already trying out
[`orbit-db-powergate-io`](https://github.com/orbitdb/orbit-db-powergate-io).

Being a visual product, a GUI for databases, this project is valuable for promotional and PR
opportunities. Textile has agreed to host a Powergate instance for the duration of this project,
providing a stable location and a potential for a trifecta of promotional opportunities between
our three organizations.

### Risks, past and present

This list includes the risk from the previous grant, a brief report on how it was mitigated, and
adds a new risk category based on knowledge gained from the completed work.

#### Mitigated: Last-minute changes/issues with Filecoin network/client behavior
> Likelihood: Low | Impact: Low

During the previous milestones we were concerned that things would change quickly and often,
hampering our ability to deliver. However, through the diligence of the Filecoin engineers, as well
as the community's efforts during the Space Race, things have gone remarkably smoothly.

One big component to this is of course the abstraction provided by Powergate itself, which makes
connecting to Filcoin and interacting with the chain easy by way of its API endpoints.

This still remains a risk but has been mitigated thus far; it has therefore been downgraded to a
"Low" likelihood.

#### Minimum sector size and deal lengths introduce complexities.
> Likelihood: Near Certain | Impact: High

As of this writing, Filecoin's mainnet is aiming for a 32GB minimum sector size and a six month
deal length. This is not ideal for OrbitDB, which is made of textual / small binary data
that will have trouble filling up a 32GB sector. However, an `orbit-db-powergate-io` node could
make aggregate bulk requests, storing its known snapshots at once, for all users.

### Benefits

Within the UI, developers can easily create, replicate and manage their databases, and for
OrbitDB, IPFS and Filecoin developers this works as debuggin/verification tool for any changes
to the underlying technology.

Furthermore, this should be a seamless process of ensuring their databases are archived in Filecoin.
Also, by way of using Powergate, the snapshot CIDs are persisted in the IPFS node's "hot" storage
before they are archived to Filecoin, so the pinned data is instantly available.

The main benefit of all of this is _abstraction_. OrbitDB users will be one step closer to a "set
it and forget it" solution to persistence, and the overall system is one step closer to becoming
fully automated and decentralized.

## Development Roadmap

### Milestone 1 - UI Development

This milestone will comprise the bulk of the work for the grant. We will extend the
[OrbitDB Control Center](https://github.com/orbitdb/orbit-db-control-center) in the following ways:

#### Deliverables

- `orbit-db-powergate-io` browser support via Webpack
- Powergate API integration
    - online + status indicators
    - wallet information, including balance
    - Filecoin File System (FFS) information
    - Known CIDs
- Snapshotting app section, which includes
    - Snapshot creation
    - Snapshot pinning + archival via the aforementioned Powergate API
- Additional UI polish (as time allows)

**Estimated duration:** 4 weeks<br />
**Estimated cost:** 19,200€ / $22,397.95 USD

### Milestone 2 - Metamask snap implementation

In order to utilize the best work of the greater Filecoin community, the grant team will
incorporate [filsnap](https://github.com/NodeFactoryIo/filsnap) into the UI as well.

#### Deliverables

- A working filsnap integration within the OrbitDB control center
- Basic workflows to spend FIL and get storage on the hosted Powergate instance

**Estimated duration:** 2 weeks<br />
**Estimated cost:** 9,600€ / $11,198.98 USD

### Milestone 3 - Infrastructure Deployment

Equilibrium strives to follow all best practices in software engineering, including
fast feedback loops via continuous integration (CI) and continuous deployment. As such, this
milestone will not _directly_ follow Milestones 1 and 2. Instead, the work here will be woven
into Milestones 1 and 2, with a period of final checks and validations that follow.

#### Deliverables

- A working CI pipeline
- A reliably deployed production instance of the
[OrbitDB Control Center](https://github.com/orbitdb/orbit-db-control-center) which is connected to:
    - an IPFS node in the browser
    - a hosted Powergate instance
    - The Filecoin testnet

**Estimated duration:** 1 week<br />
**Estimated cost:** 4,800€ / $5599.49 USD

## TODO: Total Budget Requested

**Total Estimated duration:** 7 weeks<br />
**Total Estimated cost:** 33,600€ / $39,196.42 USD

## Maintenance and Upgrade Plans

We want to create software that will last into the future. Equilibrium, along with the support
of the community, pledge to continue to maintain the new OrbitDB functionalities to the best of
their ability, within any existing financial constraints.

Much like we will build upon community efforts, we will also enable and encourage others to build
upon our work. This will be a twofold effort that includes both permissive licensing and community
outreach: welcoming as many new contributors as possible, mapping the work out into issues of
different levels of difficulty, and providing mentoring.

# Team

The team is composed of the following [Equilibrium](https://equilibrium.co) team members.

We believe this team is uniquely qualified to complete this task, both the implementation
and communicating with the community in terms of the provided reference implementation and best
practices when using, implementing, and interacting with OrbitDB and Filecoin in general.

## Samuli Pöyhtäri
> [[github](https://github.com/haadcode)] [[linkedin](https://www.linkedin.com/in/samuli/)]

Samuli is the originating author of OrbitDB and is now the CTO at Equilibrium. Formerly the CEO at
Haja, Samuli and Vesa-Ville created and published the [Ambients](https://ambients.org) Protocol.
Samuli has published research related to data interoperability protocols and data structures, as
well as several open source projects and modules for the OrbitDB ecosystem. He was also an early
core developer of IPFS.

## Mark Henderson
> [[github](https://github.com/aphelionz)] [[resume](https://ipfs.io/ipfs/QmcHxD94cvJgq5ZZxQkEi7SRMwD5dBnkhQ3zzaVFqNWFJb)]

Mark Henderson is a core contributor to OrbitDB. For over a year, his full-time job was working
on OrbitDB which, in addition to adding features and increasing performance in the distributed
OrbitDB system, entailed both personally dealing with the more complex features of IPFS and
helping community members do the same.

## Vesa-Ville Piiroinen
> [[github](https://github.com/vvp)] [[linkedin](https://www.linkedin.com/in/vesa-ville-piiroinen-5b6b14/)]

Vesa-Ville is the Chief Research Officer at Equilibrium. As former CTO and co-founder of Haja
Networks, he worked on the original theory, research and design of the [Ambients](https://ambients.org),
a protocol for distributing and executing deterministic programs safely in a decentralized,
content-addressed network like IPFS. He has decades of experience in distributed systems,
databases, and interoperability solutions.

## Relevant code repositories

- https://github.com/orbitdb/orbit-db
- https://github.com/rs-ipfs/rust-ipfs
- https://github.com/orbitdb/orbit-db-control-center
- https://github.com/orbitdb/orbit-db-powergate-io
