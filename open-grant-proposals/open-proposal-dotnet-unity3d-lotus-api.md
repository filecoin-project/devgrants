
# Open Grant Proposal: `.Net Unity3d Lotus Api`

**.Net Unity3d Lotus API:**

**Proposal Category:** `devtools-libraries`

**Proposer:** @juanfranblanco

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

.Net and Unity3d developers are a big part of the developer space. 25% / 30%  developers worldwide are .Net developers and around 50% of the games developed use Unity3d as an engine.

To enable these developers to interact with the Lotus Filecoin RPC integrating their existing or new applications, games or VR resources this project will create a new .Net Api and a specific Unity3d api, for all the rpc methods provided by Lotus https://github.com/filecoin-project/lotus/blob/master/api/api_full.go.

This project will also create simple examples of usage, first providing simple interaction (for example retrieving the wallet balance) and finally an example of importing a file (asset) and loading it in a Unity application or game.

## Deliverables and Development Roadmap

Milestone | Hours | Cost
--- | --- | ---
 Generic feasibility research. | 16 | £960
Create .Net Standard RPC Api supporting all methods here:
https://github.com/filecoin-project/lotus/blob/master/api/api_full.go
Create Unit tests following the generic input / output:
Example of input and output generated from the Lotus api. https://gist.github.com/jimpick/7c227fc9f8e7267634cf989dec8c0323
| 80 | £4,800
Create extra RPC Api supporting Unity coroutines (Support for older versions of Unity and WebGl)
| 40 | £2,400
 Create example of interaction in Unity (WalletBalance, WalletDefaultAddress, etc) | 24 | £1440
 | Create example workflow of submitting an asset (image) using the API, including User interface and loading it in Unity Ref: https://github.com/Nethereum/Unity3dSimpleSampleNet461 | 40 | £2,400
| Create blog / readme documentation explaining the API usage and example | 20 |  £1200


**Total** |  | 	**£13,200.00**

## Total Budget Requested

£13,200 VAT Not included

## Maintenance and Upgrade Plans

General support, bugs fixes will be provided as general maintenance for a period of time. Future work and phases are expected to provide support for offline signing, full documentation, extended samples, crosschain support and smart contract integration.

# Team

## Team Members

- @juanfranblanco
- TBC

## Team Member LinkedIn Profiles

https://uk.linkedin.com/in/juanfranblanco

## Team Website

## Relevant Experience

Founder and creator of Nethereum, Solidity vs code plugin, 20 years architect and senior .net developer.

## Team code repositories

https://github.com/Nethereum/Nethereum
https://github.com/Nethereum/Unity3dSimpleSampleNet461

