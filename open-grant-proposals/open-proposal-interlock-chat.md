# Open Grant Proposal: `Interlock Chat`

**Name of Project:** `Interlock Chat`

**Proposal Category:** `app-dev`

**Proposer:** `@operatorjen`

**Technical Sponsor:** `@autonome`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** YES

## Project Description

Disenfranchisement with the major social media continues to grow as more and more people realize that the corporate interests underpinning are often detrimental to communities.

The growth of Mastodon, a federated microblogging platform, suggests there is appetite for alternatives, even when significant technical expertise is required to operate a server instance.

However, no such solution exists to date that has garnered sufficient adoption with respect to real-time chat. We are developing a chat system that is flexible enough to accommodate the need to balance privacy, independence, and usability for both technical and less technical users to put them squarely in the driver’s seat.

Renewed interest in NLP methods spurred by recent advances with ChatGPT demonstrated that machine learning associated algorithms remain largely black-box black magic to most users, including technical users. These methods are still largely the domain of topic experts and researchers.

We are confident that with the right set of tools, putting machine-learning driven algorithms in place to assist with topic detection and sentiment analysis will give users more control over their content and how it is displayed, as well as lead to better chat moderation capabilities and thus effective online community management.

Interlock is real-time chat enabling pseudo-anonymous data sovereignty, achieved through the distributed and addressable ownership of chats, digital art and social achievements.

Interlock gives chat-based communities the option to choose centralized ephemerality, or data sovereignty of their content. With this combination, we create a seamless bridge between Web 2 and web3.

Our plan of action, at a high level, is the following:

1. Build a “centralized-first” real-time social messaging service, ensuring proof-of-concept for major features is sufficiently usable and adaptable for several key use cases critical to user adoption, one of them being pseudo-anonymous chatting capability

2. Iterate on privacy, security, usability, and content algorithms to sufficient satisfaction

3. Evolve the platform from “centralized-first” architecture to a federated model

4. Double-down on community education and tooling to ensure that anybody, not just ‘tech’ people, can deploy and manager their own instances of Interlock chat with minimal friction

In the rest of this proposal, we detail each of these phases further as well as the challenges we expect to encounter during this project.

## How It Works

The platform provides a user with a pseudo-anonymous identity. Their profiles rely on an auto-generated user ID and an API Key pair that is stored in their browser's localStorage. This is what the user provides to authenticate on the server. This allows a user to authenticate on multiple devices, including native app client implementations in iOS and Android.

Messages posted on the server are ephemeral and are automatically destroyed at a predetermined amount of time (TTL). If the user does not specify the time, the server has a "max TTL" fallback.

On the other hand, if the user wishes to save their own authored messages (and user ID) forever, then they can store them in web3 storage via the platform. The user can store their own messages only (not messages by other authors) as a way to respect author ownership and privacy.

If a user clears their localStorage and does not store the user ID and API Key elsewhere to re-authenticate later, then their profile will eventually be one with no content on the server since the messages are eventually auto-deleted. If the user stores their messages on web3.storage, then there will always be a way to reference the message with the user ID.

Messages are fed through a sentiment analysis and topic detection system to determine what to recommend to which users based on their activity and content. These may also be used by moderators to detect when there might be conflict between users in the chat so a human can step in to mediate as appropriate.

Users who wish to respond to certain messages can either reply with their own message or share a customized pixel stamp that they can create on the platform.

If a user does not wish to see a message or similar content from the author, they can either mute the message specifically or mute the author and all of their messages entirely. If a user wants to share or store their created stamps off the server, they have the option to upload it to NFT.Storage.

## Value

### What are the benefits to getting this right?

De-emphasizing identity and starting as a "centralized-first"  service makes it easier for people to start using a social messaging platform with a bridge to web3, ostensibly broadening the service to a wider audience.

By engineering the service to be somewhat ‘Web 2.5’, we make the web3 experience feel like the default in user experience and the expectations around privacy and ownership become table stakes for users moving forward. 

In turn, this will allow us to create more interesting and creative decentralized opportunities to evolve the open source social network and chat platform design.

Letting users to store their own messages in web3.storage gives them the freedom to have their content outside of a centralized system, encouraging personal data ownership and control from the start.

Unlike many existing chat platforms, user data storage is ephemeral unless it is hosted in web3.storage, and so long as we have the link to that content, Interlock can display the distributed content.

Enabling creators to store their customized pixel stamps in NFT.Storage will also give them a flexible model to decentralize and distribute their art, reusing it in other contexts outside of Interlock if they choose to.

Additionally, by having users store their creations off of a centralized server, it limits liability issues for the server maintainer, such as copyright violations.

When successful, we expect to make running and maintaining federated real-time social experiences easy if not on-demand for the average user. This will be measured by user adoption, both in the end-user participation sense as well as number of independent instances run successfully without our intervention.

We also expect to see more people engage with the ideas of topic suggestion and sentiment analysis, understanding them well enough to be able to explain why or why not they might use them to administer their real-time system.

Further, we may measure the success of our educational efforts through qualitative surveys and informal user feedback.

### What are the risks if you don't get it right?

The “centralized-first” platform will have similar risks and challenges in scaling to the average startup product that achieves an influx of user adoption.

In our case, if there are a lot of users connected, there may be a flood of messages that could be overwhelming for users to experience. This could be mitigated through throttling, or by implementing a feature to set a minimum waiting period between messages similar to how Discord operates.

