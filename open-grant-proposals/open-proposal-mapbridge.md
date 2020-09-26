# Open Grant Proposal: `MAP Bridge`

**MAP bridge:**

**Proposal Category:** `technical-design`

**Proposer:** `zcheng9

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** YES

# Project Description

This project deliver a bridge to connect filecoin and other PoW（POS） chains（here we specific Ethereum）. For most current bridge solutions, it needs a relayer group to provide service for SPV verification. Our Map Bridge can provide a functionality that reading cross-chain information can be achieved without a relayer group. The reason for the existence of relayer group is SPV need the relayer group holding all block headers of the blockchain and provide it to any verifier who need such information. Map Bridge can provide a non-interactive, succinct proof which grows sub-linearly as chain grows. We hope that MAP bridge could help filecoin and other blockchains form a borderless, open ecosystem composed of heterogeneous interoperable blockchains. 

MAP-Bridge could achieve this through the following technology:

+ MAP-Bridge would implement a new data structure called MMR(merkle mountain range) which contain the information of  all confirmed block headers. And the root of MMR would be include in the header of  new mined block.

+ Map-Bridge would use ULVP(ultra-light verification protocol) to acquire non-interactive proof of POW verification of the bridged chain. ULVP is a flyclient-type verification module to verify the validity of tail block of a certain blockchain carry heaviest proof of work.  The size of proof  grows sub-linearly as the length of the bridged chain. 

+ Once the header of tail block in a certain blockchain can be confirmed, any block header in this blockchain can be determined through the MMR branch proof,  with the fact that the header of tail block contain the root of MMR including all headers.

+ Furthermore if any block header can be determined, any transaction or inner state of certain account could be verified through merkle branch proof similar to SPV(simplified payment verification).

+ Once the cross-chain data reading is complete, MAP Feeder could make sure the following cross-chain event would be triggered and thus achieve chain interoperability.



## Value

If MAP-bridge could be construct successful, the filecoin ecosystem could interoperate with Ethereum blockchain system. Through this, user of Ethereum could take advantage of the IPFS storage in their smart contract. Also user of filecoin could change their filecoin directly to Ethereum without centralized exchanges.

## Deliverables

We wil deliver a MAP-Bridge system which can enbale the chain interopration between filecoin and Ethereum. MAP-Bridge would include two modules, ULVP(ultra-light verification protocol) and MAP Feeder.  In order to accomplish this, we need to implement MMR structure and MAP-P2P network first.  Thus we will deliver the following modules:
+ MMR Trie structure:  MMR would include the  information of all history blockheaders. And we will intergrate it into the new generated block header.
+ ULVP: ULVP could provide a succinct proof of any state or transaction inclusion proofs of other blockchain system.
+ MAP-P2P network: MAP-P2P network is build upon libp2p which could enable the peer in filecoin discover the peer in other blockchain system and can transmitting stream.
+ MAP Feeder:  MAP Feeder would make sure the following cross-chain events would be emit once the trigger condition is met.
+ MAP-Bridge：Intergrate all the above modules and form a complete bridge which could connect filecoin and Ethereum.
+ Demo: We will complete a demo which demostrate that this bridge is good to use.
+ Documentation: We will finish the documentation and tutorial for MAP-Bridge.

## Development Roadmap

### Milestone 1 Implement MMR Module and ULVP(ultra-light verification protocol) 

| Number | Deliverable                          | Time Period                                                |
| ------ | ------------------------------------ | ------------------------------------------------------------ |
| 1.     | Implement MMR Trie Structure  | 1 week           |
| 2.     | Integrate MMR into blockheader and complete chain header storage     | 1 week |
| 3.     | Implement ULVP based on MMR                 |  2 weeks  |


### Milestone 2  Implement MAP feeder and MAP-P2P

| Number | Deliverable         | Time Period                                          |
| ------ | ------------------- | ----------------------------------------------------- |
| 1.     | Implement MAP feeder | 2 weeks         |
| 2.     | Implement MAP-P2P based on libp2p     | 2 weeks         |


### Milestone 3 Intergrate ULVP and MAP feeder and complete MAP-bridge.

| Number | Deliverable                       | Time Period                                                |
| ------ | --------------------------------- | ------------------------------------------------------------ |
| 1.     |Intergrate ULVP and MAP feeder into MAP-bridge | 2 weeks |
| 2.     | Provide a demo show how MAP-bridge connect filecoin and other POW blockchain.             | 1 week |
| 3.     | Make document about the map-bridge                  | 1 week |


## Total Budget Requested

Budgets Summary 
| Step | Total                       | item   |detail|
| ------------ |---------------| --------------------|-----|
| milestone1   | 15500  |  salary($) / cloud service($)  |   $15000 / $500  |
| milestone2   | 16000  |  salary($) / cloud service($)  |   $15000 / $1000 |
| milestone3   | 16000  |  salary($) / cloud service($)  |   $15000 / $1000 |

## Maintenance and Upgrade Plans

We plan to develop a protocol called MAP protocol.  MAP protocol is an open and completely decentralized chain-to-chain interoperation protocol that enables the interoperability of multiple independently verifiable consensus blockchains. We want to continue to introduce more blockchain system to support MAP protocol, so that all blockchains who support MAP protcol can interoperate directly without proxy. And we hope MAP protocol could be standardized as a formal chain-to-chain interoperation protocol.

# Team

## Team Members

- Dr. Chan
- Dr. Seabook
- LYU.L 

## Team Website

https://www.maplabs.io/

## Relevant Experience

* Dr. Chan received the Ph.D. degree in applied mathematics from Illinois Institute of Technology, Illinois, USA in 2017. His research interests include consensus algorithms, P2P protocol, cryptography, blockchain interoperbility. 
* Dr. Seabook is based in Australia and get his Blockchain PhD. from Australian Deakin University. He has more than 15 years of professional software design, architecture and development experiences. He has worked as Chief Technology Officer and Senior Architect in Telstra, Accenture, Qantas, eBay and Citibank. 
* LYU.L holds a master degree from Tsinghua University and also a member of China national blockchain and distributed ledger committee. He has more than 13 years of experience in large-scale computing and algorithm, with many patents such as consensus algorithm and blockchain transaction.

## Team code repositories

https://github.com/marcopoloprotocol

