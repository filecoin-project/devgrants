# Open Grant Proposal: `Data Chunking and Encryption Module`

**Name of Project:** Data Chunking and Encryption Module

**Proposal Category:** `app-dev`

**Proposer:** `JadTermsani`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

Filecoin currently has a limitation on the size of files to be uploaded; for now, it’s 256MiB. This number might increase in the future, but today, uploading larger files (video, photo sets, audio, data sets) requires them to be “chunked.”

Our project is to build a javascript package that enables the users to chunk and encrypt their files in order to upload them. It will be delivered as a Javascript package, which will make it reusable for anyone in the Filecoin community.

## Value

The benefits of these two functionalities are the following:

- The data chunking will allow the “Client” to upload their large files without worrying about fitting in the current or any future limitation of the file size on the Filecoin side. The encryption functionality will ensure secure data navigation within the upload process.

The risks if we don’t get it right are the following:

- The upload process for big files would be interrupted or not possible.
- Files will not be encrypted during the upload process

The risks that will make executing on this project difficult are:

- Handling each chunked file and making sure that it’s been encrypted
- Instability of the Filecoin network

## Deliverables

The deliverables will be the following:

- An open-source JavaScript package
- The ability for users to chunk their files
- The ability for users to encrypt their files
- Added functionality to “Starling” that allows it to handle encryption and data chunking automatically

## Development Roadmap

#### Milestone 1 - Project Initialization and data chunking module development

##### Team

1 Engineer and 1 Product Manager

##### Work

###### Engineering

- Project Initialization and npm configuration
- Data chunking model research and development
- File spliting algorithm Development
- Dynamic File size functionality development

###### Product Management

- Detailed requirements defintion
- Diagrams and user needs documentation
- Engineering guidance

##### Time

2 weeks

##### Budget

12500 USD

#### Milestone 2 - Encryption functionality definition and development

##### Team

1 Engineer and 1 Product Manager

##### Work

###### Engineering

- Encryption user needs and use cases defintion
- Encryption Modelization
- Encryption algorithm selection
- Encryption algorithm implementation on the file level to each split file

###### Product Management

- Detailed requirements defintion
- Diagrams and user needs documentation
- Engineering guidance

##### Time

2 weeks

##### Budget

12500 USD

#### Milestone 3 - Add and apply this package to "Starling"

##### Team

1 Engineer and 1 Product Manager

##### Work

###### Engineering

- Add the package to the Starling project
- Remove the file chunking case already developed
- Replace the file chunking code and use the developed package
- Enable "Starling" to automatically chunk and encrypt all files to be uploaded

###### Product Management

- Detailed requirements defintion
- Diagrams and user needs documentation
- Engineering guidance

##### Time

2 weeks

##### Budget

12500 USD

#### Milestone 4 - Conduct heavy testing and Launch preparation

##### Team

1 Engineer and 1 Product Manager

##### Work

###### Engineering

- One full week of testing the Javascript package developed
- Numerous Load testing and Performance Testing
- One full week to test the "Starling" integration
- Perform the required testing on the Starling CLI with large files

###### Product Management

- Detailed requirements defintion
- Diagrams and user needs documentation
- Engineering guidance

##### Time

2 weeks

##### Budget

12500 USD

## Total Budget Requested

The requested budget is: 50000 USD; 12500 USD per Milestone.

The grant will fund the development cost. In addition to a dedicated Software Engineer, Postlight will provide a Product Manager and Consulting Engineers as necessary to complete this project.

## Maintenance and Upgrade Plans

- We plan to fully support the project for 1 year - bug fixes | technical problems
- Support for upgrading to mainnet when it launches

# Team

## Team Members

- Jad Termsani - Engineer at Postlight
- Pascal Watwat - Program Manager at Postlight

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/jadtermsani/
- https://www.linkedin.com/in/pascalwatwat/

## Team Website

- https://postlight.com/

## Relevant Experience

Our team is part of Postlight, New York, a product development studio. We work as a company on many digital platforms across many industries. Our team specifically worked with Small Data Industries on “Starling” (https://github.com/filecoin-project/starling) on top of Filecoin. We are already in the community, and following up on the technical advancements of this platform since September 2019.

## Team code repositories

- https://github.com/JadTermsani
- https://github.com/postlight
