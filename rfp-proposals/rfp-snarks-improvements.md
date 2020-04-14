# RFP Proposal: `Filecoin Proofs Implementation Performance and Security Improvements`

**Name of Project:** =nil; Crypto3 Proofs Implementation Performance and Security Improvements

**Link to RFP:** https://discuss.filecoin.io/t/devgrants-wave-2-q-a/673/8

**RFP Category:** `core-dev`

**Proposer:** @nemothenoone

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

=nil; Crypto3 team intends to improve Filecoin Proofs library security and 
performance with implementation of several aspects described below and using 
C/C++ version of Groth16 zk-SNARK from  
[=nil; Crypto3 C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3).

## Value

There are following heavy computational tasks in Groth16 protocol:
- Arithmetic (multiplication and division) for polynomials of large degree over 
large prime fields. The problem arises from the QAP instance and witness reductions 
executed during setup stage.
- Multi-scalar multiplication over large prime groups.

Current Filecoin Groth16 implementation (a.k.a. bellman crypto library) solves
these tasks as follows:
- Fast polynomial evaluation and interpolation on the basis of FFT are provided, 
which enables fast polynomial multiplication.
- Point multiplication is computed using w-NAF technique. Moreover,
multiexponentiation algorithm uses Montgomery multiplication, reduction and
square algorithms.

However, the above-mentioned solutions can be improved by implementation of 
following optimizations:
	