### What are the risks that will make executing on this project difficult?

With respect to the machine learning components, while we are using established datasets and may be able to use transfer learning to enhance and extend existing models, we suspect the time and cost of training could be a factor even though we are prioritizing methods known to be more cost effective than using solely deep learning.

Although our team has a significant amount of experience with building the kinds of features required to moderate a real-time chat system, there is always the risk that malicious users will find edge cases to exploit in order to abuse community systems. This kind of activity risks the mental health of users and community managers, as malicious actors of this nature are often persistent and it is stressful to deal with them.

There is also the risk that the market for alternative social media solutions becomes crowded and it becomes more difficult to gain traction. However, we have yet to see any project trying to address the same concerns as ours with similar methods.

## Deliverables

### web3.storage and NFT.Storage Feature Deliverables

With your support, we can complete the following features for site launch:

1. Add support for authors to store their content on web3.storage if they do not want it to be auto deleted by the server.

2. Allow authors to distribute their own content on Interlock through their web3.storage link if they do store it off the server.

3. Add support for creators to store their customized pixel stamps on NFT.Storage if they want to share and store their distributed art indefinitely.

### Interlock Chat Feature Deliverables

With your support, we can complete the following objectives for site launch:

1. Run a real-time social chat platform with the following features 
	+ Pseudo-anonymous authentication
	+ Messaging with TTL
	+ Muting
	+ Stamping
	+ web3.storage support that works on web browsers, using Python on the server
	
2. Create a pixel stamp editor that 
	+ Enables users to create and share stamps
	+ Enables creators the option to store their stamps in NFT.Storage
	
3. Include open source NLP-based features to provide users with
	+ Custom content recommendations from other authors
	+ Chat moderation tools for community managers/admins

All would be in soft beta launch by the beginning of Q3 in 2023.

## Development Roadmap

### Milestone 1 - January-February 2023

+ Build a proof-of-concept foundation real-time social platform with muting support and pseudo-anonymous authentication support

### Milestone 2 - February-March 2023

+ Product design and UI development
+ Phase 1 of customized message recommendations using sentiment analysis and supervised training - training with intentional data via industry standard/vetted datasets, not user-derived data
+ Create and design the pixel editor

### Milestone 3 - March-April 2023

+ Phase 2 of customized message recommendations using sentiment analysis and unsupervised training/topic detection through incorporating actual user messages (opt-in)
+ Complete frontend product design and UI

### Milestone 4 - April-May 2023

+ Phase 3 of customized message recommendations using sentiment analysis and unsupervised training - adjusting any required training and honing hyperparameters
+ Remaining bug fixes and features to wrap up for a soft launch

### Milestone 5 - May-June 2023
Prepare for unanticipated issues and features post soft launch

## Budget

| Milestone Work		 | Time Cost
| ------------------ | ----------
| AI/NLP Development | 4-6 months
| Frontend Development/Design | 2-3 months
| API Server Development | 3-4 months
| Product + UI Design, Testing/QA | 2-3 months

## Team

### Team Members
+ Jen Fong-Adwent
+ Tracy Hinds
+ Leo Stratus

### Relevant Experience

**Jen Fong-Adwent** is the creator of Meatspace Chat, an open source chat platform that “differentiates itself from other chat systems by eschewing usernames, user registration and chat channels, and instead embracing ephemerality by limiting the exposure of a single message to a limited number of minutes, after which it does not appear again.” [^1]

Additionally, “Meatspace shifts the conversation into a different space than a conventional chat service, news feed or shared video stream. Instead, it’s an ephemeral app, similar to Snapchat.” [^2]

[^1]: “Meatspace Chat.” Wikipedia, Wikimedia Foundation, October 6, 2022, [https://en.wikipedia.org/wiki/Meatspace_Chat](https://en.wikipedia.org/wiki/Meatspace_Chat)

[^2]: "Meatspace, A World Of Animated Gifs, Human Robots And The Ephemerality Of Snapchat-Like Apps.” Techcrunch, January 1, 2014, [https://techcrunch.com/2014/01/01/meatspace-a-world-of-animated-gifs-human-robots-and-the-ephemerality-of-snapchat-like-apps/](https://techcrunch.com/2014/01/01/meatspace-a-world-of-animated-gifs-human-robots-and-the-ephemerality-of-snapchat-like-apps/)

The Meatspace Chat project was one of the earlier implementations of real-time, web-based ephemeral chat communities, encouraging a global community of users to interact in a single channel without identity and with ephemeral WebRTC interactions. She has also worked on projects in the past decade involving encryption, federation and decentralization. Her previous professional experiences include engineering and leadership positions at Mozilla, Begin, Nike and Kickstarter. Currently she is the lead developer and architect for Crow & Pitcher.

**Tracy Hinds** is the creator of Crow & Pitcher, a substance misuse activity tracker service, and is an experienced leader in building and managing communities in open source. She is the product and UI designer of Emerge, the native iOS and Android app for Crow & Pitcher.

**Leo Stratus** is an award-winning cognitive scientist and software engineer, with over fifteen years of professional experience shipping polished products. They have a background in machine learning and artificial intelligence, as well as cross-platform mobile application development. Most recently, Leo was a Director of Engineering for multiple production engineering teams at Splice and previously worked at Mozilla, Begin, and Digital Ocean. Leo lives in Brooklyn where they also work on end consumer applications for EEG hardware using neural networks to detect ‘mental commands’.