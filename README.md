# Ansible Demo Using Vagrant For Mac OS 
Big shoutout to Jerry!! who collaborated with me on this project  

Hacked Websites Demo  
(Images changed on website)

This was created with:  
- Virtual Box 6.1.4 https://www.virtualbox.org/wiki/Downloads  
- Vagrant 2.2.7 https://www.vagrantup.com/downloads.html  
- Ansible version 2.9.6
- Mac OSX 10.15.2   


The following instructions will help you create a demo/lab environment.  
This demo will run locally on your Mac laptop/desktop


After following the instructions you will have the following:  
- Ansible Tower Server  
- 2 CentOS servers (to be configured as web servers)  
- Ability to run provided playbook in Tower to configure both servers as webservers  
- Web page template with images that can be easy changed with a playbook (provided)  

++++++++++++++++++  
UNDER DEVELOPMENT   
++++++++++++++++++  

Instructions: 
1. Downoad and install Virtual Box
2. Download and install Vagrant
3. Install Ansible engine
    - https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#id18  
4. Create a folder called vagrant under "Documents"
5. Copy "Vagrantfile" to the newly created folder
6. Copy "server_access.yml" to the same folder
7. Open terminal navegate to the "vagrant" folder you created under "Documents"
8. Run the following command  
    - vagrant up  
    (This will run the vagrant config file you copied to the vagrant folder and create the first 3 virtual machines)