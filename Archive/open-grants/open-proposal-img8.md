# Open Grant Proposal: `Img8`

**Name of Project:** `Img8`

**Proposal Category:** `core-dev`

**Proposer:** `0xatm`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Nowadays, more and more web3 applications are retrieving images from IPFS and Filecoin, but most of them do not need to show the original images, for example, the NFT marketplaces, Metaverse, and dApps just needed to show thumbnails or compressed and resized images to fit into the responsive UI elements, but there is not a easy and straightforward way to do this natively in the IPFS/Filecoin ecosystem.

What we want to build is providing a gateway with native image processing and optimization protocol for IPFS and Filecoin to web3 developers, designers and creators, they just need to specify what they need in the query parameters of the gateway access url like `https://gateway.img8.io/ipfs/imgcid?w=200` and it will return the compressed and resized image with width 200px, it's easy-peasy.

## Value

- What are the benefits to getting this right?

> All users can retrive optimised and resized images directly via the IPFS CID, it'll make the design and development of the responsive web3 applications e.g. NFT marketplaces, Metaverse, Gamings, and web3 dApps etc. much easier.

- What are the risks if you don't get it right?

> The users need to backup or sync images stored on IPFS or Filecoin to centralized servers to enhance the end-users experience. It'll damage the end-users experience once these centralized servers go down。

- What are the risks that will make executing on this project difficult?

> Release PMF apps on time under budget. It would be great if we could publish this service ready as soon as we can so as to attracting early adopters and more partners to use this great service and relief their pain points.


## Deliverables

- An up and running gateway that is running on multiple regions to serve requests

- Features like images resizing, compression, watermark, compositable, and more.

- A website with WYSIWYG image processor to let users check images by CID.

## Development Roadmap

### Gateway Overview

![image](https://user-images.githubusercontent.com/79720925/134988034-ce9e23ff-3d22-4c21-bd6d-879cc1b4f44c.png)

The initial purpose of the Img8 protocol is for images retrieving/read only, and we'll see how things go and what the community needs then decide whether the upload files feature is required to be implemented.

Behind the scenes, the gateway will be mainly doing the below steps: 

- Whitelist based rating limit to avoid malicious cyber attacks .
- Retrieve images from IPFS and Filecoin using the client's requested cid with a timeout mechanism.
  - If the loaded file type is not image then return that file to client directly.
- Process and optimize the loaded image based on the query parameters like `w`, `h`, and `c` etc.
- Return either the processed and optimized image to the client or a detailed error message.

We'll consider to use nodejs as the programming language to develop the gateway for speeding up the development purpose, but we're open to use Golang if the reviewing team think that's required.


Milestone 1 (4 weeks):

- Finalize the requirements, documentation

> 2 weeks

- Website implementation - with a working feature that the user can preview and interactive with via a CID

> 2 weeks

Milestone 2 (6 weeks):

- Core features development

> 4 weeks

- Deploy and setup gateway onto cloud infrastructure

- Bug fixes according to the feedback

> 2 weeks

## Total Budget Requested

We're requesting total funding $49,640 to complete all above milestones, and the fund will be split into:

- Architecture and product design
- Development
- infrastructure cost

| Milestone  | Duration| Cost    |
|------------|---------|---------|
|   #1       | 4 weeks | $19,200 |
|   #2       | 6 weeks | $30,440 |
|            |         |         |
| **Total**  | 10 weeks| $49,640 |

> NOTE: The cost of Milestone 2 includes cloud infrastructure cost around $3,240.


## Maintenance and Upgrade Plans

This is an open source product, we are welcome any others contribute their talent no matter it's code or docs. Beyond that we'll keep adding more features from the community and partners feedback.

# Team

## Team Members

- Victor Feng (Github: [https://github.com/0xatm](@0xatm))
- Nikki Ng
- Samdanae Imran

## Team Member LinkedIn Profiles

- [Victor Feng](https://www.linkedin.com/in/imrfeng/)
- [Samdanae Imran](https://www.linkedin.com/in/samdanae/)

## Team Website

- https://www.nama.finance
- https://www.img8.io (coming soon)

## Relevant Experience

We're a squad of 4 with many years of blockchain-related products development built on top of EVM compatible chains, IPFS/Filecoin, also have hands-on experience in the image processing area. All of the team members have more than ten years of work experience in UX design, software design, and development.

We've done the MVP of this product, and you can check on https://github.com/img8io/img8-core.

## Team code repositories

All source code and docs of this product will be published on GitHub (https://github.com/img8io)

# Additional Information

We thank you for your consideration. Please feel free to reach out to nftvictor@gmail.com if you have any questions or suggestions for our proposal.
