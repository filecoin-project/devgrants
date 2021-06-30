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
We are leveraging smart contracts and blockchain technology to decentralize the deep learning process. While the traditional deep learning system works by ‘bringing the data to a central server’, our tool works by ‘bringing the deep learning model to the data owner’. Through our product, a data owner need not upload their data to a centralized server, rather can contribute to the deep learning training process through the data on their local machine itself. This will bring down the monopoly held by large institutions while at the same time guarantee data owners of data privacy. This would also enable availability of more data for training, thus improving the deep learning models greatly. As we are using Ethereum and smart contracts, all transactions are performed with a cost. This will help incentivize the process, thus providing data owners monetary benefits. 
Our mission is derived from the fact that no other person or company should benefit off our personal data

## Value

Please describe in more detail why this proposal is valuable for the Filecoin ecosystem. Answer the following questions:
- What are the benefits to getting this right?
- What are the risks if you don't get it right?
- What are the risks that will make executing on this project difficult?

This section should be 1-3 paragraphs long.

### Benefits of getting this right
Filecoin is a distributed storage system. One of the core principles of our project is using data from decentralized machines for deep learning models. Getting this right would mean that the clients/ data owners can include image files on IPFS after encryption. Traditionally, deep learning algorithm are trained over data which is stored in servers like Amazon Web services. We are trying to break this. Coincidentally, this aligns with the principles of Filecoin like using decentralization to protect integrity of a data’s location, making it easily retrievable and hard to censor. Our project is aimed at giving the control back to data owners as well as incentivizing them for providing data for deep learning training, which is also inherent in the Filecoin ecosystem. Additionally, since Filecoin is a blockchain based system that incentivizes participants to act honestly, this adds to cherry on the cake as this would mean lesser data poisoning. Also, using IPFS we intend to give control back to user. They can authorize if the doctor/ model can view the data or not/ use it or not.

### Risks if we don't get it right:
The major risk involved in this project is the uncertainty of user intentions. We need to have some regulations to prevent data poisoning, while maintaining user anonymity and ensuring that user maintains the control of their data. These two do not seem to compliment each other.

### Risks that will make executing on this project difficult:
This project has been split up into a number of milestones. It can be problematic to implement incentivization of data providers. There is risk involved as to deciding the amount of pay. Also, with the influx of cheaper wearables in the market, it is difficult to assess if the data generated is authentic or not. For example, if the app generates data related to number of steps walked by a person (on a smart watch
), a user may just sit at a place moving their arm and hence dupe the app. Additionally, we have proposed to create our own token compatible with the app. Now as the blockchain space has grown, so has the regulations. There is risk involved in usage of these custom tokens based on policies of different jurisdictions. We may need to get legal counsel for the same.



## Deliverables

Please describe in details what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished.

This is a pilot project that will help decentralize the deep learning process. We aim to deliver a the following functionalities with our tool:
1.	User friendly application - An application wrapped in a docker container that is readily usable, once downloaded. We aim to make decentralized applications easy to use. The docker image shall contain all required dependencies. Once the application is downloaded, the user can enter their wallet address or seed words through a portal, give permission to the application to access the images on the local system, path to the folder of images and that’s all they need to do. The docker application will come with the code for the deep learning model, the code for downloading the weights from the blockchain, updating the local weights, training the model with the local data, and sending the updated weights to the smart contract, connection details to the blockchain and the user shall be automatically added to the list of data owners.
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

