# Open Grant Proposal: `Browser-Based Web Archiving Design and Standardization`

**Browser-Based Web Archiving Design and Standardization**

**Proposal Category:** `technical-design` for a specification, with elements of `app-dev`, `devtools-libraries`

**Proposer:** @ikreymer, @webrecorder

**Administrator:** Dietrich Ayala

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:**

The formal specification and UX research output documents will be released under the CC-BY-4.0 license.

The work also includes updating of existing tools (ArchiveWeb.page, ReplayWeb.page, Agregore) which are released under AGPL.

Any other work created under this grant will be released under MIT and Apache licenses.

# Background

The ability to not just view and interact, but to save and preserve, is fundamental to an open web and has been part of the original design. (The very first browser had a Save As option). But as the web has become more complex, and moved away from serving static documents to dynamic, interactive applications, the ability to save and preserve content has become more difficult and less functional. While modern browsers still retain a ‘Save Page As…’ option, this option is clumsy and mostly useless for any modern web sites.

Focusing on archiving websites in bulk, a community of web archivists pioneered by memory institutions such as Internet Archive has developed alongside the web.
The traditional approach of “crawling” the web at scale and saving the HTTP traffic seen by a specialized crawler has also reached its limits when dealing with modern, complex websites that require Javascript and complex user interaction to be fully realized.

The ability to create high fidelity archives directly through a browser provides a viable alternative to the currently broken 'Save Page As...'. The ability to then efficiently load web archives then also provides a direct interface between HTTP-based web applications and new applications built around new decentralized/p2p/web3 protocols such as IPFS.

# Project Description

The overarching goal of this project will be to present a documented, standardized path for implementers wishing to create web archives in a browser environment and place these archives (archives of HTTP websites) onto decentralized systems (IPFS, other p2p/web3-protocol based systems), and provide initial proof-of-concept implementations of these standards using existing tools.

This project will consist of three parallel but interrelated strands of work that will serve to further ability to safely and easily create browser-based high-fidelity web archives, store them on decentralized systems, and efficiently access them:

1. Creation of a formal storage specification
2. Creation of UX guidelines for browser-based capture, storage and replay
3. Beginning of implementation into existing tools.

Together, the work on these three tracks will define the storage and UX requirements for high-fidelity browser-based web archiving and support existing tools begin realizing these requirements.


## Value

The main value of this project is to create a formally standardized approach to creating, storing and accessing web archives on p2p/decentralized systems.
The standard will include both the storage specification as well as ux guidelines for approach this process, as well as initial integration of these
standards into our existing tools. The standard specification will be usuable by other tools and independent developers.

The risks include not having the standard being clear enough or formal enough to enable others to adopt them on their own. The project does have a lot of moving
parts, with three concurrent tracks of work, and we will attempt to mitigate the risks through clear updates via GitHub and dedicated project manager role.

There is also a separate risk inherent in the process of allowing users to archive their own data using the browser, and ways to mitigate this risk is a key part of the research in this project. The ux research will include threat modeling and will have an emphasis on user privacy, while the specification will include approaches to encrypted storage to address these risks.

## Deliverables

The work will be divided into 6 monthly milestones. Each milestone deliverable falls into one of the work areas defined below.
The work and the associated funding for each deliverable are as follows:

| Milestone | Area | Deliverable                                                                          | Funding     | 
| --------- | ---- | ------------------------------------------------------------------------------------ | ----------- |
| A | Spec | Begin formalizing the WACZ spec, identify key use cases, identify gaps in the specificatio.n  | 3,000 |
| A | UX | Initial report for initial userbase. Interviews with a focus on interface dynamics and user/institutional privacy requirements.    | 5,000 |
| B | Spec | Initial formal draft of specification as implemented, including use cases and stakeholders. | 3,000 |
| B | UX | Threat modelling assessment for selection of 'MVP' browser-based web archiving use cases. | 10,000 |
| C | Spec | Research on scalable index and random-access full-text search approaches complete and defined in spec. | 6,000 |
| C | Spec | Evaluation/changes to the storage spec based on any insights from thread modelling. | 2,000 |
| D | Spec | Research ‘continuous archiving over time’ use case and define in specification, review any additional use cases. | 6,000 |
| D | Spec | Research on random-access encrypted storage finished and approaches defined in spec. | 4,000 |
| D | UX | Design system recommendations for core archiving features and conceptualization of privacy trade-offs. | 10,000 |
| D | Impl | Update existing command-line toolset (py-wacz) for creating and verifying web archives according to latest specification. | 5,000 |
| E | Spec | IPFS considerations for storage, such as self-hosted replay data layout, and MFS for ‘continuous archiving over time’ defined in spec. | 5,000 |
| E | UX | Design system recommendations for storing web archives on external storage, including IPFS, with privacy considerations. | 10,000 |
| E | Impl | ReplayWeb.page updated to support latest specification (index and full text search) | 5,000 |
| E | Impl | Agregore Browser extension API updated to support archiving requirements | 3,000 |
| F | Spec | Final WACZ specification reviewed by all stakeholders and next steps decided (W3C, IETF, other processes...) | 2,000 |
| F | UX | Final recommendations for privacy-facilitating capture, storage, replay, as a documentation report | 8,000 |
| F | Impl | ArchiveWeb.page supported in Agregore Browser | 2,000 |
| F | Impl | Integration of at least one recommendation from the UX research into ArchiveWeb.page. | 5,000 |
| - | - | Project Management: A dedicated project management budget will help coordinate work between different collaborators, as well as outreach to key stakeholders and key users, especially related to beginning formal standardization process, and ensure timely progress on all deliverables. | 6,000 |
| - | - | Total | $100,000 |


