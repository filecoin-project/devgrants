# RFP Proposal: `Storage Helper Libraries`

**Name of Project: Storage Helper Libraries

**Link to RFP:** [Storage Helper Libraries](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-storage-helper-libraries.md)

**RFP Category:** `devtools-libraries`

**Proposer:** [@deaswang](https://github.com/deaswang)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

go-filecoin is to handle operations at the detailed, protocol level. Storage Helper Libraries separate from the go-filecoin node but generally reusable across a variety of storage use cases and implementations.

Storage Helper Libraries should include:

- **Data Structure**: file or folder information for DAG

```
MetaData {
  path string // file path and name.
  chunkNum int // the number of chunk.
  size int //the size of file.
  cids []string // all chunk cid order by seq.
}
```

if store folder, it will be one list of MetaData.

- **File ingestion and splitting**: prepares files for storage deals in dag-compatible way. recurse through folders. split files that are larger than selected filecoin sector size into chunks according to dag.

```
AddPiece(file): add file to the dag. return one MetaData object.
AddPieces(folder, filter): add files by regular filtering to the dag, return list of MetaData object.
```


- **Get files**: get file from filecoin network.

```
GetFile(cid, filename): get file by metaData cid, and store as filename.
GetFiles(cid, folder): get files by metaData cid, and store into the folder.
```

- **Storage deal agent**: primary job would be to monitor deals and renew as needed. could also select from miners with the best reputations, desired price range(s), desired geographical distribution.

```
ProposeDeal(miner, ask, datacid, price, duration, location): propose one deal.
GetDeal(cid): get deal status.
RenewDeal(cid, miner, ask, price, duration, location): renew deal.
CancelDeal(cid): cancel deal.
```

- **Node operate**: operate with go-filecoin node.

```
InitNode(nodeAddr): connect go-filecoin node for other operate.
BindWallet(address): bind with the wallet use for pay for deal.
UnbindWallet(): unbind current wallet.
```

- **Sector**: sector operate for storage helper.

```
GetSectorSize(): get filecoin sector size.
GetPiece(pieceCid): get piece by cid.
GetSector(): get sector information on the node.
SealSector(): seal all the staged sector. 
```

## Workflow

First of all, connect go-filecoin node and bind wallet.

### store file

1. Client use AddPiece or AddPieces to import data to the DAG.
2. Use the metaData from step 1 to propose deal to the go-filecoin node.
3. After deal finished, store the JSON encoding of metaData to DAG.
4. Propose deal for metaData and get the data cid as the result.

### get file

1. Use GetPiece() and metaData cid to get metaData.
2. Parse metaData to get file or files.
3. store files to local driver.

## Deliverables

- An open-sourced, dual-licensed (under MIT and APACHE2) library in Golang that performs a storage workflow and can be used modularly by other software applications in the Filecoin ecosystem
- Documentation of how to use and install the library
- Sample application (can be extremely simple) that uses both this helper library and `go-filecoin` to perform the intended workflow
- Well-documented, human-readable codebase

## Development Roadmap

**Milestones:** 

| Milestone No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | store file API | $2000 | Oct. 14 |
| 1 | get file API | $1500 | Oct. 21 |
| 2 | All deliverables (codebase, sample application, documentation, testing) | $1500 | Oct. 28 |

## Total Budget Requested

**Total Funding Amount:** $5000

## Maintenance and Upgrade Plans

We will maintenance and upgrade with go-filecoin upgrade.

# Team

## Team Members

- Frank(@deaswang)
- 
- 
- 

## Team Member LinkedIn Profiles

- github.com/deaswang
- 
- 
- 

## Team Website

Please link to your team's website here (make sure it's `https`)


## Relevant Experience

Our team have develop one [test tool](https://github.com/filcloud/filutil) for go-filecoin storage.

## Team code repositories

Our team have develop one [test tool](https://github.com/filcloud/filutil) for go-filecoin storage.

# Additional Information

Please include any additional information that you think would be useful in helping us to evaluate your grant application.