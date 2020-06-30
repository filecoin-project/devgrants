To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: distributed market documentation

**Name of Project:** distributed market documentation automation

**Proposal Category:** Choose one of `app-dev`

**Proposer:** brianebert

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Marketplaces comprise significant use of the internet.  Decentralized exchanges offer advantages, such as maintaining custody of one's funds while trading, and the ability to trade assets an exchange is not prepared to process.  Unless a token trading has already become well known, discovering what a given offer signifies can be arduos and error prone.  Neither is it easy for a token issuer to link information about their offer to an asset being traded.

To address those issues I write documentation pertaining to tokens trading on a blockchain's marketplace into IPFS.  Required documentation of the token includes its unique offer ID.  The IPFS hash is written indellibly in a signed blockchain transaction which enters the offer into the exchange.   A similar operation binds statements of identity, also stored in IPFS, to public keys, thus binding identifying documents of both participants and wares in a distributed market.  The process is very simple for users, promising use of distributed exchanges for transaction in a wide variety of goods and services.

While I link self authenticating documents indelibly with market offers, buyers and sellers, the storage of the data depends upon entrepreneurs getting storage offers to market participants.  I will seek storage deals for market users' documents among Filecoin storage providers.

The fastest approach to doing so appears to be colocating a lotus server with my ipfs repo and taking advantage of itegration with ipfs offered in lotus's documentation.  Any problems with this approach leave options available to change storage servers from ipfs to filecoin, or otherwise integrate the two services while keeping the existing ipfs repo.

## Value

Expansion of distributed exchanges from tokens to tokenized general goods and services explodes available markets, growing storage requirements with each transaction.  Filecoin storage uptake among marketplaces, social networks, and other service providers will homologate the experience of sharing data while remaining in control of it.  Leaving data siloed among service providers threatens one rational for a distributed web.

## Deliverables

Deliverable 1: A user interface enabling storage purchase for description documents bound to buy or sell offers in a public market.
Deliverable 2: Colocated lotus server requesting storage offers and executing available deals.
Deliverable 3: Revision of user experience based on learnings in 1 & 2, striving for easy entry agreements.

## Development Roadmap

I'm sorry, but this is too much to ask at this stage.   I would like instead to make a couple cautionary remarks.  I love Filecoin with most of the fibers of my heart, because it makes work proved in proof of work algorithms useful.  That is the biggest improvement in blockchains since bitcoin.  Its retrieval spec however may render the technology useless; it's too early to tell.

My third deliverable is hard to describe right now for lack of experience with the technology.  Say I offer to sell a hamburger, but a prospective hamburger buyer near me has to wait two minutes if they click on the link for the hamburger's descriptiom document?  What kink of ux can I make so the user comes back to the market when they want to buy something?  Nothing occurs to me at this point.

I solved this problem for myself with ipns.  The name binding I mentioned second paragraph of this Project Description exists because I could not wait for ipns to resolve names.  Mine works realy fast, is served from any blockchain node, and is Olog2.  I will work with Filecoin with the same dissatisfaction I found with ipns, looking for workarounds like I can share for ipns.

I don't expect things to be perfect, but I do expect that between technology providers and application developers, we need to create distributed services that can supplant existing service analogs seamlessly from the user's point of view.  If  you spend your money helping me integrate Filecoin to what I've done, we will at least have a experimentation article to ask: what if a user wants to buy or sell something in a market stored exclusively with ipfs &/| Filecoin.

## Total Budget Requested

Deliverable Time(mo) Cost($K)
  1             1       5
  2             1       5
  3             2       10
  
  Total elapsed time: 4 mos
  Total cost:         $20K

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

I've already covered quite a bit of this.

## Team code repositories

Here's a wannabe wysiwig text editor that outputs html, which I've integrated to an IPFS backend.  Integration is split between index.html and ckeIpfs.js: https://rocketgit.com/user/brianebert/editor

# Additional Information

I serve everything I mention out of IPFS.  It isn't ready to live in the wild yet.  If you want to see it, I'll show you everything I mention operating.
