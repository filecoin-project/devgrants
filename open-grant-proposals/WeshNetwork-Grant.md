**Project Name:** Wesh Network, an open source, wild & asynchronous mesh network protocol

**Proposal Category:** Research & Protocols

**Individual or Entity Name:** Berty Technologies 

**Proposer:** https://github.com/berty/weshnet/

**Filecoin ecosystem affiliations:** Berty Technologies has an agreement with Protocol Labs. 

This Agreement governs a grant as set forth in the Program (the “Grant”) for contributing
to those certain deliverables related to the open source project(s) and work plan(s).

**Technical Sponsor:** We already proposed this project to Protocol Labs.

**Do you agree to open source all work you do on behalf of this RFP under the MIT/Apache-2 dual-license?:** Yes

# Project Summary

Berty Technologies is an NGO Berty Technologies, dedicated to researching and developing our decentralized communication protocol, called Wesh Network. Wesh is a secure, distributed, and asynchronous communication protocol, with or without internet access, that utilizes direct transports such as Bluetooth. It ensures end-to-end encryption and perfect privacy for all exchanged messages. The Wesh Network protocol is designed to provide unparalleled resilience, interoperability, security, and modularity. We believe that people deserve access to free, robust, and reliable communication, regardless of the circumstances they find themselves in. Berty is building the Wesh Network to fulfil this mission and become the foundation of unstoppable communication for the next era of the internet.

We have successfully developed Wesh Network and the Berty Messenger application the first use case based on it.
Now in the context of our research and development lab, we will obviously improve the protocol's performance, but we will open up new use cases for the Wesh protocol. By leveraging our expertise and experience in the field, we can advance the Wesh protocol's capabilities and enable it to be used in various applications and industries. Our lab is committed to innovation and excellence, and we are excited to contribute to developing the Wesh protocol through our research and development efforts. 
The next step is developing a Wesh Companion using Filecoin to incentivize storing messages on ”Wesh companion” as replication server. 

The operator of the replication node can be rewarded with FIL.
Because storing files requires FIL, this can limit abuse.
Can also incentivize long-term archival storage (not currently done).
Currently, replications servers are only set up by group members. 

## Impact

Why this proposal is valuable for the Filecoin, IPFS, or related ecosystems.

- What pain points does this project seek to address?
    
    This project provides the industry with powerful tools to build communication applications without relying on centralized infrastructure.
    

- What are the benefits to getting this right? What are the risks of not getting this right?
A successful implementation of the Wesh protocol is equivalent to a low-cost infrastructure and is attractive for obvious reasons to the industry.
- What impact will this project have in a specific vertical, market, or ecosystem? What does success look like? --> 
A new Framework for developing extreme decentralized communication apps using Filecoin as storage. **Using Filecoin could enable a service industry for offering replication services.**

## Outcomes

What your final outcomes & deliverable(s) for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished.-->

**Outcome is software part of the Wesh replication node.**

- API for Wesh network that implements the decentralized extreme communication protocol.
- A mobile APP to serve as POC
- Console and extra Tools to facilitate the development process.
- A website to attract developers

## Adoption, Reach, and Growth Strategies

Who is the target audience for your project? How large is this audience, and how are you currently engaging with them?

Our goal is to empower Web3 developers to create peer-to-peer communications available on billions of devices. Wesh Network is intended to be a "toolbox" for developers, enabling them to create products based on decentralization. It was built by developers in a non-profit organization for developers to help build the next internet, completely free from constraints.

## Development Roadmap @

Please break up your development work into a clear set of 2-4 milestones. This section should be detailed (will vary by project, but aim for 1-2 pages for this section). -->

**Milestone 1 : Filecoin for linked assets in Wesh message**s

Currently Wesh stores all messages in a local database. This is OK for text messages. But we want to support videos or messages with large attached documents. It is not efficient to store these large objects in the Wesh message database, and mobile devices may not have the space. Managing large data assets is one of the features that Filecoin was designed to do.

In this milestone, we update the Wesh message format to support a CID for related data stored in Filecoin. We update the Wesh API and library to make it easy for Wesh application developers to retrieve data from the Filecoin network. This support includes cryptographic verification of the retrieved data (already made easy by the security design of Filecoin). In addition to storing related data, Filecoin can also be used to hold backups and archives of the entire message log.

Steps:

1. Study Filecoin protocol and the put/get API, write proof-of-concept code - 30 person-days
2. Technical design for weshnet to use Filecoin - 30 person-days
3. Implement using the CID in a message to retrieve from Filecoin - 60 person-days
4. Implement restoring messages from Filecoin backup - 30 person-days
5. Demonstrate this new weshnet feature: implement in Berty Messenger - 30 person-days

**Milestone 2 : Wesh companion group replication service with Filecoin**

Wesh works by letting members of a group communicate securely. The group members form a peer-to-peer network where all members don’t need to be online at the same time. A group member can come online and their device can communicate with another member’s device, over Bluetooth or local wifi or the Internet if available. When connected, the Wesh protocol securely brings their message store up to date for the group.

