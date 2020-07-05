# Ansible Tower Lab (With Demos) Using Vagrant For Mac OS 
Created by Christian Trujillo   

Follow me:  

LinkedIn [/trujillochristian](https://linkedin.com/in/trujillochristian)  
Twitter [@hciadvisor](https://twitter.com/hciadvisor)  
Website [HCIBlos.com](https://hciblogs.com)  
YouTube [HCIBlogs](https://www.youtube.com/channel/UCuzUAh-TVnbfwa8VxhWrUVg)    
Podcast [Datacenter Evolution](https://hciblogs.com/show/)  


Thank you Jerry @Corumj for your help!!

I have created an instructional video to walk you through the setup:

[Ansible Tower Lab Setup Video](https://youtu.be/b3Utw4YGmOI)  


[Jump to the Install Process](#Install-Process)

This project was created to generate a stable, portable, and permanent, Ansible Tower lab environment.
The idea is to have a lab environment that can stay permanent so your configurations can be saved everytime you want to use it.

The demos will provide a way to create, recreate and destroy only the demo portion without hurting the base environment. 


<b>This was created with: </b> 
- Virtual Box 6.1.4 [Download VirtualBox](https://www.virtualbox.org/wiki/Downloads)  
- Vagrant 2.2.7 [Download Vagrant](https://www.vagrantup.com/downloads.html)  
- Ansible version 2.9.6 [Install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-macos)  
- Mac OSX 10.15.2   
You may be able to run through this instructions on a Windows/Linux based system.  
I have not tested so any help with this would be greatly appreciated.   


The following instructions will help you create a demo/lab environment.  
This demo will run locally on your MacOS machine


<h1>Lab Configuration</h1>
<h2>Base lab configuration to be use with all the available Demos</h2>  

<b>After you complete the install process you will have the following:</b>  

- Ansible Tower Server  
- 2 Fedora servers
- 2 Windows VMs (coming soon)

<b>Inventory:</b>

Ansible Tower Server  
Hostname: tower  
IP: 192.168.50.10    
https://192.168.50.10

Static Website  
Hostname: web1  (Fedora31)  
IP: 192.168.50.11  

WordPress  
Hostname: web2 (Fedora31)  
IP: 192.168.50.12  

# Install Process  
<h2>Installing and running Ansible Tower Lab</h2>
<b>Instructions: </b>

1. Download and install Virtual Box [Download VirtualBox](https://www.virtualbox.org/wiki/Downloads) 
2. Download and install Vagrant [Download Vagrant](https://www.vagrantup.com/downloads.html) 
3. Install Ansible engine
    - [Ansible Installation Documentation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-macos)  
4. Create a folder called vagrant under "Documents"
5. Download and copy "Vagrantfile" from the setup_files folder to the newly created folder
6. Download and copy "server_access.yml" from the setup_files folder to the same folder
7. Open terminal navigate to the "vagrant" folder you created under "Documents"
8. Run the following command  
    `vagrant up `   
    This will do the following:  
        - Run the vagrant config file you copied to the vagrant folder   
        - Create the first 3 virtual machines (Ansible Tower, 2 Fedora servers)    
        - Run through the server_access.yml file which will configure access to the VMs using ssh key pairs  
    `MacOS 10.9.3 and upwards might require to close VirtualBox and restart it with the following command:`
    ```bash
    sudo "/Library/Application Support/VirtualBox/LaunchDaemons/VirtualBoxStartup.sh" restart
    ```
    More information can be found [here](https://stackoverflow.com/questions/21069908/vboxmanage-error-failed-to-create-the-host-only-adapter).
9. Once the vagrant up command finishes you would have to login to the Ansible Tower Server and add a subscription  
    - For Red Hatters reach out to me internally if you are not sure how to get a sub for it
    - For non-Red Hatters you can request a trial license here: https://www.ansible.com/products/tower/trial  
10. Once you get the trial subscription for tower you will need to find out the login credentials to access the Tower Server:
    - On the terminal window under the same vagrant directory type: `vagrant ssh tower`  
    - As soon as you login you will see the user name and password for the Tower server
11. Login to the Tower server via the browser https://192.168.50.10
12. Within Tower go the user menu on the left and change the admin password to something you can remember

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++  
Now you have a fully functional Ansible Tower server with two Fedora VMs running.   
You can access your Tower server and run playbooks etc.  
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++  

### Configuring Tower to run playbooks

1. Login to Ansible Tower
2. Add your Fedora servers to your invetory:
   - Resources > Inventory > Create new "inventory" (plus sign button top right)
   - Give it a name and save
   - Under the newly created inventory click on hosts
   - Click on the plus sign to add a new host
   - Under host name add the IP address of the web1 (192.168.50.11)
   - Follow the same procedure to add the second server web2 (192.168.50.12)
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

You have now confgured Ansible Tower with the inventory of the Fedora servers, added the github project which will give you access to the playbooks, and added the correct credentials.

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++  
It's time to setup your Templates/Playbooks   
Now you can run any of the available demos below  
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++  

<h2>Demos - Instructions</h2>
<h3> Linux Demos </h3>
<ul>
  <li><a href="https://github.com/m1820/atd/blob/master/Demos/Linux/hacked_website_demo/">Hacked Website</a> </li> 
</ul>
<h3> Windows Demos </h3>
<ul>
  <li><a href="#">Coming Soon</a> </li> 
</ul>
