# Open Grant Proposal: `Ceramic pinning to Filecoin`

**Name of Project:** Ceramic pinning to Filecoin

**Proposal Category:** `app-dev`

**Proposer:** [`@ukstv`](http://github.com/ukstv)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes.

# Project Description

[Ceramic](https://www.ceramic.network) is a protocol for decentralised identity [DID](https://w3c.github.io/did-core/) spearheaded by [3Box](https://3box.io) team. In the protocol, DID document is represented as a log of linked IPFS documents.
Currently, Ceramic _pins_ a document on a local IPFS node and maintains a list of pins on LevelDB.
As IPFS provides no guarantees for storing and retrieving records, it makes sense to use Filecoin for guaranteed data availability in distributed setting.

The project's goal is to make pinning mechanism of Ceramic node pluggable and interchangeable, with an addition of Filecoin pinning as default method. This would bring certainty and independence to storing your DID, while not relying on particular node.

Storing documents on Filecoin is quite a complex process. We intend to use [Powergate](https://docs.textile.io/powergate) as an abstraction layer. This way, Ceramic node expresses intent to pin, while some Powergate pinning provider handles the actual deal.

![Deployment](https://nd8jnw.db.files.1drv.com/y4m2RwldF6ImbjXjP1brkoI-8QPQF5ORH_wKt1V-0Kj_ThoNGD7P7SU5_HrjfE52nCrqYkReZRpAkehDrSffckEogRxfK5HcAZeefMOPVzac7q6Mtk-ORBt1WyCnWbi-RPjMund-XdpyghtJvQG4spbE-96rdQoglivUcJpuDMXdREj3Ss-SipQwbJDd59YboMHye__FLCqfnyFAJWllmuiOdasON_lyDNP730HHDERwRU/scheme.png?psid=1)

As part of effort to provide multiple redundant pinning options, Ceramic has to encapsulate that multitude into some collection, that combines different options.

![Pinning Service](https://nd8inw.db.files.1drv.com/y4maGBp-E0Z3DwJIS57R74ohIvigUGvMtfIzqmrkHmSPWAh5JTLkgbaW8bb8p-y2m2BG6cntDvEo7YsbfoYX9K69TAK0c6NuH9R8NqjKol1phOkKNy7xm1EdH_aW5QoJmjtMIAHOBGHU6xcFTUbLJpwx5pMXWhUdSyowfp95ef8cdb7e6g030ARVSEvUm_Wccv71-eIewO1tA7mLKEQNtghfQ/pinning-service.png?psid=1)

PinningService delegates actual operations to particular pinners. We assume that a call succeeds if at least one request to pinner succeeds (stricter requirement for all pinner calls to succeed would lead to distributed transaction problem, which is not quite nice).

## Value

Ceramic protocol is a foundation for the next 3Box infrastructure. In its current incarnation it is an extremely successful project, measured by users and applications that are built on top of it.
If done right, this audience would contribute to actual mass adoption of Filecoin.

Currently, the single risk I (`@ukstv`) see is complexity of running Powergate+Lotus+IPFS. It is mitigated by [managed Powergate instances](https://blog.textile.io/announcing-managed-powergate-instances-enterprise-filecoin-and-ipfs).

## Deliverables

Final delivery is a contribution to [Ceramic codebase](https://github.com/ceramicnetwork/ceramic/) which includes:
- pluggable pinning service architecture,
- local pinning service,
- Filecoin pinning service,
- documentation on Filecoin pinning set up.

## Development Roadmap

The development here is done by Sergey Ukustov (`@ukstv`), with advisory by Joel Thorstensson (`@oed`).

| Milestone                                                    | Raw time | Delivery time | Budget  |
| ------------------------------------------------------------ | -------- | ------------- | ------- |
| **Pluggable pinning services**<br />Generalisation of the current local pinning service, and providing it as a configuration option to Ceramic node. The configuration is expected to provide primary pinning service, backup pinning service, and a bunch of secondary ones. | 24hrs    | 1 week        | 1560DAI |
| **Filecoin pinning service**<br />Addition of the Filecoin pinning service. Testing against Powergate instance. | 48 hrs   | 1.5 weeks     | 3120DAI |
| **Expose Filecoin balance/pinning stats**<br />Report what pinning service is used, and provide balance, deals details, and overall count of pinned files. | 8 hrs    | 2 days        | 520DAI  |
| **Hand off documentation**<br />Document Filecoin pinning setup for Ceramic nodes, and a test scenario. | 16hrs    | 2 days        | 1040DAI |
| **Total**                                                    |          |               | 6240DAI |

## Total Budget Requested

6240DAI.

## Maintenance and Upgrade Plans

The delievery becomes a part of Ceramic codebase. Ongoing changes are to be supported by Ceramic team.

# Team

## Team Members

- Sergey Ukustov (engineer) - [@ukstv](https://github.com/ukstv)
- Joel Thorstensson (Ceramic advisor) - [@oed](https://github.com/oed)

## Relevant Experience

Sergey is an engineer with 15 years of experience in software development, including focus on distributed and blockchain technology for the last 5 years. Was involved in bringing blockchain tech to Russian banking and energy sectors. Built the first payment channels implementation in production.