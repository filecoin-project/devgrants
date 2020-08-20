To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: Add Filecoin support to Ethereum Name Service

**Name of Project:** Ethereum Name Service

**Proposal Category:** app-dev

**Proposer:** brantlymillegan

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

We'd like to support Filecoin addresses in our Other Addresses record in our Manager (app.ens.domains), so that users can send Filecoins to names rather than addresses.

Then we'd like to work with wallets that add Filecoin support to ensure they work with ENS. We could also help add ENS support to any Filecoin native clients (answer questions), if desired.

ENS is already the leading blockchain-based naming solution, with 158 integrations (including 43 wallets and 5 browsers). Adding support for Filecoin in these ways will make Filecoin more user-friendly, as well as increase the usefulness of ENS.

## Value

Filecoin needs naming for Filecoin addresses. ENS is already the leader in decentralized naming. ENS support for Filecoin will make Filecoin easier to use and increase the usefuleness of ENS.

This project is low risk, as it is simply integrating Filecoin addresses and hashes into an already existing and functioning framework. It mostly just takes time and coordination of relevant stakeholders.

## Deliverables

1) Filecoin addresses will be supported in the ENS Manager. This means: FIL will be an option in the drop down menu for adding different cryptocurrency addresses, and our cryptocurrency addresses encoding library will support the appropriate encoding for Filecoin addresses.

2) We will check with wallets that support ENS and that add Filecoin to ensure their support works.

## Development Roadmap

Milestone 1: Support for Filecoin addresses (1 week; $3k)

This requires updating our cryptocurrency address encoding library with the appropriate encoding for Filecoin addresess and adding FIL support to our Manager UI. Protocol Labs will provide us with information about how Filecoin addresses are encoded.

Milestone 2: Check with wallets (1 week; $0.5k)

We will check with multi-coin wallets that already support ENS and that add support for Filecoin to ensure they support everything correctly.

*Totals*: This should all be able to be accomplished in about two weeks and for $3.5k.

## Total Budget Requested

$3.5k. This will be spent on developer time.

## Maintenance and Upgrade Plans

Since it will be a feature of ENS, it will be updated, maintained, and supported as needed indefinitely.

# Team

## Team Members

- Nick Johnson
- Brantly Millegan
- Jeff Lau
- Makoto Inoue
- Becca Liebert

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/nicksdjohnson/
- https://www.linkedin.com/in/brantly-millegan/
- https://www.linkedin.com/in/makotoinoue/
- https://www.linkedin.com/in/jeflau/
- https://www.linkedin.com/in/becca-liebert-aa778857/

## Team Website

https://ens.domains/

## Relevant Experience

We already successfully develop and manage the ENS project.

## Team code repositories

https://github.com/ensdomains/

# Additional Information

We have a positive relationship with Protocol Labs. We've worked with your team in the past and we'd be happy to work together again.
