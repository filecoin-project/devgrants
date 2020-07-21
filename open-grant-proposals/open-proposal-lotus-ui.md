# Open Grant Proposal: `Lotus UI`

**Name of Project:** LotusUI

**Proposal Category:** `app-dev`

**Proposer:** `RobQuistNL`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Since I've been working out how to use Lotus and setup a (small scale) miner, there were quite a few hurdles to jump. 
Mostly its lack of documentation, but once I got that figured out, getting decent reports of performance / processes 
running wasn't really trivial. There's a lot of commands and environment variables to know about, and a fairly good 
understanding of the lower-level architecture is required. In the end I spent a lot of time figuring out the proper way
to compile, install, and run the software. Most of the issues can be solved by improving documentation (also working on that),
but then there's still a lack of neat and organized metrics / control.

This project tries to solve those issues by providing a simple piece of software that manages a lotus installation. Compilation,
installation, hardware requirements, connectivity with the network, and detailed statistics / metrics about the miner
as well as the hardware its running on. A simple dashboard with some of the most important metrics was my initial wish.

Extending that into a simple package / script that can be ran in order to install every dependency and provide the user with a 
simple web-interface should lower the bar for the less-experienced (or lazy, like me) miners.


## Value

- What are the benefits to getting this right?
Having a single piece of software managing updates, dependencies, requirements and checking hardware greatly reduces the time (and required knowledge) to set up a miner / full node. This in turn will lower the bar for people to join the network, increasing its power.

- What are the risks if you don't get it right?
If this software does not work well - it could end up frustrating the user, driving the user away from the Filecoin ecosystem.
If the software is buggy - results _could_ be catastrophic - imagine accidentally deleting wallet keys or sealed sectors due to a bug. Possible, as this software would manage a lot.

- What are the risks that will make executing on this project difficult?
I personally don't have that much time available, and I don't have a lot of experience with the lotus / filecoin code itself. 

## Deliverables

- Simple installation of the software (probably a single line `curl | sh`) on the desired machine
- This installation will spawn a web-server through which the user can manage the next installation steps;
- The software will be able to install, update and manage a lotus daemon node.
- The software will be able to install, update and manage a lotus miner node.
- Detailed statistics and performance reports about sectors, mined blocks, CPU, GPU, storage and memory usage.

Ideas:
- Windows version as a simple packaged installer. Would allow people to run a lotus fullnode (or even miner) on their windows machine. Requires https://github.com/filecoin-project/lotus/issues/2133 to be fixed.

## Development Roadmap

As of now, for each milestone, I (RobQuistNL) would be the only person working on it.

- Simple dashboard on single machine, running both daemon and miner, with statistics about sectors pledged and resources used.
- ETA: Already functional

- Installation tool for LotusUI - installing the Web UI, as well as the lotus binaries, and management thereof (including updates)
- ETA: end July 2020

Managing multiple nodes might be a long-term goal - depends on how difficult it will end up being. Right now I'm developing this software on a single machine that runs both the miner and the daemon. Will be adding a second machine shortly, and will try to add that in the dashboard too. My main target would be a simple overview of mining statistics.

## Total Budget Requested

USD 2000 (?)

Mainly as compensation for time spent on development. I already have hardware and software (IDE) in my posession to develop with - no real costs other than time.
Regardless of the compensation, I will be working on this software as I would personally like to use it. Added a grant proposal as that
was adviced. Any compensation received will probably go towards mining hardware :)

## Maintenance and Upgrade Plans

As far as I can tell now, my plan is to keep a miner around and manage it with this software. Will probably keep adding improvements as I see fit.

# Team

## Team Members

- Rob Quist (@RobQuistNL)

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/webdevver/

## Team Website

https://dukesoft.nl/

## Relevant Experience

- Rob Quist
12+ years of PHP experience - back-end developer in PHP. Currenty employed by Enrise. Currently working on an API serving around 1 million active mobile telecom customers. Experienced in (multiplayer) game development (Unreal Engine, GML, NodeJS, custom game engines), dev-ops, SQL-databases, CI / CD, embedded software development, some cryptocurrency mining experience. Developer & maintainer of an open source package manager / coding standards guide for GameMaker (https://gamemakerhub.net). Some frontend experience. Home automation - also through a similar setup, using a Raspberry Pi with a custom web-interface controlling infrared devices (TV's), 433mhz RF controlled homebrew PCB's, weatherstations, dashboard on TV, voice recognition etc (https://github.com/RobQuistNL/PieStation). 

## Team code repositories

https://github.com/RobQuistNL

# Additional Information

Please note that I will be working on this software regardless of the grant. The initial plan is to release it under MIT license, allthough that might change if required for the devgrant. I've added this proposal on recommendation of @eshon, hoping to gain more attention and possibly help / feedback.

I've rushed this document - if you have any questions or notes, please let me know!
