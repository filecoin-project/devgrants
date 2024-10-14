# RFP Proposal: `Filecoin-Mobile-Wallets`

**Name of Project:** Filecoin-Mobile-Wallets
**Link to RFP:** [rfp-filecoin-wallets.md](https://github.com/filecoin-project/devgrants/blob/master/rfps/rfp-filecoin-wallets.md).
**RFP Category:** `app-dev`
**Proposer:** `BonoTechnologies`
**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** YES


# Project Description
Filecoin-Mobile-Wallets is a Decentralized Cryptocurrency HD-Wallet for Android and iOS applications.
It is connected to Filecoin Node(lotus daemon) API in order to provide necessary information for the wallet service.
All wallet functions are performed within the device and the server does not receive sensitive user information.
Immediately after creating Mnemonic, it is encrypted with the pin number entered by the user and stored locally.
Users can create and delete multiple wallets with the push of a button.
And you can send Filecoin by inputing the address and quantity you want to send.


Supported OS is Android and iOS.
Android is in JAVA and iOS is in Swift language.


## Deliverables

### Track 1:
- Build Filecoin Node(lotus daemon) for Wallet API.
- Create multiple wallets using one Mnemonic through HD-Wallet Base.
- Mnemonic is stored locally encrypted through AES256 algorithm with the user's pin number.
- Mnemonic is converted to an encrypted QR code and the image is stored within the device.
- Individual extraction of private key, public key, and address through Mnemonic.
- Check Filecoin Balance for each address.
- Restore encrypted QR code image camera.
- Transfer Filecoin.
- Easy UI/UX to add/delete wallet.
- Implement identical UI/UX for Android and iOS.

### Track 2:
- Provide Mobile (Java, Swift) FileCoin SDK open source for Android and iOS.
- Provide java15 server SDK open source.
- Provide SDK document.
- Provide Android and iOS SDK demo app.
- Provide Unit Test
- Android and iOS Unit Test Source for node API testing.


## Development Roadmap

### Milestone 1
1. Build Filecoin Node Server
- Participants : 2 developer
- Period : 1 week
- Build a node server that stores Filecoin block information
- Build JSON-RPC API that can be used in the Application

2.  Mobile Wallet UI/UX Design
- Participants : 1 designer
- Period : 1 week
- Mnemonic View, Receive View, TransferView, etc...


### Milestone 2
- Android Application & OS Application
- Participants : 2 developers
- Period : 2 week
- Extract privatekey, publickey, address from Android/iOS Device
- Filecoin Transfer from Android/iOS Device


### Milestone 3
1. QA
- Participants : 4 developers, 1 Designer
- Period : 1 week
- Testnet, Mainnet에서 Wallet Test

2. Deploying
- Participants : 2 developers
- Period : 1 week
- Open completed Application on github.
- Write UserGuide.


## Total Budget Requested
Total Budget: $30,194.56

| Role | Rate/Hr | HC | Man-Hour | Man-Week | Price |
|------|--------|----|------------|------------|------|
| PM | $40 | 1 | 240 | 6 | $9,600 |
| Backend-Dev | $30 | 2 | 80 | 2 | $4,800 |
| Android-Dev | $35 | 1 | 160 | 4 | $5,600 |
| iOS-Dev | $35 | 1 | 160 | 4 | $5,600 |
| Designer | $30 | 1 | 80 | 2 | $2,400 |
| AWS Backend | $0.508 | 2 | 2160 | 12 | $2194.56 |

## Maintenance and Upgrade Plans
- By providing Filecoin transfer function to CoinUs Wallet operated by BonoTechnologies, users can use Filecoin Mobile Wallet.
- To support SDK so other wallets can easily use Filecoin.
(ex: android can use through gradle, iOS can use through cocoapods, etc)
- Wallet maintenance in response to Filecoin version upgrade.
- Convert Android Java SDK to implement Java Filecoin Wallet SDK for Server.


# Team

## Contact Info
- `dev@bono.tech` : Bono Technologies Developer Team's e-mail
- `bs.jung@bono.tech` : Project Manager

## Team Members
- Jay (Boseup) Jung (Project Manager)
- Kiwung Eom (Android Application Developer)
- Min Soo Kang (iOS Application Developer)
- Cheolho Kim (Server Developer)
- Seokho Lee (Server Developer)

## Team Member LinkedIn Profiles
- Jay (Boseup) Jung `https://www.linkedin.com/in/hazymayon/`
- Kiwung Eom `https://www.linkedin.com/in/kiwung-eom-931314113/`
- Min Soo Kang `https://www.linkedin.com/in/minsoo-kang-999797134/`
- Cheolho Kim `https://www.linkedin.com/in/cheolho-kim-9a86781a5/`
- Seokho Lee `https://www.linkedin.com/in/%EC%84%9D%ED%98%B8-%EC%9D%B4-7926221a4/`

## Team Website
`https://bono.tech`

## Relevant Experience
Bono Technologies provides/operates Blockchain services in South Korea.
Our mobile development team has years of experience in developing and operating mobile HD wallet services, and is currently providing Bitcoin(BTC), Ethereum(ETH), Ravencoin(RVN), and EOS wallets.
Mobile HD wallet is a decentralized wallet, and all wallet functions are performed within the device.
It also provides wallet security and convenience by interlocking with hardware devices.
We are operating Mobile HD Wallet App, Blockchain API Service, Blockchain Billing System and Blockchain Explorer to provide various services within the Blockchain Service Industry.



## Team code repositories
- `https://github.com/BonoTechnologies/BonoTechnologies.github.io`
- `https://github.com/BonoTechnologies/eth2.0-specs`
- `https://github.com/BoxeRgOm/Shamir39Swift`

# Additional Information
- CoinUs Wallet App Link 
Android - https://play.google.com/store/apps/details?id=com.theblockchain.coinus.wallet&hl=ko
iOS - https://apps.apple.com/kr/app/coinus-wallet/id1367339746

- CoinUs Hardware
Hardware Info - https://www.coinus.io/keeper
Hardware Usecase - https://www.youtube.com/watch?v=k9c2-6UDJ2I

- BlockApi Explorer Link
BTC - https://blockapi.io/bitcoin/blocks
ETH - https://blockapi.io/ethereum/blocks
RVN - https://blockapi.io/raven/blocks

