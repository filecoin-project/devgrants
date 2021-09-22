To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Glif module automation`

**Name of Project:** [`Glif`](https://www.glif.io)

**Proposal Category:** `devtools-libraries`

**Proposer:** `Schwartz10`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Infinite Scroll started working on the Glif project 1 year ago. Glifs are interoperable tools for the Filecoin network. The Glif suite includes end user apps _and_ developer tools. The apps - the Glif wallet, Glif multisig (Vault), Glif Faucet (for Space Race, and Glif Verifier (as a Filecoin notary) all rely heavily on the [Glif modules](https://github.com/glifio/modules). Other teams in the space are relying on the Glif modules as well. The Glif modules contain core Filecoin business logic:

- [filecoin-address](https://www.npmjs.com/package/@glif/filecoin-address) - a JS implementation of the Filecoin address type, [inspired by go-address](https://github.com/filecoin-project/go-address).
- [filecoin-message-confirmer](https://www.npmjs.com/package/@glif/filecoin-message-confirmer) - a service that takes a message CID and notifies the caller once the message is confirmed.
- [filecoin-message](https://www.npmjs.com/package/@glif/filecoin-message) - helper methods for handling Filecoin messages.
- [filecoin-number](https://www.npmjs.com/package/@glif/filecoin-number) - a wrapper class built around javascript's [bignumber](https://github.com/MikeMcl/bignumber.js) for handling FIL <> AttoFIL <> PicoFIL conversions.
- [filecoin-rpc-client](https://www.npmjs.com/package/@glif/filecoin-rpc-client) - a json-rpc client that handles interacting with Lotus.
- [filecoin-wallet-provider](https://www.npmjs.com/package/@glif/filecoin-wallet-provider) - helper methods for handling Filecoin wallet operations.
- [react-components](https://www.npmjs.com/package/@glif/react-components) - commonly used react components across Glif applications.

We are planning to automate the building, testing, versioning, publishing, and releasing of the Glif modules, as well as automating the process of updating any Glifs that rely on any newly published Glif modules.

The value of automation is best seen through before/after. Imagine I (Jon Schwartz) merge a PR into the filecoin-number repository, what happens next?

_Before automation_:

1. Jon pulls `primary` branch locally.
2. Jon runs the Glif modules tests, locally.
3. If passing... Jon manually builds the modules.
4. Jon manually versions the modules.
5. Jon manually publishes the modules to npm.
6. Jon manually releases the modules.
7. Jon manually opens a new PR in the wallet repo to bump the `filecoin-version` number.
8. Jon manually opens a new PR in the verifier-frontend repo to bump the `filecoin-version` number.
9. Jon manually opens a new PR in the faucet-frontend repo to bump the `filecoin-version` number.

There are several problems with this approach:

- Although it hasn't happened yet, so many manual steps is _asking_ for human error at some point along the way, which could jeopardize the security of upstream applications.
- The modules are way harder to maintain from a community standpoint, since no one knows all the necessary steps and processes to get new versions out the door.
- Building and testing locally can have side effects related to the types of machines and environments being used, which means unnoticed bugs can slip through the cracks.

_After automation_:

1. GitHub action runs Glif module tests in the cloud, in a sandboxed VM with no potential for local environments to interfere.
2. GitHub action runs Glif module lints in the cloud, so stylistic errors get caught.
3. GitHub action builds the modules automatically.
4. GitHub action versions the modules automatically.
5. GitHub action publishes the modules automatically.
6. Github action releases the modules automatically.
7. Dependabot notices the new release, submits PRs into all upstream Glif apps.

This much automation is much safer, standard, and easier to maintain. It sets the community up to take over the Glif modules in the event that the original maintainers aren't around anymore.

## Value

Benefits to the Filecoin ecosystem:

- Developers can be more confident relying on stable tools.
- The community is better positioned to maintain Glif modules together, rather than rely on any single entity.
- Our team is better positioned to take on new work to help the ecosystem, rather than spending time maintaining the modules.

## Deliverables

The deliverable is a fully automated Glif modules repo with GitHub actions and dependabot.

## Development Roadmap

Since the project is small, we only have a single milestone. Whenever this proposal is accepted, we will complete the work 3 weeks after the acceptance date. The total actual working days will fall around 1.5 weeks.

## Total Budget Requested

$4,500 USD

## Maintenance and Upgrade Plans

We plan on maintaining the Glif app suite for a long time into the future. These Glif modules are essential in keeping those apps working well, so these modules must be maintained and upgraded over time to ensure the success of Glif as a whole!

# Team

## Team Members

- Jon Schwartz
- Bret Comnes

## Team Member LinkedIn Profiles

- [Jon Schwartz](https://www.linkedin.com/in/schwartzz8990/)
- [Bret Comnes](https://www.linkedin.com/in/bret-c-32ba74109/)

## Team Website

[https://www.infinitescroll.org](https://www.infinitescroll.org)
[https://www.glif.io](https://www.glif.io)

## Relevant Experience

We built the Glif modules, so we are best positioned to automate them. Bret wrote [this blog post](https://bret.io/projects/package-automation/) on automation, he's well qualified.

## Team code repositories

Check out the [Glif GitHub org](https://github.com/glifio/).
