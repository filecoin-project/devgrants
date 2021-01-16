# Open Grant Proposal: Filecoin Loans (filecoin.loans)

**Name of Project:** Non-custodial Filecoin Loans

**Proposal Category:** `app-dev`

**Proposer:** @blitslabs

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Filecoin’s current circulating supply is currently around 2% of the Max supply so liquidity is limited. Furthermore, this is exacerbated because FIL miners require tokens as collateral in order to complete “deals” to provide storage for users [1]. Likewise, many token holders do not have mechanisms to trade the time-value of their holdings. As a consequence, Centralized Lending solutions have emerged to provide liquidity to the market, however, these lending services are centralized entities that can seize or steal funds and are not easily accessible to everyone.

As a solution to this problem we propose a decentralized, non-custodial and trustless protocol to allow users to create overcollateralized debt instruments across Filecoin and Ethereum. Thus, users will be able to borrow and lend FIL using Ethereum tokens as collateral.

To develop this cross-chain protocol we are going to make use of Hashed Time Locked Contracts (HTLCs) and extend the concept of “Atomic Swaps” to enable debt and repayment between parties by strategically revealing secrets to represent actions in the loan process [2]. This system is going to use the `TimeLockMin`, `TimeLockMax`, and `SecretPreimage` parameters in Filecoin’s Payment Channel functionality to make Payment Channels work as HTLCs.

## Value

Creating cross-chain interoperability between Filecoin and Ethereum will allow market participants to access liquidity between blockchains by enabling loans to occur between different blockchains without intermediaries.

Some of the benefits to the Filecoin ecosystem are:
- Enabling stablecoin/ERC20 tokens access to Filecoin holders.
- Allowing FIL holders to exchange the time value of their tokens without selling.
- Allowing users to Lend and Borrow tokens without intermediaries or giving up custody of their assets.

Some of the risks to the ecosystem if this system is not implemented correctly:
- FIL market volatility due to lack of liquidity.
- Centralized FIL lending services can be hacked or steal the funds of their users.
- Lack of FIL interoperability with other blockchains.

Risks that could make executing this project difficult:
- Libraries in early development stages.
- Filecoin specifications / functionality still not implemented.
- Lack of library support for web/mobile environments.


## Deliverables

#### 1) filecoin.loans (web)
Web-based dApp that allows FIL holders to lend tokens to borrowers using Ethereum-based tokens as collateral, as well as lending Ethereum-based tokens to borrowers using FIL as collateral.

#### 2) Mobile Implementation
Mobile implementation of the Filecoin Loans protocol in the Blits mobile wallet.

#### 3) Solidity Smart Contracts & FIL Payment Channels Implementation
Ethereum Smart Contracts (solidity) and Filecoin Payment Channels implementations required to create loans across blockchains.

#### 4) UI/UX designs and Protocol Documentation
The UI/UX design files (Figma) and protocol documentation to enable other developers to implement the system in their respective applications.




## Development Roadmap

#### Milestone #1
- Time: 2 weeks 
- Objective: UI/UX Planning & Implementation
- Technologies: Photoshop, Figma, React Native, ReactJS, Javascript, HTML, CSS.
- Team: 4
   - UI/UX Designer
   - 2x Fullstack Developer
   - Mobile Developer
-  Funding: $5,000
- Deliverables: 
   - UI/UX Web & Mobile
   - Web dApp Frontend Implementation
   - Mobile App Frontend Implementation

#### Milestone #2
- Time: 2 weeks
- Objective: Lend FIL using ERC20 tokens as collateral
- Technologies: Filecoin Javascript libraries, Solidity, Web3, ReactJS, Redux.
- Team: 4
  - 2x Blockchain Developer
  - 2x Fullstack Developer
- Funding: $10,000
- Deliverables:
  - Loan creation process using Filecoin Payment Channels (HTLCs).
  - Solidity Collateral Smart Contract.
  - Web Implementation of the Lend FIL process.
  - Web Implementation of the Lock Collateral ERC20 process.

