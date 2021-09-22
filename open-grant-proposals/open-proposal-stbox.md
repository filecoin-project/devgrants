# Open Grant Proposal: `StBox - Storage application based on IPFS/FIL`

**Name of Project:** StBox

**Proposal Category:** `app-dev`

**Proposer:** `kikakkz@hotmail.com`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

As Filecoin mainnet is coming soon, a lot of developers are focusing on mining optimization and involving in continuous hardware upgrading competition. The miner entry threshold is very high, home devices cannot provide large latent storage space or high speed bandwidth to join IPFS/Filecoin network. Therefore, Filecoin community is exclusive to IT developers and big data storage providers at this moment. But the key of adding value of a network and bringing greater benefit of the whole community is to achieve mass adoption and to expand IPFS/FIL ecosystem. StBox is committed to improve the infrastructure of IPFS/FIL network by providing convenient and user-friendly application to include home devices joining IPFS/Filecoin network and to encourage more people to use IPFS/FIL network on a daily basis.

Our team is experience in the development and implementation of large-scale audio and video Peer-to-Peer network. After conducting deep research on IPFS & Filecoin network, we plan to build StBox, a user-friendly application to help IPFS & Filecoin network to achieve massive adoption quickly. Stbox is a cross-platform Dropbox alternative application, which enables everyone store his data on IPFS network easily. Moreover, Stbox makes every home device be able to provide its latent storage space to IPFS network and earn Filecoin block rewards accordingly. StBox is a Dropbox alternative on IPFS network, it allows users to upload their photos and data to IPFS network instantly. Users can pay FIL token or fiat currency for using IPFS storage space. Moverover, StBox will build an aggregate cluster and develop a storage space sharing interface in this application. Users can join the aggregate cluster and contribute latent storage space of their home devices to IPFS network though StBox and earn FIL block rewards accordingly.

Technically, StBox will adopt Fountain codes as the channel code and build a reliable transport protocol to ensure high quality data transport. This protocol combines Supplementary BBR Congestion Control Algorithm with Fountain codes to enhance the efficiency of data transport. Once Stbox gets a storage deal from IPFS/Filecoin network, it will encode receiving data and send them to home devices aggregate cluster. All the home devices within one aggregate cluster is sorted by their storage quality. The higher its storage quality is, the better chance a home device receives new storage task. After applying Fountain codes，the existence of every piece of redundant data can double the reliability of the original data. There are limited storage capacity and bandwidth of home devices, so the encoded data will be sent to multiple home devices at the same time. When receiving data retrieval request, Stbox’s Fountain codes based transport protocol can simultaneously retrieve data from hundreds of home devices within its aggregate cluster in the most efficient manner. This transport protocol turns hundreds of home devices with limited storage capacity into a powerful storage array. Moreover, Fountain code’s rateless feature results in massive savings on the number of storage units for a given level of redundancy and reliability. StBox’s special data transport protocol will fully use each home device’s upstream bandwidth and combine them to hundreds of Mbps high speed virtual link to connect home devices to Filecoin/IPFS network, in this way, many home devices with limited storage capacity and bandwidth can join Filecoin/IPFS network easily.

## Value

Stbox provide paid storage service based on IPFS/Filecoin network. If this project works out as we planned, Stbox will bring many home devices into IPFS/Filecoin network and enable individual clients to use IPFS/Filecoin storage easily, which accelerates the process of IPFS network to achieve massive adoption. Moreover, Stbox will provide paid storage service to enterprise clients when the project develops to mature stage, which will bring a lot of valuable business data to IPFS network.

Stbox has an aggregate node in IPFS/Filecoin network. There will be a lot of home devices within Stbox’s umbrella. If our transport protocol doesn’t work well or any home device loses data, the collaterals Stbox pledged for the home devices will be lost. That’s the risk our team have to bear. If paid enterprise clients lost their business data, we might have legal issues. But overall, the potential risk of our project is under control and much less than its benefits.  Even the project fails, it won’t bring negative effects to IPFS/Filecoin network.