- There exist improved techniques of point multiplication such as 
[Seo2013](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3758659/pdf/sensors-13-09483.pdf), 
[Witnet](https://medium.com/witnet/speeding-up-elliptic-curve-multiplication-through-scalar-decomposition-for-w-naf-39cdb5814d3f) and 
[wNAF](https://link.springer.com/content/pdf/10.1007\%2F978-3-540-68914-0\_26.pdf).

- There is a improved method of Montgomery multiplication evaluation which can 
  give us up to 18% speed improvement.

- Filecoin's GPU Fast Fourier Transform in Groth16 is based on the algorithm 
  described in the [gpu_fft](http://www.bealto.com/gpu-fft_ref.html). It is 
  remarkable that [gpu_fft](http://www.bealto.com/gpu-fft_ref.html) also gives 
  a description of possible code bottlenecks, which imply that the most 
  time-consuming operations are global memory reads and writes. One of the 
  possible optimizations is to implement recursive FFT which is cache-friendly.

- Current Filecoin proof library implementation supposes CRS are generated 
  according to [Groth2016](https://eprint.iacr.org/2016/260.pdf). 
  However, the authors of [BGM2017](https://eprint.iacr.org/2017/1050.pdf) 
  suggest multi-party protocol to generate secure CRS which differs from the one in 
  [Groth2016](https://eprint.iacr.org/2016/260.pdf).

- Several superoptimisation cases similar to ones which allowed us to 
  [take 2-nd place at Chia Network VDF contest](https://github.com/Chia-Network/vdfcontest2results).
  We've managed to achieve up to 2x performance increase with such
  superoptimisations.

## Deliverables

* An open-sourced, dual-licensed (under MIT and APACHE2) C++ Zero-Knowledge 
cryptography library with zk-SNARKs implemented as a module for 
[=nil; Crypto3 C++ Cryptography Suite](https://crypto3.nil.foundation/projects/crypto3).
  Such a library will also be usable as self-contained, standalone and independent library.
* Rust bindings for for previously-mentioned module.
* User documentation.
* Developer documentation.
* Examples along with tests.

## Development Roadmap

**Total Funding Amount:** $85500.

Thus it is discussable.

**Milestones:** 

The team works with 1-week cycles, so milestones are defined respectively.

| Milestone No. | Milestone Description                                             | Funding | Timeframe |
|---------------|-------------------------------------------------------------------|---------|-----------|
| 1             | Implementation of better solution of point multiplication problem | $19000  | 2 weeks   |
| 2             | Montgomery multiplication improvement                             | $19000  | 2 weeks   |
| 3             | Faster FFT Implementation                                         | $19000  | 2 weeks   |
| 4             | Secured CRS Implementation                                        | $19000  | 2 weeks   |
| 5             | Rust bindings & Testing                                           | $9500   | 1 week    |

### Implementation of better solution of point multiplication problem

As mentioned above, current Filecoin Groth16 implementation library uses 
w-NAF method for point multiplication. However, there exist improved techniques such as 
[Seo2013](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3758659/pdf/sensors-13-09483.pdf), 
[Witnet](https://medium.com/witnet/speeding-up-elliptic-curve-multiplication-through-scalar-decomposition-for-w-naf-39cdb5814d3f) and 
[wNAF](https://link.springer.com/content/pdf/10.1007\%2F978-3-540-68914-0\_26.pdf).

Team Leader intends to implement basic Groth16 concept and look through improved 
techniques and choices appropriate solution of point multiplication problem. 
He also intends to develop the concepts, module architecture. First developer would 
follow the team leader across the code and finalize the implementation internals, 
optimize, develop test. Other developer is supposed to implement  which would require 
to be passed with the code first developer made. Meanwhile team leader will initialize 
Montgomery multiplication improvement.

This milestone would require fill team employment and would take 2 weeks to be 
done. It is very likely this milestone would be done in time.

The result of this milestone is some of the above-mentioned point multiplication 
problem solution implementation and more secure Groth16 implementation.

We will obviously take into consideration existing [libsnark](https://github.com/scipr-lab/libsnark/) 
libraries while implementation, so that would not result in something useless.
It is important to mention that current zkSNARK implementations contain
security flaws during to GMP usage (which is famous by its' lack of
constant-time operations usage).

### Montgomery multiplication improvement

Filecoin uses CIOS Montgomery multiplication to effectively multiply big integers 
a and b modulo q. The description of this algorithm can be found in Section 2.3.2 
of [Tolga Acar's thesis](https://www.microsoft.com/en-us/research/wp-content/uploads/1998/06/97Acar.pdf).
The complexity of the CIOS method is 4N^2 + 4N + 2 unsigned integer additions and 
2N^2 + N unsigned integer multiplications, where N is the number of machine words 
needed to store the modulus q.

However, if the highest bit of the modulus q is zero and not all of the remaining 
words are set, the words t[N] and t[N + 1] of the temporary array t used in CIOS 
method are equal to 0 at the beginning of the outer i-loop. This observation allows 
to improve the performance approximately by 5-18 percents for small N (N <= N <= 8).

Such an [optimization](https://hackmd.io/@zkteam/modular_multiplication) suggested 
by Gnark researchers. According to them, their Go-implemented approach leads to 
10-15% speed improvement over existing libraries on 64-bit architectures for 
moduli of bit-length 704 or less.

Team Leader also intends to develop the concepts, module architecture. First developer would 
follow the team leader across the code and finalize the implementation internals, 
optimize, develop test. Other developer is supposed to implement  which would require 
to be passed with the code first developer made. Meanwhile team leader will initialize 
Faster FFT implementation.

This milestone would require fill team employment and would take 2 weeks to be 
done. It is very likely this milestone would be done in time.

The result of this milestone is more performant implementation of the Montgomery multiplication.

### Faster FFT Implementation

As mentioned above, Filecoin's GPU Fast Fourier Transform in Groth16 is based on 
the algorithm described in the [gpu_fft](http://www.bealto.com/gpu-fft_ref.html). 
It is remarkable that [gpu_fft](http://www.bealto.com/gpu-fft_ref.html) also gives 
a description of possible code bottlenecks, which imply that the most time-consuming 
operations are global memory reads and writes. One of the possible optimizations is 
to implement recursive FFT which is cache-friendly.

Team Leader also intends to develop the concepts, module architecture. First developer would 
follow the team leader across the code and finalize the implementation internals, 
optimize, develop test. Other developer is supposed to implement  which would require 
to be passed with the code first developer made. Meanwhile team leader will initialize 
Secured CRS implementation.

This milestone would require fill team employment and would take 2 weeks to be 
done. It is very likely this milestone would be done faster.

The result of this milestone is more performant implementation of the FFT.

### Secured CRS Implementation

In current Filecoin implementation, CRS are generated according to 
[Groth2016](https://eprint.iacr.org/2016/260.pdf). However, the authors of 
[BGM2017](https://eprint.iacr.org/2017/1050.pdf) suggest multi-party protocol 
to generate secure CRS which differs from the one in [Groth2016](https://eprint.iacr.org/2016/260.pdf).

This is more a security problem than a efficiency problem, but it is also 
quite relevant.

Team Leader also intends to develop the concepts, module architecture. First developer would 
follow the team leader across the code and finalize the implementation internals, 
optimize, develop test. Other developer is supposed to implement  which would require 
to be passed with the code first developer made. Meanwhile team leader will initialize 
Rust bindings.

This milestone would require fill team employment and would take 2 weeks to be 
done. It is very likely this milestone would be done faster.

The result of this milestone is implementation of a secured CRS.

### Rust bindings & Testing

Rust bindings is, actually, an optional module to implement. But in case the
Filecoin's community requirements include library usage from Rust, this would be
definitely done with a tiny wrapper using the original library with FFI.

Such a wrapper library would include all the dependencies required and will
server as a standalone library without any clue, there is a suite module inside.

Every development is a complicated process, which is required to be syncronized
week-by-week with the requirements. This milestone is supposed to be a
community communication and problem fixing milestone. Team leader along with
developers (if there would be any) would be accessible for faster communication 
with GitHub Issues especially to collect the feedback and fix bugs found.

This milestone would require fill team employment and would probably last 1 week.

The result of this milestone is a Rust wrapper along with documentation to the
Rust and C++ implementations. The result of the milestone also implies that all the 
zk-SNARK module is well-tested.

## Total Budget Requested

Total budget assumed to be $85500. Why is it so?

Following compensations are required by team members:

* Team Leader - $4000/week
* Developer 1 - $3000/week
* Developer 2 - $2500/week

These compensations include all the organisational costs along with some budget
reserved for 5+ year support. Thus compensations are discussable.

Project duration is 9 weeks. This leads to the following budget: $85500.

## Maintenance and Upgrade Plans

Cryptography suite is planned to be maintaned as long as possible by the team,
or by me (@nemothenoone) myself. This means ZK-cryptography module will be 
maintained as long as possible. 5+ years.

# Team

## Contact Info

Mikhail Komarov:

E-Mail: nemo@nil.foundation
Telegram: @nemothenoone

Nikita Kaskov:

E-Mail: nbering@nil.foundation

## Team Members

- Mikhail Komarov (https://github.com/nemothenoone). Team Leader.
- Aleksandr Sokolov (https://github.com/a1falcon). Developer 1.
- Nikita Kaskov (https://github.com/nkaskov). Developer 2. 

## Team Member LinkedIn Profiles

We don't really keep our LinkedIn accounts up to date, so they probably aren't 
done well enough.

- Mikhail Komarov: https://www.linkedin.com/in/mikhail-komarov-7084a9139/
- Alexander Sokolov: https://www.linkedin.com/in/alexander-sokolov-18a8341a4/
- Nikita Kaskov: https://www.linkedin.com/in/nikita-kaskov-07029812a/

## Team Website

Still in heavy development, but better than noting:

https://crypto3.nil.foundation or https://nil.foundation

## Relevant Experience

Our team is high-skilled in the area of implementation improvement. We took part,
for example, in the [Chia-Network VDF contest](https://github.com/Chia-Network/vdfcontest2results) 
and also in the [Chia-Network Proof Of Space competition](https://github.com/Chia-Network/proofofspaceresults) 
under the nicks nemo1369 and pulmark. As you can see, our improvements of the 
original implementation was quite successful in both cases and had more than 1.5x 
acceleration. It is important to note that the acceleration received only by 
imlementation improvements with no protocol or specs changes.

Apart from that, our team has the following experience:

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
* Aleksandr Sokolov. 5+ years experience in developing security-related C++ software.
  Ex-CryptoPro developer. Developing =nil; Crypto3 C++ Cryptography Suite for the 
  last year.
* Nikita Kaskov. 4+ years experience in security analysis of cryptographic
  schemes and software. Works with =nil; Crypto3 for the last year.

## Team code repositories

=nil; Foundation's Github Organisation: https://github.com/nilfoundation
=nil; Crypto3's Github Team: https://github.com/orgs/NilFoundation/teams/nil-crypto3

# Additional Information

Ask me (@nemothenoone).