#### Milestone #3
- Time: 2 weeks
- Objective: Borrow ERC20 tokens using FIL as collateral.
- Technologies: Filecoin Javascript Libraries, Solidity, Web3, ReactJS, Redux.
- Team: 4
  - 2x Blockchain Developer
  - 2x Fullstack Developer 
- Funding: $10,000
- Deliverables:
  - Loan creation process using ERC20 tokens.
  - Solidity Loans Smart Contracts.
  - Web Implementation of the Lend ERC20 tokens process.
  - Web Implementation of the Lock FIL as collateral process.

#### Milestone #4
- Time: 2 weeks
- Objective: Filecoin Mobile Implementation in Blits Wallet
- Technologies: React Native, Redux.
- Team: 3
  - Mobile Developer
  - 2x Blockchain Developer
- Funding: $5,000
- Deliverables:
  - Implement Filecoin in Blits Wallet
    - Send FIL
    - Receive FIL
    - Fetch Balance
    - Fetch Tx Details  

#### Milestone #5
- Time: 1 week
- Objective: Filecoin Loans protocol mobile implementation in Blits Wallet
- Team: 3
- Funding: $10,000
- Deliverables:
   - Implement FIL -> ERC20 Lending process
   - Implement ERC20 -> Lending process
   

#### Milestone #6
- Time: 1 week
- Objective: Audit, Marketing & Documentation
- Team: 3
- Funding: $10,000
- Deliverables:   
   - In-depth documentation of the protocol.
   - External Source code audit.
   - Marketing and giveaway campaign.
   - 100 Loans Created


## Total Budget Requested

Total: $50,000 
- Salaries & Development Costs: $40,000
- Marketing & Giveaway campaigns: $2,000
- External Audit: $8,000

## Maintenance and Upgrade Plans

Our long-term plans to maintain this software and upgrade it over time include:
- Maintain & update the Web dApp to implement newer Filecoin browser-based wallets.
- Migrate Filecoin Loans protocol from using Payment Channels to the native virtual machine smart contracts once it is released.
- Create interoperability with other EVM based blockchains.


# Team

## Team Members
- Kenia Chávez - CEO - https://www.linkedin.com/in/kenia-ch%C3%A1vez-45142a1a1?originalSubdomain=mx 
- Jennifer Suárez - Marketing & Design - https://www.linkedin.com/in/jennifer-suarez-/
- Rolando Andrade - Blockchain Developer - https://www.linkedin.com/in/rolando-andrade 
- Jesús Castro - Blockchain Developer - https://www.linkedin.com/in/jcstr/ 
- Gustavo Sánchez - Fullstack Developer - https://www.linkedin.com/in/gustavo-sanchez-b943a712b/ 
- Roberto Cervantes - Block Architect

## Team Website

- https://blits.net - Company Website
- https://crosschain.loans - EVM-EVM Cross-chain Loans MVP
- https://filecoin.loans - Filecoin Loans Domain

## Relevant Experience

We developed a DeFi Mobile Wallet with +350 installs across platforms:
- Android: https://play.google.com/store/apps/details?id=com.blits.wallet
- iOS: https://apps.apple.com/app/blits-wallet/id1533509547

We were selected by Harmony Protocol as a grantee to develop a DeFi Wallet & EVM-EVM Cross-chain Loans:
- https://medium.com/harmony-one/blits-defi-super-app-and-cross-chain-loans-1f6aea8ce72f
- https://www.youtube.com/watch?v=9pNyb_IWAso&t=165s 
- https://crosschain.loans/ (Testnet dApp)

## Team code repositories

- https://github.com/blitslabs/blits_wallet
- https://github.com/blitslabs/crosschain.loans-contracts
- https://github.com/blitslabs/crosschain.loans-frontend


# Additional Information
## References
- [1] https://www.coindesk.com/desperation-among-filecoin-miners-creating-a-big-market-for-fil-borrowing
- [2] https://arxiv.org/pdf/1901.05117.pdf <br/>