To rely on each member to store all the group messages is fully distributed and works. However, we would also like to offer a “decentralized” option where, in addition to syncing with other users when available, each member can sync with a dedicated service that replicates the messages in the group.

Therefore, in this milestone we develop an easy-to-install application called “Wesh companion” which typically runs on a computer at a fairly static address and which can be accessed by each member’s device. The Wesh companion application runs a “replication service” as described in the Wesh protocol white paper https://berty.tech/docs/protocol#replication-server . The replication service stores (”replicates”) group messages for members who may be off line so that there is a place to retrieve the messages when they come online. This has been designed and tested on a limited basis, but needs a robust system for long-term reliable storage.

This is where Filecoin comes in. We update the Wesh software to work with the Filecoin protocol to store and maintain group messages in Wesh companion. In this way, group members have a service to connect to in order to retrieve messages asynchronously (if other members are not reachable) and have reliable storage of the information in the group. In this case the FIL transaction fees circulate among local group members, but the transaction fees also provide a defense against DDoS and other potential abuse of the replication server.

Steps:

1. Study Filecoin node operator API, write proof-of-concept code - 40 person-days
2. Write Wesh companion base application w/ replication service - 80 person-days
3. Technical design for replication service to use Filecoin - 60 person-days
4. Integrate Filecoin node operations with Wesh companion - 80 person-days
5. Demonstrate using replication service: implement in Berty Messenger - 40 person-days

**Milestone 3 : Incentivized replication server network with Filecoin**

In Milestone 2, it is envisioned that the Wesh companion app is set up by the members of the group who want to share messages. It could be on a local area network behind a firewall or on the Internet at a non-advertized static IP address. But Filecoin is designed with an incentive structure in a trustless environment where the operator of the Filecoin node doesn’t need to be a member of the group which is storing the data.

Therefore, in this milestone we take Wesh companion to the next level so that a Filecoin provider can offer the replication service to Wesh users. The Wesh companion software is updated to work with the Filecoin software which is familiar to providers, and who earn FIL. This allows a Wesh application developer to have an established foundation for message storage including long-term archiving. And it’s another way to grow the Filecoin network.

Steps:

1. Technical design for Wesh companion mode targeted for public Filecoin operators. Easy install for just this purpose and monitoring utilities (utilization metrics of the replication node, how much FIL is earned due to Wesh Filecoin storage, etc.) - 20 person-days
2. Technical design for Wesh application support to use/pay for public replication node service. (May include FIL wallet integration with Wesh apps.) - 20 person-days
3. Implement and test the Wesh companion updates and Wesh application support. - 40 person-days
4. Outreach: Write announcement blog posts/tutorials. Get Filecoin to list Wesh companion in their docs for operators. - 10 person-days
5. Design and launch digital marketing campaign for growing the Wesh replication node network by on-boarding Filecoin operators to run Wesh companion, earn more FIL. - 40 person-days


For each milestone, please describe:

- The functionality that is expected after the completion of each milestone.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates) -->

**Total Budget Requested**

| Milestone # | Description | Deliverables | Completion Date | Funding |

**Milestone 1 : 180 person-days 

**Milestone 2 : 300 person-days

**Milestone 3 : 130 person-days 

Please see the detailed budget attached

[FILECOIN BUDGET - Feuille 1.pdf](https://github.com/filecoin-project/devgrants/files/11980860/FILECOIN.BUDGET.-.Feuille.1.pdf)

**Team Members**

Jeff - Project Lead

Natacha: Project Management / Marketing

Tech :

- Rémi: Lead transversal Tech
- Jeff: Lead Wesh
- Iuri: Lead front end

**Team Member LinkedIn Profiles**

Iuri Pereira  -->https://www.linkedin.com/in/iuri-pereira-cpm/
Remi Barbero -->https://www.linkedin.com/in/remi-barbero/

**Website**

https://berty.tech/

https://wesh.network/

**Relevant Experience**

The core team recognized as a pionneer in niche domains:

- P2P on mobile with hardcore runtime conditions.
- P2P & Privacy.
- P2P+Cryptography for non-technical users (with simple UX).
- True P2P using bluetooth and other proximity drivers, not depending on bootstrap nodes or the internet.
- Building new protocols to solve complex issues with simple SDKs
- The Berty Technologies team is regularly invited to talk about Wesh Network, Berty Messenger and showcase our innovative technologies.
- We also organize our own events and festival, such as the Paris P2P Festival.
- We now have the reputation of being a local gem for our expertise."

**Team code repositories**

Links to your team's prior code repos for similar or related projects. -->

- https://github.com/berty/berty


How did you learn about the Open Grants Program? --> It was Protocol Labs’s team who informed us about this grant.
Email address for discussing the grant agreement and general next steps. --> **natacha@berty.tech**