We plan to complete the entire project in about 16 - 20 months. We will have 2 developers and 1 intern working on each milestone. Each milestone would be achieved sequentially
We have divided the project in two stages:
Stage 1 - Implementation
1.	Milestone 1: Understanding the users and data providers.
Today every other person has wearables to track health related stats like number of steps. This data is often collected and used by associated companies to train their deep learning models without authorization from users. Additionally, doctors and hospitals may hold data like mammograms and X-rays which can be used for training of neural networks without authorization from the users. To complete this milestone, we would review the user base of the wearable application or the hospital under scope. We will outline the devices used by majority of the user to understand what type of data is being collected and which algorithms would be trainable by this type of data. 
#### We intend to finish this within one month.
2.	Milestone 2: Implementation of deep learning model for one system.
After understanding the type of data generated by the wearable app, we can decide the algorithm and the type of deep learning neural network we should use. During this stage we will decide upon the problem that can be solved by this network. For example, if the data generated is related to breast cancer mammograms, then we could potentially use a deep convolutional network to classify the cancer as malignant or benign. We intend to implement this using Python.
#### This should take up to 4 weeks to implement and review
3.	Milestone 3: Implementation of first level decentralized system .
This milestone would cater to implementation of smart contract to store neural network weights. This stage will also include coding python modules for – downloading the code of the updated neural network on local systems, onboarding of new user, code for permission from user to allow data usage for training (backend). We will also require monetary and computation resources to adjust GAS rates for these tasks. 
#### This stage would take about 4 months to complete
4.	Milestone 4: Generation of portals.
This milestone will deal with creation of user interfaces and their coding. We intend to implement different portals, primarily written using Front End technologies and React. The portal for data owners will have the functionality to allow them to choose if they want their data to be used for training or not and be accessed by medical authorities or not. This would not be a one-time action. The data owner can choose to revoke/ grant access at any time. Data owners can put in their meta mask keywords/ wallet address to link the wallet. Additionally, they will have the provision to provide file path location from local system or hash of the file stored in IPFS.  We also intend to have medical practitioners on board, just in case a user wants consultation, or if a doctor wants to recommend a user to join the network. 
#### This milestone should take about 3 months to complete.
5.	Milestone 5: Average pay system. 
One of the major goals of our project is to provide incentives to people who provide their data for training. We intend to implement this functionality in this milestone. We would be creating our own token during this phase and also implement the smart contract code to incentivize data providers. We have planned to keep a specific average pay system for all data providers, no matter the effect on performance. The created token would be exchangeable as well. 
#### This stage should take 2 months to implement.
6.	Milestone 6 - Performance comparison.
In this milestone, we would study which performance metrics are appropriate for the problem at hand. We would study which metrics is appropriate to be used with the neural network. Additionally, we will brainstorm and implement ‘when’ to update the neural network weights. We will decide upon - If we should update the weights by taking an average of performance metrics from each user, take the highest value in an epoch or aggregate raw values from each user. This would primarily be implemented in Python. 
#### This should take a month to finish. 
7.	Milestone 7 - Containerization of the application for download.
This is the milestone that would pack all the above into a single application. This application should be downloadable from reliable yet compatible sources like App store. This can be done using containers like Docker. We assume that a general data provider is devoid of the knowledge required to set everything up, hence this stage is required. 
#### It should take about 2 months to implement.
8.	Milestone 8 – User centric Dashboard. 
We will be providing each user with a dashboard where they can view and track the tokens collected, amount of data provided for training and the impact of their contribution in comparison to public validation set. We intend to make this using front end technologies, python’s data visualization libraries and dashboarding tools. 
#### It should be completed within a month.
9.	Milestone 9 – Reduce the effect of data poisoning
We plan to compare the results of our model against publicly available data, using the latter as a validation set. We want to use neural net weights on this validation data set. This can be done only after some initial training has been done. We would like to incentivize/ reward data owners whose data helped improve the results. This should effectively reduce data poisoning as well. 
#### This should take about 1 month to implement
Stage 2 - Research and development
We plan to use next 4 months to research the following and integrate within the system:
1.	We intend to reward users who provide better training data. To implement this, we propose to use a ‘Gamble and test’ initiative. The users can go back to a certain point of saved neural network weights, fork the chain from there, download the weights locally and train the model using their data. It is equivalent to creating a competitive environment where on one side the data providers can benefit from additional incentives, the model will benefit on the other side, with the provided better training data.
2.	The first level implementation should help in reducing local minima of the model; however, this research will help in reduction of global minima.
3.	We also aim to research a method to onboard medical authorities that can verify user’s data in cases like cancer imaging and detection. This would also reduce the possibility of data poisoning by malicious users. However, we need to research a method through which we can keep the user identity under covers and that data is not misused.
4.	We intend to store user data through IPFS. But we also aim to store neural network weights through IPFS eventually and research a method through which we can update these stored weights.
5.	Lastly, we would like to research the performance of the model in case we take a global view of the users or if we segregate users into clusters and combine results from these clusters as an average. Again, we can test several items, for example, is it better to make model weights from the cluster with the best local performance, or if we should take an aggregate.

### Overview
![Image of Yaktocat](https://github.com/Garima5/Federated-Learning-for-Transfer-Learning/blob/main/Screen%20Shot%202021-06-30%20at%203.44.11%20PM.png)

## Total Budget Requested

Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds.
#### We require the budget for following:
1. Development Team
  * 2 Developers –> $5000 * 2 * 20
  * Intern –> $2500 *  20
  * Total: $250000
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
