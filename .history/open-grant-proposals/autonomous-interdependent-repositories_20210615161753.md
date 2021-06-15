# Open Grant Proposal: `Autonomous Interdependent Repositories`

**Name of Project:** Autonomous Interdependent Repositories

**Proposal Category:** `devtools-libraries`

**Proposer:** [artem-v-shamsutdinov](https://www.linkedin.com/in/artem-shamsutdinov-1b5910/)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

- The problem: 

Distributed Applications (DApps) lack an easy-to-use database layer.

The new DApps are gaining more functionality, getting more complex and 
currently the number of applications devs is limited due to a steep 
learning curve.   For the majority of Software Engineers (who are used 
to working with relational databases) it is hard to write applications 
with complex data schemas.

- Our solution:

AIRport is a reference implementation of
[Autonomous Interdependent Repositories](https://patents.google.com/patent/US10902016B2).

AIRport provides a net-like relational database of Repositories.  Repositories
are virtual databases, each with its own transaction log.  Each Repository has
a globally unique identifier that allows to distinguish it from other 
repositories in the same relational database (such as WebSql, or SqLite in 
a Cordova based App). For two Users to share a Repository it must be present 
on their devices, and the schemas used by that repository must be installed
in AIRport databases on those devices.

![AIR reposiories](presentations/images/AIRport_diagram_2.png)

Each device/phone contains a single AIRport database that is shared by all
applications on that device.  The composition of the applications on each
device can be different.  The composition of the schemas installed in each
AIRport database on each device can be different as well.  Each database
contains only the Repositories the user of that device decides to keep on it.

![AIR across devices](presentations/images/AIRport_diagram_1.png)

## Value

Our target users are developers for Distributed Applications.  AIRport allows
multiple applications to share the same schemas.  It also allows to 
independently track data as Repositories.  A Repository is a virtual database
tracked in a number of tables across any number of schemas.  At a high level,
it's a "virtual interface" between applications and schemas.

This:

* Allows the Application End Users to seamlessly share the data only with 
  selected Users.
* Lowers the barrier to entry for new Apps as they can reuse existing schemas 
  or write add-on functionality to existing Apps.
* Lowers the barrier to entry by providing exiting data to new Apps.
* Allows hybrid applications where part of the data is centralized (for 
  large scale sharing) and part is in private Repositories.
  

    For example in an event tracking App data for each event is a separate Repository.
    Other Applications can build upon this App's schema and provide functionality
    (such as  event specific chat and voting systems) in their own schemas. Using all
    of these Apps the users add data to the same Repositories (for the the same
    events).  Thus Repositories for events span schemas of all the Apps that together
    provide better functionality than each one separately.  AIRport enables synergies
    between Apps where "the whole is greater than the sum its parts" thus reducing the
    overall costs.

- The benefits to getting this right

Each repository is completely autonomous and can be added to a host relational
database and/or removed from it, at any time, without affecting other
repositories.  Repositories can have references to each other thus depending
on data that other repository contains, but must be usable without referenced
repositories (thus being both interdependent and autonomous).

AIRport Repositories have blockchain based transaction log storage to enable
communication between devices.

AIRport offers refined, high productivity developer APIS:
  
* Simplified JPA annotations (no session concept, easier relations)
* GraphQL like query API
* GraphQL/Firebase like hybrid solution for mutation & access rules
* Automatic schema generation and installation

AIRport is fully functional off-line, commits are made locally and are added
to the "longest chain" once device is back on-line.

- The risks:

Project is completely thought out and largely coded with a granted patent, risks of 
getting it wrong mostly relate to it being "developed in a vacuum".  In order to
ensure that AIRport does not diverge from requirements of real applications we
are developing a seed application - Votecube.  Votecube has a complex relational
schema and various persistence and validation needs.

The seed project is completely thought out and its most complex part is coded,
  the need for automatic reviews of articles based on multiple dimensions is
clear and present (there are already working solutions out there with manual
reviews from multiple points of view, we are now just taking it to the next
level with automatic, and thus large scale, processing 3D interfaces, and
aggregate analysis).  The more basic break down interface will be based on the
same (already thought out and implemented schemas) and will also be based on
existing UI implementation (will add a simpler 3D axis based UI. for example: 

```
X-axis: Liberal - Conservative
Y-axis: Left Wing - Right Wing
Z-axis: Traditional - Progressive
```

The key risk is in figuring out how to monetize on the platform.
  Our current thinking is building a distributed advertisement engine that
  will solve the problem of big organizations retaining user data to provide
  relevant ads.  This should be doable with a combination of personalized tensor
  based model, and an anonymized data collection for a group of centralized models.
  The monetization is the difficult part of the project, we have the experience
  to get it done [Nik Dobrinov](https://www.linkedin.com/in/nikolaydobrinov/) on
  central modeling and [Andrei Belitski](https://www.linkedin.com/in/dr-andrei-belitski-178b3a75/)
  on AI and we are working on how we'll make data anonymous for high definition 
  model building.

## Deliverables

- Artem Shamsutdinov

A relation database central to the device (which it is running on) with a
localhost-only web API for native and web applications (as well as a 
web-only trial version of the application).
  
Shared virtual repositories (via independent transaction logs) based on IPFS DAG.

- Nikolay Dobrinov

A centralized (high precision) advertisement model based on anonymous user data.

- Andrei Belitski

A local tensor based (or newer tech if available) advertisement engine.

- [Brian Gill](https://www.linkedin.com/in/brian-gill-1353b21/)

A seed application source: Full implementation of the seed project
[Votecube](https://github.com/votecube) 
([Prototype](https://votecube.com/#!/poll/info/Cube/vote/kBSVLFHn01lMtvPXYIzu/4vz9cPyZiMoaGG4JOh6t))).
AIRport documentation.

## Development Roadmap

- Artem Shamsutdinov
    
    * Functionality:
        
        Final working framework
    
    * People:
      
        1 person - framework developer
  
    * Required organizational finding (salary/org expenses/taxes/cryto converson tax/fees):
      
        $150000
  
    * Timeline
    
        1. Finish core framework - 6 month
  
        2. Finish device integration - 1 month
  
        3.  Integrate with IPFS DAG - 1 month
  
        4.  Integration test framework/device/DAG combination - 1 month  
  
        5.  Integrate local tensor model - 1 month
        
        6.  Integrate centralized ad models - 1 month  
        
        7.  Integration test complete solution - 1 month
  
        Total time:
      
        1 year

- Nikolay Dobrinov
  
    * Functionality:
  
        High precision advertisement engine
    
    * People:
      
        1 person - researcher/implementer
      
    * Required organizational finding (salary/org expenses/taxes/cryto converson tax/fees):
        
        $170000
      
    * Timeline

        1. Research Python & tools - 1 month
    
        2. Develop Votecube web article processing statistical model - 2 month
  
        3. Implement core Ad modeling code - 4 month
  
        4. Train/Tune/Test core modeling solution - 3 month
  
        5. Integrate with core framework and local AI solution - 1 month
  
        6. Final modeling adjustments - 1 month

        Total time:
      
        1 year

- Andrei Belitski
  
    * Functionality:
      
        Local personalized advertisement engine
    
    * People:
      
        1 person - researcher/implementer
    
    * Required organizational finding (salary/org expenses/taxes/cryto converson tax/fees):
        
        $170000
      
    * Timeline

        1. Develop Votecube web article processing engine AI - 2 month
        2. Implement core local ad AI solution - 4 month
        3. Train/Tune/Tst core modeling solution - 3 month
        4. Integrate with core framework and central modeling solution - 1 month  
        5. Final modeling adjustments - 1 month

        Total time:
        
        1 year

- Brian Gill
    * Functionality:
      
      High impact seed application
      
    * People:
        
        1 person - application developer
      
    * Required organizational finding (salary/org expenses/taxes/cryto converson tax/fees):
      
        $150000
      
    * Timeline

        1. Technology ramp up - 1 month
        
        2. Finish Votecube seed project (thus demonstrating usage of framework with a complex schema) - 5 month
        
        3. Integrate Votecube seed project with core framework and centralized segment (assist in API finalization 
           and core testing and distirbuted/central hybrid solution) - 1 month  
        
        4. Integrate final solution with IPFS DAG and central component - 1 month
        
        5. Document core framework - 3 month  
        
        6. Integration test the app on the complete solution (with local and central Adds) - 1 month

        Total time:
      
        1 year

- Off-shore Block-chain development team
    * Functionality:

      Integration with Filecoin infrastructure.

    * People:

      Off-shore dev team - will pick a veteran blockchain team that has relevant experience.

    * Required organizational finding (contract fees/org expenses/taxes/cryto converson tax/fees):

      $60000

    * Timeline (starting 5 month into the project)

        1. Project ramp up and prototyping - 1 month
    
        2. Bare-bones implementation & integration - 2 month
    
        3. Full featured implementation & integration - 4 month

      Total time:

      7 month

- Totals
    * Project start date August 1st 2021
    * Project completion date August 1st 2022

## Total Budget Requested

    * Salary + Benefits
        Artem Shamsutdinov:               $130000
        Nikolay Dobrinov:                 $140000
        Andrei Belitski:                  $150000
        Brian Gill:                       $130000
        Off-shore Block Chain Dev Team     $60000
    * Hardware rental (AWS):               $10000
    * Operational Overhead:                $90000

    * Total cost:                         $710000


## Maintenance and Upgrade Plans

We will be seeking additional funding for the next year of operation to:

1. Fix bugs in core framework and develop new framework features

2. Improve centralized advertisement model

3. Improve localized advertisement engine

4. Fix bugs in Votecube & add new features

5. Write an additional seed application

6. Advertise seed applications

7. Popularize the technology

# Team

## Team Members

- Artem Shamsutdinov
- Nikolay Dobrinov
- Andrei Belitski
- Brian Gill

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/artem-shamsutdinov-1b5910/
- https://www.linkedin.com/in/nikolaydobrinov/
- https://www.linkedin.com/in/dr-andrei-belitski-178b3a75/
- https://www.linkedin.com/in/brian-gill-1353b21/

## Team Website

[https://dataindependence.net](https://dataindependence.net)

## Relevant Experience

Dr. Nikolay Dobrinov - extensive experience in statistical model research 
and implementation

Dr. Andrei Belitski - extensive experience in AI, neural networks research 
and implementation

Brian Gill - overwhelming experience in application development

Artem Shamsutdinov - inventor of the technology and implementor of the
core framework

## Team code repositories

https://github.com/autonomous-interdependent-repositories

https://github.com/votecube

# Additional Information

1. AIRport framework greatly aids development acceleration of distributed
   applications.

The process of installing AIRport is:

*  User navigates to a consumer Application that uses AIRport and creates
   a Repository
*  Application prompts the user to install AIRport database App (if not
   installed already)
*  User installs AIRport App
*  The consumer application creates the private Repository and prompts 
   to add other participating users
*  Creating user shares the Repository, and the App notifies new users

![AIRport as Cordova application](presentations/images/AIRport-in-Cordova.png)

AIRport Repositories have blockchain based transaction log storage to enable
communication between devices. AIRport is fully functional off-line, commits
are made locally and are added to the "longest chain" once device is back on-line.
Each Repository transaction log is a separate chain and itself can consist of
sub-chains if devices go out of sync. Thus, the Repository transaction log is a
Directed Acyclic Graph with each commit being a separate block and all
sub-chains are resolved to the "longest chain" via timestamp based conflict
resolution mechanism.

    For examle if Alice modifies record 1 while being offline and Charlie
    modifies the same record also offline but at a later time then both
    with be notified of the conflict and automatic conflict resolution
    will pick the latest column values while allowing for manual confict
    resolution.

![AIR Transaction Log](presentations/images/AIRPort_Transaction_Log.png)

Based on my current limited understanding of blockchains:

A Repository chain can be integrated with IPFS since it supports DAG
datastructure and is storage centric.  Integrations with other chains 
are possible: A Repository chain can be tied to the chains of the
individual chains of creators/participators in the Repository.  In
turn, those can be integrated into any 3.0 blockchain.

Core to AIRport is the idea is for multiple applications to collaborate 
and re-use data.  The two key points here are:

* User is in control of their data they allow applications to access 
  their data (usually only a part of their data).
* Applications are in control of sharing schemas with other applications 
- they can allow or deny access to their schemas.

This the applications only interact with the device-local database, making AIRport
fully operational in offline-mode.  The database is in charge of maintaining the
repositories contained in it.  It may occasionally prompt the user to purge
infrequently used repositories (or may do so automatically if not configured),
leaving them only in the cloud backup.  The applications however may request the
user to load additional repositories from the cloud, for processing.

AIRport aims to provide zero code deployments where a thin shim is provided
for the framework and TypeScript interfaces are used to define the
query+mutation API against the schemas used by the application.  The rest
is defined in the schema configuration file, which is loaded into the
device's AIRport database directly.  The config file is generated from
the annotated Entities and the DAO code, which itself relies on
auto-generated TIQL (Typescript Instrumented Query Language ) objects
and interfaces as well as core framework code and generated Base DAO objects.

2. The time for Votecube decentralized decision-making system is at hand:

Existing businesses are doing manual reviews of articles from multiple points
of view (centrist, left and right).  We have the experience to do better 
with automated processing of a much larger number of articles and 
statistical analysis on the aggregate information.  A new 3-Dimensional UI 
in the Votecube project will display 3 dimensional positional graph for each
article and for all articles in on the topic.  Dimensions could be many, but
we'll be showing the ones most relevant for the topic (as determined by AI
algorithms and per article automated statistical analysis).  For example for
political articles the dimensions could be:

X:  Liberal - Conservative
Y:  Left - Right
Z:  Traditional - Progressive

Each individual article will be automatically evaluated for its position 
on these axes, and a graph will be presented for this article.  An additional
aggregate 3-D graph across all evaluated articles on the issue will present
the overall picture of the public opinion.

The new UI will allow users to add their input on the article in terms of 
providing their own position of the article's position on the selected axis
and allow adding comments on a forum.

Then based on distilled information from each article the "contrast cube" will 
be constructed. This aggregate cube will be based on the dimensions with 
the "strongest" ratings and will allow easy user voting on the topic.
