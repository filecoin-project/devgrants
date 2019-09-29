# Open Grant Proposal: `Filecoin miner analyzer and stats`

**Name of Project:** Filecoin miner stats

**Proposal Category:** `app-dev`

**Proposer:** `nodefactoryio`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes!

# Project Description

When a a mining node is installed and stared, a miner has a hard time of tracking what's happening with the node and gaining insights into the node's performance. This is almost always the case as such software is installed on the server and requires time for connecting to it and checking if everything is all right.

The solution we propose is a responsive web application with a notification system that gives full insight into node's status. The web app would give analysis to miner about the node performance, earnings, uptime and available disk space. In case there is a required action to be made i.e. a node goes down or software update is required, email notification would be sent to the user. Anything that can possibly help miners to improve their doing.

## Value

This is an added value for the miners and has no risk of failure for the Filecoin ecosystem. As miners have the clear incentive to make money on the provided service, we want to make sure they keep up with it and get the right statistics on their performance, how much money they are making and how to possibly improve that.

If we get this right, there is a possibility to expand this depending on the future development of Filecoin, for example it's reputation system. 

## Deliverables

The project will be considered as finished when the following is delivered:

* Clear project specification
* UI/UX design for both mobile and web version
* Frontend application (React)
* Backend application (Node.Js)
* Light daemon app for setup and uptime tracking (Go)
* User onboarding and project documentation

The web app should be able to provide to user the following functionalities:
* registration and login with email,
* adding nodes to be tracked (generation of URL for our daemon app),
* email notifications on required action

and insights into: 
* node connection status,
* calculated profit,
    * earnings through block rewards
    * retrieval earnings
* history of past and active deals with their status,
    * inspection of deal's state
    * payment redeemal status
* utilization and disk space occupancy,
* status of pledged collateral (past slashings).

Note that this functionalities may slightly change as we are open to adapting to user's needs or Filecoin network changes discovered during the development process. 

## Development Roadmap

### Milestone 1

Goals:
 1. Create clear specifications document
     * created and architectured by 2 team members (project manager and lead dev)
     * 1 week
     * 1000$
 2. Finished UI/UX design for web and mobile
     * done by an external team that we collaborate with
     * 2 weeks
     * 3000$

Cost: 4000$
Time: 2 weeks


### Milestone 2

Goals:
 1. Light daemon application that contains daemon initalization, reports uptime and disk space. App is developed with Go and contains unit tests.
     * 1 backend developer
     * 8 days
     * 3200$
 2. Backend application initalization, API for user and node registration, uptime tracking service, disk occupancy tracking. App is developed in Node.Js with TypeScript and contains unit tests.
    * 1 backend developer
    * 8 days
    * 3200$
 3. Web application initalization, design integration in React.
    * 1 frontend developer
    * 2 weeks
    * 3200$
     
Cost: 9600$
Time: 2 weeks

### Milestone 3

Goals:

 1. Integration in web application of user registration, reading node connection status, history of deals, calculating profits, slashing records.
    * 2 frontend developers
    * 2 weeks
    * 6400$
 2. Email notifications
    * 1 backend developer
    * 3 days
    * 1200$

Cost: 7600$
Time: 2 weeks

### Milestone 4

Goals:
 1. Production deployment
    * 3 days
    * 1200$
 3. QA of complete solution and bug fixing
 5. Project documentation

Cost: 2500$
Time: 2 weeks

## Total Budget Requested

Milestone 1 - 4000$
Milestone 2 - 9600$
Milestone 3 - 7600$
Milestone 4 - 2500$

Total: 23,700$


| Role | Rate / day |
| -------- | -------- |
| Designer     | 300$     |
| Lead developer     | 400$     |
| Backend developer     | 400$     |
| Frontend developer     | 320$     |


Note that the whole project management everyday costs are free of charge due to the good faith of our team.


## Maintenance and Upgrade Plans

Complete project will be open source and therefore it can be self hosted too. We plan to introduce (at some point when there is enough users) a payed plug-and-play service that is hosted by us and that will allow us the funding to maintain the project. However, in the beginning, it will be provided and hosted by us free of charge for everyone.

This project can be later expanded with more statistics depending on the Filecoin network protocol changes and updates. We are now building a separated daemon app but depending on the success level, we are open to integrating it with the Filecoin's node client.

# Team

## Team Members

NodeFactory is a blockchain R&D company that develops dapps, infrastructure and tooling. We are a team of 6, mostly fullstack developers with blockchain development experience since 2017.

## Team Member LinkedIn Profiles

- [Belma Gutlić](https://www.linkedin.com/in/belmagutlic/)
- [Marin Petrunić](https://www.linkedin.com/in/mpetrunic/)

## Team Website

[https://nodefactory.io](https://nodefactory.io)

## Relevant Experience

You can find some of our previous work in the [portfolio](https://www.nodefactory.io/Portfolio-NodeFactory-v3.pdf). Currently, we are also working on a similar application for Eth2 validators called ChainGuardian that has been funded by MolochDAO.

## Team code repositories

You can check out our [Github profile](https://github.com/nodefactoryIo/). Some of the open source work we'd like to emphasize is:
* [ChainGuardian](https://github.com/NodeFactoryIo/ChainGuardian)
* [GitMythX](https://github.com/NodeFactoryIo/gitmythx)
* [Node.Js TypeScript starter](https://github.com/NodeFactoryIo/node-ts-starter)
* [Solidity + Node.Js starter](https://github.com/NodeFactoryIo/solidity-node-docker-starter)

# Additional Information

Feel free to contact us on email info!@!nodefactory.io or [Twitter](https://twitter.com/nodefactoryio) if you have any questions. 
