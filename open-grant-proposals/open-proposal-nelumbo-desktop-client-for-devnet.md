# Open Grant Proposal: `Nelumbo - MacOS Desktop Client For Local Devnet`

**Name of Project:** `Nelumbo`

**Proposal Category:** `devtools-libraries`

**Proposer:** `jehunter5811`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** `yes`

# Project Description

When developing applications for the Filecoin network, it is important to have a fast, easy-to-use development network for quick iterations. Developing against a deployed testnet 
is not ideal, and Filecoin already provides a local devnet. However, the local devnet requires a lot of command line configuration which gets in the way 
of the ultimate goal—building an app. 

Nelumbo is designed to solve this problem by making a local devnet as easy to start as launching a desktop app. As Filecoin progresses and matures, there will be more and 
more developers building apps without running their own Filecoin nodes (see Ethereum as an example of this). As such, an easy to use local blockchain for Filecoin is imperative. 

Nelumbo will allow developers to start a Lotus local devnet blockchain with just a click of the mouse. It will expose API methods to help speed up the development process. It will also have 
a built-in block explorer to help developers quickly see the results of their code. By making Filecoin development easier, the entire ecosystem can expand. That process starts with 
making application development atop Filecoin more accessible through an easier to use version of the local devnet. 

## Value

Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:

If we get this right, we will be providing a tool that will bring Filecoin development exposure to a much wider audience. There is an entire class of developer who 
does not want to learn DevOps procedures just to build their application. Those developers need tools that will help them interfae with Filecoin in an easier way. That starts 
with the local devnet. The intention here is to make development easier, and when you do that, more developers can participate in the community. A vibrant community benefits everyone.

Getting this wrong could mean turning developers off to Filecoin. This is why it's so important focus on the user experience. Thus far, Filecoin has been exclusively accessible to very technical developers. 
Getting this wrong would mean Nelumbo did not improve the experience enough for less technical developers to get invovled. 

The risks that make executing this project difficult include a range of things, but most challenging is the possibility that the network evolves in a way that 
development is not possible without expensive machines. Developers should have accessible solutions both in terms of technology and the machine cost overhead. With Filecoin, 
we've already seen the expenses piling up when running things in production. A major risk is that to even run a local devnet, the hardware requirements will price us out and in turn price out other developers. 

## Deliverables

The Nelumbo project will deliver a total self-contained MacOS applications, dstributed in `dmg` and `.zip` format. It will run on all modern Macintosh systems and will create a user interface atop the Filecoin local devnet. 
This application will include functionality to install a Lotus local devnet, start the devnet, stop the devnet, and integrate with external projects (starting with IPFS). The interface will include tools to help make development
 easy, including API documentation, a block explorer, and wallet generation tools. 
 
 *Spec* 
 
 * Native MacOS application (built in Electron)  
 * Automated checks for Lotus binaries  
 * One-click install option  
 * One-click start option  
 * One-click stop option  
 * Local block explorer  
 * API documentation (including a built-in NodeJS SDK)  
 * Visual configuration editing (no need to edit the config.toml manually)  
 * IPFS integration  
 * Wallet creation  
 * FIL Transfer  
 
 The application will be written in NodeJS/Electron, but all UI and core functionality will be implemented in HTML and plain JavaScript to ensure as wide a range of open source contribution potential as possible. 

## Development Roadmap

Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section).

### Milestone 1  
*Upgradeable desktop client that will install Lotus, start lotus, and stop lotus.* 

This milestone is the most important milestone because it lays the foundation for everything else. A working proof of concept can be seen here: 

