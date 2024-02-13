# Open Grant Proposal: `BitBlock`

**Name of Project:** BitBlock

**Proposal Category:** `app-dev`

**Proposer:** `PatrickNercessian`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

Popular video-sharing platforms, such as TikTok and YouTube, extract large portions of value from creators and viewers. Most of the advertising revenue is kept by the centralized company for servers, employees, investments, and profit. A decentralized competitor could alter these categories in ways that allow for a significantly larger portion of revenue to go to users.
  
Centralized data storage servers can be replaced with IPFS, and Filecoin can augment this storage by ensuring that videos can persist indefinitely. Centralized computational servers can be replaced with local computation and with smart contract blockchains, such as Cardano, in which computation is decentralized and automatic. Costs associated with employees are unnecessary, as the platform can be managed and developed by a Decentralized Autonomous Organization (DAO). Additionally, unless the DAO decides otherwise, most investments are unnecessary (as scaling to user growth can happen automatically). Finally, and perhaps most importantly, the concept of profit extraction does not exist in this model.  
  
All of these (previously necessary) costs can instead be funneled into users’ wallets, which would attract new viewers and creators and incentivize the creation of better content. To implement these decentralized and financial concepts, I propose an application that takes advantage of decentralized data storage (through IPFS and Filecoin) and decentralized computation (through local devices and Cardano) to allow users to upload their own videos and stream others’ videos while retaining the large majority of advertising revenue they generate.

## Value

