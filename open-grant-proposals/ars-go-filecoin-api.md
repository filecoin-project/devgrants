# Open Grant Proposal: `go-filecoin-api-client`

**Name of Project:** `go-filecoin-api-client`

**Proposal Category:** `devtools-libraries`

**Proposer:** 	[@waynewyang](https://github.com/waynewyang)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?** 	"Yes"

# Project Description

Currently, filecoin have not provided the corresponding filecoin-api of go version. Every developer must implement their own set of code logic to access filecoin when using go-lang.

In order to solve the above problems, avoid developers from manufacturing wheels repeatedly and improve development efficiency, a complete set of go version filecoin-api can be developed. Through various packages of SDK, third-party or specific function implementation can be effectively blocked, so as to reduce the cost of developers' understanding of functions and improve access efficiency.

## Value

Currently, filecoin ecology does not have a go version of the API, which can greatly improve developers' access efficiency.

- What are the risks if you don't get it right?

​	Once released, anything will affect anyone who USES the release package, so doing it wrong will affect anyone who USES the SDK.

- What are the risks that will make executing on this project difficult?

​	How to design a general extensible SDK architecture, easy to understand the naming specification.

## Deliverables

## Development Roadmap

| Milestone No. | Milestone Description                                        | Funding | Estimated Timeframe                        |
| ------------- | ------------------------------------------------------------ | ------- | ------------------------------------------ |
| 1             | design and Implement                                         | $2000   | Three weeks                                |
| 2             | All project deliverables are completed and added to the [Filecoin Shipyard](https://github.com/filecoin-shipyard) and Maintenance | $500    | One week<br />+<br />Long time maintenance |



For each milestone, please describe:

**M1:**


| No   | Description          | Team Member                         | Funding Required |
| ---- | -------------------- | ----------------------------------- | ---------------- |
| 1    | design and Implement | @johnli-helloworld<br />@waynewyang | $2000            |

**M2:**

| No   | Description                                                  | Team Member | Funding Required |
| ---- | ------------------------------------------------------------ | ----------- | ---------------- |
| 1    | All project deliverables are completed and added to the [Filecoin Shipyard](https://github.com/filecoin-shipyard) and Maintenance | Arsyun Team | $500             |


## Total Budget Requested

| Milestones | Funding Amount |
| ---------- | -------------- |
| M1         | $2000          |
| M2         | $500           |
| **Total**  | $2500          |



## Maintenance and Upgrade Plans

- Version maintenance: every time we release a new version of filecoin, we check to see if any new features have been released or changed. And according to the changes of the new version to add API functions, or modify the original functions, to ensure that the functions of our API perfect available.

- Bug resolution: we will assign a person to focus on the issue of the project on a daily basis, record all issues, and arrange the time according to the severity to solve and submit in the fastest time.

- Communication: developers using this open source project are welcome, and we will be in constant contact with them to hear Suggestions to improve our project

# Team
## Team Members

- [@johnli-helloworld](https://github.com/johnli-helloworld): developer

- [@wyblyf](https://github.com/wyblyf):guidance

- [@waynewyang](https://github.com/waynewyang) : guidance

## Team Member LinkedIn Profiles

- [@johnli-helloworld](https://github.com/johnli-helloworld)
- [waynewyang](https://www.linkedin.com/in/waynewyang/?locale=en_US)

## Team Website

- https://www.arsyun.com   
- https://github.com/arsyun

## Relevant Experience
- ARS team has rich experience in distributed cloud storage and has deployed practical products. And provides cloud service base on IPFS and filecoin.
  - [Essential-Thinking-of-Blockchain](https://github.com/arsyun/Essential-Thinking-of-Blockchain)
  - [Product:pServer](https://www.arsyun.com/web/index.html)
- [@waynewyang](https://github.com/waynewyang)  is the [Contributor](https://github.com/filecoin-project/go-filecoin/graphs/contributors) of go-filecoin, we can deeply understand the work flow about file coin.
- ARS Team has been attended IPFS camp in berlin and Barcelona, We're very interesting in IPFS and filecoin, and plan to do some application based on IPFS & filecoin.

## Team code repositories

- https://github.com/arsyun.

- https://github.com/arsyun/go-filecoin-api-client

# Additional Information

- We've already finish the code

[Code of ars-go-filecoin-api-client](https://github.com/arsyun/go-filecoin-api-client)