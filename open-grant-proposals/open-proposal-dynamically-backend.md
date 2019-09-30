Name of Project: Dynamically configurable storage backend
Proposal Category: devtools-libraries
Proposer: ipfsmainoffical
Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?: Yes
Project Description
During the actual use of Filecoin, miners are very unlikely to install all hard drives at once, so they will frequently add new hard drives or replace old hard drives for a variety of reasons. Current Filecoin has a hard time supporting this. 
We want to develop a disk management backend that supports dynamic configuration to help miners use a variety of hard drives at any time. 
Our storage backend supports multiple directories and can either dynamically configure new directories or delete old ones. The storage backend uses these directories through user-defined strategies like “less free space first”, “more free space first”, “space reserve”, etc.  
    1) Maybe user can set a new directory via config or delete the old one.
    2) Develop a monitoring module for the disk, which has been damaged or removed.
    3) Develop multiple directory access interface in the rust-fil-sector-builder library, and maintain the correspondence between the sector and the directory.
    4) Develop different disk usage strategies to let users decide how to use their disks, Is each disk balanced, or one by one. 
    5) Users can choose to be invisible to these processes, no need to pay attention to storage details.

Value
Mask the complexity of hard drives operations for ordinary miners. Allow miners to add or remove hard drives according to their needs, instead of having all the hardware ready and professionally operated like raids. 
Lack of this function will probably prevent miners from interest or use Filecoin network.
The difficulty should be how to do more in line with the miner’s needs, and the actual test will encounter a variety of problems with the hard drives. 
Deliverables
Store the back or module's go or rust code
Design document
Development Roadmap
Milestone 1
This milestone will take 3 weeks
Design an interface that suits the user's daily habits, design Strategy, and consider how to interact with go-filecoin. 

Milestone 2
This milestone will take 4 weeks
Develop real code for the storage backend and develop various strategies.

This milestone will take 4 weeks
Test these strategies in real-world scenarios and communicate with users to make changes.
Total Budget Requested
1000 dollars. Reward to users who assist us in testing.
Maintenance and Upgrade Plans
We will maintain the code for a long time and iterate over our modules based on the iteration of the filecoin project. Solve bugs, new requirements, etc.
Team
Team Members
IPFSMAIN development team.
Team Member LinkedIn Profiles
Team Website
Relevant Experience
We have developed a large-scale distributed mining system, as well as corresponding management tools, APP, etc., and carried out some research and improvement on the nodes. We believe that maybe we are not perfect, but in the field of filecoin we must be professional and sincerely.
Team code repositories
Additional Information