If successful, this project would benefit the Filecoin ecosystem by drastically increasing the demand for storage on the Filecoin network. The Filecoin network has about [26 Petabytes](https://file.app/) of actual data storage, or about 0.25% of the available storage on the network [(10 Exabytes)](https://filfox.info/en). An increase in demand for data storage on the network would dramatically improve the state and reputation of the overall ecosystem. Although clearly an upper bound, 500 hours of content are uploaded to YouTube every minute. At a conservative 1GB per hour of video, that's 250PiB each year. If BitBlock achieved even 1% of that amount, that would increase the useful storage on Filecoin by over 10% in a single year.
  
If not successful, the risks to the Filecoin ecosystem are nonexistant. Although not existentially blocking for the application, there may be some difficulties in executing certain features of this project:
1. The application requires videos to be stored on both IPFS and Filecoin, and current services pairing the two together (such as [Textile](https://docs.textile.io/)) are "undergoing rapid development" and may be difficult to incorporate and maintain.
2. Widespread adoption will require videos to load sufficiently quickly, and it remains to be seen whether this can be achieved through IPFS/Filecoin.
3. Creating a competitive recommendation algorithm may prove difficult with only one developer and a necessity of using local computation.

## Deliverables

The final deliverable for this project will be a web application which allows creators to upload video content and viewers to watch content. Uploaded videos should be stored on IPFS (for ease of access) and Filecoin (for persistence of data). A novel cryptocurrency token on Cardano will be used by advertisers to pay to advertise on the platform. These payments will funnel into users' wallets: viewers will receive payments for watching advertisements, and creators will receive payments for each view of their content.

Ideally, this will eventually translate into a mobile application which provides a very simple user experience so that cryptocurrency laymen can easily access their funds, watch videos, and upload content.

## Development Roadmap

### Uploading and Downloading
_One part-time developer -- 1 week -- $500_

A proof-of-concept web application. This will consist of a basic user interface and a TypeScript backend which connects to Textile's Hub. A hypothetical user should be able to: "log in" with their private key (or generate a new one), view a list of their buckets, create new buckets, view the contents of each bucket, select a local video file, and upload a video file to a specific bucket.

Using Textile's archive services, buckets should be stored on Filecoin's network as well. Retrieving through both IPFS and Filecoin should be possible and tested.

### Display Videos from Global Database
_One part-time developer -- 1 week -- $750_

1. A 'global' database (either through Textile's ThreadDB or Buckets) of video's CIDs and their metadata (such as uploader public key, timestamp, etc.)
2. Upon prompting, the application should choose a (temporarily random) CID and then download the video. Preferably, rather than downloading to the hard drive, the web app should simply display the video.
3. (Optional) The most recent downloaded videos should be cached on the local application's IPFS node. This should be tested on multiple devices in order to ensure that the viewer is properly caching and serving the file.

### Video Ownership
_One part-time developer -- 3 weeks -- $2500_

1. Pair a Cardano wallet address to the application.
2. Create a 'user-info' bucket for each user. For now, this will just contain the user's video CIDs and Cardano public key.
3. Mint a new Cardano NFT for each video upload, containing the same data as the records in the global database (CID, public key, timestamp, etc.)

### Improve User Interface and Expanded Data Collection
_One part-time developer -- 3 weeks -- $3000_

User interface should be ready or near-ready for production release. Users should be able to:
1. 'like' videos and 'follow' creators. 
2. search for specific creators. This will likely require a customizable username to be paired with each public key
3. view a creator's page which shows their videos, follower count, username, etc.

The network should store as much data as is economically viable.
1. Add public keys of each 'liker' to each record in global database
2. Add watch history, likes, follows, followers to user-info bucket

### Basic Recommendation Software
_One part-time developer -- 2 weeks -- $2000_

Use local computation to decide which CIDs from the global database to present to the user. Should start out basic, can use more advanced techniques later in production.

### Cardano Token and Smart Contracts
_Unknown -- $0_

1. Create a relevant token on Cardano.
2. Create a Plutus smart contract for seed funding: receives ADA and returns the new token
3. Implement smart contracts which allow advertisers to use tokens promote their content
4. Implement smart contracts which pay viewers and creators.

The y-th video shown to a viewer will be randomly selected from a global database of “promoted” videos, rather than the global database of “user” videos. y will be a random integer between, say, 5 and 15. This will keep advertisements from monotonously becoming a story of “every y videos I’ll see an ad”. The y range can actually be set individually by each viewer, so they could choose to not see any advertisements at all (and thus forego any income).

Advertisers will be able to upload and promote content through the application. In fact, users themselves will be able to promote their own content through the application, blurring the line between advertisers and users (although a “[Sponsored]” flag will always be displayed when a viewer is shown promoted content). After uploading a normal video, advertisers/users will be able to sign a smart contract promoting their video a certain number of times. This will cost a certain amount “per-view”.

For example, let’s say Company X wants to show their advertisement to 1000 people, and it costs 0.01 tokens per view. After uploading their video, they will sign a smart contract transaction which sends 10 BitBlock tokens (name TBD) to the BitBlock DAO along with “CID: xyz” and “numPromotedViews: 1000”. Every time a viewer is shown the promoted video, they sign a smart contract which decrements the numPromotedViews on that video and awards them some BitBlock tokens for watching an advertisement. When numPromotedViews reaches 0, the advertisement is no longer displayed to viewers.

This is a clear target for malicious actors and botnets, which is why using smart contracts seems to be the best option rather than allowing users access to the global database. Additional security decisions may be necessary such as daily limits on ads watched per user and/or a minimum required balance for a user to be able to participate in these smart contracts. Furthermore, the economics of viewers receiving payments from DAOs and sending payments for gas fees must be automatically balanced to ensure that viewers are always net positive for having watched an advertisement.

As a reminder, the above outlined technical plan for advertising may not come to fruition. It is certainly possible that unforeseen technical or economic difficulties arise that make this system infeasible or impossible. For example, if no smart contract platform has fees that are inexpensive enough to result in viewers and creators being net positive for every interaction. As a result of this uncertainty, I have requested $0 for this milestone and assigned a timeframe of “Unknown”. Even without this economy, BitBlock would still be a competitive application for the likes of TikTok, YouTube, etc. and would provide huge value to the Filecoin ecosystem by having users indirectly use Filecoin to store their content.

## Total Budget Requested

In total, I request $8,750 to complete this project until I can fundraise further through a token release and/or Cardano grants. I estimate using $500 for testing the application (using FIL to test storing data, using ADA to test minting and trading NFTs). The remaining $8,250 will go towards salary for time spent developing, researching, and testing.

## Maintenance and Upgrade Plans

I plan to reach out to current popular content creators on TikTok and YouTube and give a pitch on how they could dramatically increase their income by posting on BitBlock. I would start with cryptocurrency content creators, as they would be most likely to understand and adopt BitBlock's economics and technology, and expand to other content creators over time. The idea is that bringing creators to the app will initially bring their biggest fans to the app first, and then word of mouth will continue to grow the user-base.

Directly after release of the Cardano token, I would begin working on smart contracts to create a creator/viewer/advertiser economy. The advertisers would pay the DAO to advertise videos on the application. In turn, the DAO would pay viewers for watching advertisements (similar to the Brave browser). Creators would be paid for each view of their content.

After the hypothetical initial sale(s) of the related token, the DAO would automatically start depositing tokens into creators' wallets (perhaps before advertisers are even onboarded, as the DAO would have its own initial treasury) based on viewership. Either directly before or after this, advertisers would be onboarded and able to pay the DAO to promote their content. Next, the DAO would pay viewers for each advertisement they view. As each component of the economic cycle is completed, the incentives for users to join the platform will continue to grow.

We could even explore using the DAO's treasury to buy advertisements or to pay content creators (who are already on BitBlock) to post about the application on their other platforms.

My long-term plan includes drastically improving the recommendation algorithm to rival mainstream competitors' abilities to personalize content for each viewer. Furthermore, a mobile application is necessary to reach broader audiences who wouldn't typically download unknown applications to their computer, much less to watch videos.

# Team

## Team Members

- Patrick Nercessian

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/patrick-nercessian-b26a04183

## Relevant Experience

I have experience working as a software developer for a furniture export company where I created an application which helps to: facillitate internal communication, digitize and automate the creation of order documents, analyze multiple existing Excel databases, and more. I also worked as a software engineer intern at NCR corporation where I created QA features to ensure their self-ordering kiosks were running properly. Furthermore, I understand the Filecoin network fairly well, as I heavily researched the technology to determine whether I wanted to participate in storage mining.

Although less relevant to the project at hand, I also worked as a virtual reality developer for the University of Georgia and a software development engineer intern for Amazon Web Services.

I think I am the right person to build this project because I am very passionate about it, and I have the relevant experience and mindset to create a great product.

## Team code repositories

https://github.com/PatrickNercessian
