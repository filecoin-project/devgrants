# Open Grant Proposal: Cadbury Storage

**Name of Project:**  Cadbury Meet

**Proposal Category:** app-dev

**Proposer:** Susmit 

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

There are plenty of video conferencing solutions that exist in the present market but they lack in one or more of the  following: open, neutral, borderless, decentralized or not being censorship resistant. Adding further, time limits for freemium offering, performance (frame drops and high RTT,latency), no meeting storage option / highly costly storage and generic solutions (ex not perfect for university) problems also exist.

Cadbury Meet approach these problems by taking a dual approach of capturing value on applications as well as protocol side. Cadbury Meet attempts to solve present high priced storage offerings by lowering prices by integrating Filecoin via textile powegate (on application level). Filecoin integration besides being economical also gives ownership to users about their meeting data and artifacts. Data generated from the meetings have a strong use-case to be stored (especially for universities, ed-tech startups and big corporations) These stored data could be used by the users to unlock personal revenue for them. Due to decentralized approach of solving the problem cadbury will be able to provide better and faster performance as RTT (round trip time) and frame drop rates would be very low.
 
## Value

Filecoin integration would be very economical for the users of Cadbury who want to store the data generated from the meetings. This will enable a premium package of present solutions like Zoom,G-meet to be a near-freemium package with Cadbury. Moreover, it will also allow users to gain ownership of their data and further monetize it in any aftermarket on their consent.

Storage solutions of meetings (collectively predicted in Terabytes) can be resolved best by Filecoin. Best alternative would be AWS S3 but it would compromise on decentralization, ownership and binding to Amazon AWS policies.

Here is a brief of storage requirements by Cadbury Meet.

**For a 1 to 1 video calling:**
* 600kbps (up/down) for high quality video
* 1.2 Mbps (up/down) for 720p HD video
* Receiving 1080p HD video requires 1.8 Mbps (up/down)
* Sending 1080p HD video requires 1.8 Mbps (up/down)

**For a multiparty video meeting:**
* 800kbps/1.0Mbps (up/down) for high quality video
* For gallery view and/or 720p HD video: 1.5Mbps/1.5Mbps (up/down)
* Receiving 1080p HD video requires 2.5mbps (up/down)
* Sending 1080p HD video requires 3.0 Mbps (up/down)

**For a screen sharing only (no video thumbnail): 50–75kbps**
* For screen sharing with video thumbnail: 50–150kbps
* For audio VoiP: 60–80kbps

**For a Cadbury Phone: 60–100kbps**

### Cadbury data usage for a 1:1 meeting

| Quality        | Download   | Upload  | Total |
| ------------- |:-------------:| -----:|---------:|
| High      | 270 MB/hr. | 270 MB/hr. | 540 MB/hr  |
| 720p      | 540 MB/hr. | 540 MB/hr. | 1.08 GB/hr. |
| 1080p | 810 MB/hr.  | 810 MB/hr. | 1.62 GB/hr. |

Storage demand is between 540 MB and 1.62 GB per hour (between 9 MB and 27 MB per minute) for a 1:1 Cadbury meeting, depending upon the streaming quality.

### Cadbury data usage for a group call

| Quality | Download | Upload | Total |
| ------  |:-------------:| -----:|---------:|
| High.   | 450 MB/hr.| 360 MB/hr.| 810 MB/hr.|
| 720p | 675 MB/hr. | 675 MB/hr. | 1.35 GB/hr.|
| 1080p | 1.2 GB/hr. | 1.2 GB/hr. | 2.4 GB/hr. |

Cadbury data usage jumps up with more people on the call. Group Cadbury meetings take up somewhere between 810 MB and 2.4 GB per hour, or between 13.5 MB and 40 MB per minute.

**Estimated storage usage for the following activities:**
* 4K video streaming
  * 5.85 GB/hr.
* HD video streaming
  * 2.5 GB/hr.
* SD video streaming
  * 0.7 GB/hr.
* Audio streaming
  * 72 MB/hr.
* Uploading one image
  * 5 MB/photo
* Sending texts (without attachment)
  * 20 KB/text
* Sending texts (with standard attachment)
  * 300 KB/text

## Deliverables

* Browser based Cadbury Meet with Filecoin integration via textile powergate
* Android Port with Filecoin integration .
* IOS port with Filecoin integration .
* Whitelabel solutions for signed up/partnership clients

## Development Roadmap

