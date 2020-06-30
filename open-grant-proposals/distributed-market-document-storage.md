# Open Grant Proposal: distributed market document storage

**Name of Project:**  distributed market document storage

**Proposal Category:** Choose one of `app-dev`

**Proposer:** brianebert

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Internet users expect to find markets at their fingertips.  Decentralized exchanges offer advantages, such as maintaining custody of one's funds while trading, and the ability to trade a broad assortment of assets an exchange is not prepared to process.  Unless a token has already become well known, discovering what a given offer signifies can be arduous and error prone.  Neither is it easy for a token issuer to bind published information to a market asset.

To address those issues I write documentation pertaining to tokens trading on a blockchain's marketplace, into IPFS.  Required documentation of the token includes its unique offer ID.  The IPFS hash is written indelibly in a signed blockchain transaction which enters the offer into exchange.   A similar operation binds statements of identity, also stored in IPFS, to public keys, thus binding identifying documents of both participants and wares in a distributed market/exchange.  The process is very simple for users, promising use of distributed exchanges for transaction in a wide variety of goods and services.

While I link self authenticating documents indelibly with market offers, buyers and sellers, the storage of the data depends upon entrepreneurs getting storage offers to market participants.  I will seek storage deals for market users' documents among Filecoin storage providers.

The fastest approach to doing so appears to be colocating a lotus server with my ipfs repo and taking advantage of integration with ipfs offered in lotus's documentation.  Any problems with this approach leave options available to change storage servers from ipfs to filecoin, or otherwise integrate the two services.

## Value

Expansion of distributed exchanges from tokens to tokenized general goods and services explodes available markets, growing storage requirements with each transaction.  Filecoin storage uptake among marketplaces, social networks, and other services will homologate the experience of sharing data while remaining in control of it.  A user-centric data model divests data giants advantage to develop learning models, which will become more useful and perhaps more invasive without vigilance.  Leaving data siloed among service giants threatens one rational for a distributed web.  It also leaves them burning loads of electricity looking for sales-worthy data relations.  I'm proposing data storage for distributed markets as a step.  What do you think?

## Deliverables

|Deliverable|description|
|:---:|---|
|1|(a) An api enabling storage purchase for description documents bound to buy or sell offers in a public market|
||(b) A browser ui talking to the (a)|
|2|Colocated Filecoin server requesting storage offers and executing available deals under cli control|
|3|Revision of user experience based on learnings in 1 & 2|

## Development Roadmap

I'm sorry, but this is too much to ask at this stage.   I would like instead to make a couple cautionary remarks.  I love Filecoin with most of the fibers of my heart, for its proof of *useful* work.  Its retrieval spec however may threaten uptake; it's too early to tell.

I offer to sell a hamburger, but a prospective hamburger buyer near me has to wait two minutes if they click on the link for the hamburger's description, what kind of ux can I make so the user comes back to the market when they want to buy a pizza?  Nothing occurs to me at this point.  I'm more likely to find an answer once I dirty my hands.

I solved a similar problem for myself with ipns.  DNS demands faster resolution than a page load.  The name binding I mentioned second paragraph of this Project Description exists because I could not wait for ipns to resolve names.  Mine works really fast and is served from any blockchain node.  If Filecoin in fact exhibits excessive retrieval time, I might propose workarounds for that too.

I don't expect things to be perfect, but I do expect that between technology providers and application developers, we need to create distributed services that can supplant centralized services seamlessly from the user's point of view.  Yuval Harari says efficient distributed data processing may be a necessary capability in order to avoid authoritarianism.  If  you spend your money helping me integrate Filecoin to what I've done, we will at least have a experimentation article to ask: what if a user wants to buy or sell something in a market stored with ipfs and Filecoin.

Since this is the roadmap section, I'll finish by mentioning that blockchain algorithms should end up running as services on distributed file systems.  We will choose when to distribute trust, and when to abstract it.  All proofs of work abstracting trust will accomplish useful things, like storing data or exposing market offers, or helping people find information.  (The forgoing paragraph with Louis Armstrong, "What a wonderful world" in the background, and golden sunrise.  And a yellow brick path winding its way toward the orb.)


## Total Budget Requested

|Deliverable|Time(mo)|Cost($K)|
|:---:|:---:|---:|
|1|1|5|
|2|1|5|
|3|2|10|
|total|4|$20|

I would appreciate early payments corresponding with any early delivery.

## Maintenance and Upgrade Plans

To the best of my ability...

# Team

## Team Members

Brian Ebert

## Team Member LinkedIn Profiles

None, sorry


## Team Website

https://motia.com

## Relevant Experience

I've already covered quite a bit of this.  I also know other things; who knows in the end what will prove relevant.

## Team code repositories

Here's a wannabe wysiwig text editor that outputs html, which I've integrated to an IPFS data store.  Integration is split between index.html and ckeIpfs.js: https://rocketgit.com/user/brianebert/editor

# Additional Information

I serve everything I mention out of IPFS.  It isn't ready to live in the wild yet.  If you want to see it, I'll show you everything I mention operating and you're more than welcome to monitor my repos during developments you fund.
