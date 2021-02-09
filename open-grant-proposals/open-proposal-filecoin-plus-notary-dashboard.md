**Name of Project:** Filecoin Plus Notary Dashboard

**Proposal Category:** App-dev

**Proposer:** Digital MOB

# Project description:

The purpose of the Filecoin Plus Notary dashboard is to make it possible to easily see which Fil+ Notaries approved which Clients, how many Verified Deals each client has, and with how many miners.

## Deliverables:

The Dashboard will have the following functionalities:
* The ability to switch between a notary view and a client view.
* The notary view shows a list with all the Fil+notaries along with the following information: Notary ID, Address, No of Verified Clients/,  Datacap allocated, and Datacap Available. The user will have the possibility to see an expanded view of verified clients and an expanded view of Verified Deals as per the wireframe: https://whimsical.com/notaries-MYTDFcDbe6J281snkFt7bX. Each Deal ID will link to the filecoin.tools dashboard.
* The client view shows a list with all the verified clients along with the following information: Verified Client ID, Address, Notary ID, Verified Deals, the no. of miners the client made deals with, Datacap allocated and Datacap available.
* Search functionality. Inside each view, the user can search based on different params: Notary ID, Address, Client ID, Deal ID. The search can also be used as a filtering tool.
* Export csv functionality.

In order to extract in a reliable manner all info relating to the fil+ system, we plan to monitor state changes of the verified registry actor (f06). If a state change occurs, we can deduce what happened based on the allowance changes and verifier / verified clients counts.
After we know what event happened (add verifier, add verified client, make a verified deal, etc.), we can search through the messages in that tipset to gather more info. For example, if a verified client data cap decreases and there is no change related to verifiers it means that the client made a verified deal. We can extract more info related to the deal by looking at messages sent to the market actor (f05) and finding the one that's relevant to this deal.
All this data can be accessed via a public API and displayed in various ways.

## Project timing:
For the above functionalities, 1 month of development is required.

## Resources:

The project requires the following resources:

| Role                 | DMOB Provided Resources | Allocation     |
| :---                 |    :----:               |           ---: |
| Designer             | 1                       | 40%            |
| Frontend Developer   | 1                       | 60%            |
| Backend Dev          | 1                       | 100%           |
| Project Manager      | 1                       | 40%            |
| DevOps               | 1                       | 20%            |

## Budget:

The requested budget is $32000


