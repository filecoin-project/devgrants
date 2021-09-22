# Open Grant Proposal: `Social bookmarking standard`

**Name of Project:** Archive and share any social media post, by bookmarking link

**Proposal Category:** `app-dev`

**Proposer:** [`@seichris`](https://github.com/seichris)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

# Project Description

In times when social media access is becoming a geopolitical weapon, web3 enables users to gain back full control over their data from any platform, to share it through open APIs with developers, who use it to build better products and monetize them natively on a protocol level.

1. Data sovereignty creates a more secure internet
Youtube channel takedowns; TikTok, Wechat ban; User data hacks;  - Centralized data storage benefits attackers, and advertisement companies - not content creators. We feed a decentralized database through 1. Filecoin archive services like Deplatformr and 2. a chrome bookmarking extension, and standardize the format of social media data to show all posts in one feed. We standardize access control to this data, to give back full control to the content creator.

2. A web without silos allows for better content curation
This curated database with a user's favorite content is more expressive than data from just one silo like Facebook. We aim to showcase this value creation by building a superior social bookmarking tool.

## Value

We see our tool as a user-facing building block for Filecoin to become the backbone of Web3 Social Media.

- Developing infrastructure and standards for Filecoin community projects to become interoperable, regarding reputation, identity and media sharing.
- Linking social media information to Filecoin identifiers adds trust to the Filecoin ecosystem.
- Generating value on Filecoin benefits anyone invested in Filecoin.
- Our app creates demand for Filecoin storage and showcases the business case for the Web3 Social Media as a sustainable alternative to current ad-based business models.
- We plug into existing identity infrastructure, like Ceramic DIDs and Sourcecred as well as Filecoin archiving solutions like Deplatformr.

Technical challenges:
- Ceramic DID authentication for Powergate/Lotus hasn’t been run in production yet, which we aim to use to authenticate users and standardize media data and reputation.

Product challenges:
- UX challenges in standardizing diverse media formats of different platforms

## Deliverables

### Tech stack specification:

- Filecoin storage
- Ceramic DID authentication
- Ceramic doctypes
- Web app
- Chrome extension

### Final deliverables:

**Social Bookmarking Web App**
- DID-based signup and login
   - Signup: User is able to create a new DID and use the app using the newly created DID
   - Login: User is able to use an existing DID and use the app
- Bookmarks feed
   - Public bookmarks: List of publicly available bookmarks
   - Private bookmarks: List of bookmarks only accessible to the logged in user
- Sort, search and filter bookmarks:
   - Sort bookmarks based on time, author, tags, popularity
   - Search bookmarks based on search text
   - Filter bookmarks based on time, author, tags, popularity
- Add and edit personal bookmarks:
   - Add new bookmarks
   - Edit existing personal bookmarks
- Share bookmarks
   - Access control: Share bookmarks via URL to certain people
   - Share favorite lists
- Up- / Down-vote bookmarks

**API**
- Create a doctype standard for any social media site to
   - Plug into web2 archive services
   - Plug into Facebook media services like [Deplatformr](https://deplatformr.com/) &
   - Plug into the Weibo Filecoin backup service by Cobo team

**Ceramic doctype standard**
- Bookmarks:
   - For social media content data
   - For media like videos or images
- Reputation data
   - Up- / Down-votes on individual bookmarks
   - Measure of cumulative reputation per user profile
- Access management standard
   - Let users to share their bookmarks via URL

**Chrome extension**
- Bookmarking tool to feed Filecoin storage
   - URL
   - Comments
   - Ratings

**Filecoin archive**
- Automatically archive content behind bookmark URLS
   - Trigger on reputation threshold
   - Trigger on user prompt

## Development Roadmap

Each milestone implements the corresponding deliverables.

| Milestone No. | Milestone Description | Funding | Delivery Time | Raw time
| --- | --- | --- | --- | --- |
| 1 | **Goal:** Finalize scope, architectural design, and standardize doctypes for bookmarks <br> **Amount of members:** 2 | 3200 USD | 1 week | 32 hours |
| 2 | **Goal:** Build API and chrome extension to feed storage <br> **Amount of members:** 2 | 4000 USD | 2 weeks | 40 hours |
| 3 | **Goal:** Build web application incl feed, profile, filters, search UI <br> **Amount of members:** 2 | 5600 USD | 2 weeks | 56 hours |
| 4 | **Goal:** Filecoin archiver <br> **Amount of members:** 2 | 3200 USD | 1 week | 32 hours |
| 5 | **Goal:** Finalize project deliverables (website, extension, documentation, API) <br> **Amount of members:** 2 | 3200 USD | 1 week | 32 hours |

## Total Budget Requested

- Milestone 1: 3200 USD
- Milestone 2: 4000 USD
- Milestone 3: 5600 USD
- Milestone 4: 3200 USD
- Milestone 5: 3200 USD

Total: 19200 USD

## Maintenance and Upgrade Plans

As soon as Ceramic document pinning is live on Filecoin mainnet, we will update our app to work with the new network. (Ceramic Network is planned to go live by end of this year, which will make our login flow interoperable with standard wallets like Metamask.)

If changes in Ceramic or Filecoin brake our app or standards, we will continue to update those to make the app work again, in the scope of this grant.

We will continue to develop doctype standards for different media formats as well as reputation data.

We will build the bookmarking extension, the web app and the archiver into one coherent product flow. And onboard users from the Ethereum community to use as a complementary social media platform, and thus bridge the Ethereum into the new Filecoin communities.

In the medium term, we plan to build a data marketplace to optimize curation algorithms, which is not part of this grant, but we think the Filecoin ecosystem will greatly benefit from.

# Team

## Team Members

- Christopher Seifert @seichris
- Dongha Kim @dakingha69

## Team Member LinkedIn Profiles

- [linkedin.com/in/chris-seifert](https://www.linkedin.com/in/chris-seifert/)
- [linkedin.com/in/dhkim0210](https://www.linkedin.com/in/dhkim0210/)

## Team Website

[kontext.app](https://kontext.app/)

## Relevant Experience

Chris and Dongha have unique experience in developing products that tokenize trust-relationships through Ethereum-based community currencies, NFTs and onchain legal contracts.

We have over 10 years experience in UX/UI design, Full Stack Javascript, Web and Smart Contract development.

After designing and coding the Trustlines Network app, Chris went on to co-build [radi.cards](https://radi.cards), Multiply.charity, a crowdfunding platform for the largest African community currency economy (see our xDAI network dashboard: [dashboard.sarafu.network](https://dashboard.sarafu.network/)) and design and co-build [linkdrop.io](https://linkdrop.io).

Dongha was one of the core contributors to the JS SDK of the Trustlines Protocol and the Trustlines Network App. He also has a strong blockchain-related academic background and co-authored papers on practical use cases of blockchain technology. For these he also implemented prototypes, which are currently being further enhanced and integrated into production systems.

## Team code repositories

Chris
- [Multiply.charity webapp](https://github.com/multiplycharity/donationsapp)
- [Kontext demo](https://github.com/seichris/xanadu)
- [Kontext extension](https://github.com/seichris/xanadu-chrome)
- [Linkdrop design board](https://www.figma.com/file/m3LuBle2I7y6000q5KEgLx/amigo-berlin?node-id=2%3A176)

Dongha
- [Trustlines Protocol JS SDK](https://github.com/trustlines-protocol)
- [Trustlines Network App](https://trustlines.app/#/) (source code is not open-sourced right now, but will be soon)
- UN CITES Blockchain Challenge ([paper](https://depositonce.tu-berlin.de/bitstream/11303/9170/4/busse_etal_2019.pdf), [repo](https://github.com/cites-on-blocks/cites-on-blocks_dapp))
- Privacy-preserving netting in local energy grids ([paper](https://www.ise.tu-berlin.de/fileadmin/fg308/publications/2020/preprint-ICBC-Eberhard.pdf), [repo](https://github.com/JacobEberhardt/decentralized-energy-trading))
