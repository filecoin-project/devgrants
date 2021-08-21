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
IPFS is a distributed storage system. One of the core principles of our project is using data from decentralized machines for deep learning models. Getting this right would mean that the clients/ data owners can include image files on IPFS after encryption. Traditionally, deep learning algorithm are trained over data which is stored in servers like Amazon Web services. We are trying to break this. Coincidentally, this aligns with the principles of Filecoin like using decentralization to protect integrity of a data’s location, making it easily retrievable and hard to censor. Our project is aimed at giving the control back to data owners as well as incentivizing them for providing data for deep learning training, which is also inherent in the Filecoin ecosystem. Additionally, since Filecoin is a blockchain based system that incentivizes participants to act honestly, this adds to cherry on the cake as this would mean lesser data poisoning. Users can authorize if the doctor/ model can view the data or not/ use it or not. We plan to leverage the Filecoin system to provide persistent distributed storage system to data providers while at the same time ensuring success for training the algorithm through consistent availability of data

### Risks if we don't get it right:
The major risk involved in this project is the uncertainty of user intentions. We need to have some regulations to prevent data poisoning, while maintaining user anonymity and ensuring that user maintains the control of their data. These two seem to be contradicting propositions.

### Risks that will make executing on this project difficult:
This project has been split up into a number of milestones. It can be problematic to implement incentivization of data providers. There is risk involved as to deciding the amount of pay. Also, with the influx of cheaper wearables in the market, it is difficult to assess if the data generated is authentic or not. For example, if the app generates data related to number of steps walked by a person (on a smart watch
), a user may just sit at a place moving their arm and hence dupe the app. Additionally, we have proposed to create our own token compatible with the app. Now as the blockchain space has grown, so has the regulations. There is risk involved in usage of these custom tokens based on policies of different jurisdictions. We may need to get legal counsel for the same.



## Deliverables and Development Roadmap

Please describe in details what your final deliverable for this project will be. Include a specification of the project and what functionality the software will deliver when it is finished.

This is a pilot project that will help decentralize the deep learning process. We plan to complete the entire project in about 12 months. We will have 2 developers working on each milestone We aim to deliver the following functionalities with our tool: 
<br>
A. Prototype of the tool: The prototype for the tool will contain the following deliverables:
1.	Milestone 1- Docker Image: The docker image will contain the code for the deep learning model. The user/ data providers run this docker file to download the model on their local system. The image will also contain the code for the user to provide path to their images on IPFS. Additionally, the stage will also contain the code for onboarding new users. Deep learning model will be coded using Python libraries.
####  This milestone should take about 2 months to complete

2. 	Milestone 2 - Code for users to store their files on IPFS: The data can be in the form of images or text files. These files need to be stored on the IPFS and their hash codes can be used for training the neural network. We can also compare the hash codes for images that improve the model performances for different models. We also need to implement this to prevent redundancy. IPFS hash code system would help prevent the user from uploading the same data multiple times. 
####  This milestone would take about 2 months to complete

3. 	Milestone 3 - Code to store the neural network weights on IPFS: Our current tool stores neural network weights in the smart contract. However, this limits the number of weights that can be stored and is also computationally heavy. The prototype will contain code to store the weights on the IPFS itself, thus allowing scalability and computation efficiency. Each node in the tree can store the weights and accuracy metrics.
####  This milestone should take about 2 months to implement.

4. 	Milestone 4 - Code for users to provide data storage on their local system: For users who wish to contribute their storage from their local systems on IPFS. 
####  This milestone should take a month to implement.
5.	Milestone 5 - Payment mechanism for local storage providers: The proposers of the deep learning model shall pay the local storage providers in Filecoin.
6.	Milestone 6 - ERC20 token: We plan to launch our own ERC20 token. All the data providers shall be paid in this new token by the model proposer. 
####  Milestone 5 and 6 should take about 2 months to implement.
7.	Milestone 7 - Option for user to choose whichever training path they want: Code to leverage the Merkel tree structure and give user the option of choose the node from where they want to start the training.
####  This should take about 2 months to implement.
B.	Milestone 8 - Dashboard for the Users: We will be providing each user with a dashboard where they can view and track the tokens collected, amount of data provided for training and the impact of their contribution in comparison to public validation set. We intend to make this using front end technologies, python’s data visualization libraries and dashboarding tools. 
####  It should be completed within a month.

### Overview
![Image of Yaktocat](https://github.com/Garima5/Federated-Learning-for-Transfer-Learning/blob/main/Screen%20Shot%202021-08-20%20at%209.53.03%20PM.png)

## Total Budget Requested

Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds.
#### We require the budget for following:
1. Development Team
  * 2 Developers –> $5000 * 2 * 12
  * Total: $$120000
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
