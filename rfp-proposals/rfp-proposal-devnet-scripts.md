# RFP Proposal: `Devnet scripts`

**Name of Project: Devnet automation with Kubernetes**

**Link to RFP:** https://github.com/filecoin-project/devgrants/blob/master/rfps/new-wave-4-rfps.md#devnet-scripts

**Proposal Category:** `devtools-libraries`

**Proposer:** `mike1729`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

The motivation behind this proposal is to make it easier to set up, customize, and scale a shared Filecoin Devnet.

The solution is going to utilize Kubernetes scripts to automate setting up the network consisting of bootstrap nodes, faucet, and the ability to add additional miners from a prespecified whitelist.


## Value

This project is an added value for the Filecoin ecosystem as it lowers the complexity of spinning up a development environment that more closely resembles the actual mainnet. It enables faster development, easier testing, and shared collaboration for parties interested in testing in a real environment without experiencing issues with setting up a one.

## Deliverables

Kubernetes based automation scripts for running devnet environments.


## Development Roadmap

### Milestone 1 - Project and Preparation


Goals:

1.  Technical documentation and schematics for Kubernetes infrastructure.

	 *  1 team member
	 *  1 week
	 * 1000$

Time: 1 week
Cost: 1000 $

### Milestone 2 - Run Kubernetes Infrastructure

Goals:

1.  YAML configuration files for: bootstrap, faucet, miner and explorer nodes.

	* 2 team members
	* 1 week
	* 4000$  

2.  Underlying K8s infrastructure: deployments, Kubelet monitoring registration, namespaces.

	* 2 team members
	* 1 week
	* 4000$

Time: 2 week
Cost: 8000 $

### Milestone 3 - Make Application Run on Kubernetes

Goals:

1.  New dockerfiles or fitting already existing ones.

	* 1 team member
	* 1 week
	* 1000$

2.  Security improvements: whitelisting, role based access control.

	* 1 team member
	* 1 week
	* 2000$

Time: 1 week
Cost: 3000$

### Milestone 4 - Samples to Run Project on AWS

Goals:

1.  Terraform modules for setting sample infrastructure on AWS.

	* 1 team member
	* 1 week
	* 2000$

Time: 1 week
Cost: 2000 $

### Milestone 5 - Configure & Automate For Easier Use

Goals:

1.  Developing configuration and automation scripts in Golang:

	*  1 team member
	*  1 week
	*  2000$

Time: 1 week
Cost: 2000 $


## Total Budget Requested

-   Milestone 1: $1,000
-   Milestone 2: $8,000
-   Milestone 3: $3,000
-   Milestone 4: $2,000
-   Milestone 5: $2,000

Total: $16,000


## Maintenance and Upgrade Plans

After the project is delivered, it will be open-sourced for the community to add new features. Bugfixes will be done on demand, upgrades will be compatible at the protocol levels with the previous version (in case FileCoin would also support backward compatibility).

# Team

## Contact Info

michal.swietek@cardinals.cc

## Team Members

-   [Piotr Kuśnierzowski](https://www.linkedin.com/in/piotr-ku%C5%9Bnierzowski-46b1768a/)
-   [Michał Świętek](https://www.linkedin.com/in/micha%C5%82-%C5%9Bwi%C4%99tek-40720b168/)

## Team Website

https://cardinals.cc/

## Relevant Experience

We believe that only software on production is really finished, so for the last decade pushing it there was our main focus. From Docker and Docker Swarm to Kubernetes, we tend to create solutions that support every team no matter the size. We understand how to scale container-based infrastructures to reach a level of the largest European e-commerce platforms and international online newspapers. In other words, we specialize in delivering applications designed to operate and scale despite huge numbers of requests.

We consider public clouds as the best solution to go global. Our team consists of not only Go developers but also a certified AWS Architect responsible for two large enterprise-grade Kubernetes projects: a business e-learning platform and infrastructure for a logistics company working across Europe and Asia.

## Team code repositories

https://gitlab.com/alephledger/consensus-go
