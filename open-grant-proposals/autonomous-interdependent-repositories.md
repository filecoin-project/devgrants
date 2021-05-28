# Open Grant Proposal: `Autonomous Interdependent Repositories`

**Name of Project:** Autonomous Interdependent Repositories

**Proposal Category:** `devtools-libraries`

**Proposer:** [artem-v-shamsutdinov](https://www.linkedin.com/in/artem-shamsutdinov-1b5910/)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

- The problem: 

Distributed Applications (DApps) lack an easy-to-use database layer.

The new DApps are gaining more functionality, getting more complex and currently the number of applications devs is limited due to a steep learning curve.   For the majority of Software Engineers (who are used to working with relational databases) it is hard to write applications with complex data schemas.

- Our solution:

AIRport is a reference implementation of [Autonomous Interdependent Repositories](https://patents.google.com/patent/US10902016B2).

Our target users are developers for Distributed Applications.  AIRport allows multiple applications to share the same schemas.  It also allows to independently track data as Repositories.  A Repository is a virtual database tracked in a number of tables across any number of schemas.  Each device/phone contains a single AIRport database that is shared by all applications on that device.  The composition of the applications on each devices can be different.  Also the composition of the schemas installed in each AIRport database on each device can be different as well.  Each database contains only the Repositories the user of that device desides to keep on it.  This:

* Allows the Application End Users to seamlessly share the data only with selected Users.
* Lowers the barrier to entry for new Apps as they can reuse existing schemas or write add-on functionality to existing Apps.
* Lowers the barrier to entry by providing exiting data to new Apps.
* Allows hybrid applications where part of the data is centralized (for large scale sharing) and part is in private Repositories.

For example in an event tracking App each event can be it's own Repository.  And there maybe addional Apps share the schema with this App and provide functionality such as calendar, chat, docs.  The additional apps will still add data to the sare Repositories represeting the same event, with those Repositories now spanning schemas of different Apps.

![AIR across devices](presentations/images/AIR-across-devices.jpg)

The process of installing AIRport is:

*  User navigates to a consumer Application that uses AIRport and creates a private Repository
*  Application prompts the user to install AIRport database App (if it's not installed already)
*  User installs AIRport App and navigates back to the application
*  The consumer application creates the private Repository and prompts the user for who to share it with
*  User shares the repository and the other users of that repository are notified

AIRport provides a net-like relational database of Repositories.  Repositories are virtual databases, each with it's own transaction log.  
Each Repository has a globally unique identifier that allows to distinguish it from other repositories in the same relational
database (such as WebSql, or SqLite in a Cordova based App). For 2 Users to share a Repository it must be present on their devices and the
schemas used by that repository must be installed in AIRport databases on those devices.



## Value

![AIRport as Cordova application](presentations/images/AIRport-in-Cordova.png)

- The benefits to getting this right

Each repository is completely autonomous and can be added to a host relational database and/or removed from it,
at any time, without affecting other repositories.  Repositories can have references to each other thus depending
on data that other repository contains, but must be usable without referenced repositories (thus being
both interdependent and autonomous).

Initial AIRport deployments will have server components to enable communication between mobile devices.
In it's final form AIRport could be used directly between devices to communicate
changes in the state of repositories shared between their members (based on some form of
[mobile device-to-device Web Access](https://patents.google.com/patent/WO2019036410A1)).

![Autonomous Interdependent Repository sharing](presentations/images/Figure02.png)


- The risks:

Project is completely thought out and largely coded with a granted patent, risks of getting it wrong
  are minimal.

The seed project is competely thought out and its most complex part is coded,
  the need for automatic reviews of articles based on multiple dimentions is
clear and present (there are already working solutions out there with manual reviews from
multiple points of view, we are now just taking it to the next level with automatic,
and thus large scale, processing 3D interfaces, and aggregate analysis).  The more basic break down
interface will be based on the same (already thought out and implemented schemas)
and will also be based on existing UI implementation (will add a simpler 3D axis
based UI. for example: 

```
X-axis: Liberal - Conservative
Y-axis: Left Wing - Right Wing
Z-axis: Traditional - Progressive
```

The key risk is in figuring out how to monetize on the platform.
  Our current thinking is building a distributed advertisement engine that
  will solve the problem of big organizations retaining user data to provide
  relevant ads.  This should be doable with a combination of personsalized tensor
  based model and a anonomized data collection for a group of centralized models.
  The monetization is the difficult part of the project, we have the experience
  to get it done [Nik Dobrinov](https://www.linkedin.com/in/nikolaydobrinov/) on
  central modeling and [Andrei Belitski](https://www.linkedin.com/in/dr-andrei-belitski-178b3a75/)
  on AI but we are presently not sure exactly how we'll make data anonymous
  for central model building (initial thought is to one way hash all of PI).

## Deliverables

- Artem Shamsutdinov

A relation database central to the device (which it is running on) with a localhost-only
web API for native and web applications (as well as a web-only trial version of the application).
  
Best in breed, high productivity developer APIS:
  
* Simplified JPA annotations (no session concept, easier relations)
* GraphQL like query API
* GraphQL/Firebase like hybrid solution for mutation & access rules.  
  
Shared virtual repositories (via independent transaction logs) based on IPFS DAG.

- Nikolay Dobrinov

A centralized (high precision) advertizement model based on anonymous user data.

- Andrei Belitski

A local tensor based (or newer tech if available) advertisement engine.

- [Brian Gill](https://www.linkedin.com/in/brian-gill-1353b21/)

A seed application source: [Votecube](https://github.com/votecube), partial prototype: [votecube.com](https://votecube.com/#!/poll/info/Cube/vote/kBSVLFHn01lMtvPXYIzu/4vz9cPyZiMoaGG4JOh6t)
with a complex relational schema and a forward thinking opinion gathering
engine & UI.

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
        
        2. Finish Votecube seed project (thus demonstrating usage of framework with a complex schema) - 4 month
        
        3. Integrate Votecube seed project with core framework and centralized segment (assist in API finalization and core testing and distirbuted/central hybrid solution) - 1 month  
        
        4. Integrate final solution with IPFS DAG and central component - 1 month
        
        5. Document core framework - 4 month  
        
        6. Integration test the app on the complete solution (with local and central Adds) - 1 month

        Total time:
      
        1 year

- Totals
    * Project start date August 1st 2021
    * Project completion date August 1st 2022

## Total Budget Requested

    * Salary + Benefits
        Artem Shamsutdinov:   $130000
        Nikolay Dobrinov:     $140000
        Andrei Belitski:      $150000
        Brian Gill:           $130000
    * Hardware rental (AWS):   $10000
    * Operational Overhead:    $80000

    * Total cost:             $640000


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

Artem Shamsutdinov - inventor of the technology and implementor of the
core framework

Dr. Nikolay Dobrinov - extensive experience in statistical model research and implementation

Dr. Andrei Belitski - extensive experience in AI, neural networks research and impelentation

Brian Gill - overwhelming experience in application development

## Team code repositories

https://github.com/autonomous-interdependent-repositories

https://github.com/votecube

# Additional Information

1. AIR technology and AIRport framework are absolutely necessary to accelerate
development of distributed applications in general.

2. The time for Votecube decentralized decision-making system is at hand:

Existing businesses are doing manual reviews of articles from multiple points
of view (centrist, left and right).  We have the experience to do better 
with automated processing of a much larger number of articles and 
statistical analysis on the aggregate information.  A new 3-Dimensional UI 
in the Votecube project will display 3 dimensional positional graph for each
article and for all articles in on the topic.  Dimensions could be many, but
we'll be showing the most relevant once for the topic (as determined by AI
algorithms and per article automated statistical analysis).  For example for
political articles the dimensions could be:

X:  Liberal - Conservative
Y:  Left - Right
Z:  Traditional - Progressive

Each individual article will be automatically evaluated for its position 
on these axes an a graph will be presented for this article.  An additional
aggregate 3-D graph across all evaluated articles on the issue will present
the overall picture of the public opinion.

The new UI will be largely based on the existing technology for the cube,
with different look and feel.  It will also allow users to add their
input on the article in terms of providing their own positioning of the
article on the evaluated axis and allow to add comments on a forum
(partially designed and implemented).

Then based on the information from each article the current cube will 
be constructed with the default positioning of the automatic rating.
This aggregate cube will be based on the dimensions with the "strongest"
ratings.  It is the visualization that makes user voting on the topic
easy (based on highly distilled information).
