# Open Grant Proposal: `Decentralized Social Network`

**Name of Project:** Gravity

**Proposal Category:** `app-dev`

**Proposer:** [@npfoss](https://github.com/npfoss/)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

<!--
Please describe exactly what you are planning to build. Make sure to include the following:
- Start with the need or problem you are trying to solve with this project.
- Describe why your solution is going to adequately solve this problem.

This section should be 2-3 paragraphs long.
 -->

The first truly decentralized, private, full-featured social network.
Naturally, built with IPFS and ideally stored with Filecoin.

The dominant network, Facebook (/Instagram) has repeatedly disregarded user privacy, common decency, and laws around the world,
and people are finally starting to care en masse:
42% of people in the US reported taking a break from Facebook in the year after Cambridge Analytica,
and Facebook is losing users in the US by the tens of millions.
The US is behind Europe in terms of privacy consciousness, but even here people have lost trust in Big Tech and there's real demand for alternatives.
However, while some offer privacy, federation, or novel features, not even Matrix or Secure Scuttlebutt (SSB)
free you from reliance on some third party which could turn around and charge an unreasonably high price for their service.

Gravity's unique solution is to decouple the data itself from the client you use to view it _and_ the host where it's stored,
so anyone can frictionlessly move their data between apps and hosts as they choose,
not trapped with anyone and always able to interact with the rest of the network without their friends noticing the change.
This is only possible with content-addressing.
When you have to request from a particular _location_ to read messages (e.g. gmail.com),
it becomes much harder to switch if that entity misbehaves.
However, if you're requesting by hash or IPNS ID, it can come from anyone on the network and the requester is agnostic;
leaving each person free to swap out message sources as they please.
In this kind of system, there can be many totally independent apps which all interoperate and compete with each other, optimizing for the user instead of the advertiser.
We are proposing to build the underlying protocol and the first app which uses it.
Unlike most privacy-focused platforms we intend to be more than just a messenger and, in a user-friendly way, fully replace all of Facebook's rich functionality,
including the news feed, posts, groups, etc, plus additional proven features such as custom reacts and message threads.

You can read the entire system design [here](https://courses.csail.mit.edu/6.857/2019/project/17-Foss-Pfeiffer-Woldu-Williams.pdf), but in summary:
Everyone's profiles are encrypted-at-rest blobs of data on IPFS which anyone can download but only the people you choose can decrypt.
This is possible because the friending process is an exchange of public keys (though of course the user never has to think about key management).
These profiles are structured in such a way that friends can read individual messages out directly without having to test-decrypt hundreds of potential messages, yet from looking at the encrypted profile no one can tell who you're talking to or how often.
One big distinction from SSB is that you don't have to connect to a pub for other people to see your posts and messages;
thanks to IPFS, as long as your most recent hash is published under your public key
(which we also had to build and overlay for since the DHT is slow)
and someone on the network has cached the relevant pieces, anyone in the world can request your profile without having to know where to look.
Of course, some of the time, especially in the beginning, none of your friends will be online during some periods of time,
so we are also running a server to pin everyone's profiles and make sure they're always available.
As soon as it's ready, we hope to transition that storage to Filecoin very naturally, and allow users to do so themselves instead of trusting us to be storing their (encrypted) data.


<!-- Looking at the options currently available, you would think there's an inherent trade-off between privacy and usability. -->



## Value

<!--
Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:
- What are the benefits to getting this right?
- What are the risks if you don't get it right?
- What are the risks that will make executing on this project difficult?

This section should be 1-3 paragraphs long.
 -->

### Benefits of Success

If we succeed in building a viable Facebook alternative with a large user base,
it would be a huge increase in the usage of IPFS and a massive spike in demand for a service like Filecoin,
which of course is the most natural choice for decentralized storage of IPLD data.
More broadly, it would provide a service (third-party-independent rich social networking) better than the current options,
which is _not possible_ without content addressing, i.e. the IPFS and Filecoin ecosystem,
and prove them as a useful, practical platform for massive consumer adoption and widespread use.
Gravity would be the poster child of how powerful IPFS applications can be.

### Benefits of a Flop

Even if we build this system, launch it, and fail to get many users, we'll have contributed a significant piece to the ecosystem.
For example, Orbit is pretty old, but is still one of the most polished apps that people point to as an example of what you can make on IPFS.
We have already reached that level of polish and functionality, and Gravity takes advantage of the full functionality of IPFS, not just pubsub.
Worst case, what we have now is an example of a powerful, functioning IPFS app that you can point to on awesome.ipfs.io.

Better yet, we've already open sourced the basic protocol, so anyone could pick that up and potentially succeed where we failed, or at least make their own app which is interoperable.
It is a novel and interesting distributed system in its own right.

Milestone 1 is all about making this 'example IPFS app' as impressive, useful, and full-featured as possible,
pushing the limits of what has currently been demonstrated on IPFS.

### Costs of a Flop

Low, which is the point of the milestone system.
We only get funded for the parts which succeed by design, and the 'flop' case above is what we're starting from
(albeit as an encrypted messenger right now, not a full-fledged social network).

If it doesn't hit Milestone 2 and never begins to take off,
then you're still left with that great example of what can be done (technically) in this ecosystem.

### Risks and Difficulties

The network effect is our biggest challenge, certainly bigger than any technical one.
We’ve already built the basic foundation and it works.
The only room for unknown unknowns on the technical side is how well it will scale,
but we designed everything to be at worst on the order of your number of friends between profiles,
and almost entirely constant within a single profile,
so while we’re sure there will be unexpected bumps it seems unlikely that any will be fatal.

Ultimately, to most people, what makes a social platform the most valuable is if their friends are on it,
and solving this chicken and egg problem is key.
We recognize this and think that launching first at MIT, then other universities is the best shot,
in part because we're well connected to that community and the people there are more friendly towards new tech.
Very importantly, universities are also densely connected subgraphs, making it easier to get a majority of each person's friends online.
We have a few tricks up our sleeves in the MIT case as well,
such as potential support from the administration and the ability to pre-generate groups and invites.

While this largest challenge is nontechnical, we think we are uniquely positioned to have a good chance at overcoming it.

## Deliverables

<!-- Please describe in details what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished. -->

Firstly, an open source, general purpose, decentralized, privacy-preserving protocol anyone can use for social networking apps which all interoperate out of the box.
Second, the first webapp built on that protocol, which has a modern user-friendly UI and features such as: instant messaging, groups (with nicknames, etc), bcc-ed posts to subsets of your friends and a news feed to aggregate them, custom reactions to messages and posts, and a message threading system better than the standard append-only log.
For the ecosystem: more IPFS nodes on more computers, increased invisibility, and a strong source of demand for exactly Filecoin's use case.

## Development Roadmap

<!--
Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section).

For each milestone, please describe:
- The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates)
 -->

