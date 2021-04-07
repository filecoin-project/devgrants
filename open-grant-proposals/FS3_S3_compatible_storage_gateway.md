Open Grant Proposal: `FS3 - A S3 compatible storage gateway to Filecoin`

** Name of Project: *FS3 for S3 compatible storage gateway to Filecoin network*

** Proposal Category:**  `app-dev`

** Proposer:** `flyworker`

** Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?**
Yes

# Project Description
S3 as a wildly used industry object storage technology is adopt by many clients nowadays. Most of the cloud user getting
used to S3 SDK for providing service like, web site hosting, machine learning data storage, video content editing, from
TB level to PB level.

In order to onboarding more client from industry without ask them to redesign the system, a tool as a replacement of S3
for connecting to Filecoin is strongly needed.

MinIO is an Amazon S3 compatible object storage suite capable of handling structured and unstructured data including log
files, artifacts, backups, container images, photos and videos. If we add the interface to Filecoin, it can be a product
easily adapt by industry users with minimal integration effort. We have previous integration experience integrate MinIO

## Value
Once the solution is built, the tool can be used in several scenarios.

- Industry users: Industry users can migrate their code to Filecoin network without redesign their system

- Ecosystem Developers: Working as a container-based case layer for Filecoin network. Developers can user FS3 as a local
  container to communicate to Filecoin directly, they can also deploy the image to AWS or other cloud service provide
  for communication with

- Hosted Platform:  For platform like Powergate and Filswan, they can easily add it as a service component integrated to
  their current infrastructure.

The trick part of the implementation is how to find stable miners and save the content to network. It requires a payment
channel for the payment to the Filecoin miners. Several command line method need to be added for communication with
miners

## Deliverables
The software kit has two components: UI-side tools and command line tool

On UI side:
User can manage upload/download files, share with others, choose the miner for storage the object as a deal, it provides

- login MinIO with the API key and secreter key
- Upload file
- Setup payment wallet
- Choose the time and price you want to pay backup MnIO to filecoin network
- Backup folder as a deal paid by wallet
- Backup file as a deal paid by wallet
- List a deal cid with miner info for retrieval

Command line tool:

- Create a bucket for Backup to Filecoin network
- Choose the time and price you want to pay backup MnIO to Filecoin network
- Backup folder as a deal paid by wallet
- Backup file as a deal paid by wallet
- List history backup jobs
- List history deals

### User Sample
Init the setup
```shell
$> export MINIO_ACCESS_KEY=fs3
$> export MINIO_SECRET_KEY=fs3torage
$> export fil_wallet=f12bxpqyyc...7hffregtypiifjq
```

```shell
# add the host to our mc config
$> mc config host add fs3 http://127.0.0.1:9000 minio miniostorage 
# create a bucket called testbucket
$> mc mb fs3/testbucket
# copy a local file called file.txt inside of testbucket
$> mc cp file.txt fs3/testbucket
# send file.txt as a deal to filecoin miner id f019104
$> mc send fs3/testbucket/file.txt f019104
# get the cid of the object in the bucket on filecoin
$> curl "http://localhost:8889/info?bucket=testbucket&object=file.txt"
```

## Development Roadmap
| No. | Milestone Description | Funding | Estimated Timeframe |
| --- | --- | --- | --- |
| 1 | FS3 functionality design and scope definition. | NA | 2 weeks |
| 2 | FS3 user interface design | NA | 1 weeks |
| 3 | Infrastructure architecture design and implementation plan readiness.| NA | 1 weeks |
| 4 | Command line tool coding  | 10,000 | 4 weeks |
| 5 | User interface coding  | 10,000 | 3 weeks |
| 7 | Document and tutorial | TBD | 1 weeks |
| 8 | Product release go marketing  | 10,000 | 1 weeks |

## Total Budget Requested

Total: $30,000 .

## Maintenance and Upgrade Plans

We have a dedicated team in Montreal with 10 developer team, since this product has very close relationship with the
Storage market project Swan we are building we will keep a code upgrade at weekly bases. Future upgrade can be add S3
compatible file importer service, enhancement of key management, connect to swan project. Etc.

# Team

## Team Members

- Charles Cao
- Chi Zhang
- Boqian Wang

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/charles-cao-09a79526/
- https://www.linkedin.com/in/ch-zhang/
- https://www.linkedin.com/in/boqian-wang-6b0955171/

## Team Website

https://filswan.com

## Relevant Experience

Please describe (in words) your team's relevant experience, and why you think you are the right team to build this
project. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members'
backgrounds, etc.

We - NBFS Canada participated in SR1, SR2, and cooperation with starling and pinata project. In slingshot 2 we processed
over 10,000 deals and over 500 offline deals, talked to 100 miners and actively working data transfer service between
Asia and North American users. Prior to working on Filecoin project, we were working on a decentrilized AI computing
platform which using smart contract for data/task transmission to different AI workers, we have in hand experience of
handling encryption and data pipeline.

We build the following product

- https://nbai.io GPU cloud computing
- https://nbfspool.com One of the largest Filecoin mining node in North America
- Https://swan.nbfspool.com A storage market for price decovering and offline trasfer

The team get the following reward and honor.

- The Natural Science and Engineering Research Council of Canada (NSERC) special fund supports research on the direction
  of video coding.
- Canadian government high-tech research and development grant
- Natural Science Foundation of Canada (NSERC) Blockchain to AI Cloud Computing Research Grant
- Canadian Information Technology and Integrated Systems Mathematical Organization (Mitacs) AI medical identification
  project grants
- Canadian tax support for scientific research and experimental development
- Quebec e-commerce innovation enterprise support
- CENGN (Canadian Center of Excellence for Next Generation Networks) Research Support Project
- Canadian D3 incubator Hosted Startup support
- Microsoft Entrepreneurship Support Program (BizSpark) Support
- HP Enterprise Supplier Partner, Dell Enterprise Supplier Partner, ASUS Enterprise Service Partner, Amazon Enterprise
  Partner, NVIDIA Canadian Cloud Computing Supplier

Charles Cao, Founder of Filecoin node NBFS Canada, CEO of Nebule AI inc, previous working for IBM, Autodesk, Exepida and
Paysafe. NBFS Canada is working on building an edge cloud computing platform (Project Swan) integrated with Filecoin
decentralized storage solution. Project Swan integrates computing, online/offline deal management and storage price
discovering in one platform to bring enterprise applications closer to where the data located.

## Team code repositories

https://github.com/nebulaai

# Additional Information

Fronter accelerator participants
