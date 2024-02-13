# Open Grant Proposal: Bidirectional FIL <=> WFIL Bridge to Ethereum

**Name of Project:** Bidirectional FIL <=> WFIL Bridge to Ethereum

**Proposal Category:** `app-dev`

**Proposer:** `wbnns`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes. 👍

# Project Description

Late last year, Wrapped Filecoin (WFIL) [launched](https://medium.com/anchorage/anchorage-and-tokensoft-bring-wrapped-filecoin-wfil-to-ethereum-44aa7f294d) on Ethereum, via a joint collaboration between [Anchorage](https://www.anchorage.com/) and [Tokensoft](https://www.tokensoft.io/). WFIL is an ERC20 standard token which represents a 1:1 value of WFIL to Filecoin (FIL) held in custody by Anchorage, a US-based trust. WFIL allows for FIL to be used in traditional DeFi applications such as Uniswap, Balancer and Curve. FIL holders often would like to be able to wrap their Filecoin so that they can participate in [yield farming opportunities](https://twitter.com/OmakaseBar/status/1403751584211910663?s=20) that exist in Ethereum and on layer two networks like Polygon.

While a centralized model is good for some, it doesn't service the entire marketplace. Some FIL holders would like a trustless way to easily get into WFIL. Since that isn't possible at the moment, FIL holders that want to wrap and put their holdings to work to generate additional yield, are unable to do so. This is a missed opportunity; some FIL holders end up selling their FIL for a stablecoin, then subsequently using it to purchase WFIL directly on a DEX on Ethereum, like Sushi or Uniswap.

To create a solution for this, we're applying for a grant to build a trustless / open source and bidirectional bridge from FIL to WFIL to enable many of the users who are requesting to do so, a way to easily move back and forth.

## Value

A trustless bridge between FIL and WFIL will allow long term holders of FIL a way to take advantage of many of the opportunities that exist in DeFi, particularly on Ethereum and L2s like Polygon. The primary risk associated with constructing a bridge is ensuring that sufficient liquidity is in place to facilitate the crossover from FIL to WFIL. The lack of liquidity does not put a FIL holders funds at risk, it simply limits the amount one would potentially be able to bridge.

## Deliverables

+ 60 days post-grant (~8 weeks); launch bridge

## Development Roadmap

+ 1W: Finalize formal specification
+ 2W: Design API
+ 3W: Toolchain & Infrastructure
+ 4W: Test Suite & Development
+ 5W: Development
+ 6W: User Acceptance Testing
+ 7W: Post UAT Refactor
+ 8W: Release

## Total Budget Requested

$20000 USD/FIL (~345 FIL as of 30/06/2021)

These funds will be dedicated to the associative labor required to construct the WFIL/FIL link.

## Maintenance and Upgrade Plans

We plan to continue to support and maintain the core functionality of the bridge for at least the next 2 years (24 months), as long as it is technically possible alongside the respective states of each network, and in accordance/adherence to with laws/regulations in the respective regions where the bridge is available.

# Team

## Team Members

+ Will Binns
+ Erwan Ounn

## Team Member Profiles

+ [Will Binns](https://github.com/wbnns)
+ [Erwan Ounn](https://github.com/aaronwinter)

## Team Website

+ [Wrapped.com](https://wrapped.com/)

## Relevant Experience

Both Erwan and I work on Wrapped.com at Tokensoft. Tokensoft is an industry leading provider of services for issuance of security tokens allowing for precise regulatory compliance during all stages of fundraising. Tokensoft also manages the smart contract security of the minting, burning and distribution of the wrapped tokens. Anchorage is a Qualified Custodian which secures over 100 billion in transactions annually through cutting edge cyber security architecture.

## Team code repositories

+ [WFIL Token](https://www.github.com/tokensoft/tokensoft_token)

# Additional Information

+ [WFIL on Etherscan](https://etherscan.io/token/0x6e1A19F235bE7ED8E3369eF73b196C07257494DE)
+ [Smart Contract Audit](https://certificate.quantstamp.com/full/token-soft-token)