### Milestone 0

A proof-of-concept fully encrypted group messaging protocol and webapp with friending, named groups, nicknames, and plaintext messaging.
Plus a draft landing page with some information on how it works and a detailed whitepaper, for good measure.

Amount requested: $0

[**Done**](https://www.gravitynet.io/)

### Milestone 1

Complete the protocol to be able to handle the rest of the immediate feature set for a full social network,
and build them into the webapp so people can actually use them.
These include:
- removing/blocking people and other group management
- images
- custom reacts
- powerful threading
- bcc-style posts and a news feed
- multi-device support (transferring your identity, AKA 'logging in' from elsewhere)

This would get us solidly through the 'flop' outcome at the very worst.

Roles: 2 full stack developers

Time: 2 months (est. June completion)

Amount requested: $12000

### Milestone 2

Adoption and growing pains.
Average 500 daily active users over a 7 day period.

It will take a large effort to overcome the network effect and start to swing it in our favor,
but that is a crucial element for the goal outcome of getting IPFS nodes in the homes of everyday internet users.
Along the way there will surely be unexpected issues to deal with, from bugfixes to performance bottlenecks to increasing numbers of peers,
so we're adding plenty of buffer to deal with those and keep polishing the UI.

For context, SSB consistently has [100-200 DAUs](https://ssb.celehner.com/activity/),
and they get a decent amount of press from just that.

Roles: 2 full stack developers

Time: 2 months (est. August completion)

Amount requested: $12000


### Milestone 3

Store profiles in a decentralized way with Filecoin.
They're already cached by friends, but for 100% uptime and freshness of your profile an Amazon S3-like service is currently needed.
As soon as Filecoin goes live, it becomes a much better choice!

Roles: 2 full stack developers

Time: 1 month after Filecoin mainnet launch

Amount requested: $0, or maybe some FIL to get started.
We expect this to be easier and cheaper than using AWS to back up profiles,
so we'd love to make the switch as soon as possible.


## Total Budget Requested

<!-- Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds. -->

Total: $24000

Our opportunity cost of spending a summer on this (and some of the spring semester) is a tech internship which pays \~$30k total,
so we intend to use this to pay ourselves $12k each to cover living expenses and have some extra take-home income.
We already have some cloud credits through MIT to cover the low compute and hosting costs.

## Maintenance and Upgrade Plans

<!-- Specify your team's long-term plans to maintain this software and upgrade it over time. -->

If it's successful enough, we may even take a leave of absence to continue to work on it full time,
but in the worst case we expect to be active users ourselves,
so we'll continue to fix bugs and add features throughout the following semesters.
We know this is reasonable to do since we're already been finding time to work during the semester.

In the case where we don't maintain it well, don't address issues quickly enough, or try to extort our users,
anyone is free to fork our code and make their own interoperable apps which users could switch to frictionlessly and without losing any of their friends or data.

The protocol was designed from the outset to be flexible and upgradeable,
and that's something we think a lot about as we implement everything.

# Team

## Team Members

- Nate Foss: [LinkedIn](https://www.linkedin.com/in/npfoss/) and [personal site](https://npfoss.com/)
- Georgia Shay: [LinkedIn](https://www.linkedin.com/in/georgiashay) and [personal site](https://georgia.shay.net/)

## Team Website

<!-- Please link to your team's website here (make sure it's `https`) -->

[https://gravitynet.io/](https://gravitynet.io/)--
draft site to host the POC encrypted messaging app, advertise some features, and link to related in-depth resources (such as the whitepaper and some Medium posts).

## Relevant Experience

<!-- Please describe (in words) your team's relevant experience, and why you think you are the right team to build this project. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc. -->

Nate and Georgia have been working together for over a year on a course planning tool used by thousands of MIT undergraduates (courseroad.mit.edu), and historically have been a great team.

Georgia has experience with a variety of javascript frameworks including Angular, Vue, and Express.
She has professional experience using python for signal processing, computational geometry, and backend design.
She helped launch that course planning website written in Vue in spring of last year,
and has also completed hackathon projects involving data visualization and mobile app development.

Nate has been working with IPFS for a while now, and has been active on IRC (via Discord) and the forums.
He first used `js-libp2p` over a year ago to build a simple p2p MMO game,
and since then has gotten to know it and `js-ipfs` very well through his work on Gravity.
Meanwhile, he led the team which developed that course planning tool, thoroughly rounding out his webdev experience.
Before switching to focus on trustless distributed systems a few years ago, he spent a lot of time thinking about and working on AI, especially game-playing AI,
which was interesting but isn't terribly relevant to Gravity besides being another six years of general programming experience.
Nate’s professional experience includes internships at Applied Predictive Technologies (now a part of Mastercard) and Cruise Automation,
the latter of which involved working on the Tracking & Perception team and writing code which currently drives itself around San Francisco.


## Team code repositories

<!-- Please provide links to your team's prior code repos for similar or related projects. -->

- The Gravity protocol underlying the current encrypted messenger: [https://github.com/npfoss/gravity-protocol/](https://github.com/npfoss/gravity-protocol/)
- CourseRoad, a course planning tool for MIT students which we worked together on and use the same frontend framework for: [https://github.com/sipb/courseroad2](https://github.com/sipb/courseroad2)

# Additional Information

<!-- Please include any additional information that you think would be useful in helping us to evaluate your proposal. -->

We're two MIT undergrads who have been working on Gravity for a while in our spare time,
but we know that to take it to the next level and get meaningful adoption we need to be able to focus on it full time for at least a summer.
Unfortunately, we're both in the position that we can't afford to not have income for a summer,
and don't want to commit to dropping out yet, as we would have to were we to secure VC funding.
This grant program is the perfect way to get Gravity off the ground,
both for its scale/scope and because this ecosystem is one of the very beneficiaries of us working on it.
