# RFP Proposal: `Filecoin Devnet Scripts`

**Name of Project:** Filecoin Devnet Scripts 

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-4-rfps.md#devnet-scripts

**RFP Category:** `devtools-libraries`

**Proposer:** [@ArseniiPetrovich](https://github.com/ArseniiPetrovich)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

The motivation behind the proposal is to deliver a positive change to the experience of end users and developers engaged in the Filecoin network. 

The proposed solution will automate the process of deploying the shared Devnet used for faster development, testing and collaboration.
It will include basic Devnet features:
- Setting up a faucet
- Bootstrapper nodes and a genesis miner
- Smaller sector sizes 

The solution will be based on the Helm chart and/or Ansible.

This is a proposal for one of the high priority RFP ideas listed in New RFP Ideas for Wave 4, the [Devnet Scripts](https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-4-rfps.md#devnet-scripts)
> We are interested in proposals to automate this process so shared Devnets become easier to deploy. Via an open source Kubernetes script or Helm chart would be an ideal automation script.
>Basic Devnet features should include setting up a faucet, bootstrapper nodes and a genesis miner, smaller sector sizes to speed up developer workflows and testing, dedicated storage miners, some ideas on how to prevent Devnet attacks.
>The intent is to support developers who want to use shared devnets for faster development, testing and collaboration, similar to the various testnets available for live blockchain networks.
>

## Value for the community
- Support developers who want to use shared devnets for faster development, testing and collaboration.
- Speed up developer workflows and testing reducing the efforts for manual Devnet deployment.
## Deliverables

- Automation scripts for the network genesis with Helm.
- Ansible scripts to automate network deployment on a plain machine.
- Kubernetes cloud cluster deployment automation for AWS, GCP, and Azure.
- Open source repositories dual-licensed (under MIT and APACHE2) licenses for the Devnet Scripts.
- Documentation.

## Development Roadmap

### Milestone 1 - MVP
- Goals:
  - Create a minimum viable product
- Deliverables:
  - A Helm chart that will allow to deploy network nodes with different roles: faucet, miner, bootnode
  - Automatic health checks that restart failing nodes
  - Documentation describing the deployment process
- Outcomes:
  - User will be able to run its own network on Kubernetes, but it will require additional manual work to generate network a genesis file
- Duration: 1 week 3 days
- Team: Full-time DevOps
- Budget: $ 5,640

### Milestone 2 - Automation with Helm
- Goals:
  - Automate the network genesis
- Deliverables:
  - Scripts, init containers, readiness probes
- Outcomes:
  - Automatic network creation
  - Convenient README so any user familiar with Helm can deploy the Filecoin Devnet 
- Duration: 1 week 2 days
- Team: Full-time DevOps
- Budget: $4,930

### Milestone 3 - Ansible scripts
- Goals:
  - Automate network deployment on plain VMs
- Deliverables:
  - Ansible scripts 
- Outcomes:
  - Running blockchain on containers is not always a good choice, so as an outcome of this milestone user will be able to choose between Helm (containers) and Ansible (plain VMs) as a deployment options
- Duration: 2 weeks
- Team: Full-time DevOps
- Budget: $7,040

### Milestone 4 - Kubernetes cloud cluster deployment automation
- Goals:
  - Automate cluster deployment so end user can test the solution even when not having a Kubernetes cluster
- Deliverables: 
    - Terraform scripts for AWS
    - Terraform scripts for GCP
    - Terraform scripts for Azure
- Outcomes:
  - One of the known problems of modern public blockchain networks is that a lot of nodes are currently running on AWS. The idea here is to create examples for three major cloud services to ensure better distribution across the cloud providers. 
  - A Cluster comes with security mechanisms configured. That will ensure Helm charts are deployed in compliance with the best security practices.
- Duration: 3 weeks
- Team: Full-time DevOps
- Budget: $10,560

### Milestone 5 - Testing and CI enablement
- Goals:
  - Complete automated tests
  - Fix bugs
  - Publish the code repository
  - Finalize documentation
- Deliverables: 
  - Continuous integration tests
  - The code is added to the GitHub repository
  - Detailed `Readme.md` explaining how to automatically deploy the network
  - Instruction for end-users for both deployment options
- Outcomes:
  - All project deliverables are completed and added to the Github repository
  - A tested Devnet is running and available for testing from the side of Filecoin team
- Duration: 1 week
- Team: Full-time DevOps
- Budget: $3,520


### Assumptions

The Filecoin team will provide a point of contact for technical questions so our development doesn’t get blocked when we have technical issues or questions impacting on delivery dates and team allocation costs.

## Milestones & Funding

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | MVP | $5,640 | 1 week 3 days|
| 2 | Automation with Helm | $4,930 | 1 week 2 days|
| 3 | Ansible scripts (Optional) | $7,040 | 2 weeks|
| 4 | Kubernetes cloud cluster deployment automation (Optional) | $10,560 | 3 weeks|
| 5 | Testing and CI enablement | $3,520 | 1 week|


Total funding (Milestones 1,2,5): $17,090 (including 10% of total effort for communication)
Project duration: 4 weeks

Total funding (full scope): $31,690 (including 10% of total effort for communication)
Project duration: 9 weeks

## Maintenance and Upgrade Plans

Any updates needed to ensure the Devnet Scripts work for a latest implementation of Filecoin network should be performed at no additional cost unless Filecoin nodes or Filecoin Network have undergone significant changes since Altoros’s commencement of the project. In this case, Altoros will request additional funding should the changes implementation require more than 10 hours/month.


# Team

## Contact Info

arsenii.petrovich@altoros.com

## Team Members

| Role | Team member | Role Description |
|---|---|---|
| DevOps Engineer | Arsenii Petrovich [LinkedIn](https://www.linkedin.com/in/arsenii-petrovich/) | DevOps engineer is responsible for developing automation, deploying monitoring solutions, designing and implementing architectures and writing documentation  |


## Team Website

https://www.altoros.com

## Relevant Experience

Altoros is a mid-size software development provider, integrator and consultancy company around Digital transformation, Cloud solutions, Kubernetes and Blockchain. 
We have experienced DevOps teams both in the USA and Belarus that are delivering projects for start-ups and enterprises around classic DevOps (Cloud enablement and CI/CD pipelines implementations), Cloud Foundry and Open Source Blockchain projects (under the DBA Protofire) automating cloud operations for decentralized networks. 

Our goal is to invest in building expertise with Filecoin and become a long-term contributor and partner.


1. Altoros (under the DBA Protofire) has successfully completed the [Filecoin Cloud Images project](https://github.com/protofire/filecoin-cloud-images) 
2. Altoros (under the DBA Protofire) has won three Tezos grants and delivered the following projects: 
 - Automation of Tezos setup and management process for all popular clouds. 
 **Code repo:**  https://gitlab.com/protofire/tezos-automation-scripts
 - Implementations of common smart contracts found in popular decentralized finance (“DeFi”) applications (Phase 1 and 2).
**Code repo:** Phase 1: https://github.com/protofire/tezos-defi-dev-experience
**Code repo:** Phase 2 (in progress): https://github.com/protofire/tezos-defi-dapp

3. Our team helped POA Network to develop a set of tools, which includes the Token Wizard, Proof of Physical Address, Proof of Bank Account, Token Bridge and **[Block Explorer (Block Scout).](https://blockscout.com/poa/core)**
  **Code repos (BlockScout):**
  https://github.com/poanetwork/blockscout
  https://github.com/poanetwork/blockscout-terraform

  We also contributed to enabling a single-click deployment of the POA network. 
  **Code repos:**
  https://github.com/poanetwork/deployment-terraform
  https://github.com/poanetwork/deployment-playbooks

4. **CROSS-CHAIN BRIDGE**
POA Bridge, an interoperability protocol between Ethereum networks for native to ERC20 and ERC20 to ERC20 cross chain transfers. Using the POA Bridge, projects can deploy their own instances of the POA Bridge and facilitate the transfer of ERC20 tokens between POA Network and Ethereum. 
**Code repo:** https://github.com/poanetwork/tokenbridge

5. **[xDAI Chain](https://blockscout.com/poa/xdai/)** 
Altoros (under the DBA Protofire) participates as a validator for the xDAI network and for the bridge, besides being a core developer of a great part of the technology stack (Blockchain Explorer, Cross-chain bridge, Network automation scripts).


## Team code repositories

Arsenii Petrovich [GitHub](https://github.com/ArseniiPetrovich)
