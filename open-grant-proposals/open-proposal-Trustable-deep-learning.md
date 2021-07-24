To submit a proposal, please create a PR against this template in this repo. Please title your file `open-proposal-title.md`, replacing `title` with the name of your project.

# Open Grant Proposal: `Decentralized deep learning for medical data`

**Trustable deep learning**

**Proposal Category:** Choose one of `app-dev`

**Proposer:** `Garima5`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes" 

# Project Description

Please describe exactly what you are planning to build. Make sure to include the following:
- Start with the need or problem you are trying to solve with this project.
- Describe why your solution is going to adequately solve this problem.
- This section should be 2-3 paragraphs long.

### Need or the problem we are trying to solve:
The team at ByteSpark is creating a tool to decentralize the machine learning/ deep learning process involved in cancer detection and other algorithms which require medical data for training purposes. Currently, this process is server dependent. With the increase in usage of wearable devices, there has also been a mammoth increase in the generated medical data. This data, however, may be used by companies for training their deep learning algorithms, without user’s consent. Additionally, the data has to be provided to a centralized entity (server) which leads to risk of data loss and theft. Centralization also leads to monopolizing of the algorithm and it’s results. It becomes a vicious circle where only large institutions which hold the data, resources, servers, and money to employ deep learning engineers can train the network and produce results. While this entire process may be used for targeted advertisements, ironically, the data owners may be oblivious to the use of their data for training. They are also generally not incentivized.

### Describe why your solution is going to adequately solve this problem:
We are leveraging smart contracts and blockchain technology to decentralize the deep learning process. While the traditional deep learning system works by ‘bringing the data to a central server’, our tool works by ‘bringing the deep learning model to the data owner’. Through our product, a data owner need not upload their data to a centralized server, rather can contribute to the deep learning training process through the data on their local machine itself or through data stored via IPFS. This will bring down the monopoly held by large institutions while at the same time guarantee data owners of data privacy. This would also enable availability of more data for training, thus improving the deep learning models greatly. As we are using Ethereum and smart contracts, all transactions are performed with a cost. This will help incentivize the process, thus providing data owners monetary benefits. 
Our mission is derived from the fact that no other person or company should benefit off our personal data


## Value

Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:
- What are the benefits to getting this right?
- What are the risks if you don't get it right?
- What are the risks that will make executing on this project difficult?

This section should be 1-3 paragraphs long.

### Benefits of getting this right
Filecoin is a distributed storage system. One of the core principles of our project is using data from decentralized machines for deep learning models. Getting this right would mean that the clients/ data owners can include image files on IPFS after encryption. Traditionally, deep learning algorithm are trained over data which is stored in servers like Amazon Web services. We are trying to break this. Coincidentally, this aligns with the principles of Filecoin like using decentralization to protect integrity of a data’s location, making it easily retrievable and hard to censor. Our project is aimed at giving the control back to data owners as well as incentivizing them for providing data for deep learning training, which is also inherent in the Filecoin ecosystem. Additionally, since Filecoin is a blockchain based system that incentivizes participants to act honestly, this adds to cherry on the cake as this would mean lesser data poisoning. Also, using IPFS we intend to give control back to user. They can authorize if the doctor/ model can view the data or not/ use it or not. We plan to leverage the Filecoin system to provide persistent distributed storage system to data providers while at the same time ensuring success for training the algorithm through consistent availability of data

### Risks if we don't get it right:
The major risk involved in this project is the uncertainty of user intentions. We need to have some regulations to prevent data poisoning, while maintaining user anonymity and ensuring that user maintains the control of their data. These two seem to be contradicting propositions.

### Risks that will make executing on this project difficult:
This project has been split up into a number of milestones. It can be problematic to implement incentivization of data providers. There is risk involved as to deciding the amount of pay. Also, with the influx of cheaper wearables in the market, it is difficult to assess if the data generated is authentic or not. For example, if the app generates data related to number of steps walked by a person (on a smart watch
), a user may just sit at a place moving their arm and hence dupe the app. Additionally, we have proposed to create our own token compatible with the app. Now as the blockchain space has grown, so has the regulations. There is risk involved in usage of these custom tokens based on policies of different jurisdictions. We may need to get legal counsel for the same.


## Deliverables

Please describe in details what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished.

This is a pilot project that will help decentralize the deep learning process. We aim to deliver a the following functionalities with our tool:
1.	Decentralized Deep learning system: A system where users need not upload their data to a centralized server, rather the neural network model is brought to them. The user can enter their wallet address or seed words through a portal, give permission to the application to access the images on the local system (path to the folder of images), or IPFS hash and that’s all they need to do. The system will have the code to - download the weights from the blockchain, update the local weights, train the model with the local data, and send the updated weights to the smart contract.
2.	Smart Contract - The smart contract written in Solidity will hold the neural network weights and the performance metrics. These weights are downloaded by the peers in the network, locally trained. Updated weights are sent to the smart contract. Depending on the client’s preference, we can write various types of performance metrics into the smart contract - it could be an aggregated measure, where we take an average of all the peer metrics, or we can update the metrics sequentially.
3.	Payment mechanism for data providers: We aim to incentivize data providers. The incentives could be in form of Ether or the custom tokens we generate for this application
4. Dashboard for users: We would also provide a dashboard to data owners - a single pane of glass to show their data contribution, quality of their data and their rewards.

