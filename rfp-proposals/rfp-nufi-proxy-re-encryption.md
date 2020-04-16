# RFP Proposal: `nufi`

**Name of Project:** `nufi` – NuCypher Proxy Re-Encryption into Filecoin


**Link to RFP:** [New RFP Ideas for Wave 3](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#storage-client-application-with-erasure-coding-and-basic-pgp)

**RFP Category:** `app-dev`

**Proposer:** [cygnusv](https://github.com/cygnusv) (from [nucypher](https://github.com/nucypher))

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Data stored in the Filecoin network is securely encrypted, but it can’t be shared easily since only the data owner knows the secret key. The data owner would have to either share their secret key with intended recipients or encrypt their data specifically for each recipient (e.g. using the recipient's key). These options are impractical regarding privacy and scalability; this is a classic problem of secure storage solutions based on symmetric encryption. To mitigate this shortcoming, we propose `nufi`, an integration of Filecoin with the NuCypher Network, a decentralized access control service based on proxy re-encryption that allows data owners to securely and scalably share encrypted data with recipients of their choice without exposing their secret key. Its decentralized nature ensures that it is permissionless and censorship-resistant. One of the main advantages of NuCypher’s PRE-based solution for data sharing is that encryption of data is independent from the data sharing decision; that is, data can be encrypted with the ability to grant access to anyone at a later date, without having to encrypt it again.

The NuCypher Network is storage-agnostic since it exclusively manages access rights and does not store any data; it works with data stored locally or remotely (cloud storage providers, IPFS, etc). Instead, it is an application layer that is only engaged when data owners grant or revoke access to data and when access rights need to be enforced when data is retrieved. The data is shared in an end-to-end encrypted fashion, without the network ever having access to secret keys or the data. Data owners can issue sharing policies to the network for any number of recipients, and the recipients can subsequently have the data re-encrypted for them by the network. We have also added functionality to sharing policies to facilitate re-encryption thresholds (`m-of-n` scheme) where `m` nodes are needed for re-encryption, and an expiry date/time after which the sharing policy is voided and data will no longer be re-encrypted for the corresponding recipient. 

From a high-level, what we propose with `nufi` is an application that provides a seamless experience for users wanting to share their data encrypted on Filecoin. Under the hood, `nufi` will be built on top of the Filecoin and NuCypher Network stacks, where the former provides the substrate where data is stored and the latter serves as a secure data sharing and access control layer.

Value points from our proposal:

* Filecoin and the NuCypher Network are complementary solutions, the former being decentralized encrypted data storage, and the latter being decentralized access control of that data. The addition of end-to-end encrypted data sharing facilitates a variety of more complex use cases for the Filecoin platform. Some use cases that have already gravitated to the NuCypher platform include medical data sharing, data marketplaces, Internet of Things.
* Existing proxy re-encryption platform: NuCypher is currently running on the Ethereum Goerli testnet with hundreds of active nodes all around the world, which ensures a 24/7 available platform to develop this project. These nodes already provide a proxy re-encryption service, which means that this proposal only has to focus on the integration with Filecoin.
* Traction: NuCypher mainnet will be released in the next few months, which will give the Filecoin project not only a more secure and stable network to run this service, but also additional attention from users, developers and the broader decentralized community.



## Deliverables

The main deliverable of this project is `nufi`, a software application that leverages Filecoin for storage and NuCypher for access control. Technically, it's an integration between a NuCypher client and a Filecoin client; this integration may be in the form of a plugin for the Filecoin client (if possible) or an extension. The Filecoin client may be either `lotus` or `go-filecoin`, depending on the potential for integration.

The details of the functionality provided by `nufi` can be better explained by this user story:

1. Alice, a user wishing to securely store and share files, uses a Filecoin client (e.g., `lotus`) to interact with Filecoin. Alice is the owner of her data, and as such, only her should decide when and with whom is her data shared.
1. Before storing the data, Alice must “label” the data she wants to store and protect. Labels are simple strings, but NuCypher cryptographically enforces access-control depending on the data labels. Although the same label can be used multiple times (typically, this is the case), each piece of data can only have one label. In our example, she has a lot of heartbeat readings from a heart monitor, and she tags all of them with the “heartbeat” label.
1. The Filecoin client, which integrates `nufi`, encrypts her data according to her defined labels. Data is sent to the Filecoin network for storage. `nufi` will check that storage contract expiry matches or exceeds sharing policy expiry date, based on cost/duration and committed FIL and ETH funds.
1. Some weeks later, Alice decides she wants to give access to her heartbeat data to her doctor, Bob. Note that data was encrypted and sent to the Filecoin network before this access decision, and that there’s no need to do anything with it. Alice uses `nufi` to create a data sharing policy granting access to Bob for a certain duration. The policy is accepted and enforced by the NuCypher network.
1. Bob uses the Filecoin client, which integrates `nufi`, to request access to some heartbeat data files from Alice. This step engages an interaction with the NuCypher Network to perform the re-encryption of encrypted data. If Alice’s data sharing policy is still valid, Bob will receive a re-encrypted version of the heartbeat data file.
1. Bob’s Filecoin client uses his private key to decrypt Alice’s files. The keys involved in encryption and decryption are never exposed to the nodes of NuCypher network or Filecoin.
1. At any time, Alice can revoke access to Bob. She uses `nufi` to interact with the NuCypher network and send a revocation request that will deactivate her data sharing policy.

In addition to the main deliverable, we’ll provide a simple demo application which demonstrates `nufi`’s functionality with a user story like the one above, as well as complete documentation.


## Development Roadmap

### Overview

| Milestone | Description                                   | Duration  | # of People | Cost    |
|-----------|-----------------------------------------------|-----------|-------------|---------|
| M0        | Technical deep-dive into Filecoin             | 2 weeks   | 4           | $4,500  |
| M1        | Integration of proxy re-encryption primitives | 2 weeks   | 2           | $7,500  |
| M2        | Gateway for unified user experience           | 4-5 weeks | 4           | $30,000 |
| M3        | Connection to NuCypher Network                | 2-3 weeks | 4           | $12,000 |
| M4        | Showcase of `nufi` MVP                        | 2 weeks   | 3           | $6,000  |

*Note: we don't specify the roles of participants as we try to be very fluid about it.*

### Milestone 0: Technical deep-dive into Filecoin

There are two main aspects that we will investigate here:

* Interoperability between native encryption layer of Filecoin and our Umbral PRE scheme. Our scheme uses hybrid encryption following a [key encapsulation approach](https://en.wikipedia.org/wiki/Key_encapsulation), so it also produces symmetric keys for data. This brings the question of how both types of symmetric keys can be integrated. 
* Interoperability of Filecoin with other blockchains (particularly, Ethereum). In order to improve user experience, it would be valuable that `nufi` offers an integrated gateway to both Filecoin and NuCypher platforms (based on Ethereum).

Rather than a software outcome, the goal here is to obtain a clear understanding of how to proceed in the next phases of development.

### Milestone 1: Integration of proxy re-encryption primitives
This milestone is focused on the development of the necessary plugins or connectors to allow the PRE-based encryption and decryption by Filecoin clients, such as `lotus`. It’s worth mentioning that (i) these primitives are already implemented by our `pyUmbral` library, and (ii) the Filecoin client doesn’t implement re-encryption primitives, as this is a service already provided by the NuCypher network. Hence, the major development here is the integration with current Filecoin’s approach for encryption and decryption of data. 

### Milestone 2: Gateway for unified user experience

Ideally, users that hold FIL tokens need to be able to create data sharing policies in NuCypher (which currently requires paying with ETH). This could be achieved through different ways, depending on the findings on Milestone 1 and the expected effort. We list here some options, in increasing order of difficulty:

* Unified user interface where users interact independently with both blockchains. This requires that users hold FIL and ETH.
* A FIL-to-ETH gateway, exclusively limited to enabling the use of FIL tokens to create NuCypher policies.
* Ethereum-Filecoin Bridge, allowing Filecoin users to read and transact with the Ethereum blockchain. This option probably exceeds the scope of this proposal and seems like a project on its own.

Note that this milestone can run in parallel to milestone 1. Also, this is the milestone which presents more unknowns (both known unknowns and unknown unknowns), so it’s difficult to estimate the duration of this milestone (and therefore, also the funding). For this reason, we can consider devoting additional resources if necessary.

### Milestone 3: Connection to NuCypher Network

From the outcome of milestones 1 and 2, we will be in position to achieve data sharing and retrieving using the proxy re-encryption service provided by the NuCypher Network. The goal of this milestone is to integrate NuCypher’s access granting and access requests workflows with the Filecoin client. 

### Milestone 4: Showcase of `nufi` MVP

Create a simple demo application to showcase the ability to store data via Filecoin and utilize the NuCypher Network to enforce access controlled privileges when data is shared with various recipients. The goals of this milestone are to reinforce that `nufi` provides its purported functionality in a practical manner and to confirm our platform/API design decisions.




## Total Budget Requested

$60,000

## Maintenance and Upgrade Plans

NuCypher’s mandate is to implement the cryptographic primitives of today and research the cryptographic primitives of tomorrow that will enable individuals to assert their right to privacy. Our long-term vision is for the widespread use of the NuCypher Network by privacy-preserving applications. This includes continued development and maintenance of the network while ensuring compatibility with applications built on top of it.

`nufi` will be developed by part of the NuCypher team, but additionally, will be open-sourced and therefore can be maintained both by our team and the broader open-source community. As our existing cryptographic research progresses, the network may provide additional cryptographic primitives which may also be incorporated into `nufi`.


# Team

## Team Members

* David Núñez: Cryptographer and engineer
	* https://www.linkedin.com/in/davidnunezmontanez/
	* https://github.com/cygnusv
* Derek Pierre: Business Development and engineer
	* https://www.linkedin.com/in/derek-pierre/
	* https://github.com/derekpierre
* Justin Holmes: Involuntary Time Traveler
	* http://justinholmes.com
	* https://github.com/jmyles
* John Pacific: Cryptography Engineer
	* https://github.com/tuxxy/
* Kieran Prasch: Software Engineer
	* https://github.com/kprasch/
* Damon Ciarelli: Engineer
	* https://github.com/vepkenez
* Arjun Hassard: Product & Protocol
	* https://www.linkedin.com/in/arjhaz/


## Team Website

https://www.nucypher.com/

## Relevant Experience

Why we are the right team to build this proposal:

* Mission and Values: We believe that unconditional privacy is a fundamental human right, and NuCypher was founded to empower individuals to assert that right in the digital age. See our [“mission and values” statement](https://blog.nucypher.com/nucypher-s-mission---values/).
* Expertise: Our team has extensive experience in cryptographic engineering. We have created NuCypher Network, a decentralized access control service based on proxy re-encryption, as well its core cryptographic library, `pyUmbral`.
* Solid engineering: Development of our major building blocks (the `pyUmbral` threshold proxy re-encryption library and the `nucypher` software) has been audited by major security firms such as Trail of Bits and NCC, and no major issues have been found. See [here](https://blog.nucypher.com/security-audits--round-1--3/) for more information.
* Open source: All of our projects are released under open source licenses.

Individually:

* David Núñez is a cryptographer, specialized in proxy re-encryption, which was the topic of his [PhD thesis](https://riuma.uma.es/xmlui/bitstream/handle/10630/13221/TD_NUNEZ_MONTANEZ_David_Alejandro.pdf?sequence=1&isAllowed=y). David’s threshold proxy re-encryption scheme, called Umbral, formed the basis for NuCypher’s underlying decentralized technology. He’s also one of the core developers of both `pyUmbral` and `nucypher`. 
* Derek Pierre is a former software engineer at BlackBerry and Dell. He studied Computer Science at the University of Waterloo and has an MBA from the University of Toronto. He has worked on a variety of technologies that include product integrations and standardizations, core platform/API development, and proxy re-encryption. Derek juggles roles as both a Business Development Lead and an Engineer at NuCypher.
* Justin Holmes: There isn’t a whole lot about Justin that makes sense, or where he lives likewise. In his school bus, he has explored the USA from the Everglades to Portland, OR, and on down to Fresno. Like so many young men of his generation, Justin writes Python. Now, Justin is an educated man - not the world’s greatest sage maybe - no Rabbi Marshak - but he has a degree in political science from SUNY New Paltz.
* John Pacific: Not a whole lot about John, either. A former cyberpunk warlord, John has navigated the intricacies of cyberspace, including the dark corners of cryptography and information security. With their newfound knowledge, John found theirself in a position of power and has yet to be defeated. John likes to write Python, Rust, and Go, among other languages. They also like really complex problems and immersing themselves in them to find interesting solutions.
* Damon Ciarelli had a career in computer graphics and visual effects before being seduced by the Internet.  His suitability for projects like this has been very astutely assessed in [this blog post](https://blog.nucypher.com/welcoming-my-friend-damon-ciarelli-to-nucypher/) detailing the painful hiring conundrum that led him to be employed at NuCypher.
* Arjun works on product and network protocol development at NuCypher. Previously, he built NLP products at an anti-fake news org, and ran product at a large crowdfunding platform. Arjun studied physics at Imperial College London and published energy policy research whilst at Kyoto University.
* Kieran is a former volunteer firefighter and python educator turned passionate engineer with a diverse background ranging from front-end design through distributed systems. Inspired by the recent surge of interest around a budding decentralization movement, Kieran now is a full-time contributor to NuCypher expressing his best technology optimism.


## Team code repositories

* `pyUmbral`, our reference implementation of the Umbral proxy re-encryption scheme
   * https://github.com/nucypher/pyUmbral
* `nucypher`, the software platform for the NuCypher network
   * https://github.com/nucypher/nucypher/


# Additional Information

["NuCypher - A proxy re-encryption network to empower privacy in decentralized systems"](https://github.com/nucypher/whitepaper/blob/master/whitepaper.pdf), by Michael Egorov, David Nuñez, and MacLane Wilkison

["Umbral: A Threshold Proxy Re-Encryption Scheme"](https://github.com/nucypher/umbral-doc/blob/master/umbral-doc.pdf), by David Nuñez

