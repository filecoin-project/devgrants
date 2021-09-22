# Open Grant Proposal: `Decentralizing the People's Branch with Filecoin`

**Decentralizing the People's Branch with Filecoin:**

**Proposal Category:** `devtools-libraries`, `docs`

**Proposer:** `antoinemcgrath`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?: ** `Yes`

# Project Description

The problem: There is no single, comprehensive repository for research reports created by legislative branches of national governments around the world. Free resources are topically focused, and existing paid repositories typically host reports created by a single country. Some countries do not make their reports easily accessible. For example, before the US government's launch of crsreports.congress.gov, there was no official US Government website providing CRS reports to the general public. Still, the official website is missing older reports that are available from other sources. For a researcher, gathering comprehensive resources is a time intensive endeavor that prohibits the kind of comparative research that would promote good governance.

Proposed solution: Congress.ai is a project that will address this information gap by creating the first free resource of all nations' legislative research reports, preserved permanently and made available to all using Filecoin. Congress.ai will include a website allowing journalists, researchers, activists, and others to easily search through the corpus to compare and contrast reports relevant to their work or interests. By uploading nation collections of reports to a decentralized web Congress.ai and anyone on the network can access and host replications

Conceptually and practically speaking, parliamentary policy reports of the world are an ideal use case for Filecoin because its decentralized storage and protocols reflect the values and decisions of individuals as does the parliamentary branch.


This section should be 2-3 paragraphs long.

## Value

Anticipated impact: Using Filecoin to support the storage and access these important documents will ensure that people can access all the parliamentary reports. This will enable any researcher to confidently focus on analysis and good governance recommendations rather than undertaking a complex resource gathering process. Government archivists will likely make use of redundant hosting per LOCKSS principles which is enabled through the use of Filecoins, the resulting effect will increase the tenacity and speed at which others will be able to access the collection.


## Deliverables

Wiithin 3 months we will provide open access to Congress.ai with a near complete collection of Filecoin legislative research reports from 4 countries,

## Development Roadmap

We propose a 3 month timeline to build an initial prototype of Congress.ai. Our project will focus on 4 countries, and will involve two phases.  In Phase One, we will ingest and label reports from official government websites, and use them to train a classifier to detect reports in a similar format.  We will retool our existing codebase for our crsreports.com website to utilize Filecoin.  In Phase Two, we will begin applying our classifier to large datasets (such as the Internet Archive's corpus of PDFs) to identify and extract additional reports.  Creating a unique and thorough collection requires dedication to resolve all of the technical, linguistic and challenges of scale that will arise, some solutions I will be capable of addressing on my own, others will require additional hardware, engineering and region specific archival expertise.
This project is independent, however it can also be seen as phase 2 of a larger effort to provide universal access to all law. Phase 1 CRSreports.com (detailed below) focused on US Congressional research reports. Congress.ai will focus on global parliamentary reports. The tool and procedures developed for phase 2 can be applied in phase 3 beyond the focus of global parliamentary aggregation and onto a global judicial focus. Phase 3 would result in an all laws global repository project.


## Total Budget Requested

Expense estimate $30,000 USD

- OCR services
- H2O.ai license
- Cloud Provisioning
- Full Time engineer
- Supplemental Engineer
- Project Mgr Supplemental Expenses
- Crowdwork Budget (Mechanical Turk)
- International Federation of Library Associations and Institutions (IFLA) Membership
- Website
- ML Classifier based on 4 countries, 1 classifier set per country
- ML Libraries, training classifiers:
- Website build & research database


## Maintenance and Upgrade Plans

This proposal is to collect and host the legislative reports from only 4 countries. Once completed we will accept funding from private practises that wish to be associated with the content and provide them with recognition, and consider partnerships with academic and archival institutions including archive.org and public.resource.org and the yet to be formed UN library lab.

# Team

## Team Members

- Bill Marczak
- Antoine McGrath

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/bill-marczak-46535456
- https://www.linkedin.com/in/antoinemcgrath/

## Team Website

- https://www.Congress.ai
- https://antoinemcgrath.com/Gov_Research_Services_Help.html

## Relevant Experience

Post Internet Archive Antoine designed a related workflow to Congress.ai for the US congressional research service which resulted in CRSReports.com This resource was profiled in the Washington Post and has become a cited resource by more than a dozen law libraries and internally by several US government agencies. Bill co-creator of CRSReports.com is a Postdoctoral Researcher at UC Berkeley, where he received a PhD in Computer Science. Bill is a Senior Research Fellow at Citizen Lab, a co-founder of Bahrain Watch. His focus is on novel technological threats to Internet freedom, including new censorship and surveillance tools. His expertise in Internet scanning and conducting digital investigations has been featured in Vanity Fair, the New York Times, the Washington Post, on CNN, and on Larry King.


## Team code repositories

- https://crsreports.com/
- https://github.com/antoinemcgrath?tab=repositories

# Additional Information

In evaluating dedication to this project please reach out to Demand Progress' Daniel Schuman or Protocol Labs' Marvin Ammori