## Development Roadmap

The development roadmap follows three strands of work, including work storage specification, UX research and design, and implementation of research
into existing tools. The three tracks are defined below:


### Creation of Storage Specification (Standardizing the WACZ Format) (SPEC)

*Work performed by: Ilya Kreymer and Ed Summers*

To facilitate the storage of web archive data on decentralized systems, an open-standard format is necessary to represent web archive data and any necessary metadata. This specification will enable the placement for archived web (HTTP-based content) to be served from decentralized (web3, etc...) systems.
 
Webrecorder has created an initial prototype of such a format, [WACZ (Web Archive Collection Zipped)](https://github.com/webrecorder/wacz-format). The format packages existing web archive data, WARC along with indexes and other metadata in a random-access-readable way. The format should allow for efficient access to web archive data over any protocol that supports random access read. Any IPFS-specific considerations will also be included in the specification, such as including the replay system for self-hosted storage or using MFS for incremental updates. The specification in its current form can be found here: https://github.com/webrecorder/wacz-format. 

Webrecorder has also created and maintains tools that read and write WACZ files. The specification broadly follows the basics of the [Frictionless Data Package](https://specs.frictionlessdata.io/data-package/) format, although the individual components of the package are not fully specified. To aid further adoption and implementation of the format with decentralized/p2p storage systems, a formal specification of the WACZ format will be created. The specification will address specific use cases from a group range of stakeholders in and around the web archiving community, who will provide input on the development of the specification. A technical writer/editor will be responsible for maintaining the draft of the specification and seek to achieve rough consensus with the group of stakeholders, while iterating on the specification.

The WACZ specification will be expanded in the following:

- Formal defintion of the WACZ (ZIP format) and all parts of the data layout, possibly improvements to the Frictionless Data Spec framework.

- Research on the most versatile approach to indexing, considering the current (CDXJ) approach and other approaches (e.g. sqlite).

- Research on best approach to store full-text search data in a scalable way.

- Specification for incremental/continuous archiving, where a web archive collection is increased through periodic automated capture.

- Plan for IPFS storage, including using MFS for incremental storage, specification storage of the replay system for standalone access via HTTP gateways.

- Specification for storing additional metadata as part of the data package based on standard metadata schemas.

- Research on potential approaches to support encryption while maintaing random access.

At Milestone C, and possibly at later stages, we will also evaluate if any changes to the storage specification, are necessary in response to the UX research and threat modeling to better account for privacy of stored data.

At the end of the grant period, the specification will more rigorously define aspects of a storage model for web archives on decentralized/p2p systems, identify key use cases - from small static websites to larger growing collections, and receive a thorough vetting from initial stakeholders. A decision on the next steps for formal standardization, for example via W3C or IETF, will be made and the specification will be ready for submission into the proper standardization path.



### Privacy-Centric Design Research for Browser-Based Capture, Storage and Replay (UX)

*Work performed by New Design Congress, led by Cade Diehm*

Traditional web archiving, such as that performed by larger institutions like Internet Archive, generally only archive publicly available content. However, browser-based archiving enables the user to archive anything loaded in their browser, including private content. The browser-based approach to web archiving is more powerful, but also riskier, as it allows users to archive and share potentially private content. Thus far, the privacy implications of personalized, browser-based web archiving have not been extensively research, and this effort will certain user privacy and security as a core facet of the work.

The UI/UX research will cover three key stages of web archiving process: web archive creation in the browser, web archive replay in the browser, and user decisions about web archive storage (where data should be stored, with whom it should be shared, etc…), with a special focus on user privacy throughout all stages of archiving. Web archiving UX contains numerous challenges, tied not only the interfaces of capture, storage and replay, but also the proposed file formats and underlying distribution models. In this grant, UI/UX research will deliver best practice recommendations for providing high-fidelity web archiving  implementations directly into a web browser or browser-based extensions.

The UX research will include core must-have features that must exist for a user to create and access web archives in the browser. The UX research will cover more advanced/optional features, and designs will be informed by UI/UX best practices alongside careful threat modelling techniques. As a result, the UX research will deliver recommendations that take into consideration the privacy and security concerns associated with sharing potentially private or sensitive data, the politics of social graphing inherent in P2P distribution models, and how to facilitate user decisions as they choose which data to share, and the curation of archived pages.

The UX research will include the following deliverables:
- Interviews with diverse group of individual and instititonal users, both currently creating web archives and those who may be able to create web archives in the future, if given the opportunity and the right tools.

- Threat modeling assessment based on the gathered use cases, covering the basic process of capture, storage and replay as required by users.

- Design system proposal that covers the basic the goal of web archiving, storage and replay/curation, designing for complexity within each of these stages of archival processes, and taking into user privacy concerns at each stage.

- Design system proposal that also covers storing web archives to IPFS or other decentralized/p2p systems. The proposals will be informed by security considerations as documented in the research to identify drawbacks or compromises inherent in the proposed design system. 

- A recommendations document on user privacy covering how to present web archiving functionality and associated trade-offs associated with archiving fidelity vs privacy, and guidelines on how to express the limitations and trade-offs to users to allow them to make best decisions given their needs. 

The design research output (UX design mockups and guidelines document) will be directly usable by implementers wishing to integrate web archiving functionality into existing tools, and provide actionable next steps for a variety of browser interface, including browser extensions such as Webrecorder's ArchiveWeb.page, native browser implementations, and Electron-based browsers such as Agregore and the ArchiveWeb.page App.


### Implementation (IMPL)

*Worked performed by: Ilya Kreymer, Ed Summers, and Mauve (Georgi S)*

The implementation phase will begin during the second half of the grant and will be focused on implementing the output of the other two tracks, the WACZ specification and UX research into new and existing tools in support of browser-based web archiving.

The goal will be to ensure the web archiving output can work with different systems and even different browsers.

The implementation work will encompass the following:

- Updates to the [py-wacz](https://github.com/webrecorder/wacz-format/tree/main/py-wacz) command-line tool for creating and verifying web archives according to the latest specification.

- Improvements to the [ReplayWeb.page](https://github.com/webrecorder/replayweb.page) (and core [wabac.js](https://github.com/webrecorder/wabac.js)) replay systems to ensure that they can read web archives according to the latest specification, particularly any new approaches to indexing, full-text search, metadata, standalone loading, and loading from IPFS.

- Improvements to the [ArchiveWeb.page](https://github.com/webrecorder/archiveweb.page) system will be made to ensure the system can write web archives according to latest specification, including storage to IPFS.

- The [Agregore Browser](https://github.com/AgregoreWeb/agregore-browser), an existing Electron-based browser which already provides support for several p2p protocols, including IPFS, but currently lacks the full Chrome extensions API necessary for web archiving to be supported, will be updated with the necessary extension APIs. Aregore will then be updated to fully support running the ArchiveWeb.page extension natively in Argregore with IPFS storage.

- Updates to ArchiveWeb.page UX to support output of UX research, such as privacy preserving workflows.

## Total Budget Requested

The total budget requests is $100,000. The breakdown of the budget is associated with the deliverables of each milestone, defined above.

## Maintenance and Upgrade Plans

The goal for the storage specification is to enter into a formal standardization process, such as with IETF or W3C, and to follow the guidelines
associated with those processes for creating a long-term standard. The ux research may be updated as needed in the future.
The existing open source tools that will be updated are already being maintained, either by Webrecorder or in case of Agregore Browser, by Mauve Software,
and will continue to be maintained by those organizations.

# Team

## Team Members

The staff for the project will consist of:

- Lead Developer & Project Lead, Webrecorder - Ilya Kreymer
- Project Manager, Webrecorder - Lorena Ramírez-López
- UX Research - [New Design Congress](https://newdesigncongress.org/en/about), led by Cade Diehm
    - [New Design Congress Team](https://newdesigncongress.org/en/team)
- Technical Writing / Specification Research Dev - Ed Summers
- Agregore Integration Developer - [Mauve Software](https://software.mauve.moe/)

## Team Member LinkedIn Profiles

- Ilya Kreymer - https://www.linkedin.com/in/ilya-kreymer-55110093/
- Lorena Ramírez-López - https://www.linkedin.com/in/lorena-a-ramirez-lopez/
- Cade Diehm - https://www.linkedin.com/in/shibacomputer/
- Ed Summers - https://www.linkedin.com/in/esummers/
- Mauve/Georgi S. - https://www.linkedin.com/in/georgiy-s-47697579/

## Team Website

- https://webrecorder.net/ - for Webrecorder team
- https://newdesigncongress.org/ - for New Design Congress

## Relevant Experience

- The Webrecorder project has been focused on addressing these limits by pushing the capabilities of web archiving technologies through open source tools and new formats in support of high fidelity digital web preservation. Webrecorder tools are grounded in some of the formats and techniques of the web archiving community but designed to work with the web browser itself, with the goal of making high-fidelity web archiving available to all. The Webrecorder project seeks to accomplish this by pushing the limits of what browsers can do, either through browser automation, creating browser extensions, or helping to influence changes in future browsers to make improved save and archive capabilities a core feature.

- Ilya Kreymer has worked in the web archiving field for 10 years. He started the Webrecorder project in 2014, previously working at the Interent Archive on their Wayback Machine software.

- Lorena Ramírez-López is currently a developer and community manager for Webrecorder. She was previously the project manager for the [Media Conservation Initiative](https://www.mediaconservation.io/) and handled the budget, fellowships, and workshop logistics.

- Cade Diehm is a systems theorist, researcher and founder of the New Design Congress, a non-profit organisation developing a nuanced understanding of technology's role as a social, political and environmental accelerant. He has spent ten years embedded in tech infrastructure and security projects in six countries. New Design Congress' multi-year research focus includes designing new decentralised identity paradigms (current collaborations with [Ink & Switch](https://www.inkandswitch.com/backchannel/) and [Radicle](https://radicle.xyz/)), collaborative infrastructure design, and [embedded economic systems](https://stream.undersco.re).

- Ed Summers is a design researcher and software developer working at the [Maryland Institute for Technology in the Humanities](https://mith.umd.edu). For the last 25 years he has worked in the field of digital preservation and the web, in government, business and academic settings. During that time he worked as a technical writer and developer on the [Simple Knowledge Organization System](https://www.w3.org/TR/skos-primer/) (SKOS) and [RDFa](https://www.w3.org/2006/07/SWD/RDFa/tr-metadata/) W3C standards. While working at the Library of Congress he helped create a reference implementation and write the initial drafts of the [BagIt File Packaging Format](https://datatracker.ietf.org/doc/html/rfc8493) (RFC 8493).

- Mauve is a decentralized software consultant and has worked on grants for Protocol labs as well as a wide range of peer to peer projects.
One of their focuses has been on making peer to peer web technologies more accessible via the [Agregore Browser](https://agregore.mauve.moe/) project.

## Team code repositories

Existing code repositories that will be updated in this work:

- https://github.com/webrecorder/wacz-format include the spec and https://github.com/webrecorder/wacz-format/py-wacz for python WACZ library.
- https://github.com/webrecorder/wabac.js
- https://github.com/webrecorder/archiveweb.page
- https://github.com/webrecorder/replayweb.page
- https://github.com/AgregoreWeb/agregore-browser

# Additional Information

## Advisors

In drafting the specification, we will seek input and feedback from various experts and interested parties in the fields of decentralized protocols and web archiving. The list of advisors will expand as we start work, and currently includes:

- Jim Pick @jimpick
- @phiresky

## Further / Follow-Up Work

This project will define a core specification for browser-based, user-driven web archiving and produce usable UX research for implementors to begin to support browser-based archiving. The goal of the implementation work will be to integrate the bulk of the updated WACZ format specification into existing tools
(py-wacz, ArchiveWeb.page, ReplayWeb.page) and to begin implementing the work from the UX research into ArchiveWeb.page and ReplayWeb.page.

Some follow-up work that can be undertaken at the completion of the six month period will be as follows:

- Implementation of automated web archiving system, such as performed by a browser-based crawler like Webrecorder: [Browsertrix Crawler](https://github.com/webrecorder/browsertrix-crawler) at fixed intervals and depositing data to p2p/decentralized systems automatically 'at scale'. The specification for this use case will be well defined, and will be well-positioned to begin implementation of such a system.

- A C++ library for creating WACZ web archives. The Python and Javascript libraries, such as py-wacz and wabac.js will be updated during this period, paving them for a C++ implementation afterwards.

- Full implementation of encrypted storage. The specification and UX research will focus on defining the threat models and requirements, and the specification will define the low-level requirements for encrypted web archive storage, positioning us to proceed with full implementation after this six month period.

- Further design research into context-driven navigation systems for larger, multi-contributor archive projects.

- Development of a broader political framework for assessing private archive systems.
