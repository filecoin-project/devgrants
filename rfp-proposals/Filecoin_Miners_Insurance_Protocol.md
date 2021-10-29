# NEAR x Filecoin RFP: Filecoin Miners Insurance Protocol

**Name of Project:** Filecoin Miners Insurance protocol

**Link to RFP:** [NEAR x Filecoin](https://github.com/filecoin-project/devgrants/blob/master/rfps/near-and-filecoin.md)

**Proposal Category:** New Web3 Applications

**Proposer:**  [lendmi.finance](https://lendmi.finance)          mail: contact@lendmi.finance

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:**

 Yes

# Project Description

At present, Filecoin miners may suffer huge penalties on the network due to irresistible factors causing "sector termination". The purpose of Filecoin miner insurance is to allow the low probability, high loss and unavoidable event risk of "sector termination". Hedging to reduce the impact of random events on miners and make miners’ income more stable. In the long run, a market that can hedge risks is a mature market.

We will manage insurance through a risk-sharing fund pool model. The fund pool is composed of an insurance fund pool and an underwriting fund pool. The insurance money purchased for insurance will enter the insurance fund pool, and the underwriting fund for gambling wealth management will enter the underwriting fund pool. This pool of funds jointly assumes the risks and responsibilities of claim settlement. Of course, when no compensation occurs, both fund pools will receive the benefits of the insurance deposit.

The core of the entire insurance model is the calculation of the risk cost. In our design, the risk cost depends on the willingness to underwrite in the market, the willingness to buy insurance, and the system's MCR% (current fund pool funds/minimum funds required to redeem the policy) If the market underwriting willingness is high, it means that the probability of compensation is low and the risk is low. On the contrary, the risk is high and the insurance premium is high. If the MCR% of the fund pool is low, it means that the fund pool is unhealthy or the willingness to buy insurance is high. At this time, the system is under heavy redemption pressure, and the insurance premium will be appropriately increased.

Different from other decentralized insurance, the entire process of buying insurance and claim settlement takes place on the chain without human participation in decision-making. When the Filecoin network punishes, the payment process will take effect, and miners only need to withdraw the payment in time. That is, the amount of compensation is determined by the policy agreement and the health of the entire fund pool by the algorithm.

There is no possibility of bad mining work. The amount of insurance compensation is at most equal to the amount of network penalties, and the miners have to pay the cost of insurance premiums.

## Value

What are the benefits to getting this right?

- Miner insurance can make the income model of Filecoin miners healthier, attract more wait-and-see funds to participate in the Filecoin network, and expand the scale of the network.
- For existing miners, miner insurance can diversify risks, resist the impact of the black swan event on miners, and maintain the stability of the network.
- For investors, insurance is also a financial option that allows investors to participate and further diversify the risks and profits of the entire network.

What are the risks if you don't get it right?

- Regarding the doubts about miners maliciously damaging disks to cheat insurance, since the amount of compensation received by miners is definitely less than the network penalty + the cost of buying insurance, such cheating will not occur.
- Because of the accumulation of funds, there is a risk of smart contracts being stolen. Of course, all projects have this risk.

What are the risks that will make executing on this project difficult?

- Determination of risk cost. Reasonable risk cost estimation can enable the insurance pool to operate stably, but since there is no reference to historical data, in the initial stage, there may be cases where the risk cost is too high and the premium is too high or the risk cost is too low and the amount of compensation is reduced.
- Flow and funding during the cold start phase. In the absence of incentive behavior, the accumulation of the fund pool should take some time.

## Deliverables

**Near Insurance Smart Contract**

The smart contract will contain the following functions:

- Insurance gold pool and underwriting gold pool
- Calculation of risk cost
- Calculation of MCR and MCR%
- Purchase of insurance and creation and destruction of insurance policies
- Management of compensation and compensation process
- Circulation of insurance money and bonus
- Management of underwriting funds and calculation and distribution of income

**Off-chain observer**

When a payment should take effect, anyone can start the payment process, similar to the Keeper in Compound. Although this part of the code runs off-chain, the code is open source and can be verified by everyone.

The Payout Observer mainly includes the following functions:

- Comparing the penalties of the insurance policy and the network, when it is found that the penalties include the sectors in the policy, start the on-chain compensation and get the compensation

**Dapp front-end UI**

This is a complete Dapp, so it needs an easy-to-use UI. It mainly contains the following pages:

- Project introduction page
- Insurance rules introduction page
- Purchase warranty page
- Claim payment page
- Underwriting page
- Receiving underwriting fund and income page
- Statistics page
- Document Center
- Team introduction page

## Development Roadmap

**near**

-  Insurance smart contract design and development
  - On the premise of ensuring the security of product funds, try to decentralize as much as possible. For example, when users apply for compensation, mechanisms such as the lock-up period for compensation applications and challenges for compensation applications are introduced. We are looking for a decentralized compensation mechanism, but this ultimately requires filecoin's fvm.
  - To ensure the security of the insurer's funds, the insurer's access to funds lies with him, but for product stability, there may be mechanisms such as withdrawal lock-up periods.
-  Contract testing and audit
-  Contract call SDK development
-  Testnet deployment simulation test
-  Documentation

Period: 6 weeks from November 15 to December 30

Role: Smart contract developer

Budget: 2 people 5000 USD

**filecoin**

-  Chain data analysis service
  - Sector penalty and penalty information collection and analysis caused by sector termination
-  Off-chain payment observers
  - Construct a payment process based on the data provided by the chain data analysis service

- Unit test

-  Documentation

 Period: 6 weeks from December to January 15

 Role: filecoin developer

 Budget: 2 people 5000 USD

 **Product design and front-end**

-  Design and develop an easy-to-use interface
-  Connect to the smart contract and start using it

 Period: 5 weeks, December 1-January 7

 Role: product manager, front-end developer

 Budget: 2 people 4000 USD

 **Testnet test and release Alpha version**

-  -Perform functional and security tests on the developed smart contracts
-  -Release Alpha version

 Period: 4 weeks, January 15-February 15

 Role: Filecoin developer, contract developer, UI developer, Testers

 Budget: 4 people 6000 USD

## Total Budget Requested

Total = 20000 USD

Expected to take 3 months

## Maintenance and Upgrade Plans

Long-term operation. After the Alpha version is launched, the Beta and official versions will be launched based on market feedback.

At the same time, financing opportunities will be sought.

# Team

**Team Members**

- DongDong Su | Development Manager (worked previously in LendMi)
- Life Zou | Smart Contract Developer (worked previously in LendMi)
- Xuesong Zhang | Smart Contract Developer (worked previously in LendMi)
- DongDong Hou | Front-end Developer (worked previously in LendMi)
- Pete Zhang | Product Manager (worked previously in LendMi)
- Aeolus Chai | Product Manager (worked previously in LendMi)

## Team Website

https://lendmi.finance

## Relevant Experience

LendMi is a IPFS Ecology Revenue Protocol.It has a variety of products including VFIL lending mining funds.LendMi opens up mining and coin circles through DEFI to generate higher coin-based returns for investors.

LendMi collects FIL in the form of central lending, lends FIL to large nodes (large mining pools) for mining, and rewards for output are then distributed to investors. Because output is stable, investors can be guaranteed fixed income. On the other hand, in order to ensure the validity of the node pledge assets, the community elects large nodes (high value) and requires the node pledge node private key to ensure control of the node (control can be verified by the miner’s signature).

LendMi now supports HECO and BSC Main Chain Ecology, with deposit exceeded 900,000 coins and TVL once exceeded $150 million.