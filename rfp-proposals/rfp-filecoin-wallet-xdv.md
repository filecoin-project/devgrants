To submit a proposal, please create a PR against this template in this repo. Please title your file `rfp-proposal-title.md`, replacing `title` with the name of your project.

# RFP Proposal: `Filecoin-Mobile-Wallets`

**Name of Project:** Filecoin Flutter and XDV Core for Filecoin
**Link to RFP:** [rfp-filecoin-wallet-xdv.md](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-filecoin-wallet-xdv.md).


**RFP Category:** Choose one of  `app-dev`

**Proposer:** @molekilla

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

XDV team already has an  existing core wallet tech [XDV wallet](https://github.com/xdvplatform/xdvplatform-wallet). Because our roadmap includes IPLD and blockchain, we would like to help Filecoin, as  we think is the best technology for our platform.  We'll add `Filecoin signing API` to our wallet, having builds both in `WASM` and `Typescript` output from the migration to `Dart`.

This in turn will be used to create an open source Filecoin only Flutter wallet.

## Deliverables

Please describe in details what your final deliverable for this project will be.

### XDV Wallet Core
- Migrate to Dart (BoringSSL, other crypto libs) 
- Complete BLS
- Add Filecoin signing support
- Fix Unit Tests and update them

### Flutter Dev Pipeline
- Boilerplate

### Flutter wallet
- Add Wallet integration
- Add blockchain dapp integration (JSON-RPC or lib)
- UX design
- QA
- Tests in browsers and mobile

### Flutter OS Builds
- QA Mac, Windows, Linux

### Filecoin Flutter Wallet Reference Impl
- Clean
- Document

### Nice to haves
- DID integration

## Development Roadmap

### XDV Wallet Core  @molekilla, @bradleysuira, @mikaelagarroz - 3 to 4 weeks - $ 5,000
- Migrate to Dart (BoringSSL, other crypto libs) 
- Complete BLS
- Add Filecoin signing support
- Fix Unit Tests and update them

### Flutter Dev Pipeline @bradleysuira, @elfgod - 1 week $1,000
- Boilerplate

### Flutter wallet @bradleysuira, @elfgod, @molekilla, @mikaelagarroz - 3 weeks $6,000
- Add Wallet integration
- Add blockchain dapp integration (JSON-RPC or lib)
- UX design
- QA
- Tests in browsers and mobile

### Flutter OS Builds  @molekilla, @bradleysuira -  2 -  3 weeks $6,000
- QA Mac, Windows, Linux

### Filecoin Flutter Wallet Reference Impl @molekilla, @bradleysuira - 2 weeks $4,000
- Clean
- Document

### Nice to haves - @molekilla, @bradleysuira, @elfgod - 2 weeks - $2,000 
- DID integration



## Total Budget Requested

Sum up the total requested budget across all milestones, and include that figure here. Ensure that it does not exceed the total funding limit on the RFP.

Developer Resources - $24,000
PM and Architect - $3,500 - @luissanchez0305 - Luis Sanchez

## Maintenance and Upgrade Plans

Specify your team's long-term plans to maintain this software and upgrade it over time.

XDV Wallet and Filecoin tooling are going to be maintained by our team, to meet business demands of our platform. Attach roadmaps.

- [XDV Roadmap](https://drive.google.com/file/d/1jE_QTtEhGI9XTRPd_V4G-XMAG7ueZ-ot/view)
- [XDV Invoice Protocol](https://drive.google.com/file/d/1q781Uf9G6fVN8JQFnY4JwaFIWM3aow0N/view?usp=sharing)
- [XDV DeFi](https://drive.google.com/file/d/1UoINe7G4VlY4NIeD3fFNYz7Uh_p2iIlf/view)

# Team

- Luis Sanchez @luissanchez0305 - Lead Arch and PM
- Rogelio Morrell Caballero - @molekilla - Developer
- Bradley Suira - @bradleysuira - Developer
- Mikaela Novoa Garroz - @mikaelagarroz - Developer
- Alberto Guzman - @elfgod - Developer

## Contact Info

Provide us with a way to contact you (email is probably easiest) so we can communicate our selection decision to you directly. You can also email devgrants@filecoin.org with your GH username and link to your public proposal.

## Team Members

- Team Member 1
- Team Member 2
- Team Member 3
- ...

## Team Member LinkedIn Profiles

- Team Member 1 LinkedIn profile
- Team Member 2 LinkedIn profile
- Team Member 3 LinkedIn profile
- ...

## Team Website

Please link to your team's website here (make sure it's `https`)

## Relevant Experience

Please describe (in words) your team's relevant experience, and why you think would do a great job with this RFP. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc.

## Team code repositories

Please provide links to your team's prior code repos for similar or related projects.

# Additional Information

Please include any additional information that you think would be useful in helping us to evaluate your grant application.
