# RFP Proposal: `Filecoin protocol implementations`

**Name of Project:** Filecoin Proofs C++ Implementation

**Link to RFP:** https://docs.google.com/document/d/1L7ZZOC4cms3SZNyx7u1Hr0H_XFDUI8FYA2W8dXWBGsY

**RFP Category:** `app-dev`

**Proposer:** @nemothenoone 

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

=nil; Crypto3 team intends to introduce second Filecoin Proofs implementation
written in C++, assembling it from existing (and working in production) 
proprietary C++ Filecoin Distributed Prover parts, and integrate it with
existing Filecoin protocol implementations (Venus, Lotus, Futhon and possibly
Forest).

## Value

The intention to have several Filecoin protocol implementations is reasoned by
several points:
1. Security. Multiple protocol implementations are required to have to diversify
   the risk of something being wrong inside one of the implementations.
2. Specialization. Every implementation turns out to be specific for particular
   application. Venus, for example, was proposed to be set on a way to become a 
   mining-specific implementation (https://github.com/filecoin-project/devgrants/issues/140).
   Fuhon (cpp-filecoin) implementation is obviously on its way to become a less
   hardware-demanding alternative to Lotus.

Unfortunately, all of the implementations use the same [Rust-based proofs
implementation](https://github.com/filecoin-project/rust-fil-proofs), which 
reduces the overall sence of having several protocol implementations. 
Meanwhile proofs implementation is crucial in terms of security 
(protocol data consistency) as well. Initially it was stated in the RFP description 
that the reimplementation of Rust-based parts is not a priority, but now, after the 
project launch has already succesfully happened, maybe the time has come to 
present make existing 4 implementations (Lotus, Venus, Futhon, Forest) fully 
independent of each other or any shared components, reducing bugs security risks 
to 0. This is what alternative C++-based Filecoin Proofs implementation is about.

Initial comminuty discussion took place in a couple of places and the feedback
(mostly from Protocol Labs, but anyway) was pretty positive.

https://filecoinproject.slack.com/archives/CEGB67XJ8/p1614080944002500
https://github.com/filecoin-project/rust-fil-proofs/discussions/1418

## Architecture & Implementation

The implementation is supposed to be done from open source and publicly available 
cryptography modules from 
[=nil; Crypto3 C++ Cryptography Suite](https://github.com/nilfoundation/crypto3.git) 
and with their private enhanced versions along with additional libraries which are 
already being used in the proprietary C++-based distributed Filecoin Prover 
(which is being used for running actual large scale mining operations for more
than half of year now).

Since the distributed Filecoin Prover does not architecturally suite the
purpose of introducing second publicly-usable alternative Filecoin Proofs
C++ implementation, private C++ cryptography modules are going to be needed to 
be open-sourced, correctly licensed and embedded into existing Filecoin protocol 
implementations. This also means, THIS PROPOSAL IS NOT AN IMPLEMENTATION FROM
SCRATCH PROPOSAL, BUT AN OPEN-SOURCING EXISTING WORKING MODULES PROPOSAL. Sorry for caps.

The embedding work is initially planned to be done with 3 out of 4 existing
well-known implementations: [Lotus](https://github.com/filecoin-project/lotus), 
[Venus](https://github.com/filecoin-project/venus) and 
[Futhon](https://github.com/filecoin-project/cpp-filecoin). 
[Forest](https://github.com/ChainSafe/forest) seems to be the most comfortable
to work with Rust-based Filecoin Proofs implementation, so the need for alternative
C++ Filecoin Proofs integration introduction is arguable.

The particular embedding way is going to be about providing an alternative
filecoin-ffi submodule which will be ABI-compatible with traditional
[Filecoin Proofs FFI](https://github.com/filecoin-project/filecoin-ffi) module so 
the replacement could be simply substituted instead of the usual 
[Filecoin Proofs FFI](https://github.com/filecoin-project/filecoin-ffi) 
submodule in any of the Filecoin protocol implementations selected for the embedding 
work. So, in case of any troubles within the traditional [Rust-based Filecoin
Proofs implementation](https://github.com/filecoin-project/rust-fil-proofs) or
within the C++ Filecoin Proofs implementation, switching will be a zero-cost
operation. Quick and easy.

# Deliverables

* Open source Filecoin proofs C++ implementation architecturally suitable for
    being embedded into publicly-available Filecoin protocol implementations.
* Alternative Filecoin-FFI module implementation enabling Filecoin protocol 
    implementations to use C++ Filecoin proofs.
* Maintenance and support.

# Development Roadmap

Since this is a non-commercial thing for the team, open-sourcing and maintenance 
work would require some financing.

**Total Funding Amount:** \$80000

**Milestones:** 

| Milestone No. | Milestone Description                | Funding | Timeframe |
|---------------|--------------------------------------|---------|-----------|
| 1             | Filecoin Proofs C++ Implementation   | \$40000 |  6 weeks  |
| 2             | Alternative Filecoin-FFI Module      | \$10000 |  2 weeks  |
| 3             | Futhon (cpp-filecoin) Integration    | \$30000 |  4 weeks  |
| 4             | Support & Updates                    |    ~    |     ~     |

## Filecoin Proofs C++ Implementation

Filecoin Proofs C++ library is based on 
[=nil; Crypto3 C++ Cryptography Suite](https://github.com/nilfoundation/crypto3.git) 
components. 

Following open source components are going to be enhanced from private repositories:
* [Finite Fields and Curves Operations Library](https://github.com/nilfoundation/crypto3-algebra.git). Required for BLS12-381 curve operations implementation.
* [Multiprecision Library](https://github.com/nilfoundation/crypto3-multiprecision). Required for multiprecision arithmetics implementation.
* [zk-Proofs Library](https://github.com/nilfoundation/crypto3-zk). Required for building a PoRep/PoSt-related circuits and proofs generation.

Following components are going to be open-sourced and refactored from private repositories:
* C++ Filecoin Proofs Library. C++ alternative to `rust-fil-proofs`. Needs to be
    refactored to suite the open-source version architecture requirements.
* OpenCL/CUDA modules.

Time required for such an open-sourcing work is estimated in 6 weeks. Mostly
because of the work consists of opensourcing and refactoring existing modules,
not designing them from scratch.

## Alternative Filecoin-FFI Module

Alternative Filecoin-FFI module purpose is to provide the ABI-compatible
replacement to traditional 
[Filecoin Proofs FFI](https://github.com/filecoin-project/filecoin-ffi) 
module to enable users to work with alternative proofs implementation. The
implementation supposes for the module to be simply swipable with the
traditional one in any of the Filecoin protocol implementations

Following modules are going to be revived and updated:
* C++ Filecoin-FFI module. Replacement for the traditional [Filecoin Proofs FFI](https://github.com/filecoin-project/filecoin-ffi) module to enable users to work with alternative proofs implementation. Such an FFI implementation was once present before the private Filecoin Proofs C++ implementation's overall architecture was changed, so it is only required to revive that old module, update it, license it correctly and publish.


Time required for reviving, updating and open-sourcing such a module is
estimated in 2 weeks.

## Futhon (cpp-filecoin) Integration

[Futhon (cpp-filecoin)](https://github.com/filecoin-project/cpp-filecoin) 
integration is a separate milestone because this is that kind of Filecoin
protocol implementation which could have much tighter integration with proofs
subsystem, than usual implementations. Just like for 
[Forest](https://github.com/ChainSafe/forest) it is more convenient to be 
integrated with [Rust Filecoin Proofs subsystem](https://github.com/filecoin-project/rust-fil-proofs)
natively, than via [FFI submodule](https://github.com/filecoin-project/filecoin-ffi), 
it is being considered that [Futhon (cpp-filecoin)](https://github.com/filecoin-project/cpp-filecoin)
would be more convenient to be integrated with C++ proofs implementation
natively, but not via [FFI submodule](https://github.com/filecoin-project/filecoin-ffi).

This milestone would require closer cooperation with 
[Futhon (cpp-filecoin)](https://github.com/filecoin-project/cpp-filecoin) team,
so its time is estimated in at least 4 weeks. This milestone's timeframe will 
probably be extended until the integration of a proper quality is achieved.

## Support & Updates

This proposal supposes for the continious support, development and updates to be
provided. Since parts of the proofs implementation proposed for opensourcing 
are already a part of a proprietary commercial Filecoin mining software, all 
the updates and and continious support are going to be provided for free with 
no limiting timeframe.

Many security and updates coordination questions were raised during the
discussion in here: https://github.com/filecoin-project/rust-fil-proofs/discussions/1418. 
Most of them luckily have their answers developed over time. Any other questions
of similar kind can be discussed publicly or privately with email.

## Total Budget Requested

Total budget assumed to be \$80000. It includes testing infrastructure costs,
so total budget is discussable.

Project duration is 12 weeks.

## Maintenance and Upgrade Plans

All further maintenance and upgrades are going to be done for free with no time
limitations.

# Team

## Contact Info

Mikhail Komarov: nemo@nil.foundation.
Filecoin Slack: @Mikhail Komarov.

## Team Members

- Mikhail Komarov (https://github.com/nemothenoone). Team Leader.
- Ilyas Khairullin. Cryptographer. Developer.
- Nikita Kaskov. Developer. (https://github.com/nkaskov).
- Ilia Shirobokov. Cryptographer. Developer.
- Alisa Cherniaeva. Cryptographer. Developer.
- Alexey Moskvin. Developer.

## Team Member LinkedIn Profiles

- Mikhail Komarov: https://www.linkedin.com/in/mikhail-komarov-7084a9139/
- Nikita Kaskov: https://www.linkedin.com/in/nikita-kaskov-07029812a/

## Team Website

https://crypto3.nil.foundation or https://nil.foundation

## Relevant Experience

The team has succesfully developed, maintained and provided proprietary Filecoin 
mining software since May 2020 (reach the contact person for proofs). 
The team also made contributions into Rust-y Filecoin Proofs implementation, 
improving the performance of the opensource code. Same C++ cryptography suite
was successfully used in several other projects (reach the contact person for
proofs and explanations - this proposal is not for advertizing other projects)
for more than 3 years up to now. Well, just reach the contact person for all the
other questions.

## Team code repositories

=nil; Foundation's Github Organisation: https://github.com/nilfoundation
=nil; Crypto3's Github Team: https://github.com/orgs/NilFoundation/teams/nil-crypto3

# Additional Information

Every line in this proposal is discussable. Ask me (@nemothenoone).
