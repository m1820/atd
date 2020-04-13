# Hacked Website Demo Instructions 
<h4>Im working on a video to demonstrate the demo (comming soon)</h4>

Created by Christian Trujillo  

This demo will do the following:
 - Build apache webserver
 - Will copy html, css, and all necessary files for the demo website
 - Will hack the website by replacing the existing files with new ones
 - Restore the website to its original state
 - Clean up the the demo files


<b>Instructions:</b>

All the playbooks are labled from Step 1 to Step 4

### Configuring Tower to run playbooks

1. Login to Ansible Tower
2. Add your CentOS servers to your invetory:
   - Resources > Inventory > Create new "inventory" (plus sign button top right)
   - Give it a name and save
   - Under the newly created inventory click on hosts
   - Click on the plus sign to add a new host
   - Under host name add the IP address of the first sever web1 (192.168.50.11)
 3. Add a project:
   - Resources > Projects > Plus sign to add new project
   - For the SCM type select git 
   - Under the SCM URL enter https://github.com/m1820/atd
   - Give it a name and click save
 4. Add the credentials to manage your web hosts. The hosts were configured with SSH KeyPairs:
   - Navegate to the vagrant folder you created under your documents
   - Login to the Tower server by going to the terminal and entering the following command  
     ` vagrant ssh tower `
   - Get the ssh private key by entering the following command
     `cat ~/.ssh/id_rsa`
   - Copy the Private Key
     -----BEGIN RSA PRIVATE KEY----  
     -----END RSA PRIVATE KEY-----  
   - Now that you have the key go back to the Tower Server UI
   - Resources > Credentials
   - Select credential tye and select Machine
   - Give it a name
   - Under user name enter vagrant
   - Paste the Private Key you copied from the Tower server into the SSH Private Key section
   - Click Save

You have now confgured Ansible Tower with the inventory of the CentOS servers, added the github project which will give you access to the playbooks, and added the correct credentials.

Its time to setup your playbooks   

### Configuring playbooks to run the demo  

1. STEP 1 Setting up web servers: 
   - Under Tower go to Resources > Templates click on the plus sign to add a new "job playbook"
   - Enter a Name
   - Under Inventory select the inventory you created with your CentOS servers
   - Under project select the github project you created
   - Under Playbook slect the Step1_webserver_setup.yml
   - For ther Job Type select run
   - Under credentials select the ssh key credentials you created 
   - On the bottom right under Options select Enable Privilege Escalation
   - Click save
2. STEP 2 Building demo website
   - Under Tower go to Resources > Templates click on the plus sign to add a new "job playbook"
   - Enter a Name
   - Under Inventory select the inventory you created with your CentOS servers
   - Under project select the github project you created
   - Under Playbook slect the Step2_Build_Website.yml
   - For ther Job Type select run
   - Under credentials select the ssh key credentials you created 
   - On the bottom right under Options select Enable Privilege Escalation
   - Click save
3. STEP 3 Hacking website
   - Under Tower go to Resources > Templates click on the plus sign to add a new "job playbook"
   - Enter a Name
   - Under Inventory select the inventory you created with your CentOS servers
   - Under project select the github project you created
   - Under Playbook slect the Step3_hacking_website.yml
   - For ther Job Type select run
   - Under credentials select the ssh key credentials you created 
   - On the bottom right under Options select Enable Privilege Escalation
   - Click save
4. STEP 4 Restoring website
   - Under Tower go to Resources > Templates click on the plus sign to add a new "job playbook"
   - Enter a Name
   - Under Inventory select the inventory you created with your CentOS servers
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