Cadbury aims with an approach to solve the problem via application + protocol. It would start with making applications (Web, Android & IOS). Based on its current market research and surveys, Cadbury identifies its target audience as universities, startups in the educational tech space and big corporations. For them Cadbury plans to unveil extra features like white-boarding, 24X7 support for seamless experience. 
All developments happening on application level will be under the scope of Filecoin Devgrant. We plan to keep the development timeline of protocol out of scope of Filecoin Dev Grant as it is in early RnD phase.

**Milestone summary**
* Market-  Identification & positioning for high-expectation customers (hypothesis testing). Define pricing. First paying users. North star metrics being retention and NPS. 
* Product & research-   Alpha launch of webapp + Android & iOS mvp launch with customizable solutions. Building media topon (off-chain computation & on-chain verification). 
* Hiring-  On-boarding ux, full-stack dev, RnD ( webrtc,sip etc)  and growth folks. 

### Milestone 1

* Filecoin testnet integration via textile powergate
* UI / UX enhancement for webapp 
* Feature additions: screen share, gallery view, joining permissions, mic, camera customization.  
* SDP messages batching and compression, svc + vp9
* Customizing webrtc protocol and experimenting simulcast + vp8, H.264
* Android & iOS Port via Flutter
* Custom live streaming to other platforms
* Recording option integration and mvp bug fixes
* Timeline deadline : Nov 15 (Beta Launch)

### Milestone 2

* Filecoin mainnet integration
* UI/UX enhancement for mobile app 
* Android and IOS port completion 
* Loudest speaker algorithm integration
* Speech to text subtitles, whiteboarding
* Background swap via computer vision algorithm 
* SIP (Session Initiation Protocol) integration and Scaling
* Testing and Benchmarking
* Timeline deadline :- Dec 31, buffer 7 days (Alpha Launch)

### Milestone 3

* A/B testing & security.
* Codecs SVC, VP9, HEVC & AV1
* Improvement on fps and resolution while livestreaming
* Major functionalities achieved.
* Porting to protocol
* Rolling out white labels solutions for clients and partnership
* Timeline deadline : Jan 31 ( Main Launch)

## Total Budget Requested

We have formulated the budget for a 3-month runway for product development & technical research.

**People:**
* UX/UI - $1600/mo
* 1 Full-stack developer - $2000/month
* 1 Mobile developer - $2000/month
* Total budget requested = $17,000 

## Maintenance and Upgrade Plans

Applications developed by Cadbury will enjoy the following benefits.
* Upgrade and Maintenance wrt to Filecoin and its tool developments.
* Upgrade and Maintenance wrt to Webrtc ecosystem development.
* Upgrade to Cadbury Protocol.

# Team

## Team Members

- **Susmit Lavania**
- **Ayush Ranjan**

## Team Member LinkedIn Profiles

- [Susmit Linkedin](https://www.linkedin.com/in/susmit-lavania-4b9558107/)
- [Ayush Linkedin](https://www.linkedin.com/in/ranjan18/)

## Team Website

- [Cadbury](https://cadbury.on.fleek.co/)

## Relevant Experience

Cadbury's foundation was laid down by Susmit and Ayush. They are co-founders from the same engineering school (LNMIIT) where their entrepreneurial traits got nurtured. They've known each other for over 5 years and share complementing traits for building & scaling Cadbury. Moreover, they share a similar ethos as well as a common desire for Cadbury's role in web 3.0 space. 

Susmit has an expertise in crypto space as a blockchain developer and technical researcher. Earlier, he co-founded a decentralized crypto exchange 'OC2' (backed by Matic, 0x) which was later acquired by India's biggest crypto exchange, CoinDCX.

Ayush has worked in the founding team of Taskbob (backed by IvyCap & Orios Venture) and Zefo (backed by Sequoia) as a growth marketer. He specializes in business development, performance and brand marketing. 

## Team code repositories

- [https://github.com/susmit/Cadbury](https://github.com/susmit/Cadbury)
- [https://github.com/susmit/Cadbury-Flutter](https://github.com/susmit/Cadbury-Flutter)

# Additional Information

* Protocol Labs (Top Audio Hack) HackFS Sponsor Winners
* Ethereum Foundation (Libp2p + ETH 2.0) HackFS Sponsor Winners
* Unstoppable Domain (Best Chat) HackFS Sponsor Winners
* Fleek (Hosting) HackFS Sponsor Winners
* Gitcoin Apollo Kernel fellowship
* [Filecoin Blog](https://filecoin.io/blog/hackfs-next/)
* [Demo video](https://www.youtube.com/watch?v=EVE4ydX0XfQ&feature=youtu.be)
* [HackFS ](https://hack.ethglobal.co/showcase/cadbury-reckhMFHOxGqXC8DY)
* [Twitter ](https://twitter.com/cadburymeet)
 