When we executing our project, we may face the following problems and risks
- Stbox paid service will accept both Filecoin and Fiat currency payments from users, the high volatility of cryptocurrency will result in the fluctuation of storage service price and may cause some difficulties in practice.

## Deliverables

- An Open Source Client Application
  - Cross platform, IOS/MAC/Windows/Android
  - Storage order
  - Data uploading
  - Monitor system for data storage expiration
  - Billing system
  - Instant photo storage service
  - Home device storage space rental service
  - Device ID Login/Logout
- An Open Source Storage Service
  - Run on Linux and OpenWrt
  - Sub node data storage space management
  - Sub node data retrieval
- An Open Source Sub Node Management Service
  - Sub node management service
  - Encoding Service
  - Data pushing service
  - Sub node data retrieval service
  - Billing system and reward distribution system
  - Multipath transportation protocol

## Development Roadmap

| Milestone NO. | Milestone Description | People | Roles | Funding | Estimated Timeframe | Output |
|---------------|-----------------------|--------|-------|---------|---------------------|--------|
| 1 | Clarify the scope of this project and design business architecture | 2 | Zhao KK: Requirement analysis and analysis on how to combine Stbox project with Filecoin/IPFS network in technical level<br>Jin Xuelong: Requirement analysis and business architecture design | $1000 | 2020/8/30 | 1) Requirement Specification; <br>2) StBox Whitepaper; <br>3) Application Business Architecture Report. |
| 2 | Technology selection & technical architecture design | 2 | Wang Zhengzhong: & Zhao KK: Conducting a series of technology assessment & selection, designing Stbox technical architecture together | $2000 | 2020/9/20 | 1) Technical Research Report;<br>2) Network Architecture Report;<br>3) Interaction Design Report. |
| 3 | Product Design | 1 | Qiu Junhua: UX prototype design | $5000 | 2020/9/30 | UX Prototype |
| 4 | C library of Fountain codes implementation | 1 | Wang Zhengzhong: C library of Fountain codes implementation | $8000 | 2020/10/15 | 1) Codec library;<br>2) unit test code;<br>3) performance test code;<br>4) application reference code;<br>5) API documentation |
| 5 | Instruction optimization of Fountain Codes library on X86 and ARM platforms | 1 | Wang Zhengzhong: Instruction optimization of Fountain Codes library on X86 and ARM platforms | $12000 | 2020/11/15 | 1) Assembly code of Fountain codes library;<br>2) Unit test code;<br>3) Performance test code. |
| 6 | Transport Protocol Design | 2 | Zhao KK: Transport protocol state machine design and packet design<br>Wang Zhengzhong: Build transport protocol network model and simulation environment | $40000 | 2020/11/15 | 1) Transport protocol design document;<br>2) Congestion control algorithm design document;<br>3) Protocol applicable scenario design document. |
| 7 | Implementation of transport protocol | 5 | Zhao KK: Implementation of the state machine of the transport protocol library<br>Wang Zhengzhong: Implementation of congestion control algorithm of transport protocol<br>Qiu Junhua: Implementation of transport protocol packet<br>Jin Xuelong: Construction of the transport protocol hardware simulation environment<br>Zhang Tao: Implementation of transport protocol statistical and testing application | $100000 | 2021/2/15 | 1) Transport protocol library;<br>2) unit test code;<br>3) performance test code;<br>4) reference application code;<br>5) test report;<br>6) API documentation. |
| 8 | Application architecture design and framework selection | 2 | Wang Zhengzhong: Technology selection of StBox application<br>Zhao KK: Application architecture design | $1000 | 2021/3/1 | 1) Application architecture design report;<br>2) Application framework analysis report.<br>Both reports need to be in line with UX prototype. |
| 9 | Home device node storage model design | 1 | Jin Xuelong: Home device node storage model design | $2000 | 2021/3/1 | Home device node storage model design report |
| 10 | Implementation of StBox application for Linux desktop platform | 4 | Zhao KK/Wang Zhengzhong/Qiu Junhua: Linux application development<br>Zhang Tao: Build test environment and system test | $50000 | 2021/5/1 | Application source code which could be compiled and run on Linux desktop with data storage, photo upload and storage rental. |
| 11 | Porting application to Windows | 1 | Zhang Tao: Porting application to Windows<br>Zhang Tao: System test | $10000 | 2021/5/20 | Stbox featured with data storage, instant photo upload and home device storage rental, can be compiled, ran and install on Win 10. |
| 12 | Development of StBox for Android | 4 | Zhao KK/Wang Zhengzhong/Qiu Junhua: Android Development of StBox for Android<br>Zhang Tao: Build test environment and system test | $70000 | 2021/7/1 | Stbox featured with data storage, instant photo upload and home device storage rental, can be compiled, ran and install on Android 8.0. |
| 13 | Implementation of Stbox for iOS/Mac | 4 | Zhao KK/Wang Zhengzhong/Qiu Junhua: Implementation of StBox for iOS/Mac<br>Zhang Tao: Build test environment and system test | $70000 | 2021/10/1 | Stbox featured with data storage, instant photo upload and home device storage rental, can be compiled, ran and install on iOS/Mac. |
| 14 | Implementation of storage service on Linux/OpenWrt | 3 | Wang Zhengzhong: Implementation of storage service on Linux/OpenWrt<br>Jin Xuelong: Multipath transport protocol verification<br>Zhang Tao: Build test environment and system test | $20000 | 2021/11/1 | Storage service deployed on home device |

