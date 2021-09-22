# Open Grant Proposal: `DID Authentication for Powergate/Lotus`

**Name of Project:** DID Authentication for Powergate/Lotus

**Proposal Category:** `app-dev`

**Proposer:** [`@ukstv`](https://github.com/ukstv)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes.

# Project Description

Powergate serves as a front end for Lotus Filecoin client. Lotus manages Filecoin private keys, as well as provides API for low level storage/deals management. Powergate exposes higher-level functions allowing an end user to specify configuration for storage declaratively. Powergate then handles lower-level details with Lotus.

Powergate provides an API for storage management. The API is authenticated via UUID token.

There is a certain mismatch. Lotus manages private key, of a user apparently. Powergate authenticates via UUID that has nothing to do with the keys that are managed by Lotus. It is beneficial to for a user to (1) link Filecoin private key to her DID, (2) import her private key to Powergate/Lotus, (3) authenticate to Powergate via DID.

We intend to use [Ceramic](https://ceramic.network) 3id as DID. It uses own set of main keys, and also it allows a user to link additional keys to DID, like Ethereum ones. Linking requires signing a payload with Filecoin key. This implies adding Filecoin keys (both BLS and secp256k1) to [`3id-blockchain-utils`](https://github.com/ceramicnetwork/js-3id-blockchain-utils), and creating a CLI tool that allows signing the payload with raw private keys, as well as providing input for Lotus CLI.

Parts (2) and (3) above require building authentication frontend for Powergate, that manages Powergate FFS instances based on DID. The frontend is API-only, it is accompanied with a console client that allows linking Filecoin key to DID, importing keys to FFS instance (see [issue #456 on Powergate repo](https://github.com/textileio/powergate/issues/456)), and making FFS calls based on DID.

Expected scenario:

1. User creates her Ceramic DID on CLI, using seed.
2. User links her Filecoin key with the created DID.
3. User imports her Filecoin key into daemon
4. User stores her file to Powergate, authenticating via DID
   - Here Daemon checks if DID corresponds to one of the Filecoin keys inside Lotus

![Scenario](https://nd8hnw.db.files.1drv.com/y4mV2lo7y2Nkh_dTS4nCckjlT3BgWkOM-NZYD85NTHssjakAUHVAEo-K8ve_o36yj3NrpHjtT6LWnSecT_fST6IZBhugtm7fRCweIWutghAjkGUKfeoAf_KyPcYpANyPCCesxgxOV2cL2QeHMVyQ8BUx_5SlHGe63paLppYRdJgTkjrx33LQrQNqsDNGrScqK4YooleBpoNEiJZzo2UKhe0ow/did-auth.png?psid=1)

## Value

If we envision Filecoin keys to be used outside of huge mining farms, providing authentication mechanism based on a Filecoin key, i.e. proof of ownership, seems beneficial to the ecosystem. Currently the most viable way to do this is via DID and linked keys, which Ceramic provides infrastructure for. Results of this project could be used as an example for other DID protocols as well. This covers key linking.

Authentication part (daemon and accompanying client) could later be integrated into Powergate UI, which simplifies the user flow, which is also beneficial for the Filecoin ecosystem.

The single risk I (`@ukstv`) see is inability to  [import key to Powergate](https://github.com/textileio/powergate/issues/456) at the time everything else is ready. In this case, the scenario

## Deliverables

1. Expanded `3id-blockchain-utils` with support for Filecoin keys: `createLink`, `validateLink`, `authenticate` functions. Handles signing through [filecoin-signing-tools](https://github.com/Zondax/filecoin-signing-tools).
2. Linking client - CLI tool that accepts Filecoin key and links it to existing Ceramic DID using `3id-blockchain-utils` ; should cover:
   - accepting hex BLS, secp256k1 key,
   - accepting seed phrase,
   - creating payload for Lotus CLI signing,
   - accepting signature from Lotus CLI,
   - provides CLI as well as NPM library.
3. Authentication frontend for Powergate
   - manages Powergate FFS-UUID-DID mapping,
   - authenticates via DID (based on [`did-auth-jose`](https://github.com/decentralized-identity/did-auth-jose#readme))
   - proxies calls to Powergate FFS
4. Client for the authentication frontend:
   - manages local DID (through connection to Ceramic node),
   - creates Filecoin link (see 2 above)
   - create calls to Powergate FFS,
   - in CLI form.

## Development Roadmap

The development here is done by Sergey Ukustov (`@ukstv`) with advisory by Joel Thorstensson (`@oed`).

| Milestone                              | Raw time | Delivery time | Budget   |
| -------------------------------------- | -------- | ------------- | -------- |
| Expanded `3id-blockchain-utils`        | 24hrs    | 1 week        | 1560 DAI |
| Linking client                         | 36 hrs   | 1.5 weeks     | 2340 DAI |
| Authentication frontend                | 48 hrs   | 1.5 weeks     | 3120 DAI |
| Client for the authentication frontend | 36 hrs   | 1 week        | 2340 DAI |
| **Total**                              |          |               | 9360 DAI |

## Total Budget Requested

9360 DAI

## Maintenance and Upgrade Plans

`3id-blockchain-utils` as well as linking client go as part of Ceramic, so the maintenance goes to Ceramic team. As time goes, I (`@ukstv`) see authenticatin frontend and accompanying client to become in some form part of Powergate UI.

# Team

## Team Members

- Sergey Ukustov (engineer) - [@ukstv](https://github.com/ukstv)
- Joel Thorstensson (Ceramic advisor) - [@oed](https://github.com/oed)

## Relevant Experience

Sergey is an engineer with 15 years of experience in software development, including focus on distributed and blockchain technology for the last 5 years. Was involved in bringing blockchain tech to Russian banking and energy sectors. Built the first payment channels implementation in production.
