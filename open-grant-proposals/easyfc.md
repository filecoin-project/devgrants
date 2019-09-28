# Open Grant Proposal: `EasyFilecoin`

**Name of Project:**`EasyFilecoin`

**Proposal Category:** `app-dev`

**Proposer:** `chainhubdev`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `Yes`

# Project Description

EasyFilecoin is a cross platform graphical client for Filecoin node. 

The installation and operation of  Filecoin is too complicated for most people. It is difficult to install packages on a Linux or macOS host using the command line and resolve potential software conflicts. Non-professional users are more willing to use graphical software. 

EasyFilecoin would simplify installation, upgrade and configuration of Filecoin node. It provides a clean interface and a series of scripts that interact with Filecoin nodes.

## Value

The Filecoin network requires enough nodes to provide value. EasyFilecoin provides a quick way to participate in the Filecoin network and should speed up the popularity of Filecoin.

As EasyFilecoin is just a graphical client, if the project fails, Filecoin network will not be affected.

The main risks are the technical difficulties and the large workload brought by cross-platform development.

## Deliverables

Graphical client of Filecoin node working on multi platforms which are Linux, macOSOS and Windows. 

Graphical interface of installation and configuration. Users can choose where software will be installed and how much disk space the node uses.

Graphical interface for the creation, backup, and use of Filecoin wallets.

Graphical interface for the Filecoin mining operation including starting, stopping, etc.

## Development Roadmap

We split the development process into three phases.

| No.  | Software Functionality                                       | Staff | Funding | Estimated Timeframe    |
| ---- | ------------------------------------------------------------ | ----- | ------- | ---------------------- |
| 1    | EasyFilecoin Linux version:<br />Graphical interface of installation and configuration.<br />Graphical interface for the creation, backup, and use of Filecoin wallets.<br /><br />Graphical interface for the Filecoin mining operation. | 2     | 0       | 10/1/2019 - 12/31/2020 |
| 2    | EasyFilecoin macOSOS version:<br />Graphical interface of installation and configuration.<br />Graphical interface for the creation, backup, and use of Filecoin wallets.<br /><br />Graphical interface for the Filecoin mining operation. | 2     | $12000  | 1/1/2020 - 1/31/2020   |
| 3    | EasyFilecoin Windows version:<br />Graphical interface of installation and configuration.<br />Graphical interface for the creation, backup, and use of Filecoin wallets.<br /><br />Graphical interface for the Filecoin mining operation. | 2     | $6000   | 2/1/2020 - 3/31/2020   |

We will invest the longest time in the first milestone. In order to prove our ability and reduce the risk of the Filecoin Foundation, we do not apply for funding at the beginning of the first milestone. Only when we have completed the first phase will we apply for funding of milestone 1 and 2  at the beginning of the second phase.

The progress of the second phase will be accelerated due to previously work in the first phase. EasyFilecoin Linux version and macOS version would be released on the date when Filecoin main network be available.

The third milestone is the most technically risky because Filecoin currently does not have a native Windows program. So we will spend twice the time of phase 2 at this stage and do our best to make EasyFilecoin available on Windows via  container technology.

At each stage we provide installation packages, documentation and Q&A sets for end users.

Detailed development plan.

| No.  | Development Content                                  | Estimated Timeframe   |
| ---- | ---------------------------------------------------- | --------------------- |
| 1    | Build a Filecoin node on aws.                        | 10/1/2019-10/10/2019  |
| 2    | Api design of EasyFilecoin Linux daemon .            | 10/1/2019-10/10/2019  |
| 3    | UI design.                                           | 10/1/2019-10/15/2019  |
| 4    | Development of EasyFilecoin Linux daemon.            | 10/11/2019-11/30/2019 |
| 5    | Development of EasyFilecoin Linux UI.                | 10/16/2019-11/30/2019 |
| 6    | Integration testing of EasyFilecoin Linux version.   | 12/1/2019-12/15/2019  |
| 7    | Installation package for Ubuntu and CentOS.          | 12/16/2019-12/20/2019 |
| 8    | Documentation and EasyFilecoin website.              | 12/21/2019-12/27/2019 |
| 9    | EasyFilecoin Linux version release.                  | 12/28/2019-12/31/2019 |
| 10   | Development of EasyFilecoin macOSOS daemon.          | 1/1/2020-1/15/2020    |
| 11   | Development of EasyFilecoin macOSOS UI.              | 1/1/2020-1/15/2020    |
| 12   | Integration testing of EasyFilecoin macOSOS version. | 1/16/2020-1/21/2020   |
| 13   | Installation package for macOSOS.                    | 1/22/2020-1/25/2020   |
| 14   | Documentation and EasyFilecoin website.              | 1/25/2020-1/27/2020   |
| 15   | EasyFilecoin macOSOS version release.                | 1/28/2020-1/31/2020   |
| 16   | Development of Filecoin docker file.                 | 2/1/2020-2/25/2020    |
| 17   | Testing of Filecoin docker on Windows.               | 2/26/2020-3/5/2020    |
| 18   | Development of EasyFilecoin Windows UI.              | 3/6/2020-3/20/2020    |
| 19   | Integration testing of EasyFilecoin Windows version. | 3/21/2020-3/25/2020   |
| 20   | Installation package for Windows.                    | 3/26/2020-3/27/2020   |
| 21   | Documentation and EasyFilecoin website.              | 3/26/2020-3/27/2020   |
| 22   | EasyFilecoin Windows version release.                | 3/28/2020/-3/31/2020  |



## Total Budget Requested

Total budget is $18000. As mentioned earlier, we will only apply for funds after completing the first milestone. Funds are mainly used to rent UI design outsourcing, cloud servers and developer grants.

| No.  | Use of funds                          | Amount |
| ---- | ------------------------------------- | ------ |
| 1    | UI design outsourcing.                | $1000  |
| 2    | AWS cloud server for testing purpose. | $2000  |
| 3    | Developer grants.                     | $15000 |



## Maintenance and Upgrade Plans

Provide at least three years of maintenance after the first stable version release. Software and documentation would be upgarded within one month after the new version of Filecoin node is released.

# Team

## Team Members

- Fred Zhou
- Vincent Zhu

## Team Member LinkedIn Profiles

All members don't have LinkedIn profiles.

## Team Website

No team websties。

## Relevant Experience

Both developers have more than 10 years of work experience and have cooperated in an enterprise blockchain project based on hyperledger which is a famous open source blockchain. Fred is good at go language and php. Vincent is good at python and c#. 

## Team code repositories

https://github.com/chainhubdev/zilliqa-laya-sdk

It's a javascript library for developing with Zilliqa blockchain technology on Laya platform.

# Additional Information

