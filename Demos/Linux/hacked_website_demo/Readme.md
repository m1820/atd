# Hacked Website Demo Instructions 
Created by Christian Trujillo   

Follow me:  

Linkedin [/trujillochristian](https://linkedin.com/in/trujillochristian)  
Twitter [@hciadvisor](https://twitter.com/hciadvisor)  
Website [HCIBlos.com](https://hciblogs.com)  
YouTube [HCIBlogs](https://www.youtube.com/channel/UCuzUAh-TVnbfwa8VxhWrUVg)  
Podcast [Datacenter Evolution](https://hciblogs.com/show/)

[Check out the Video Tutorial](https://youtu.be/skPJtJYKrPs)

This demo will do the following:
 - Build apache webserver
 - Will copy html, css, and all necessary files for the demo website
 - Will hack the website by replacing the existing files with new ones
 - Restore the website to its original state
 - Clean up the the demo files


<b>Instructions:</b>

All the playbooks are labled from Step 1 to Step 4

### Configuring playbooks to run the demo  

1. STEP 1 Setting up web servers: 
   - Under Tower go to Resources > Templates click on the plus sign to add a new "job playbook"
   - Enter a Name
   - Under Inventory select the inventory you created with your Fedora servers
   - Under project select the github project you created
   - Under Playbook slect the Step1_webserver_setup.yml
   - For ther Job Type select run
   - Under credentials select the ssh key credentials you created 
   - On the bottom right under Options select Enable Privilege Escalation
   - Click save
2. STEP 2 Building demo website
   - Under Tower go to Resources > Templates click on the plus sign to add a new "job playbook"
   - Enter a Name
   - Under Inventory select the inventory you created with your Fedora servers
   - Under project select the github project you created
   - Under Playbook slect the Step2_Build_Website.yml
   - For ther Job Type select run
   - Under credentials select the ssh key credentials you created 
   - On the bottom right under Options select Enable Privilege Escalation
   - Click save
3. STEP 3 Hacking website
   - Under Tower go to Resources > Templates click on the plus sign to add a new "job playbook"
   - Enter a Name
   - Under Inventory select the inventory you created with your Fedora servers
   - Under project select the github project you created
   - Under Playbook slect the Step3_hacking_website.yml
   - For ther Job Type select run
   - Under credentials select the ssh key credentials you created 
   - On the bottom right under Options select Enable Privilege Escalation
   - Click save
4. STEP 4 Restoring website
   - Under Tower go to Resources > Templates click on the plus sign to add a new "job playbook"
   - Enter a Name
   - Under Inventory select the inventory you created with your Fedora servers
   - Under project select the github project you created
   - Under Playbook slect the Step4_restoring_website.yml
   - For ther Job Type select run
   - Under credentials select the ssh key credentials you created 
   - On the bottom right under Options select Enable Privilege Escalation
   - Click save
 
 ### Running The Demo
 
1. Install and configure the web server
   - From the Tower server go to Resources>Templates 
   - Click on the rocket icon for STEP1 to setup the webserver setup from the template you created
2. Build the demo website
   - From the Tower server go to Resources>Templates 
   - Click on the rocket icon for STEP2 to build the website from the template you created
3. Hack the demo website
   - From the Tower server go to Resources>Templates 
   - Click on the rocket icon for STEP3 to hack the website from the template you created
4. Restore the demo website
   - From the Tower server go to Resources>Templates 
   - Click on the rocket icon for STEP4 to restore the website from the template you created
   
## Clean up demo to run again in the future
1. Clean up demo
   - From the Tower server go to Resources>Templates 
   - Click on the rocket icon for the hacked demo cleanup playbook from the template you created
