# Open Grant Proposal: `Filecoin cloud images`

**Name of Project:** Filecoin cloud images

**Proposal Category:** `devtools-libraries`

**Proposer:** @ArseniiPetrovich

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description
As a result of our discussions with the Filecoin team we identified an issue with Filecoin node deployment. The Lotus node state sync is pretty slow, which means that it takes time (weeks) for regular users to spin up nodes. This dramatically decreases the speed of the software release cycle for the new developers who do not have their own nodes and decreases the protocol adoption.

We propose to create an automatic IaC (Infrastructure as Code) solution that will periodically update the AMI of top 3 cloud providers (AWS, Azure, GCP). The solution will be based on the proven solution Packer by Hashicorp.

## Value

The delivered tool will: 
- Automatically build and update images in selected cloud providers
- Allow users to use pre-built images with synchronized state. It will simplify the process of Filecoin node deployment and remove the need to wait for state to synchronize.

We anticipate the following risks that might affect the project complexity and duration:
- As we are relatively new to Filecoin protocol, some unexpected challenges may occur, but this risk is minimized due to simplicity of the project and our experience delivering similar solutions. We are also counting on the Filecoin team support if necessary.
- Init script might be more complex to set up than we currently assume, especially if the Filecoin node needs to be configured by the end user before launching.  


## Deliverables

- A GitHub repository that contains the continuous integration pipeline configuration that builds and verifies the integrity of Filecoin cloud images. These cloud images will be publicly available for any user who wants to install a Filecoin node on one of the supported clouds (AWS, Azure, GCP). 
- Images will be built using Packer (by Hashicorp) solution. It will contain a set of Packer configuration files and init scripts.
- Continuous Integration and images publishing process (to be discussed with Filecoin)


## Development Roadmap

### Milestone 1 - WRITE PACKER SCRIPTS
- Activities:
  - Write Packer scripts
  - Write documentation
- Deliverables:
  - Packer configurations for AWS
  - Packer configurations for Azure
  - Packer configurations for GCP
  - Documentation for Lotus official website
- Outcomes:
  - Users can easily install nodes to one of the supported clouds 
  - Users have the node with fully synced state immediately
  - Using this documentation Filecoin will be able to reach wider audience as users with a lower technical background will be able to install Lotus nodes easily
- Duration: 2 weeks, 2 days
- Team: 1 Full-time DevOps Engineer
- Budget: $7,040

### Milestone 2 - ENABLE CI
- Activities:
  - Enable CI/CD system for Packer
  - Write documentation
- Deliverables:
  - Images tests
  - CI pipelines for all clouds
  - Documentation for GitHub repo
- Outcomes:
  - Images automatically updated with each Lotus release
  - CI documentation will simplify maintenance process
- Duration: 2 weeks
- Team: 1 Full-time DevOps Engineer
- Budget: $6,400


## Total Budget Requested

| Milestone No. | Milestone Description | Budget | Estimated Timeframe |
| -------- | -------- | -------- | -------- |
| 1 | WRITE PACKER SCRIPTS | $ 7,040 | 2 weeks, 2 days |
| 2 | ENABLE CI | $6,400 | 2 weeks |

Project duration: 4-5 weeks
Total funding: $13,440


## Maintenance and Upgrade Plans

The software will be maintained at our expense for the first 16 weeks following grant acceptance. Thereafter, Filecoin agrees to be charged maintenance fees involving the following tasks:

  - Infrastructure as Code artefacts: maintain and upgrade the code to support each new major release of tools used under the hood, such as Packer and chosen CI server (eg.: CircleCI).
Budget: $ 4,800 (60 hours / year)

  - Continuous Integration and image publishing infrastructure: new images will be created and published depending on criteria to be defined and agreed with the Filecoin team (eg.: new major releases of components A, B and C, X time, etc. TBD).
Budget: $ 4,800 (60 hours / year)

**Total: $ 9,600 (120 hours/year)**

# Team

## Team Members

| Role | Team Member | Role Description |
| -------- | -------- | -------- |
| Project Manager | Cristian Malfesi [LinkedIn](https://www.linkedin.com/in/cristian-malfesi/) | Project Manager is responsible for overseeing the design & development teams. |
| DevOps Engineer | Arsenii Petrovich [LinkedIn](https://www.linkedin.com/in/arsenii-petrovich/) | DevOps engineer is responsible for developing automation, deploying monitoring solutions, designing and implementing architectures and writing documentation. |
| DevOps Engineer | Yauheni Kisialiou [LinkedIn](https://www.linkedin.com/in/eugene-kiselev-9b13a342/) | DevOps engineer is responsible for developing automation, deploying monitoring solutions, designing and implementing architectures and writing documentation. |


## Team Website

https://www.altoros.com

## Relevant Experience

Altoros is a mid-size software development provider, integrator and consultancy company around Digital transformation, Cloud solutions, Kubernetes and Blockchain. 
We have experienced DevOps teams both in the USA and Belarus that are delivering projects for start-ups and enterprises around classic DevOps (Cloud enablement and CI/CD pipelines implementations), Cloud Foundry and Open Source Blockchain projects (under the DBA Protofire) automating cloud operations for decentralized networks. 

Our goal is to invest in building expertise with Filecoin and become a long-term contributor and partner.

1. Altoros (under the DBA Protofire) has won three Tezos grants and delivered the following projects: 
 - Automation of Tezos setup and management process for all popular clouds. 
 **Code repo:**  https://gitlab.com/protofire/tezos-automation-scripts
 - Implementations of common smart contracts found in popular decentralized finance (“DeFi”) applications (Phase 1 and 2).
**Code repo:** Phase 1: https://github.com/protofire/tezos-defi-dev-experience
**Code repo:** Phase 2 (in progress): https://github.com/protofire/tezos-defi-dapp

2. Our team helped POA Network to develop a set of tools, which includes the Token Wizard, Proof of Physical Address, Proof of Bank Account, Token Bridge and **[Block Explorer (Block Scout).](https://blockscout.com/poa/core)**
    **Code repos (BlockScout):**
    https://github.com/poanetwork/blockscout
    https://github.com/poanetwork/blockscout-terraform

  We also contributed to enabling a single-click deployment of the POA network. 
  **Code repos:**
  https://github.com/poanetwork/deployment-terraform
  https://github.com/poanetwork/deployment-playbooks

3. **CROSS-CHAIN BRIDGE**
POA Bridge, an interoperability protocol between Ethereum networks for native to ERC20 and ERC20 to ERC20 cross chain transfers. Using the POA Bridge, projects can deploy their own instances of the POA Bridge and facilitate the transfer of ERC20 tokens between POA Network and Ethereum. 
**Code repo:** https://github.com/poanetwork/tokenbridge

4. **[xDAI Chain](https://blockscout.com/poa/xdai/)** 
Altoros (under the DBA Protofire) participates as a validator for the xDAI network and for the bridge, besides being a core developer of a great part of the technology stack (Blockchain Explorer, Cross-chain bridge, Network automation scripts).


## Team code repositories

Arsenii Petrovich [GitHub](https://github.com/ArseniiPetrovich)
Yauheni Kisialiou [GitHub](https://github.com/Ykisialiou)

