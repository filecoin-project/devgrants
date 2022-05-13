# RFP Proposal: `FVM - AssemblyScript SDK`

**Name of Project:** FVM - AssemblyScript SDK 

**Link to RFP:** 

**RFP Category:** `devtools-libraries`

**Proposer:** `ainhoa-a`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT, GPL, and APACHE2 licenses?:**  Yes

# Project Description

In the context of the FVM Early Builder program, we propose to build a set of tools to facilitate the use of AssemblyScript to write new smart contracts that will be compiled to WASM code at the end. WASM is what FVM uses to run smart contracts.

Nowadays, there are two SDKs for FVM smart contracts: Go and Rust. However, none of these languages is as popular and widely used as Javascript.  AssemblyScript is part of the Javascript/Typescript family but it compiles to WASM. 

To contribute to the growth of the ecosystem, it would be valuable for FVM to allow users to write smart contracts using this language. 

## Development Roadmap and Deliverables
### Milestone 1  - Deep dive into the FVM  /  Growing the filbuilders community 

**Assumptions/Pre-Requirements**

- Access to the Rust SDK roadmap and development team is granted.
- Weekly call with Rust SDK dev team or at least a representative.

**Technical Scope**
- Run Hello World FVM (Lotus Go Library)
- Run Hello World FVM (miniVM - Docker or similar)
- Update Assemblyscript FAQ
- Modelize FVM methods on AssemblyScript
- List the entire set of methods FVM have now
- Create definition file with functions signature (name, params, return)
- Create context objects to allow access to contract-related data, such as caller address, gas used, contract balance, etc.
- Create storage objects to allow access to get and set functions which will allow the contract to read and persist data.

A tentative list of functions would be the following ones. 
- Current_account_id
- Signer_account_id
- Block_timestamp
- Block_index
- Storage_usage
- Account_balance
- Used_gas
- Gas_limit
- Storage_write
- Storage_read
- Storage_remove
- Storage_has_key

**Deliverables:**
- AssemblyScript SDK v0.1
- Assemblyscript FAQ
- Basic documentation about FVM (within the scope of AssemblyScript)
- Hello World tutorial and examples
- Testing CI workflows   
- Document FVM functions and minimal API 

**Funding for this Milestone**
tbd- $ 

**Estimated Milestone Delivery**
 End of June 22 

### Milestone 2   -  With  AssemblyScript to  to hell and back - The sky is the limit 

**Assumptions/Pre-Requirements**

This phase requires a close collaboration with the Assemblyscript team; it would also be valuable to collaborate with NEAR (they are pioneers in this area). A detailed planning of meetings shall be agreed at the project setup. 

Development of additional libraries  (eg. c-bor library for storage) and access to certain resources is required. 

The availability of these pre-requirements is mandatory to acomplish the Milestone 2. A close collaboration between the parties may avoid any delay. 

**Technical Scope:**

- Create data structures using FVM basic methods: arrays, maps, queues, calls to other contracts, and more. 
- Create utility packages 
- Base64 Codec
- Filecoin address support (AssemblyScript)
- Common maths operations for FVM

**Deliverables:**

Both data structures and utilities packages:
- AssemblyScript SDK v0.2
- Extended documentation
- Updated CI workflows
- Advanced tutorials and applications
  - ERC20 like example  
  - Lottery example
  - Simple Bank example

**Funding for this Milestone**
tbd- $  

**Estimated Milestone Delivery** 
 End of August 22 

### Milestone 3   - Entering the Custom Types

**Assumptions/Requirements**
Completion of Milestone 2

**Technical Scope:**
- Support user custom types (based on AssemblyScript classes).
- Evaluate different data efficient type encodings.
- Type Serialization/deserialization. 

**Deliverables:**
- Allow custom types using AssemblyScript helper classes
- Updated Documentation
- Updated CI workflows
- Advanced tutorials and applications
  - Simple Storage
  - Advanced storage concepts

**Funding for this Milestone**
tbd- $ 

**Estimated Milestone Delivery**
Beginning of October 22

### Milestone 4    - Reaching the developers & Promoting the ecosystem Growth

**Assumptions/Requirements**
Completion of Milestone 3

**Technical Scope:**
- Explore some in-browser IDE with pre-loaded projects (using GitHub templates)
- Collect community feedback and target specific contract examples
- Update Assemblyscript FAQ

**Deliverables:**
- Improved developer experience
- Extra tutorials with more complex logic
- Videos

**Funding for this Milestone**
tbd- $ 

**Estimated Milestone Delivery**
End of November 22


## Total Budget Requested

- M1  tbd- $ 
- M2  tbd- $    
- M3  tbd- $ 
- M4  tbd - $ 

Total: 

## Estimated delivery overview

- M1  End of June 22  
- M2  End of August 22    
- M3  Beginning of October 22
- M4  End of November 22

## Maintenance and Upgrade Plans

We would like to continue with further development after M4, but this is out of scope for this proposal. 
This should be agreed either at a later time or in the frame of another program.

# Team

## Contact Info and Team Members


* Emmanuel Murano
  * Role: lead development
  * [Github](https://github.com/emmanuelm41) 
  * [LinkedIn](https://www.linkedin.com/in/emurano/)

* Lola Rigaut-Luczak
  * Role: development, research
  * [Github](https://github.com/rllola)
  * [LinkedIn](https://www.linkedin.com/in/lola-rigaut-luczak-17422a17/)

* Prateek Rathod
  * Role: development, review and documentation 
  * [Github](https://github.com/lawRathod)
  * [LinkedIn](https://www.linkedin.com/in/prateekrathod/)

* Ainhoa Aldave
  * Role: project management
  * [Github](https://github.com/ainhoa-a)
  * [LinkedIn](https://www.linkedin.com/in/ainhoaaa/)


As we are a team of over 20 engineers at Zondax, more members may be added later if support or specific skills are needed. 

## Team Website

`https://zondax.ch/`

## Relevant Experience

We have been collaborating with PL for several years and have/or are currently contributing to the following projects:  Signing Tools (WASM/Typescript and FFI support, Secp256k1 and BLS support) Filecoin Indexing, Filecoin GPU Scheduler,  Exchanges & Custodian technical support among others. 

## Team code repositories

`https://github.com/Zondax`


## Additional information

We would like to be part of this program in order to:

- contribute to the growth and expansion of the Filecoin ecosystem 
- have an early exposure to this new technology. 
- have the opportunity to contribute to the design and architecture at early stages.
- drive innovation in AssemblyScript areas. 

This aligns with our willingness to work towards fully decentralized networks, collaborate with Blockchain cost-effective solutions and build Interoperability standards that are key to foundational protocols. 