[POC](https://twitter.com/polluterofminds/status/1310340115332505601)

However, the proof of concept needs considerable work before it can be released as a "Milestone 1" deliverable. Work on Milestone 1 that still needs to be completed is:  

* Support for current versions of Lotus (POC only supports up to v0.7.0)  
* Functionality to start Lotus and Miner when everything has previously been installed  
* Performance improvements around starting the Lotus client and the miner  
* Proper Lotus shutdown on app close  
* Error handling  
* In-app notifications of updates
* Pipeline to deliver updated code 

The Milestone 1 release will allow developers from all background to download Nelumbo, install it on their Mac, and start a Lotus blockchain on their local machine. This is important because it creates 90% of the core functionality 
developers need to build their applications. In fact, some developers may not need much more than Milestone 1. That said, Milestone 1 is only the start to getting a much wider array of developers involved in Filecoin.

*People Involved:*
* Justin Hunter  

*Expected Hours:*  
* 50

*Expected Days:*  
* 20

*Expected Budget:*  
* $5,000 USD

### Milestone 2 
*Local Block Explorer*  

While it would be possible to repurpose an existing block explorer, the Nelumbo explorer should be built with its specific use-case in mind. The features of the explorer will include: 
* Search for transactions 
* Search for wallets 
* Get wallet balance 
* Search for miners 
* Filter results 
* Provide click-through for more detail on wallets, deals, messages, miners, and more
* CSV export (this is important for creating automated load testing scripts)

This Milestone will largely be focused on UI/UX, but it will also be touching many of Lotus's API methods and will be a good opportunity to start documenting the API info that will be used in Milestone 4.

*People Involved:*
* Justin Hunter  

*Expected Hours:*  
* 25

*Expected Days:*  
* 12

*Expected Budget:*  
* $2,500 USD

### Milestone 3  
**API Documentation**  

This milestone is more than just documentation. It is an opportunity to educate developers on available Lotus API methods while teaching them how to use the gRPC API. 
This milestone will include both documentation and functionality to execute tests (i.e. similar to postman).

*People Involved:*
* Justin Hunter  

*Expected Hours:*  
* 10

*Expected Days:*  
* 5

*Expected Budget:*  
* $1,000 USD

### Mileston 4  
**Visual Lotus Configuration**

Currently, configuring Lotus requires manual edits of the `config.toml` file. This can be challenging, especially when many developers new to the ecosystem will not 
know where to find that file. This milestone will focus on making edits to that file visual. 

This milestone will include a simple form-based interface with validation to support proper configuration updates. For example, a field that says `Use Ipfs` with a simple radio button for yes or no. 
An interface like this will significantly speed up development time for most developers. It will also improve the experience immeasurably.

*People Involved:*
* Justin Hunter  

*Expected Hours:*  
* 15

*Expected Days:*  
* 6

*Expected Budget:*  
* $1,500 USD

### Milestone 5  
**Finishing Touches**  

This milestone will be focused on polish and a lot of the nice-to-haves. Specifically, this milestone will focus on enabling one-click start for the IPFS daemon that a user might want to integrate with. *Note: installing IPFS is outside the scope of this project.* Additionally, 
this milestone will include new wallet creation, FIL transfer functionality, and any necessary UI clean-up needed. 

This milestone is the one that will allow Nelumbo to be a fully realized application with on-going support focused on maintenance, bug fixes, and upgrades. As new features are added to Lotus, successful execution of this milestone will 
make updates and new features significantly easier to add. 

*People Involved:*
* Justin Hunter  

*Expected Hours:*  
* 20

*Expected Days:*  
* 10

*Expected Budget:*  
* $2,000 USD

## Total Budget Requested

$12,000  

All expenses will go toward development costs. See each milestone for estimated development costs.

## Maintenance and Upgrade Plans

Nelumbo will be maintained and upgraded for the forseeable future. PR will be reviewed timely and community contributions will be encouraged. However, core maintenance will 
fall on myself and anyone else who joins the team.

# Team

## Team Members

- Justin Hunter
- ...

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/justin-hunter-b30a1b80/
- ...

## Team Website

https://nelumbo.dev

## Relevant Experience

Justin Hunter has founded two prior companies in the blockchain space—Graphite and SimpleID. In both cases, he was exposed to the phenomenal community that builds around blockchain projects. He delivered successful, heavily used applications. He is currently working with Pinata 
on both their IPFS and Filecoin solutions. His expertise with Lotus development makes him the perfect person to build this project.

## Team code repositories

Graphite: https://github.com/graphite-docs/graphite 
SimpleID: https://github.com/simplesecure 
Pinata: https://github.com/PinataCloud/Pinata-SDK

# Additional Information

I have personally experienced the challenges of building applications that interface with Lotus, so I am well-equipped to deliver on this project. I know how developers work, how they think, and what they need. I also have the Lotus client experience necessary to build this. 
