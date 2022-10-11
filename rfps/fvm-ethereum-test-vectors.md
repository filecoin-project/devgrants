# RFP: Tool for applying test vectors from Ethereum on FEVM

## Project Description

FVM 2.1 which introduces support for Ethereum smart contracts in the Filecoin network (FEVM) will be the biggest network upgrade since mainnet launch. At the same time, it immensely widens the area of possible problems. That’s why it must be tested thoroughly.
One of possibilities to test FEVM is to run already existing and proven smart contracts from Ethereum and compare the state it produces on Ethereum vs Filecoin.

We are seeking proposals from teams that can build such a testing tool. This tool is expected to be in the form of a CLI.
It should be able to:

1. Fetch and store on the order of hundreds of contracts from Ethereum mainnet. These should be widely used contracts covering various use-cases. 
2. Deploy these contracts to a Filecoin testnet (Butterflynet).
3. Fetch thousands of transactions sent to these contracts on Ethereum in the past. 
4. Replay these transactions to contracts deployed on Filecoin. 
5. Compare the Ethereum state before and after these transactions with the results on Filecoin. We expect the team to research the ideas of how to do state comparison reliably.

We want to run this tool a few times if needed and fix encountered errors every time.
This tool can be written in either Go or Rust.

## List of deliverables

We expect the team to provide a Github repository containing
* Source code of the tool
* Guides on how to use it
* Fetched smart contracts and transactions so the same data doesn’t have to be re-fetched multiple times

We also expect a demo of running all steps against the Wallaby (TBD) testnet to prove it works.

## Timeline

We expect this work to be done until the 7th of November. We would like to be able to use this tool after we deploy FVM M2.1 to Butterflynet, which is scheduled for the 14th of November 2022.

## Milestones & Funding

<table>
  <tr>
   <td><strong>Milestone No.</strong>
   </td>
   <td><strong>Milestone Description</strong>
   </td>
   <td><strong>Funding</strong>
   </td>
   <td><strong>Estimated Timeframe</strong>
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>Implementation of a tool which fetches hundreds of contracts from Ethereum, stores them and and deploys them to Filecoin testnet
   </td>
   <td>TBD
   </td>
   <td>5 days
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td>Implementation of a tool which fetches thousands of transactions from Ethereum, stores them and replays them on Filecoin testnet
   </td>
   <td>TBD
   </td>
   <td>5 days
   </td>
  </tr>
  <tr>
   <td>3
   </td>
   <td>Implementation of a tool which compares the Ethereum state before and after these transactions with the results on Filecoin
   </td>
   <td>TBD
   </td>
   <td>8 days
   </td>
  </tr>
  <tr>
   <td>4
   </td>
   <td>How-to guides are prepared and demo is presented
   </td>
   <td>TBD
   </td>
   <td>2 days
   </td>
  </tr>
</table>

## Recommended Team

Please provide links to your team members' Githubs or LinkedIn profiles.

* A team with strong Ethereum development skills
* Experience extracting metadata from a blockchain or a complex tech back-end
* Solid knowledge of Filecoin chain data structures

## How to apply

To submit a grant proposal, please open a <a href="https://github.com/filecoin-project/devgrants/issues/new?assignees=realChainLife&labels=RFP&template=rfp-application.md&title=RFP+Application">new RFP issue</a> in the `filecoin-project/devgrants` repo.
For questions or to submit a private proposal you can also email maciej [dot] witowski [at] protocol.ai.

You can also contact us via [Filecoin Slack](https://filecoin.io/slack) via the [#fvm channel](https://filecoinproject.slack.com/archives/C029MT4PQB1) or DM @maciej.
