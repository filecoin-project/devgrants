# RFP Proposal: `RSA-based Vector Commitments`

**Name of Project:** =nil; Crypto3 RSA Vector Commitments

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-rsa-vector-commitments.md.

**RFP Category:** `core-dev`

**Proposer:** @nemothenoone 

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

=nil; Crypto3 team intends to implement RSA vector commitments as a part of 
=nil; Foundation's cryptography suite called "[crypto3](https://crypto3.nil.foundation)".
Still in heavy development, lacks of documentation somewhere, but moves forward
rapidly. Better [look](https://github.com/nilfoundation/vdf)
[at](https://github.com/nilfoundation/hash) the 
[code](https://github.com/nilfoundation/block). :)

As requested, implementation intents to be modular, just like "crypto3" suite
is, and is going to contain following modules implemented or opensourced
especially for RFP:

* Cryptographic Accumulators Module
* Public Key Cryptography Module

Cryptography suite itself is implemented in C++ with intention to deliver modern
(and sometimes even self-invented) cryptography for various projects 
(e.g. [VDF library](https://github.com/nilfoundation/vdf) for 
[Chia Network VDF competition](https://www.chia.net/2019/07/18/chia-vdf-competition-round-2-results-and-announcements.en.html) 
along with [Proof of Space competition](https://github.com/Chia-Network/proofofspaceresults) 
winning block ciphers and hashes) and traditional ciphers and schemes 
implementation for [Boost](https://boost.org) and probably even a C++ Standard
proposal. This means the RSA-based vector commitments module is going to be
expertly implemented in C++, but Rust or Go bindings are coming for the whole 
suite, so this makes no trouble.

It worth explicitly mentioning, that every module of a suite is implemented
either as a standalone or a self-contained (with all the in-suite dependencies inside) library.

## Deliverables

* An open-sourced, dual-licensed (under MIT and APACHE2) C++ cryptographic accumulators module for crypto3, usable as self-contained, standalone and independent library. Will contain RSA-based vector commitments cryptographic accumulator, required by RFP.
* An open-sourced, dual-licensed (under MIT and APACHE2) C++ public key cryptography module for crypto3, usable as self-contained, standalone and independent library.
* Rust bindings for previously-mentioned modules.
* User documentation.
* Developer documentation.
* Concept-based architecture description.
* Examples along with tests.
* Example C++ and Rust application used with other Filecoin module.

## Development Roadmap

**Total Funding Amount:** Varies from $48000 to $66500 depending on time requirements.

**Milestones:** 

The team works with 1-week cycles, so milestones are defined respectively.

| Milestone No. | Milestone Description              | Funding       | Timeframe |
|---------------|------------------------------------|---------------|-----------|
| 1             | Cryptographic Accumulators Library | $9500-$19000  | 1-2 weeks |
| 2             | Public Key Cryptography Library    | $19000-$28500 | 2-3 weeks |
| 3             | RSA-based VC Accumulator           | $19000-$28500 | 2-3 weeks |
| 4             | Rust bindings & Docs               | $9500-$19000  | 1-2 weeks |
| 5             | Testing & Adjustments              | $9500-$19000  | 1-2 weeks |

### Cryptographic Accumulators Library

Note: Cryptographic accumulators modules for crypto3 suite is supposed to be
implemented not only for RFP purposes.

Cryptographic accumulators module is a foundation and a framework for 
RSA-based vector-commitments accumulator.

Just like other suite modules, which require sometimes accumualtor-like 
containers, cryptographic accumulators module is going to be built around
Boost.Accumulators concept. 

Boost.Accumulators has already been advanced with statistics accumulators
module, with non-cryptographic, but cryptography-related accumulators, now it
gets advanced with full-featured cryptographic accumulators.

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
* Foreign functions interface for Rust or Go bindings (no example at the moment - suite bindings are on
  the final stage of development).
* Standalone version of a cryptographic accumulators module with all the
  dependencies embedded and "minified".

Milestone developers involvement depends on the budget available and varies
from full team employment, to the employment of team leader only. Time varies as
well, from minimum to maximum depending on developers involvement and 
mentioned in the milestones table above.

Minumum time for this particular milestone is 1 week. This requires involvment
of a team leader and a couple of developers (mentioned below in Team section).
Maximum time for this particular milestone is 2 weeks. This requires involvement
of a team leader only.

Team leader intends to develop the concepts, library architecture, accumulator 
framework architecture and implement a basic generic accumulator prototype. 
In case there are developers financed, one would follow the team leader across 
the code and finalize the implementation internals, optimize. Other developer 
is supposed to develop tests which would require to be passed with the code 
first developer made. Meanwhile team leader is required to implement basic 
library FFI. In case there are no developers financed, team leader would be 
required to do all this by himself, which is no trouble, but a week longer.

This milestone is very likely will be done faster, than planned.

The result of such a milestone would be a high quality standalone extension
library to Boost.Accumulators accumulator concept, intended to be used for 
cryptographic accumulators purposes, with sufficient FFI for other language 
bindings.

### Public Key Cryptography Library

Public key cryptography module is for now a closed-source module for internal
=nil; Foundation's usage, which would be given a reason to get opensourced 
specially for RFP implementation. It includes various public key encryption, 
signature, key agreement schemes. It is also the foundation for threshold and 
zero-knowledge cryptography modules, which are also closed for now.

Public key cryptography module for crypto3 suite is supposed to be put in shape
and opensourced.

What exactly is supposed to be done with this module:

* Extensive RSA testing and optimizations. This includes testing and optimizing
  (with up to assembly superoptimizations, if needed) RSA scheme policies and
  related non-cryptographic accumulators.
* Extensive numerics library, used in public key cryptography module, testing and optimizations. (Why not to use GMP/MPIR? Because it is full of side-channel vulnerabilities, which is inacceptable for generic purpose usage)
* Foreign functions interface for Rust or Go bindings.
* Standalone version of a public key cryptography module with all the dependencies embedded and "minified".

Milestone developers involvement depends on the budget available as well and varies
from full team employment, to the employment of team leader only. Time varies as
well, from minimum to maximum depending on developers involvement and 
mentioned in the milestones table above.

Minumum time for this particular milestone is 2 weeks. This requires involvment
of a team leader and a couple of developers (mentioned below in Team section).
Maximum time for this particular milestone is 3 weeks. This requires involvement
of a team leader only.

Team leader intends to review and possibly advance public key accumulator and
its' policies architectures and implement a basic prototype. Then it is required 
for the team leader to inspect, advance and possibly fix numerics library used for
public key cryptography. In case there are developers financed, first developer 
would follow the team leader across the code and finish the implementation 
internals, optimize. Other developer is, as usual, supposed to develop tests 
which would require to be passed with the code first developer made. Meanwhile 
team leader is required to implement basic library FFI and extensively test
numerics library along with RSA. In case there are no developers financed, 
team leader would be required to do all this by himself, which is also no trouble, 
but a week longer.

This milestone is likely will be done in time.

The result of such a milestone would be a high quality, standalone public key
cryptography library, extensively using C++ static type system with sufficient
FFI for other languages bindings.

### RSA-based VC Accumulator

RSA-based vector commitments scheme is a [cryptographic accumulator with special
properties](https://eprint.iacr.org/2018/1188.pdf). So this should be
implemented with cryptographic accumulators suite module as a set of policies,
specifying the accumulator framework behavior.

This particular accumulator policy would require the dependency on Hash concept,
introduced in hash module of a crypto3 suite.

Milestone developers involvement depends on the budget available as well and varies
from full team employment, to the employment of team leader only. Time varies as
well, from minimum to maximum depending on developers involvement and 
mentioned in the milestones table above.

Minumum time for this particular milestone is 2 weeks. This requires involvment
of a team leader and a couple of developers (mentioned below in Team section).
Maximum time for this particular milestone is 3 weeks. This requires involvement
of a team leader only.

Team leader intends to develop particular accumulator type parameters and 
functions policies, architecture of basic operations for vector storage 
and implement a basic prototype. In case there are developers financed, first 
developer would as always follow the team leader across the code and finish 
the implementation internals, optimize. Other developer is, as usual, 
supposed to develop tests which would require to be passed with the code first 
developer made. Meanwhile team leader is required to design and implement FFI 
and documentation draft for particular policy. In case there are no developers 
financed, team leader would be required to do all this by himself, which is as
always no trouble, but a week longer.

This milestone is likely will be done in time.

The result of this milestone is a functional cryptographic accumulator with
sufficient functionality and performance. 
This milestone would finish the functional part development.

### Rust bindings & Docs

Rust bindings is, actually, an optional module to implement. But in case the
Filecoin's community requirements include library usage from Rust, this would be
definitely done with a tiny wrapper using the original library with FFI.

Such a wrapper library would include all the dependencies required and will
server as a standalone library without any clue, there is a suite module inside.

Documentation for the whole suite is (partially for now) implemented in a way 
ISO approves: [concepts](https://crypto3.nil.foundation/df/d5d/block_ciphers_concepts.html), 
references, algorithmic complexity with implementation
[architecture notes](https://crypto3.nil.foundation/db/dee/block_ciphers_impl.html). 
This would be the way documentation gets implemented for the cryptographic
accumulators module. (Yeah, I know for now the website looks ugly, we are
getting it fixed).

Milestone developers involvement depends on the budget available as well and varies
from full team employment, to the employment of team leader only. Time varies as
well, from minimum to maximum depending on developers involvement and 
mentioned in the milestones table above.

Minumum time for this particular milestone is 1 week. This requires involvment
of a team leader and a couple of developers (mentioned below in Team section).
Maximum time for this particular milestone is 2 week. This requires involvement
of a team leader only.

Team leader intends to develop basic Rust wrapper within first week. In case
there are developers financed, first developer would follow the team leader
across the code and test the FFI interaction, fixing and optimizing in case
something to fix and optimize was found out. Meanwhile second developer would be
required to implement tests for Rust wrapper along with FFI tests as well. The
team leader is required to finalize documentation drafts made earlier. In case 
there are no developers financed, team leader would be required to do all this 
by himself, which is as always no trouble, but a week longer.

The result of this milestone is a Rust wrapper along with documentation to the
Rust and C++ implementations.

### Testing & Adjustments

Every development is a complicated process, which is required to be syncronized
week-by-week with the requirements. This milestone is supposed to be a
community communication and problem fixing milestone. Team leader along with
developers (if there would be any) would be accessible for faster communication 
with GitHub Issues especially to collect the feedback and fix bugs found.

Milestone developers involvement depends on the budget available as well and varies
from full team employment, to the employment of team leader only. Time varies as
well, from minimum to maximum depending on developers involvement and 
mentioned in the milestones table above.

Minumum time for this particular milestone is 1 week. This requires involvment
of a team leader and a couple of developers (mentioned below in Team section).
Maximum time for this particular milestone is 2 week. This requires involvement
of a team leader only.

## Total Budget Requested

Total budget assumed to be from $48000 to $66500. Why such a range?

Every milestone implementation time depends on amount of developers we can
provide for this task. The amount of developers involved depends on the budget 
available. Following compensations are required by team members:

* Team Leader - $4000/week
* Developer 1 - $3000/week
* Developer 2 - $2500/week

Project duration varies from 7 weeks to 12 weeks, depending on amount of 
developers involved. 7 weeks means there would be 3 person working on project.
12 weeks means there would be the only team leader working on project.

This leads to a minumum budget $48000. Maximum - $66500.

## Maintenance and Upgrade Plans

Cryptography suite is planned to be maintaned as long as possible by the team,
or by me (@nemothenoone) myself. This means cryptographic accumulators and
public key cryptography modules will be maintained as long as possible.

# Team

## Contact Info

Mikhail Komarov: nemo@nil.foundation

## Team Members

- Mikhail Komarov. Team Leader.
- Alexey Moskvin. Developer 1.
- Nikita Kaskov. Developer 2. 

## Team Member LinkedIn Profiles

We don't really keep our LinkedIn accounts up to date, I'm afraid I'm the only
one having one. Maybe Nikita will provide his for publishing.

- Mikhail Komarov: https://www.linkedin.com/in/mikhail-komarov-7084a9139/

## Team Website

Still in heavy development, but better than noting:

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
  were made opensouce) with no (or very small amount of) heap allocations.
* Alexey Moskvin. 5+ years experience in developing security-related C++ software. 
  Assembly superoptimizations fan. Developing =nil; Foundation's crypto3 for last
  two years.
* Nikita Kaskov. 4+ years experience in security analysis of cryptographic
  schemes and software. Worked on =nil; Foundation's crypto3 for the last year.


## Team code repositories

https://github.com/nilfoundation/

# Additional Information

Ask me (@nemothenoone).
