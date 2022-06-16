# RFP Proposal: `FVM - Go SDK`

**Name of Project:** FVM - Go/Tinygo SDK 

**Link to RFP:** 

**RFP Category:** `devtools-libraries`

**Proposer:** `hunjixin`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT, GPL, and APACHE2 licenses?:**  Yes

# Project Description

Since the announcement of [FVM](https://fvm.filecoin.io/), support for a broader developer community other than the native Rust programming language is of high importance to the FVM roadmap in general. A strong and diverse developer community has been proven to be critical to the longevity of a project and we think that FVM project have the opportunities to attract more developers with a wider SDK support.

During FVM Early Builder program, we have successfully built a PoC Go SDK that facilitates the use of Tinygo to write user-defined actors (smart contracts) that meets the requirement of WASM compilation target so that the said actors can be run in the WASM-based FVM execution environment. In extension of this PoC, we now propose the continuation of the development for the FVM GO SDK.

## Value

<!-- Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions: -->
<!-- - What are the benefits to getting this right? -->

The benefits of a Go SDK is apparent as it provides a much easier on-ramp for Go developers into the fvm ecosystem. In addition, the existing pool of contributors to Lotus and Venus implementation of Filecoin could jump right into fvm development with language they already familiar with. Some highlights FVM could leverage by bringing in Go SDK:

- A fairly easy-to-learn high-level programming language 
- An extensive selection of libraries, especially blockchain related ones
- Matches the technology stack of Filecoin which allows `import` of necessary libs

All in all, we believe that a Go SDK would contribute a great deal to the growth of the FVM ecosystem and could be the gateway language to on board more developers to write user-defined actors.

<!-- - What are the risks if you don't get it right? -->


<!-- - What are the risks that will make executing on this project difficult? -->

<!-- This section should be 1-3 paragraphs long. -->

## Development Roadmap and Deliverables

Each milestone would contain number of sub-milestones to have finer granularity.

## Milestone 1 - POC

### M1.1 - Implementation

Writing and executing actors using TinyGo.

**Deliverables**:

- go-fvm-sdk v0.1
- Implement all fvm system calls
- Implement test system tools
- Testing CI workflows   
- Hello World and ERC20 examples

**Funding for this M1.1**:

1 PM resource: 1 * 46 $/h * 40 h/week * 2 week = $3680
1 Software engineer lead resource: 1 * 76 $/h * 40 h/week * 2 week = $6080 
1 Software engineer resource: 1 * 67 $/h * 40 h/week * 2 week = $5360
1 QA engineer resource: 1 * 55 $/h * 40 h/week * 2 week = $5360

Total = $19520

See rates at [reference](#reference) section for more details.

### M1.2 - Testing & Optimizations

**Deliverables**:

- Community testing & feedback gathering
- Optimization & bug fixes
- Basic documentation about FVM (technical, Usage, FAQ)

**Funding for this M1.2**:

1 PM resource: 1 * 46 $/h * 40 h/week * 2 week = $3680
1 Software engineer lead resource: 1 * 76 $/h * 40 h/week * 2 week = $6080 
1 Software engineer resource: 1 * 67 $/h * 40 h/week * 2 week = $5360
1 QA engineer resource: 1 * 55 $/h * 40 h/week * 2 week = $5360

Total = $19520

**Estimated Milestone 1 Delivery**:

Within time framework of early builder program. Estimated to be around a month (End of August 22)

## Milestone 2 - EVM support

Taking advantage of the fact that EVM is written natively using Go, we plan to build a [Shim](https://en.wikipedia.org/wiki/Shim_(computing)) layer upon go-fvm-sdk as foundation and run Solidity code on top of it. 

### M2.1 - Implementation

**Deliverables**: 

- go-fvm-sdk v0.x
- Support evm code running in TinyGo
- Updated CI workflows

**Funding for this M2.1**:

1 PM resource: 1 * 46 $/h * 40 h/week * 2 week = $3680
1 Software engineer lead resource: 1 * 76 $/h * 40 h/week * 2 week = $6080 
1 Software engineer resource: 1 * 67 $/h * 40 h/week * 2 week = $5360
1 QA engineer resource: 1 * 55 $/h * 40 h/week * 2 week = $5360

Total = $19520

### M2.2 - Testing & Optimizations

**Deliverables**: 

- Community testing & feedback gathering
- Optimization & bug fixes
- Update Document for evm support

**Funding for this M2.2**:

1 PM resource: 1 * 46 $/h * 40 h/week * 2 week = $3680
1 Software engineer lead resource: 1 * 76 $/h * 40 h/week * 2 week = $6080 
1 Software engineer resource: 1 * 67 $/h * 40 h/week * 2 week = $5360
1 QA engineer resource: 1 * 55 $/h * 40 h/week * 2 week = $5360

Total = $19520

**Estimated Milestone Delivery**: 

Estimated to be around a month. (End of Sep 22)

## Milestone 3 - Memory optimization 

We expect that there could be performance issues given the native garbage collection. This could be amended by adopting manual memory allocation functions, which works similarly to dynamic memory allocation in C where user could allocate memory and free memory on demand. Thus, improves the performance of running actors. 

At the same time we expect to expose some basic types for managed code.

**Assumptions/Requirements**:

- Explore opportunities in Cgo and identify if minimal changes could allow Cgo to be compatible with WASM
- Manual memory management would require extra storage apart from ones designated to garbage collection, which may require support of memory allocation function of FVM

### M3.1 - Implementation

**Deliverables**:

- go-fvm-sdk v0.x
- Updated CI workflows
- types like CString, CSlice（If necessary）
- Able to load WASM lib compiled from dynamic memory allocation of C or Rust
- Can properly handle the boundaries between managed and unmanaged code

**Funding for this M3.1**:

TBD

### M3.2 - Testing & Optimizations

**Deliverables**:

- Community testing & feedback gathering
- Optimization & bug fixes
- Extended documentation

**Funding for this M3.2**:

TBD

**Estimated Milestone 3 Delivery**:

Three month. (End of Dec 22)

## Milestone 4 - Golang-fvm—sdk

Actual Golang support for FVM while retaining support for TinyGo at the same time

**Assumptions/Requirements**:

Preconditioned by the progress of how much Go would support WASI. We could either:
- Wait for Go to support WASI
- Or support Golang through `stub` which might have an impact on performance

### M4.1 - Implementations

**Deliverables**: 
- go-fvm-sdk v0.x
- Performance metrics (WASM target size, memory usage, time usage) of Go Vs. TinyGo
- Updated CI workflows

**Funding for this M4.1**:

TBD

### M4.2 - Testing & Optimizations

**Deliverables**: 
- Community testing & feedback gathering
- Optimization & bug fixes
- Update Documentatoin for golang

**Funding for this M4.2**:

TBD

**Estimated Milestone 4 Delivery**:

Three month. (End of Mar 22)


## Total Budget Requested

<!--Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds. -->

## Maintenance and Upgrade Plans

<!-- Specify your team's long-term plans to maintain this software and upgrade it over time. -->

The team is willing to continue the development of this RFP after M4. Another evaluation will be needed at then to further the planning.

## Team Members

Venus [core team](https://github.com/orgs/filecoin-project/teams/venus)

<!-- - Team Member 1 -->
<!-- - Team Member 2 -->
<!-- - Team Member 3 -->
<!-- - ...

## Team Member LinkedIn Profiles

<!-- - Team Member 1 LinkedIn profile -->
<!-- - Team Member 2 LinkedIn profile -->
<!-- - Team Member 3 LinkedIn profile -->


## Team Website

https://forcecommunity.io/

## Relevant Experience

Force community has been an active contributor to Web3 ecosystem and Filecoin ecosystem in general. The engineering team from Force community has a track record of contributing code to Lotus as far back as Testnet and Space Race. 

## Team code repositories

https://github.com/ipfs-force-community

## Additional information

Force community is committed to become a major contributor to Web3 infrastructure and we see Filecoin at the core of the big Web3 migration. We hope that we could fast track the realization of Web3 adoption by contributing our software development capacity to the course and join hand in hand with all other ecosystem developers around the globe through this historical journey!

## References

- Project manager hourly rate: [$46](https://www.salary.com/research/salary/alternate/project-manager-experienced-it-hourly-wages)
- Software engineer (Go/WASM) hourly rate: [$67](https://www.salary.com/research/salary/benchmark/software-engineer-iv-hourly-wages)
- Software engineer lead (Go/WASM) hourly rate: [$76](https://www.salary.com/research/salary/benchmark/software-engineering-manager-salary)
- QA engineer: [$55](https://www.salary.com/research/salary/alternate/software-testing-and-quality-engineer-iv-hourly-wages)