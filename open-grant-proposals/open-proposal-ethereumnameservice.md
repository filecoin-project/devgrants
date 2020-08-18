To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: Add Filecoin support to Ethereum Name Service

**Name of Project:** Ethereum Name Service

**Proposal Category:** app-dev

**Proposer:** brantlymillegan

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

We'd like to add support for Filecoin to ENS in two places. First, we'd like to support Filecoin addresses in our Other Addresses record in our Manager (app.ens.domains), so that users can send Filecoins to names rather than addresses. Second, we'd like to add support for Filecoin file hashes to our Content record (which currently supports IPFS, et al).

Then we'd like to work with wallets and browsers that add Filecoin support to ensure they work with ENS. We could also help add ENS support to any Filecoin native clients, if desired.

ENS is already the leading blockchain-based naming solution, with 158 integrations (including 43 wallets and 5 browsers). Adding support for Filecoin in these ways will make Filecoin more user-friendly, as well as increase the usefulness of ENS.

## Value

Filecoin needs naming, both for Filecoin addresses and Filecoin hashes. ENS is already the leader in decentralized naming. ENS support for Filecoin will make Filecoin easier to use and increase the usefuleness of ENS.

This project is low risk, as it is simply integrating Filecoin addresses and hashes into an already existing and functioning framework. It mostly just takes time and coordination of relevant stakeholders.

## Deliverables

1) Filecoin addresses will be supported in the ENS Manager. This means: FIL will be an option in the drop down menu for adding different cryptocurrency addresses, and our cryptocurrency addresses encoding library will support the appropriate encoding for Filecoin addresses.

2) The ENS Content record will support Filecoin hashes, and the Manager UI will include a prompt alerting users of this.

3) We will update our docs to reflect the new functionality.

4) We will check with wallets and browsers that support ENS and that add Filecoin to ensure their support works.

5) We can help you add ENS functionality to a Filecoin client of your choosing.

6) Blog post on ENS blog regarding these new features.

## Development Roadmap

Milestone 1: Support for Filecoin addresses (1 week; $5k)

This requires updating our cryptocurrency address encoding library with the appropriate encoding for Filecoin addresess and adding FIL support to our Manager UI.

Milestone 2: Support for Filecoin hashes in Content record (2 weeks; $5k)

This may require an update to content-hash (which is controlled by an outside party), and then an update to our Manager UI to support the new type of hash in the Content record.

Milestone 3: Update ENS docs (1 week; $4k)

We will need to update our docs regarding the new functionality.

Milestone 4: Check with wallets and browsers (2 weeks; $5k)

We will check with multi-coin wallets that already support ENS and that add support for Filecoin to ensure they support everything correctly. We will also contact browsers that support ENS to offer help in upgrading to also support Filecoin hashes, although we can't guarantee that they will or, if they do, on what timeline.

Milestone 5: Help you add ENS to Filecoin client (2 weeks; $1k)

We can add ENS functionality to a Filecoin client of your choosing, if you'd like.

Milestone 6: Blog post (2 days; $1k)

We will promote the new Filecoin features on the ENS blog and thank Filecoin for the grant.


Totals: This should all be able to be accomplished in about two months and for $30k. The timeline has provided for development blocks and waiting for outside parties, et al.

## Total Budget Requested

$21k. This will be spent on developer time.

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
