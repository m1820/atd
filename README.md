# Ansible Demo Using Vagrant For Mac OS 
Big shutout to Jerry @Corumj !! who collaborated with me on this project  

Hacked Websites Demo  
(Images changed on website)

++++++++++++++++++  
<b>UNDER DEVELOPMENT </b>  
++++++++++++++++++  


<b>This was created with: </b> 
- Virtual Box 6.1.4 https://www.virtualbox.org/wiki/Downloads  
- Vagrant 2.2.7 https://www.vagrantup.com/downloads.html  
- Ansible version 2.9.6
- Mac OSX 10.15.2   


The following instructions will help you create a demo/lab environment.  
This demo will run locally on your Mac laptop/desktop  
Although


<b>After following the instructions you will have the following:  </b>
- Ansible Tower Server  
- 2 CentOS servers (to be configured as web servers)  
- Ability to run provided playbook in Tower to configure both servers as webservers  
- Web page template with images that can be easy changed with a playbook (provided)  


<b>Inventory:</b>

Ansible Tower Server  
192.168.50.10  
https://127.0.0.1:8010  

web1
192.168.50.11
http://127.0.0.1:8011

web2
192.168.50.12
http://127.0.0.1:8012


<b>Instructions: </b>
1. Download and install Virtual Box
2. Download and install Vagrant
3. Install Ansible engine
    - https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#id18  
4. Create a folder called vagrant under "Documents"
5. Copy "Vagrantfile" to the newly created folder
6. Copy "server_access.yml" to the same folder
7. Open terminal navigate to the "vagrant" folder you created under "Documents"
8. Run the following command  
    - vagrant up  
    This will do the following:
        - Run the vagrant config file you copied to the vagrant folder 
        - Create the first 3 virtual machines (Ansible Tower, 2 CentOS servers)
        - Run through the server_access.yml file which will configure access to the VMS using ssh key pairs
