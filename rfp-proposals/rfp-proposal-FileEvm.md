# Open Grant Proposal: `FileCoin Evm`

**Name of Project:** FileCoin Evm

**Proposal Category:** `category:core-dev`

**Proposer:** [@jiyilanzhou](https://github.com/jiyilanzhou/)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Filecoin is a great design, but browsing the Lotus code reveals that there are no virtual machines in the engineering implementation, and the verification of transactions is called through the system contract, not a Turing complete system.

Currently, the DeFi on Ethereum is hot, and users holding Filecoin are not allowed to participate in DeFi. I would like to introduce an EVM virtual machine on the basis of Lotus, because there would be something on the market that would involve the ecology of Filecoin, which would involve a large number of programmers of using solidity. So we can both store and use things like UNiswap and YFI

If EVM can be successfully implemented in Filecoin, filecoin ecology can be enriched. It is well known that Filecoin is a big ecology, and one project is still too few. If EVM is migrated, such as a number of stabilization coins, UNiswap, YFI, Sushiswap and USDT, DEX and DeFi will be migrated. More and more people will use and study Filecoin, which will greatly promote the promotion of Filecoin.

The main implementation is to change the sector encapsulation verification and storage proof into EVM system contract, which can run solidy code or call the existing contract of filecoin. this is my update [vm update patch](https://github.com/truechain/truechain-engineering-code/commit/96ee22cfeb42f8afd29939276380d76fc29b8f8c).


## Deliverables

it needs to support sector encapsulation verification, space-time proof and normal call of corresponding system contract in spatial proof such as StoragePowerActor StorageMinerActor or PaymentChannelActor total 11 system contract, and support normal deployment of uniswap in local test network。So I need to do the following
* add eth rpc support transaction
* convert filecoin native transactions to ETH transactions
* fix evm state trie
* fix gas calculation
* add filecoin system contract
* support evm
* depoly uniswap
* support filecoin mine

we all have 2 or 3 years of public chain development experience and are able to implement this function on lotus.
## Development Roadmap

| No. | Milestone                                                                                              | Funding | Estimated Timeframe |
| --- | ------------------------------------------------------------------------------------------------------ | ------- | ------------------- |
| 1   | tidy 11 system contract. calculate gas used, according method convert abi method define, collate system contracts for EVM support                                    | \$12,000 | 2 week              |
| 2   | add evm opcode gas used evm rutime environment, fix account state triedb read write 						  | \$6,000 | 1 week              |
| 3   | fix StoragePowerActor,StorageMinerActor call to evm, can normal execute, add evm transaction test             | \$5,000 | 1 week              |
| 4   | modify file native transactions to eth transactions, add  transaction test                                    | \$4,000 | 1 weeks             |
| 5   | add eth rpc support transaction, add rpc method, support metamask  send transaction                           | \$5,000 | 1 week              |
| 6   | depoly uniswap, add liquidity  support  token swap                                                            | \$5,000 | 1 weeks             |
| 7   | test filecoin mine and add features test code                                                                 | \$5,000 | 1 week              |

The three public chain core developments will divide the work among the modules, There are mainly evm, system contract, filecoin Actor, transaction, rpc signer, miner.

## Total Budget Requested


Total: $42000

Although the logic is simple, the amount of code is large and requires a special knowledge of Ethereum to do the job.

## Maintenance and Upgrade Plans

If we can get support, my colleagues and I are willing to devote ourselves to the development and support the project all the time.

# Team
## Contact Info
Email: [jiyilanzhou@gmail.com](jiyilanzhou@gmail.com)
Email: [450595468@qq.com](450595468@qq.com)

## Team Members

- jiyilanzhou: [github](https://github.com/wbqlove)
- wbqlove: [github](https://github.com/wbqlove)
- shuxunyer [github](https://github.com/shuxunyer)

## Team Website

[https://www.truechain.pro/](https://www.truechain.pro/) --we are truechain core developer.

## Relevant Experience

In 2018, we implemented the hybrid consensus with golang, and used the pow + pbft dual chain blockchain system. POW mining provides a decentralized verifier, and selects the members of the pbft Committee through the election algorithm, and the pbft is responsible for executing the transaction, which improves the TPS. When the main network is launched in 2019, the pbft consensus of tendermint is used. In March 2020, the consensus will be changed to POW + dpos, and EVM system contract will be used to realize the election of verifier and award. At the beginning of this year, we started to design cross chain, wrote a benchmarkchain with rust, used rust libp2p, and used VRF and pure POS to implement verifier out of block, which has not been completed yet.

jiyilanzhou: Proficient in Ethereum devpp2p network, node discovery, encrypted connection rlpx, network protocol has a deep understanding.Understand the EVM execution logic, and have a deep understanding of EVM testing and debugging. Participate in the development of three blockchain projects.
This is [system contract](https://github.com/truechain/truechain-engineering-code/blob/master/core/vm/staking.go#L57) implement in evm.

## Team code repositories
* Public chain [truechain](https://github.com/truechain/truechain-engineering-code)
* An alliance chain project participated in [taiyuechain](https://github.com/taiyuechain/taiyuechain)
* A rust pos blockchain  [marcopolo](https://github.com/marcopoloprotocol/marcopolo)
* This is [depoly uniswap](https://github.com/D-CDC/go-uniswap)