## Total Budget Requested

Total amount：$391,000
| Item | Amount |
|------|--------|
| Salary for developers |$300000 |
| Equipment for network debug | $50000 |
| Cloud service | $10000 |
| Application release and marketing | $31000 |

## Maintenance and Upgrade Plans

- July 2021 Storage service Alpha test
- November 2021 Alpha test of home device storage rental service
- February 2021 Release and launch paid storage service
- March 2021 Release and launch home device storage rental service

`Note: StBox is a paid storage service application used by global users and create more value for Filecoin/IPFS network.`

# Team

## Team Members

- Zhao KK (Founder / Core Developer)
- Jin Xuelong (Co-Founder / Architect)
- Wang Zhengzhong (Co-Founder / Core Developer)
- Qiu Junhua (Core Developer)
- Zhang Tao (Core Developer)

## Team Member LinkedIn Profiles

- Zhao KK: https://www.linkedin.com/in/owen-zhao-489a6815b/
- Jin Xuelong: https://www.linkedin.com/in/%E5%AD%A6%E9%BE%99-%E9%87%91-23b72493/
- Wang Zhengzhong: https://www.linkedin.com/in/%E6%AD%A3%E4%BB%B2-%E7%8E%8B-47238426/
- Qiu Junhua: https://www.linkedin.com/in/%E5%90%9B%E5%8D%8E-%E9%82%B1-9653911b1/

## Team Website

https://www.stbox.tech

## Relevant Experience

The core team of StBox is originated from development team of Cloutropy, which provide high quality audio and video transport service based on large scale peer-to-peer network to audio and video provider. Engineers of the team are from the top internet and cloud technology company such as Alibaba, Huawei, PPTV, Shengda, etc. The team develop a large scale peer-to-peer infrastructure based on fountain codes to support VOD service, live stream, downloading. With the same QoS, the bandwidth cost of the peer-to-peer network is lower to 10% of CDN. The team adopt a special BBR as congestion control algorithm between peers. Such algorithm combines fountain code and BBR algorithm to solve the transport and storage issue which is caused by limited bandwidth and unstable storage of the peer. With the transport protocol, home devices can be used as edge of the content delivery with the same QoS as CDN edge server.

- Zhao KK：Team leader and architect of Cloutropy peer-to-peer network, core developer, develop and deploy the service to millions home devices
- Jin Xuelong：Architect of Cloutropy network, core developer, design the cloud architecture of peer monitor
- Wang Zhengzhong：Used to be Staff software engineer of Ericsson, core developer of Cloutropy peer-to-peer network, design and implement reliable transport protocol
- Qiu Junhua：Core developer of Cloutropy peer-to-peer network, design and implement reliable transport protocol
- Zhang Tao：Product developer of Cloutropy, core developer of NEO

## Team code repositories

https://github.com/kikakkz

# Additional Information

N/A
