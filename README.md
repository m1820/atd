# Ansible Tower Demos Using Vagrant For Mac OS 
Created by Christian Trujillo  
Thank you Jerry @Corumj for your help!!

I have created an instructional video to walk you through the setup:

[Ansible Tower Lab Setup Video](https://youtu.be/b3Utw4YGmOI)

This project was created to generate a stable, portable, and permanent, Ansible Tower lab environment.
The idea is to have a lab environment that can stay permanent so your configurations can be saved everytime you want to use it.

The demos will provide a way to create, recreate and destroy only the demo portion without hurting the base environment. 


<b>This was created with: </b> 
- Virtual Box 6.1.4 https://www.virtualbox.org/wiki/Downloads  
- Vagrant 2.2.7 https://www.vagrantup.com/downloads.html  
- Ansible version 2.9.6 [Install Process](#Install-Ansible-engine)
- Mac OSX 10.15.2   
You may be able to run through this instructions on a Windows/Linux based system.  
I have not tested so any help with this would be greatly appreciated.   


The following instructions will help you create a demo/lab environment.  
This demo will run locally on your MacOS machine


<h1>Lab Configuration</h1>
<h2>Base lab configuration to be use with all the available Demos</h2>  

<b>After following the instructions you will have the following:</b>  

- Ansible Tower Server  
- 2 CentOS servers
- 2 Windows Machiens (coming soon)

<b>Inventory:</b>

Ansible Tower Server  
tower
192.168.50.10  
https://192.168.50.10

Static Website  
web1  (Fedora32)  
192.168.50.11  

Wordpress  
web2 (Fedora32)  
192.168.50.12  

<h2>Installing and running Ansible Tower Lab</h2>
<b>Instructions: </b>

1. Download and install Virtual Box
2. Download and install Vagrant
3. # Install Ansible engine
    - https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-macos
4. Create a folder called vagrant under "Documents"
5. Download and copy "Vagrantfile" from the setup_files folder to the newly created folder
6. Download and copy "server_access.yml" from the setup_files folder to the same folder
7. Open terminal navigate to the "vagrant" folder you created under "Documents"
8. Run the following command  
    `vagrant up `   
    This will do the following:  
        - Run the vagrant config file you copied to the vagrant folder 
        - Create the first 3 virtual machines (Ansible Tower, 2 CentOS servers)  
        - Run through the server_access.yml file which will configure access to the VMs using ssh key pairs  
9. Once the vagrant up command finishes you would have to login to the Ansible Tower Server and add a subscription  
    - For Red Hatters reach out to me internally if you are not sure how to get a sub for it
    - For non-Red Hatters you can request a trial license here: https://www.ansible.com/products/tower/trial  
10. Once you get the trial subscription for tower you will need to find out the login credentials to access the Tower Server:
    - On the terminal window under the same vagrant directory type: `vagrant ssh tower`  
    - As soon as you login you will see the user name and password for the Tower server
11. Within Tower go the user menu on the left and change the admin password to something you can remember

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++  
Now you have a fully functional Ansible Tower server with two CentOS VMs running.   
You can access your Tower server and run playbooks etc.  
Now you can run any of the available demos below. 
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
