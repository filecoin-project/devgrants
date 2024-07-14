# RFP Proposal:   Filecoin Plus public data metadata standard and implementation

## metadata reference for Filecoin public data

RFP Category: `app-dev`

**Proposer:** @mariswang (@mariswang), @dbw9580


**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes


## Project Description

IPFS together with Filecoin provides infrastructure for a data storage market where owners of data pay storage providers to safely store the data for future retrieval.
Working with useful datasets hosted on IPFS and Filecoin network requires knowledge of their metadata, for example, the format and the schema of the datasets, etc.
However, there is no standard way to store and retrieve metadata associated with datasets that enables programmatic interaction with the datasets.

This project aims to define a public dataset metadata standard to describe the dataset and develop a reference implementation of the standard.
Such meta data info will be included in a customized CAR file.

## Value

Help make data discovery and utilization on IPFS and Filecoin easier, filling the gap between storing and trading of data, and actually making good use of the data.


## Deliverables

Documentation on the metadata standard and format;
A reference implementation of the standard, in the form of both source code and usable compiled binary.


### Week 1-4: 750 FIL
Work by two engineers.
* define the meta data reference for public data. Some standard like Dublin core will be referred.
* design the special IPDL/CAR for data package.
* coding work based on Nodejs/filecoin API.

### Week 5-8:  750 FIL
Work by two engineers.
* design function to read the meta data info.
*  design function to unpack the download car file.
* coding work based on Nodejs/filecoin API.


## Total Budget Requested

1500 FIL. This amount will be tiered with hitting the milestones.

## Maintenance and Upgrade Plans

Current plan stores the metadata along the data, and packages them into a new file of a format defined by the standard. Users still need to download the packaged file and then get the metadata in in.
In the future, users could get meta info without downloading the package. We will submit a new proposal in category:core-dev.

## Team

## Team Members

- Bowen Ding
- Liang Wang

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/liang-wang-85076b47/
- https://www.linkedin.com/in/bowen-ding-746a10189/

## Team Website

http://datahub.pub

## Relevant Experience

We have been developing [Minerva](https://github.com/bdchain/Minerva/) since 2018 primarily as a research project. We published the progress at [APNet 2019](https://conferences.sigcomm.org/events/apnet2019/posters/7.pdf). We are currently working on [merging Minerva into Apache Drill](https://github.com/apache/drill/pull/2084).

## Team code repositories

https://github.com/bdchain/

# Additional Information
