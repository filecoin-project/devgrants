# Open Grant Proposal: `Blockchain Package Manager - FileCoin Package`

**Name of Project: FileCoin BPM package**

**Proposal Category:** `devtools-libraries`

**Proposer:** `JonasPf`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

Create a basic bootstrap application using the Blockchain Package Manager that will install the FileCoin Full Node, all Blockdaemon dependencies, and anything else required to run, manage and monitor a FileCoin node. 

In addition, we will add FileCoin to our principal node-marketplace used by professionals and enterprises to evaluate which protocol to build on.

BPM supports a plugin/package architecture for different Blockchain protocols. FileCoin support will be implemented as a plugin/package. This allows to configure and launch FileCoin nodes on any supported cloud or BYOI infrastructure in a standardized way. The underlying OS can be Linux or OSX (needs Docker). BPM offers an auto-upgrade mechanism for plugins/packages to ensure users always run the latest versions.

Blockchain node events, logs, telemetry, health data will be forwarded to the Blockdaemon data pipeline for storage and analysis. Data will be analyzed and displayed to Blockdaemon users and optionally be made available to paying customers. 

The goal is to run bpm to install, download, and configure a node that connects to the FileCoin testnet as well as the mainnet when it launches.

## Value

### What are the benefits to getting this right?

Standardized way of launching FileCoin nodes making it easier for users to configure and monitor and maintain a FileCoin node. This will improve the adoption rate of FileCoin. Monitoring will provide an audit trail for SLAs. Each BPM package comes with a test suite to test the correct functionality of a node.

### What are the risks if you don't get it right?

Running FileCoin nodes will be restricted to users who can afford the engineering resources to do so. The adoption rate of FileCoin will suffer. Monitoring the overall node health and performance will remain difficult.

### What are the risks that will make executing on this project difficult?

* Logs are not in a format that we can consume
* Commands cannot be easily added to the plugin for technical reasons
* Complications when running FileCoin inside a docker container

## Deliverables

* A binary bpm FileCoin package hosted by the BPM repository
* The bpm source-code in a Github repository
* Documentation for the above
* FileCoin added to the Blockdaemon marketplace
* (Optional) monitoring support via Blockdaemon monitoring services

## Development Roadmap

### Milestone 1

* Source-code for a basic bpm plugin to launch a FileCoin node
* Basic bpm plugin deployed to BPM repository
* Documentation on how to launch a FileCoin node using bpm

This milestone will take 4 weeks

People working on this milestone
* 1 x QA
* 1 x Software Engineers
* 1 x Project Manager

Funding required: €15.000

Acceptance criteria

* The user is provided BPM cli that will download the BPM FileCoin package  that will start a FileCoin node
* The user can install on Ubuntu or OSX running on GCE, AWS, and Azure
* The user can run the individual BPM commands:
    * list - Lists all available version of the FileCoin package
    * install - Installs the latest version of the FileCoin package
    * configure - Creates the base configuration for a FileCoin node
    * start - Creates all necessary secrets and starts a FileCoin node
    * stop - Stops the FileCoin node (and optionally purges all data)
    * status - Returns the status of all configured nodes on the system
    * help - Help about any command

### Milestone 2

* Monitoring (nodestate and logs) agents will be added to the FileCoin package
* Advanced FileCoin configuration options will be added

This milestone will take 4 weeks

People working on this milestone
* 1 x QA
* 2 x Software Engineers
* 1 x Project Manager

Funding required: €15.000

Acceptance criteria:

* Logs, telemetry and node status will be sent down the Blockdaemon data pipeline
* User can query for node state with the Blockdaemon node API
* Advanced configuration options for the FileCoin node are supported via the `configure` command

### Milestone 3

* Automated Test Suite
    - The user runs/installs the node with BPM and can run “bpm test filecoin”, which will run a test suite against the running setup. 
    - Test suite should pass if the node is configured correctly for any of the supported networks of the chain. 
    - Test suite interacts on a read-only basis, does not interrupt node functionality, does not make modifications to the node, or make/affect transactions on the node. 
    - Test suite can be executed at any time during the lifecycle of the node. 

This milestone will take 4 weeks

People working on this milestone
* 2 x QA
* 1 x Software Engineers
* 1 x Project Manager

Funding required: €10.000

Acceptance criteria:

* User should be able to run the automated test suite and all tests should pass
* The user runs/installs the node with BPM and can run “bpm test filecoin”, which will run a test suite against the running setup.

### Milestone 4

* Add FileCoin to the Blockdaemon Marketplace for managed nodes with a dedicated marketing page
* Basic machine and nodestate metrics available on the FileCoin node’s dashboard
* Blockdaemon will launch and maintain one FileCoin node

This milestone will take 4 weeks

People working on this milestone
* 1 x System administrator
* 1 x Data engineer
* 1 x Web developer
* 1 x Project Manager

Funding required: €15.000

Acceptance criteria:

* Complete Product
* First users start onboarding
* Blockdaemon hosted FileCoin node accessible

### Milestone 5

* Add support for creating snapshots from a BPM managed node
* Add support to start a BPM managed node from a snapshot

This milestone will take 4 weeks

People working on this milestone
* 1 x System administrator
* 1 x Software Engineer
* 1 x Web developer
* 1 x Project Manager

Funding required: €15.000

Acceptance criteria:

* User is able to launch a filecoin node from a snapshot with BPM
* Snapshot pulled from Blockdaemon Snapshot Repository

## Total Budget Requested

€70.000

## Maintenance and Upgrade Plans

The team will maintain the package long-term and release new package versions with every new FileCoin release.

# Team

## Team Members

Blockdaemon Engineering Team

## Team Member LinkedIn Profiles

https://blockdaemon.com/about/ 

## Team Website

https://blockdaemon.com 

## Relevant Experience

Blockdaemon already built a BPM package for Polkadot and Kusama for the Web3 foundation. We have active grants for building infrastructure tooling for more than 5 other Blockchain protocols. 

Blockdaemon is the only multi-cloud (including BYOI), multi-geo middleware platform
for monitoring and orchestration, bringing cloud formation tooling to blockchain out of
the box today.

Has 8000+ users, 100s of nodes live over 20 protocols and dozens of data centres at any
given time.

Works to simplify the process of deploying nodes and creating scalable blockchain
networks with APIs, SLAs and SOC-compliance Security -- Monitoring anywhere
(Splunk partnership).

Offering includes Relay-, Monitoring-, Transaction- and Archive-nodes, with load-balancing,
latency-management and staking.

## Team code repositories

https://github.com/Blockdaemon/bpm-sdk
https://github.com/Blockdaemon/bpm-polkadot 


