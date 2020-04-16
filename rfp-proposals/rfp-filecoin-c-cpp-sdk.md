# RFP Proposal: `Filecoin C/C++ SDK`

**Name of Project:** Filecoin C/C++ SDK 

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-3-rfps.md#sdks-in-various-mainstream-programming-languages.

**RFP Category:** `devtools-libraries`

**Proposer:** @nemothenoone 

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

=nil; Crypto3 team intends to implement Filecoin C/C++ SDK with usage of 
[=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3) along with 
[=nil; Actor Model Implementation Library](https://github.com/nilfoundation/actor-core.git) and 
[=nil; Actor Model-based Networking Library](https://github.com/nilfoundation/actor-network.git).

Filecoin C/C++ SDK will support:
* Transaction serialization.
* Transaction signing with ECDSA.
* Transaction signing with ECDSA threshold signature scheme by [Genarro and Goldfeder](https://eprint.iacr.org/2019/114.pdf) implemented with [=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3)'s threshold public key module.
* Management of transactions of all kinds: account management, wallet
  management etc.
* Specialization for particular kinds of transactions:
    1. File encryption/decryption with PGP implemented with [=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3)'s public key module.
    2. File retrieval by public link along with following decryption with PGP implemented with [=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3)'s public key module.
    3. File uploading with encryption/decryption with PGP implemented with [=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3)'s public key module.
* Recommended redundancy calculation so data can be reconstructed in case a copy cannot be retrieved.
* Available miners listing.
* Working with some Filecoin node through API (e.g. Lotus).
* Several storage deals management (enter, decline etc).
* Stored files listing with deals details.

## Value

Filecoin C/C++ SDK is required to have for several reasons:
* Actual filesystems implementations (e.g. implemented with Linux Kernel Modules 
or FUSE-based implementations) using Filecoin protocol as a storage would
definitely require low-level language SDK implementation.
* Desktop file managers integrations would require Filecoin C/C++ SDK.
* No actual threshold signature scheme signers are available right now for
  Filecoin. And no low-level ones seems to be planned.
* GUI applications implementing UI/UX tools for Filecoin data management will
  be able to use C/C++ SDK so it will not compromise the performance and
  security no matter with what particular GUI is implemented: Web (React) or
  native application (iOS/Android/Desktop).
* SDK is supposed to be WebAssembly-compilable, so this is also will be usable
  within the browser.
* Other language bindings will be implementable with usage of FFI to SDK's plain
  C backend.

Such an SDK will turn out to be usable in any case Filecoin will ever be used:
filesystem implementation (signing & serialization libraries are suitable to
work properly within the kernel), implementation of a CDN-like highload server
application or inside the browser with WebAssembly.

Particular modules (signing & transaction serialization libraries) could be used
from C and from C++ as well because of their architecture.

## Architecture & Implementation

Implementation intends to be modular and is going to contain following sublibraries
implemented or opensourced especially for the RFP:

* Public key cryptography module from [=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3).
* Threshold public key cryptography module from [=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3). Will be finished and opensourced.
* [=nil; Actor - Actor Model Implementation Library](https://github.com/nilfoundation/actor-core.git). 
* [=nil; Actor.Network - Actor Model-based Networking Library](https://github.com/nilfoundation/actor-network.git).
* JSON-RPC extension for =nil; Actor.Network. Will be finished and published.
* Filecoin transaction serialization library implemented with =nil; Marshalling
  library.
* Filecoin signer library implemented with public key cryptography module from [=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3).
* Filecoin signer service implemented with public key cryptography module from [=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3), threshold public key cryptography module from [=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3) [=nil; Actor](https://github.com/nilfoundation/actor-core.git) and [=nil; Actor.Network](https://github.com/nilfoundation/actor-network.git).
* Redundancy estimation library implemented with Erasure Coding module of [=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3).
* Filecoin SDK library & service implemented with all of the libraries mentioned above
  along with PGP encryption/decryption from [=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3).

### Threshold Public Key Cryptography Module from =nil; Crypto3 C/C++ Cryptography Suite.

Cryptography suite itself is implemented in C/C++ with intention to deliver modern
(and sometimes even self-invented) cryptography for various projects 
(e.g. [VDF library](https://github.com/nilfoundation/vdf) for 
[Chia Network VDF competition](https://www.chia.net/2019/07/18/chia-vdf-competition-round-2-results-and-announcements.en.html) 
along with [Proof of Space competition](https://github.com/Chia-Network/proofofspaceresults) 
winning block ciphers and hashes) and traditional ciphers and schemes 
implementation for [Boost](https://boost.org) and probably even a C++ Standard
proposal. 

Assuming the threshold public key cryptography library architecture is mostly done 
and implemented in C and C++ as a module for 
[=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3),
it is only required to properly implement the threshold signature scheme itself by 
[Genarro and Goldfeder](https://eprint.iacr.org/2019/114.pdf).

Moreover this library is usable even within kernel extensions (which is crucial 
in case Filecoin will be implemented as a full-featured filesystem).

### Filecoin Transaction Serialization Library.

Transaction serialization is intended to be done with =nil; Marshalling library
(sources are closed for now, but we will open them especially for the RFP). This
library provides compile-time marshalling data types definitions and it is 
suitable even for bare-metal usage - no redundant memory allocations are done.

Filecoin transaction serialization format specifications will be implemented 
with this library.

### Filecoin C/C++ Transaction Signing Library

Signing library is supposed to be done with transaction serialization library
usage along with threshold public key cryptography module for 
[=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3).

It will be usable from Plain C99 and supposed to be suitable for in-kernel
usage.

This library will provide threshold signature scheme siginig module implementation 
along with usual signing tools.

### Filecoin C/C++ Transaction Signing Service

Signing service is supposed to be done with transaction signing library along
with [Actor Model Implementation Library](https://github.com/nilfoundation/actor-core.git)
and [Actor Model-based Networking Library](https://github.com/nilfoundation/actor-network.git).

This service will support ECDSA transaction signing, threshold signature schemes 
for transaction signing, and will be the most performant signer service suitable
for CDN-alike network-intensive highload storages. This is not achievable with
current signer service implementation.

JSON-RPC interface will be available for the usage. API is going to be defined 
with Swagger.

### Redundancy Estimation Library

It is required for the client to estimate storage redundancy so data can be 
reconstructed in case a copy cannot be retrieved. This is why we intend to
implement a set of tools within the SDK with usage of Erasure Coding module of 
[=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3) 
to provide GUI developers with standartized toolset for this particular task.

This library will be implemented with C/C++ and it will be usable as a part of
SDK or as a standalone library.

### Filecoin C/C++ SDK

This module is about to provide Filecoin simplified interaction for developers,
providing an SDK for GUI application developers without compromising speed and
security.

This module will use several libraries mentioned above for data
encryption/decryption with PGP from 
[=nil; Crypto3 C/C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3).

This module will also be responsible for node connection through API. API
specification will be done with Swagger (because Lotus uses JSON-RPC interface).

# Deliverables

* An open-sourced, dual-licensed (under MIT and APACHE2) native C99 & C++ 
  Filecoin transaction serialization library.
* An open-sourced, dual-licensed (under MIT and APACHE2) native C99 & C++ 
  Filecoin transaction signer library and service which supports threshold 
  signature schemes.
* An open-sourced, dual-licensed (under MIT and APACHE2) native C99 & C++ 
  Filecoin SDK library and service.
* User and developer documentation.
* Examples along with tests.

# Development Roadmap

**Total Funding Amount:** $89500

**Milestones:** 

The team works with 1-week cycles, so milestones are defined respectively.

| Milestone No. | Milestone Description                | Funding | Timeframe |
|---------------|--------------------------------------|---------|-----------|
| 1             | Transaction Serialization Library    | $19000  |  2 weeks  |
| 2             | Transaction Signing Library          | $19000  |  2 weeks  |
| 3             | Transaction Signing Service          | $19000  |  2 weeks  |
| 4             | Redundancy Estimation Library        | $9500   |  1 week   |
| 5             | SDK Library and Service              | $19000  |  2 weeks  |
| 6             | Documentation & Testing              | $4000   |  1 week   |

## Transaction Serialization Library

Transaction serialization library is intended to be implemented with [=nil;
Marshalling Library](https://github.com/nilfoundation/marshalling.git)(still yet
to be opensourced).

Particular Filecoin transactions serialization format will be implemented with
such a library because of it's lack of any overhead (thanks to hardcore 
compile-time type specifications).

Development time required for such a module estimated around 2 weeks.

Team leader intends to develop the basic Filecoin serialization format notation
with library's concepts. First developer would follow the team leader across the 
code and finalize the implementation internals, optimize. Other developer is 
supposed to develop tests which would require to be passed with the code first 
developer made. Meanwhile team leader will initialize signing library development.

The result of such a milestone would be a high quality Filecoin transaction 
serialization library suitable for the native execution or for the WebAssembly-based 
one.

The team will definitely take into consideration current 
[Filecoin C++ implementation](https://github.com/filecoin-project/cpp-filecoin)
to reduce the milestone time.

## Transaction Signing Library

Transaction signing library is intended to be implemented with public key
cryptography module from 
[=nil; Crypto3 C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3).

Transaction signing library will depend on transaction serialization library.

Development time required for such a module estimated around 2 weeks.

Team leader intends to implement initial serialized transaction signing. 
First developer would follow the team leader across the code and finalize the 
implementation internals, optimize. Other developer is supposed to develop tests 
which would require to be passed with the code first 
developer made. Meanwhile team leader will initialize signing service development.

The result of such a milestone would be a high quality Filecoin transaction 
singing library suitable for the native execution or for the WebAssembly-based 
one.

## JSON-RPC Transaction Signing Service

JSON-RPC transaction signing service is intended to be based on JSON-RPC
extension for =nil; Actor.Network library, which is implemented in C++.

This milestone would require fill team employment and would take 2 weeks to be 
done. 

Team Leader intends to define Swagger/OpenAPI service specification, providing 
YAML file for that. Meanwhile developers are supposed to finish JSON-RPC module 
for =nil; Actor.Network library. After finishing that it is supposed to build a 
whole service with all the dependencies.

The configuration (e.g. Filecoin Node address to work with) will be handled with 
Boost.ProgramOptions or any similar library. Thus such a configuration param
will be runtime-changeable.

This milestone will take 2 weeks to be done and it is very likely will be done in time.

The result of such a milestone would be a high quality Filecoin transaction 
singing service.

## Redundancy Estimation Library

Redundancy Estimation Library is supposed to be implemented with usage of
Erasure Coding module of 
[=nil; Crypto3 C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3).

This particular library is going to use [Regenerating Codes](https://arxiv.org/pdf/1202.1050.pdf)
to ensure data recoverability even if the original data is not available.

Team Leader intends to implement initial erasure codes library architecture along
with the architecture of redundancy estimation module. 
First developer is supposed to follow the team leader across the code and finalize the 
implementation internals, optimize. Other developer is supposed to develop tests 
which would require to be passed with the code first developer made.

This milestone will take 1 week with full team employment and is likely will be 
done in time.

The result of such a milestone would be a high quality erasure coding module for 
[=nil; Crypto3 C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3) 
along with redundancy estimation library for Filecoin SDK.

## SDK Library and Service

Filecoin SDK is supposed to be the final milestone of this project. It is
supposed to be implemented with C++ and depend on all of the previous
milestones.

This milestone will take 2 weeks with full team employment and is likely will be 
done in time.

The result of such a milestone would be a full-featured Filecoin C++ SDK usable
for GUI development in Web-based stack as well as for native applications
development.

## Documentation & Testing

Every development is a complicated process, which is required to be syncronized
week-by-week with the requirements. This milestone is supposed to be a
community communication and problem fixing milestone. Team leader along with
developers (if there would be any) would be accessible for faster communication 
with GitHub Issues especially to collect the feedback and fix bugs found.

Since the API is going to be defined with Swagger specifications, the
documentation will be generated right for the YAML file.

Further usage instructions will be appended.

This milestone would require employment of the only team member - team leader
and will take 1 week.

## Total Budget Requested

Total budget assumed to be $89500. Why is it so?

Every milestone implementation cost depends on time spent by every team member.
Every team member's compensation includes all of the organisational and testing
costs: servers, meetings etc. So no further expenses are supposed to appear.

* Team Leader - $4000/week
* Developer 1 - $3000/week
* Developer 2 - $2500/week

Project duration is 10 weeks. This leads to the following budget: $89500.

## Maintenance and Upgrade Plans

All of the dependencies libraries and suites are supposed and will be maintaned 
as long as possible by the team, or by me (@nemothenoone) myself. This means 
Filecoin SDK will be maintained as long as possible.

# Team

## Contact Info

Mikhail Komarov: nemo@nil.foundation

## Team Members

- Mikhail Komarov (https://github.com/nemothenoone). Team Leader.
- Aleksandr Sokolov (https://github.com/a1falcon). Developer 1.
- Nikita Kaskov (https://github.com/nkaskov). Developer 2. 

## Team Member LinkedIn Profiles

- Mikhail Komarov: https://www.linkedin.com/in/mikhail-komarov-7084a9139/
- Alexander Sokolov: https://www.linkedin.com/in/alexander-sokolov-18a8341a4/
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

It was also required for SDK-implementation team to has some examples of
particular SDKs implemented in past. As much as team leader was a
CTO of Steemit-fork and Steemit developer as well in the past, it is enough to 
look at SDKs done in here: https://github.com/GolosChain.

# Additional Information

Ask me (@nemothenoone).
