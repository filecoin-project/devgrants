# Open Grant Proposal: `OrbitDB Filecoin Integration`

**Name of Project:** `OrbitDB Filecoin Integration`

**Proposal Category:** `app-dev`

**Proposer:** `@aphelionz` on behalf of `@eqlabs`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and
APACHE2 licenses?:** Yes

# Project Description

[OrbitDB](https://github.com/orbitdb/orbit-db) is a distributed database engine that stores its
data on IPFS as Conflict-free Replicated Data Types (CRDTs). OrbitDB has a number of prominent
users including [Metamask](https://metamask.io), [bitcoin.com](https://bitcoin.com),
[3Box](https://3box.io/), [AvionDB](https://dbdb.io/db/aviondb),
and [BitcoinCash](https://www.bitcoincash.org/).

Of all the features and improvements requested by our community, reliable pinning is perhaps the
most common. An OrbitDB user wants their data to persist in the distributed swarm safely and
reliably, with minimal configuration and attention required.

If this grant is funded, we will deliver a baseline Filecoin integration into OrbitDB,
allowing users to integrate to any complaint Filecoin node via the JSON RPC APIs.

## Value

At nearly [4,500 GitHub](https://github.com/orbitdb/orbit-db/stargazers) stars, OrbitDB is one of
the more high-profile projects in the `js-ipfs` ecosystem. This means we have a track record of
positive impacts that OrbitDB has already had on a prominent Protocol Labs project.

The benefits of this have so far been:

1. Raising awareness of IPFS through its transitive use in OrbitDB
2. Driving improvements in IPFS due to community demand and response to OrbitDB

It follows, then, that Filecoin could enjoy similar, synergistic effects with OrbitDB.
This Filecoin integration, and its future users are very likely to provide valuable
context and feedback to the Filecoin Project, and drive the project roadmap forward.

### Risks

Of course this outcome is not guaranteed, and not without risk. During the initial planning
process the grant team has identified the primary risks that could impact either the
implementation process or the desired outcome of the grant effort.

#### Last-minute changes/issues with Filecoin network/client behavior
> Likelihood: High | Impact: Low

As of this writing, Filecoin is still in active development prior to its planned MainNet launch.
Things can and will change fast, potentially even after the MainNet launch. The grant team simply
accepts this risk and we will plan accordingly. The practical upshot of this is that we will allot
slightly more time in our milestone schedules to account for such contingencies.

### Benefits

If this project succeeds, OrbitDB's users will be happily pinning their data, and
Filecoin will have a successful example of a net-zero, non-profit pinning community
running within its network.

Also, as mentioned in the [value](#value) section above, the effort itself will raise awareness of
Filecoin as well as help steer the roadmap based on real-world usage.

## Development Roadmap

As per the [Risks](#risks) section, this is subject to change as the project and Filecoin
itself mature over the coming months.

Note: The budget in the milestone is based on the _equivalent_ of one full-time developer working
on the project at a time. This metric is used for ease of understanding and the work may be the
result of many team members via more granular chunks of work.

### Milestone 1 - Implementation

#### Deliverables

- A public repository with a working implementation of OrbitDB pinning using
the Powergate APIs
- Documentation, tests, and instructions

[`orbit-db-io`] is an existing package that handles reading and writing data from the
IPFS DAG, and is the cornerstone of [`ipfs-log`]. The grant team would repeat this
pattern to create `orbit-db-filecoin-io` which would be similarly composable with
[`ipfs-log`].

`orbit-db-powergate-io` would follow Filecoin standards and utilize the PowerGate APIs,
allowing it to interface with the PowerGate service, allowing OrbitDB users to utilize
the Filecoin functionalites that PowerGate exposes.

[`orbit-db-io`]: https://github.com/orbitdb/orbit-db-io
[`ipfs-log`]: https://github.com/orbitdb/ipfs-log

**Estimated duration:** 3 weeks<br />
**Estimated cost:** 14,400€ / 16,172.14 USD

#### Pre-Addendum Research

At this point, implementations of the Pinning API should be available and more robust, and we can more
reliably plan and estimate work towards making OrbitDB compatible with the official IPFS Pinning API,
meaning that any system that implements this API will be compatible with OrbitDB.

Since the state of the Pinning API implementations, and the Pinning. This next milestone is a planned
addendum to this grant effort.

Work during the addendum may include some, any, or none of the following items:
- Implementing with existing pinning APIs that hosted services are using
- Creating a shim between the Pinning API and PowerGate
- Implementing our own version of the Pinning API (or the above shim) that OrbitDB users can self-host 

## Total Budget Requested

**Total Estimated duration:** 3 weeks<br />
**Total Estimated cost:** 14,400€ / 16,172.14 USD

## Maintenance and Upgrade Plans

We want to create a codebase that will last into the future. Equilibrium, along with the support
of the community, pledge to continue to maintain the new OrbitDB functionalities to the best of their
ability, within any existing financial constraints.

Much like we will build upon community efforts, we will also enable and encourage others to build
upon our work. This will be a twofold effort that includes both permissive licensing and community outreach:
onboarding as many new contributors as possible, mapping the work out into issues of different levels of
difficulty, and providing mentorship.

# Team

The team is comprised of the following [Equilibrium](https://equilibrium.co) team members.

We believe this team is uniquely qualified to complete this task, both the implementation
and communicating with the community in terms of the provided reference implementation and best
practices when using, implementing, and interacting with OrbitDB and Filecoin in general.

## Samuli Pöyhtäri
> [[github](https://github.com/haadcode)] [[linkedin](https://www.linkedin.com/in/samuli/)]

Samuli is the originating author of OrbitDB and is now the CTO at Equilibrium. Formerly the CEO at Haja,
Samuli and Vesa-Ville created and published the [Ambients](https://ambients.org) Protocol.
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
