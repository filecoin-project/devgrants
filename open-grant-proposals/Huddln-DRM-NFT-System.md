
# Open Grant Proposal: `Huddln DRM+NFT System`
**Name of Project:** `Huddln DRM+NFT System`
**Proposal Category:** , `devtools-libraries`
**Proposer:**  `JoeGonzalez0886`
**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** YES

# Project Description

**Problem:** Currently when creating NFTs anyone can find the content on IPFS or web and download your content & distribute freely. There is no current standard to protecting creators' content.

**Solution:** To solve this issue we need to implement a DRM system from cradle to grave.

A key management system can be created on chain that handles the verification of user access control lists [ACL]. This on chain component is managed by the creator(s) of the content. This registry of **ACLs** is public and verifiable. A key generation/encryption server can be independently ran by **Content Protectors** in a distributed fashion. This "generation/encryption" layer needs to have a consensys mechanism and sufficiently difficult obfuscation techniques in order to create a **vm-blackbox**. The third piece to the puzzle is to provide a runtime to render the content on the client end, a new runtime will need to be created to provide decryption of content in browser. Content storage will follow a torrent like technique to distribute chunks across the storage layer, the maps for this content are potentially stored also in the same storage layer. A new standard NFT ERC may be proposed that extends extends logic for interfacing with **ACLs** & **Distributed Maps**.

**Food For thought:** Reputation systems can also be integrated in the ACL management to discourage attack vectors. Cost to benefit ratio may not be worth an attackers time.

## Value
 
The value is extremely high, we currently have no way to protect our content that's on IPFS/FIL. Currently creators must create keys and encrypt on their end before uploading data. Anyone can hop over to openSea, steal content and reupload as their own and profit from it and as NFTs are becoming more popular this issue will only grow.

If we do not get this right, then the creators' markets will see a decline of original content. Markets will be flooded with stolen content, and creators will be forced to provide content knowing there is nothing there to protect it. This system will be difficult to implement and will require a larger team than just myself. Some risks include -> key management, permission exploits. This project is difficult because of all the attack vectors, we are crossing into multiple domains to create this solution. The solution will need multiple types of auditing to calculate risk, currently the design includes the following main components -> **On-Chain Manager,Off-Chain key provider system, New NFT standard, Client Runtime**.

## Deliverables

 
1.  **On-Chain Key Manager:** Creates ACLs for NFTs. Provides verification of users, interacts with off-chain key provider system.

2.  **Key Provider System:** A distributed obfuscated output runtime system. May need to include zero knowledge & consensus mechanism.

3.  **NFT ERC:** A new NFT ERC proposal that includes any needed interfacing with the rest of the infrastructure.

4.  **Client Runtime:** A runtime that can facilitate the decryption/downloading(Maps) of content. Includes different levels of Viewability dependent on ACLs.

 
All of these components will be wrapped into the Protocol.

 
## Development Roadmap

  
### Milestones

**Note:** Prices are based on majority USA workers rates.

**Phase 1 Construction/Deconstruction POC**

Time Estimate: 4 - months

1.  **Create Encryption/Deconstruction Process:**

Funding: ~20k

Description:

Create the process that will upload content to IPFS/FIL. This process will include deconstructing binary data and creating maps for the reconstruction. All chunks are encrypted with a random keypair.

Input: Media

Output: Set of keys, maps, and chunks all distributed on IPFS.

Expectation: Inputting a file into the process will result in a file distributed across IPFS, and will return back a set of keys and maps.


2.  **Reconstruction Process:**

Funding: ~10k

Description:

Reconstruction of the media based on the provided keys and maps. This process may be created as a nodejs/js process, and is only meant to prove that uploading/downloading of the file set is possible.

Input: Keys,Maps

Output: The original media file.

Notes: What if we can't retrieve all items ? - What do we do ? Should multiple copies of chunks be pushed ?

Expectation: Providing the maps & keys yields the original media.

**Phase 1 Complete Expection**

Phase 1 should provide a baseline protocol for distributing and reconstructing the initial data. This can be thought of as a separate "Sharding Or Distribution Protocol" that could be used similarly to Bittorrent and may even be largely forked from this protocol. The completion of Phase 1 will lay the groundwork for other projects to utilize as well.