## Development Roadmap

Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section).

For each milestone, please describe:
- The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates)

We plan to complete the entire project in about 11 months. We will have 2 developers and 1 intern working on each milestone. Each milestone would be achieved sequentially.

1.	Milestone 1: Implementation of deep learning model for one system.
After understanding the type of available medical data, we can decide the algorithm and the type of deep learning neural network we should use to solve the problem. During this stage we will decide upon the problem that can be solved by this network. For example, if the data generated is related to breast cancer mammograms, then we could potentially use a deep convolutional network to classify the cancer as malignant or benign. We intend to implement this using Python.
#### This should take up to 4 weeks to implement and review.
2.	Milestone 2: Implementation of first level decentralized system.
This milestone would cater to implementation of smart contract to store neural network weights. This stage will also include coding python modules for – downloading the code of the updated neural network on local systems, onboarding of new user, code for permission from user to allow data usage for training (backend). We see the maximum use of filecoin system here as it provides distributed storage for large medical data for users. We will also require monetary and computation resources to adjust GAS rates for these tasks. 
#### This stage would take about 4 months to complete
3.	Milestone 3: Generation of portals.
This milestone will deal with creation of user interfaces and their coding. We intend to implement different portals, primarily written using Front End technologies and React. The portal for data owners will have the functionality to allow them to choose if they want their data to be used for training or not and be accessed by medical authorities or not. This would not be a one-time action. The data owner can choose to revoke/ grant access at any time. Data owners can put in their meta mask keywords/ wallet address to link the wallet. Additionally, they will have the provision to provide file path location from local system or hash of the file stored in IPFS.  We also intend to have medical practitioners on board, just in case a user wants consultation, or if a doctor wants to recommend a user to join the network. 
#### This milestone should take about 3 months to complete.
4.	Milestone 4: Average pay system.
One of the major goals of our project is to provide incentives to people who provide their data for training. We intend to implement this functionality in this milestone. We would be creating our own token during this phase and also implement the smart contract code to incentivize data providers. We have planned to keep a specific average pay system for all data providers, no matter the effect on performance. The created token would be exchangeable as well. to have medical practitioners on board, just in case a user wants consultation, or if a doctor wants to recommend a user to join the network. 
#### This stage should take 2 months to implement.
5.	Milestone 5: User centric Dashboard.
We will be providing each user with a dashboard where they can view and track the tokens collected, amount of data provided for training and the impact of their contribution in comparison to public validation set. We intend to make this using front end technologies, python’s data visualization libraries and dashboarding tools.
#### It should be completed within a month.

### Overview
![Image of Yaktocat](https://github.com/Garima5/Federated-Learning-for-Transfer-Learning/blob/main/Screen%20Shot%202021-07-24%20at%202.28.39%20AM.png)

## Total Budget Requested

Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds.
#### We require the budget for following:
1. Development Team
  * 2 Developers –> $5000 * 2 * 11
  * Intern –> $2500 *  11
  * Total: $137500
2. Legal Counsel for Customized tokens
  * $20,000 to $50,000
3. Validation set and server
  * 2000$
  
## Maintenance and Upgrade Plans
We will be employing at least 1 developer and 1 intern in long time run to ensure that the app is thoroughly maintained. Security audits, alpha and beta testing will also enable us to keep app up to par with user expectation. We plan to eventually integrate our research and development work as upgrades to the app.


# Team

#### Since this is a pilot project, our core team consists of the following permanent members. We would be hiring a developer and intern as we progress.
1.	Dr. Zehua Wang
2.	Garima Aggarwal

## Team Member LinkedIn Profiles

- Team Member 1 https://www.linkedin.com/in/wangzehua/
- Team Member 2 https://www.linkedin.com/in/garimaaggarwal500/ 

## Team Website

https://www.bytesparktech.com

## Relevant Experience

Our team consists of talented individuals from different walks of technological lines. Dr. Zehua Wang is an adjunct professor at UBC. Blockchain for application development is one of his areas of expertise. 
Garima has worked at one of the Big4 consulting firms in the field of information security. Her experience has helped shape the underlying ideas behind the product, which is regarding data. Currently she is working in the field of transfer learning along with solidity programming.

## Team code repositories

* https://github.com/Garima5/Federated-Learning-for-Transfer-Learning 
* https://github.com/Garima5/SupplyChain-Blockchain-

# Additional Information

Please include any additional information that you think would be useful in helping us to evaluate your proposal.
