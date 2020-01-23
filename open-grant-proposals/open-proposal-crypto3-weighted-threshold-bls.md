# Open Grant Proposal: `=nil; Crypto3 Weighted Threshold BLS`

**Name of Project:** =nil; Crypto3 Weighted Threshold BLS

**Proposal Category:** `technical-design` (or maybe `core-dev`?)

**Proposer:** @nemothenoone

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Boneh–Lynn–Shacham signature scheme was designed to produce aggregatable (thus
small-sized) thershold signatures, begginning with trivial (n,n) scheme to (t,n).
But threshold signature schemes, even (t,n), are not flexible enough to reflect
complex signature weight distribution.

Thus =nil; Crypto3 team intends to finish construction of a modification of 
such signature scheme to make it able to reflect complex weight distribution.
For the particular Filecoin's application this would allow to provide a 
signature scheme for block signers which reflects their weight respectively to 
their asset amount. Other application according to Filecon's intentions is to
provide the transaction signing author the more precise way to reflect weight 
of particular signature members.

## Value

Weighted threshold BLS signatures would provide the Filecoin protocol an
improvement to block and transaction signing logic. Weighted signature would
allow to prescisely represent the weight of signer according to its' asset
amount or any other metric.

The implementation will be included in [=nil; Foundation's crypto3 cryptography
suite](https://crypto3.nil.foundation) (pubkey module) along with traditional 
BLS signature scheme implementation.

This particular proposal is not a straightforward development proposal. This
proposal would require some research. In particular it would require finishing a
paper, started some time ago, but abandoned because of the absence of necessity
for internal =nil; Foundation's usage. This brings some risks.

The risk is that the paper needs to be published or presented at the conference. 
It can take a long time (nearly a month). At least it should be published as 
preprint. This is a preferabble option because it is faster. 

Second of all the paper contents needs to be reviewed in public. The team can
definitely arrange the independent review itself, but the private pre-publishing 
review by request and public review are different things.

These risks make this proposal more of a research proposal, than development
proposal despite the scheme implementation is going to be included in
cryptography suite.

## Deliverables

Deliverables are defined as follows:

* Reviewed paper published in conference proceedings or as preprint at IACR.
* Weighted threshold BLS scheme implementation in C++ built into a public key
  cryptography module of =nil; Foundation's cryptography suite. License is
  assumed to be MIT and APACHE2.
* Standalone version of a library.
* Rust or Go bindings for the Filecoin protocol implementers could use it
  natively.

## Development Roadmap

Milestones are defined respectively as follows:

| Milestone No. | Milestone Description              | Funding| Timeframe|
|---------------|------------------------------------|--------|----------|
| 1             | Paper                              | $36000 | 4 weeks  |
| 2             | Implementation                     | $16000 | 4 weeks  |
| 3             | Rust/Go Bindings                   | $8000  | 2 weeks  |
| 4             | Documentation                      | $6500  | 1 weeks  |
| 5             | Testing & Adjustments              | $9000  | 1 weeks  |

Development roadmap is defined as follows:

### Milestone 1. Paper.

First milestone is completely dedicated to arranging the paper draft for
publishing. Primary mechanism is already known.

This would require involvement of two researchers and team leader. Team leader
would go through the paper contents and write down a skeleton of a paper. 
First researcher goes after the team leader through the paper and expands every
article point being drafted. Second researcher goes right after the the first
one and reviews the protocol along with typewritting. This process goes at least
twice. Then, if required, team leader seeks for the independent reviewer.
Otherwise (preferrably) article goes public as preprint along with sources, so
those could be reviewed by everyone.

The result of this milestone is a reviewed paper published as conference
proceedings or as preprint ar https://iacr.org.

This milestone would take 4 weeks.

### Milestone 2. Implementation.

The paper requires the implementation to be done for the results data and
signature examples to be included in paper. This makes the team leader to
implement the scheme as a part of public key module of the [=nil; Foundation's
cryptography suite](https://crypto3.nil.foundation).

This would require for the public key library to be tested in parallel 
with the =nil; Crypto3 development team members, which is mentioned in other
devgrant proposal: https://github.com/filecoin-project/devgrants/pull/66

Implementation of weighted threshold BLS signature scheme would introduce the
threshold schemes to public key and would require implementation of a
non-cryptographic accumulator with sufficient concepts and functions set 
(just like [this one](https://github.com/nilfoundation/block/include/nil/crypto3/block/accumulators/block.hpp)).
This means at the time it comes to the implementation of the weighted BLS
threshold scheme, the development part of =nil; Crypto3 team would require to
publish at least some part of the public key module. According to the contents
of the [grant proposal related](https://github.com/filecoin-project/devgrants/pull/66)
it would be already done.

According to other team developers would be stuffed with work on 
[other grant proposal](https://github.com/filecoin-project/devgrants/pull/66),
team leader would need to make this by himself. This makes no trouble because
his part of work on other grant proposal will be finished by that time.

The result of this milestone is a weighted threshold BLS signature scheme 
implemented with C++ as a part of =nil; Crypto3 cryptography suite. 
This milestone would finish the functional part development.

This milestone would take 4 weeks.

### Milestone 3. Bindings

Bindings seem a crucial part for the Filecoin implementers because most of them
use Rust or Go.

Bindings require for the cryptography suite libraries to be separated and made
standalone, which is a part is going to be done with 
[other grant proposal](https://github.com/filecoin-project/devgrants/pull/66). 
Unique bindings-related work for this particular proposal is the implementation
of FFI for threshold schemes in public key module.

Bindings require testing. So this should be done too. Team leader pretends to
make it by himself.

The result of this milestone is a Rust or Go library with standalone C++ version 
inside.

This milestone would take 2 weeks.

### Milestone 4. Documentation

Documentation is required to make the library usable. According to the library
itself is implemented in C++ as a part of a suite, it would require
documentation for C++ version as well as for Rust/Go version.

C++ version of a documentation required description of concepts and architecture
notes along with API reference as well. Rust version hardly require architecture
notes, so well implemented API reference would be enough.

This milestone would reuqire envolvement of the team leader and the first
researcher to make sure, double check and correct, if required, the examples,
its' outputs and documentation.

The result of this milestone is a documentation for the C++ and Rust
implementations, API reference along with architecture and implementation notes
for C++.

This milestone would take 1 week.

### Milestone 5. Testing & Adgustments.

Every research & development is a complicated process, which is required to be 
syncronized week-by-week with the requirements. This milestone is supposed to be a
community communication and problem fixing milestone. Team leader along with
researchers would be accessible for faster communication with GitHub Issues 
especially to collect the feedback and fix bugs found.

This milestone would require the involvment of all the team members (team
leader, two researchers). The team assumes there would be few (if any at all) 
errors and misunderstandings after all these double-checks, so this milestone
would take 1 week.

## Total Budget Requested

Total budget assumed to be $75500. Why is it so?

Every milestone implementation cost depends on the time spent. 
Following compensations are required by team members:

* Team Leader - $4000/week
* Researcher 1 - $3000/week
* Researcher 2 - $2500/week

Project duration varies is 4 + 4 + 2 + 1 + 1 = 12 weeks. According to the amount of
developers/researchers involved in every particular milestone, this leads to
$75500.

## Maintenance and Upgrade Plans

Cryptography suite is planned to be maintaned as long as possible by the team,
or by me (@nemothenoone) myself. This means public key module along with BLS
weighted threshold schemes will be maintained as long as possible.

# Team

## Contact Info

Mikhail Komarov: nemo@nil.foundation

## Team Members

- Mikhail Komarov. Team Leader.
- Ilya Shirobokov. Researcher.
- Alisa Chernyaeva. Researcher.

## Team Member LinkedIn Profiles

- Mikhail Komarov: https://www.linkedin.com/in/mikhail-komarov-7084a9139/
- Ilya Shirobokov: https://www.linkedin.com/in/ilya-shirobokov-963466162/
- Alisa Chernyaeva: https://www.linkedin.com/in/alisa-chernyaeva-83b8b4184/

## Team Website

https://crypto3.nil.foundation

## Relevant Experience

* Mikhail Komarov. MS in Mathematics at Moscow State University. 
  Developing and designing cryptography schemes and implementations from 2013. 
  Founded [=nil; Foundation](https://nil.foundation), which intention 
  is to develop and standartize database and cryptography-related 
  specifications. Founded [=nil; Crypto3](https://crypto3.nil.foundation) 
  cryptography team currently incubated within =nil; Foundation. Designed and 
  developed =nil; Foundation's crypto3 
  modern cryptographiy suite, partially intended to be included in 
  [Boost](https://boost.org), to become a foundation for C++ STL cryptography
  proposal and partially to provide architecturally clean and type-safe modern 
  cryptography suite (mostly for internal Foundation's usage, but some modules 
  were made opensouce) with no (or very small amount of) heap allocations.
  Designed several (for internal Foundation's usage at the moment, 
  unfortunately, but the time to share will come soon) threshold signature 
  (e.g. ecdsa) and encryption schemes. 
* Ilya Shirobokov. MS in Applied Mathematics, specialization in applied
  cryptography. Performs designing and analysis of cryptography schemes for the
  last 3 years in teams related to =nil; Foundation (e.g. corestar.io). Joined
  the =nil; Crypto3 and designed 
  [Homomorphic Encryption Random Beacon](https://eprint.iacr.org/2019/1320)
  scheme along with Alisa.
* Alisa Cherniaeva. MS in Applied Mathematics, specialization in applied
  cryptography. Performs designing and analysis of cryptography schemes for the
  last 2 years in teams related to =nil; Foundation (e.g. corestar.io). Joined
  the =nil; Crypto3 and designed 
  [Homomorphic Encryption Random Beacon](https://eprint.iacr.org/2019/1320)
  scheme along with Ilya.

## Team code repositories

=nil; Foundation's Github organisation: https://github.com/nilfoundation
=nil; Crypto3's Github organisation: https://github.com/nilcrypto3

# Additional Information

Ask me (@nemothenoone).
