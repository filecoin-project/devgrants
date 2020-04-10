# RFP Proposal: `Proxy Re-Encryption Library and Service`

**Name of Project:** =nil; Crypto3 Proxy Re-Encryption Suite

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#proxy-re-encryption-library-and-service.

**RFP Category:** `core-dev`

**Proposer:** @nemothenoone 

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

=nil; Crypto3 team intends to implement proxy re-encryption library as a part of 
[=nil; Crypto3 C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3)" 
and then implement JSON-RPC service based on actor model-implementation library
[=nil; Actor](https://github.com/nilfoundation/actor) and it's 
[networking module](https://github.com/nilfoundation/actor-network).

## Value

Proxy Re-Encryption service would allow a user to delegate access to others 
using a semi-trusted proxy service that does not have to decrypt the data and can 
re-encrypt with new public keys and share. This would enable faster and more
consistent Filecoin data-access points without any need to decrypt data which is
actually being requested. Such data-access points would allow to guarantee the
particular data distribution to some particular client set.

Such a proxy re-encryption service would allow users to:
* Read data from Filecoin proxies with no security considerations.
* Share Filecoin data with particular user (or set of particular users).
* Share Filecoin data with a group of users, in which there should be a subgroup
  which is guaranteed to decrypt the data. Group-to-Group sharing.
* Write data to Filecoin with no security considerations.

## Architecture & Implementation

Implementation intends to be modular and is going to contain following sublibraries
implemented or opensourced especially for RFP:

* Proxy Re-Encryption Module for [=nil; Crypto3 C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3).
* [Actor Model Implementation Library](https://github.com/nilfoundation/actor.git). Mostly done.
* [Actor Model-based Networking Library](https://github.com/nilfoundation/actor-network.git). Mostly done.
* JSON-RPC Extension for =nil; Actor.Network. Still yet to be finished and published.
* Proxy Re-Encryption JSON-RPC Service.

### Proxy Re-Encryption Module for =nil; Crypto3 C++ Cryptography Suite.

Cryptography suite itself is implemented in C++ with intention to deliver modern
(and sometimes even self-invented) cryptography for various projects 
(e.g. [VDF library](https://github.com/nilfoundation/vdf) for 
[Chia Network VDF competition](https://www.chia.net/2019/07/18/chia-vdf-competition-round-2-results-and-announcements.en.html) 
along with [Proof of Space competition](https://github.com/Chia-Network/proofofspaceresults) 
winning block ciphers and hashes) and traditional ciphers and schemes 
implementation for [Boost](https://boost.org) and probably even a C++ Standard
proposal. 

This means the Proxy Re-Encryption module will be expertly implemented in C++
with possible proper Assembly (YASM) inlines.

The Proxy Re-Encryption module will definitely contain classic schemes of this
field: 
* PRE1. This algorithm is defined in section 3 of 
[Improved Proxy Re-Encryption Schemes with Applications to Secure Distributed Storage by Giuseppe Ateniese et al.](https://eprint.iacr.org/2005/028.pdf) 
under the heading “A Third Attempt”. 
This algorithm is secure under the Decisional Bilinear Diffie-Hellman Assumption (DBDH).
* PRE2. This algorithm is defined in section 3 of [Improved Proxy Re-Encryption Schemes with Applications to Secure Distributed Storage by Giuseppe Ateniese et al.](https://eprint.iacr.org/2005/028.pdf) 
under the heading “A Second Attempt”. 
This algorithm is secure under the Decisional Bilinear Inversion assumption (DBDHI).

Those two schemes would be enough for initial read-only Filecoin proxy which
would be able to share data with particular users or groups of users.

In case such a proxy should be not read-only, but a read-write proxy, proxy
re-encryption library would be required to have following scheme:
[Fast Proxy Re-Encryption for Publish/Subscribe Systems](https://eprint.iacr.org/2017/410.pdf).

The requirement to make groups and organisations to be able to share access not
only to particular users (or set of particular users), but to other organisations 
and groups (where at least several people have to be interested for the file 
retrieved from Filecoin to be decrypted) introduces the need to implement some 
threshold proxy re-encryption schemes. Fine example of such a scheme is a 
[NuCypher's Umbral](https://www.nucypher.com/proxy-re-encryption).

### Proxy Re-Encryption JSON-RPC Service.

Such a service implementation is intended to be done with actor-model based
networking library because of the proxy's massive parallelism requirements.
Hosting a proxy should not be extreme hardware performance demanding. Actor
model-based service implementation suits this task as good as it can and will
provide the best possible massive parallelism implementation.

# Deliverables

* An open-sourced, dual-licensed (under MIT and APACHE2) C++ proxy re-encryption 
  module for =nil; Crypto3 C++ Cryptography Suite, usable as self-contained, 
  standalone and independent library. 
* An open-sourced, dual-licensed (under MIT and APACHE2) C++ proxy re-encryption 
  JSON-RPC service based on actor-model networking library.
* User and developer documentation.
* Examples along with tests.

# Development Roadmap

**Total Funding Amount:** $85500

**Milestones:** 

The team works with 1-week cycles, so milestones are defined respectively.

| Milestone No. | Milestone Description                | Funding | Timeframe |
|---------------|--------------------------------------|---------|-----------|
| 1             | Proxy Re-Encryption Library          | $28500  |  3 weeks  |
| 2             | JSON-RPC Proxy Re-Encryption Service | $28500  |  3 weeks  |
| 3             | Library Foreign Function Interface   | $9500   |  1 week   |
| 4             | Documentation & Tools                | $9500   |  1 week   |
| 5             | Testing & Adjustments                | $9500   |  1 week   |

## Proxy Re-Encryption Library

Proxy Re-Encryption module is intended to be implemented in C++ as a part of 
[=nil; Crypto3 C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3).

Proxy Re-Encryption library will follow same concepts as suite's public key 
cryptography module does. Just like other suite modules, which require sometimes 
accumualtor-like containers, cryptographic accumulators module is going to be 
built around Boost.Accumulators concept. 

Boost.Accumulators has already been advanced with statistics accumulators
module, with non-cryptographic, but cryptography-related accumulators, so for
now such an approach will be extended to proxy re-encryption module.

What is going to be implemented in this module:

* Stateful accumulator (just like
  [this](https://github.com/nilfoundation/block/include/nil/crypto3/block/accumulators/block.hpp) or
  [this](https://github.com/nilfoundation/codec/include/nil/crypto3/codec/accumulators/codec.hpp)
* Stream preprocessor for handling various types of data passed to the
  accumulator. (This is because [accumulator concept](https://www.boost.org/doc/libs/1_72_0/doc/html/accumulators/user_s_guide.html#accumulators.user_s_guide.the_accumulators_framework.concepts) 
  requires for the data to be passed value-by-value)
* Accumulator policies for specifying params related to the particular scheme
  used (just like
  [this](https://github.com/nilfoundation/stream/include/nil/crypto3/stream/chacha.hpp))
* Template function handling various, but strictly typed data sequence (just
  like
  [this](https://github.com/nilfoundation/block/include/nil/crypto3/block/algorithms/encrypt.hpp))
* Standalone version of a cryptographic accumulators module with all the
  dependencies embedded and "minified".

Coming to particular schemes implementations, there will be several schemes:

* PRE1. This algorithm is defined in section 3 of 
[Improved Proxy Re-Encryption Schemes with Applications to Secure Distributed Storage by Giuseppe Ateniese et al.](https://eprint.iacr.org/2005/028.pdf) 
under the heading “A Third Attempt”.
* PRE2. This algorithm is defined in section 3 of [Improved Proxy Re-Encryption Schemes with Applications to Secure Distributed Storage by Giuseppe Ateniese et al.](https://eprint.iacr.org/2005/028.pdf) 
under the heading “A Second Attempt”.
* [Fast Proxy Re-Encryption for Publish/Subscribe Systems](https://eprint.iacr.org/2017/410.pdf).
* [NuCypher's Umbral](https://www.nucypher.com/proxy-re-encryption).

Development time required for such a module estimated around 4 weeks because of
no modern, type-safe and performant enough multi-scheme proxy re-encryption 
implementations are available.

Team leader intends to develop the concepts, library architecture, accumulator 
framework architecture and implement a basic generic accumulator prototype. 
First developer would follow the team leader across the code and finalize the 
implementation internals, optimize. Other developer is supposed to develop tests 
which would require to be passed with the code first developer made. Meanwhile 
team leader will initialize JSON-RPC service development.

The result of such a milestone would be a high quality proxy re-encryption library, 
based on same concepts as =nil; Crypto3 C++ Cryptography Suite public key module is.

## JSON-RPC Proxy Re-Encryption Service

JSON-RPC proxy re-encryption service is intended to be based on JSON-RPC
extension for =nil; Actor.Network library, which is implemented in C++.

This milestone would require fill team employment and would take 3 weeks to be 
done. It is very likely this milestone would be done faster.

Team Leader intends to define OpenAPI service specification, providing YAML file
for that. Meanwhile developers are supposed to finish JSON-RPC module for =nil;
Actor.Network library. After finishing that it is supposed to build a whole
service with proxy re-encryption library and implement data retrieval from
Lotus according to it's the API definitions at the moment.

The configuration (e.g. Filecoin Node address to work with) will be handled with 
Boost.ProgramOptions or any similar library. Thus such a configuration param
will be runtime-changeable.

This milestone is likely will be done in time.

The result of this milestone is a functional proxy re-encryption service with
sufficient preformance and functionality.

This milestone would finish the functional part development.

## Library Foreign Function Interface

Proxy Re-Encryption library being implemented in C/C++ with assembly inlines
would likely require foreign function interface to make possible other
languages' bindings implementation.

Team Leader intends to define the ABI, while two developers follow him and
implement C-style function calls to library backend.

This milestone would require fill team employment and would take 1 week to be 
done. It is very likely this milestone would be done faster.

The result of this milestone is a functional proxy re-encryption library with
C-style foreigh function interface.

## Documentation & Tools

Documentation for the whole suite is (partially for now) implemented in a way 
ISO approves: [concepts](https://crypto3.nil.foundation/df/d5d/block_ciphers_concepts.html), 
references, algorithmic complexity with implementation
[architecture notes](https://crypto3.nil.foundation/db/dee/block_ciphers_impl.html). 
This would be the way documentation gets implemented for the proxy re-encryption
module.

Since the API is going to be defined with Swagger specifications, the
documentation will be generated right for the YAML file.

Further usage instructions will be appended.

As much as such a proxy service would require Lotus begin deployed somewhere,
there could be a need for some Docker Compose file deploying this.

This milestone would require fill team employment and would take 1 week to be 
done.

### Testing & Adjustments

Every development is a complicated process, which is required to be syncronized
week-by-week with the requirements. This milestone is supposed to be a
community communication and problem fixing milestone. Team leader along with
developers (if there would be any) would be accessible for faster communication 
with GitHub Issues especially to collect the feedback and fix bugs found.

This milestone would require fill team employment and would probably last 1 week.

## Total Budget Requested

Total budget assumed to be $85500. Why is it so?

Every milestone implementation cost depends on time spent by every team member.
Every team member's compensation includes all of the organisational and testing
costs: servers, meetings etc.

* Team Leader - $4000/week
* Developer 1 - $3000/week
* Developer 2 - $2500/week

Project duration is 9 weeks. This leads to the following budget: $85500.

## Maintenance and Upgrade Plans

Cryptography suite is planned to be maintaned as long as possible by the team,
or by me (@nemothenoone) myself. This means proxy re-encryption module
will be maintained as long as possible.

# Team

## Contact Info

Mikhail Komarov: nemo@nil.foundation

## Team Members

- Mikhail Komarov (https://github.com/nemothenoone). Team Leader.
- Aleksandr Sokolov. Developer 1.
- Nikita Kaskov. Developer 2 (https://github.com/nkaskov). 

## Team Member LinkedIn Profiles

- Mikhail Komarov: https://www.linkedin.com/in/mikhail-komarov-7084a9139/
- Nikita Kaskov: https://www.linkedin.com/in/nikita-kaskov-07029812a/

## Team Website

https://crypto3.nil.foundation or https://nil.foundation

## Relevant Experience

* Mikhail Komarov. 10+ years experience in designing and developing databse 
  management systems (so-called blockchains are included in such a classification). 
  Most of them were done with C++. Ex-[Steemit](https://steemit.com)(less) developer,
  ex-[Golos](https://golos.io)(more) CTO. Founded 
  [=nil; Foundation](https://nil.foundation), which intention is to develop and
  standartize database and cryptography-related specifications. Founded [=nil;
  Crypto3](https://crypto3.nil.foundation) cryptography team currently incubated
  within =nil; Foundation. Designed and developed =nil; Foundation's crypto3 
  modern cryptographiy suite, partially intended to be included in 
  [Boost](https://boost.org), to become a foundation for C++ STL cryptography
  proposal and partially to provide architecturally clean and type-safe modern 
  cryptography suite (mostly for internal Foundation's usage, but some modules 
  were made opensouce) with no (or very small amount of) heap allocations. Won
  Chia Network Proof-Of-Space competition with =nil; Crypto3 block ciphers and
  hashes implementation. Took 2-nd place at Chia Network VDF competition with
  =nil; Crypto3 VDF library.
* Nikita Kaskov. 4+ years experience in security analysis of cryptographic
  schemes and software. Joined =nil; Crypto3 last year.
* Aleksandr Sokolov. 5+ years experience in developing security-related C++ software.
  Ex-CryptoPro developer. Developing =nil; Crypto3 C++ Cryptography Suite for the 
  last year.


## Team code repositories

=nil; Foundation's Github Organisation: https://github.com/nilfoundation
=nil; Crypto3's Github Team: https://github.com/orgs/NilFoundation/teams/nil-crypto3

# Additional Information

Ask me (@nemothenoone).