**Phase 2 KeyMangement**

Time Estimate: 6 - months

1.  **Create Management Contracts:**

Funding: ~15k (Without audits, W/audits- +60k)

Description: The on-chain service should be able to provide creators with licensing services on the fly and available at any time. This service should be deployed to a L2 that provides gasless TX for a better UX. The service should be able to determine what NFTs belong to whom and provide those creators with key creation/deletion and migration services. Users should also be able to grant levels of permissions to other users. These ACLS should include a "dirtyView" permission for the client end to decrypt the data but also add a layer of video/image processing in order to decrease bitrate/distort/ and reduce content fidelity. These sets of contracts will also a need a registry to keep track of what its managing and an upgradable storage design to keep it stateful. This may or may not result in an additional NFT ERC proposal.

Input: Functions available -> (ask for map, ask for keys, set ACL for users) from a web3 provider.

Output: Contract should hold ACLS, and be able communicate with off-chain

**Keyprovider** network to create/push/store keys.

Notes: The contract cannot encrypt/decrypt/send keys, all these these services must be done off-chain. For example if we ask the service to retrieve a private key it should trigger an off-chain event for the key-provider network to push a key to you that's wrapped in your own encrypted envelope.

Expectation: This service should be able to accurately determine who is allowed to access certain functions. Events may be used to trigger off-chain processes.

2.  **Key Provider system:**

Funding: ~12k

Description: It needs a mechanism for consensus of storage artifacts. Storage architecture needs to have a fast easy way to determine that keys are stored on multiple systems to thwart unavailability. The runtime needs to private keys in a distributed fashion as well (key splitting/multiple envelopes/multisig). No single private key should be stored on a node, instead pieces of keys should be generated on multiple nodes and decrypted and reconstructed using "keymaps" on the client side.

Notes: The contract cannot encrypt/decrypt/send keys, all these these services must be done off-chain. For example if we ask the service to retrieve a private key it should trigger an off-chain event for the key-provider network to push a key to you that's over a secure connection (key is also encrypted with you public key over transport).

Expectation: This service communicates with the blockchain service over pub-sub type connection. The peers running as key providers should be able to prove to each other that they have chunks of keys without showing each other the keys(signing data).
Key providers send a set of keys to the client end.
  
**Phase 3 Runtime + Tie system up**

Time Estimate: 3 - months

Create the first version of a runtime environment

1.  **Decrypt/Construct Client Runtime:**

Create the first version of a runtime environment

Funding: ~10k

Description: A client side runtime environment, that strictly follows the protocol, to decrypt data. This runtime may not need to be a blackbox because it will not store any keys. Because of this fact it may be sufficient to write this in js.

The client will need a web3 provider to connect and decrypt the keyset provided by the service.

Expectation: This service communicates with the blockchain service over pub-sub type connection. The peers running as key providers should be able to prove to each other that they have chunks of keys without showing each other the keys(signing data).

Key providers send a set of keys to the client end.

Input: A wallet identity is used to connect to the client runtime.

Output: A fully decrypted file.That is now accessible and viewable in player.

Notes: Once a client has decrypted and pieced together their media, they have full access to it. They can do what they wish with it. For future updates if we can lock down the runtime into a blackbox (not js) it may be possible to bake in a key
to keep the media only viewable by the runtime player, to prevent copying. Not sure if there is a way to do this though, creating a blackbox on the client end seems like it's not possible.

2.  **Tie up**

Description: Final protocol and system tie up. Testing and verifying security with audits.

Funding: ~10k

## Total Budget Requested

$ 117,000 USD

  
## Maintenance and Upgrade Plans

Seek funding through token economics for key provider system. Possible governance of the protocol to stimulate participation. Use those funds to expand team and maintain the protocol as an open source project.

# Team

## Team Members

Joseph Gonzalez

**Seeking interested teammates**

## Team Member LinkedIn Profiles

- Joseph Gonzalez https://www.linkedin.com/in/jge-2a7937115/

## Team Website

https://huddln.io

## Relevant Experience

Joseph Gonzalez - Degree in Computer Engineering, experience in solidity, developed the Huddln Protocol + Mobile Dapp. Has expereince delivering multistack solutions in web3 and developing protocols.

## Team code repositories
https://github.com/Huddln/contracts
