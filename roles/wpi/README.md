# Ansible-WordPress-Role
####Ansible-Role For Installing and Configuring WordBress on LAMP Stack.
# Ansible role `wordpress-LAMP-Stack`

### Ansible role for :

- installing PHP version 7.3 Dependences  and some other packages Needed for installation Latest Wordpress version
- Installing and configuring MariaDB and MariaDB-client
- Creating wordpress DataBase and DBUser for WordPress
- Removing the Annonymous user and Test DataBase to secure the Database Server
- Installing and Configuring httpd WebServer
- Downloading and Extracting The WordPress files
- Using Jinja2 Templates for creating and configuring `wp-config.php`
## Dependencies

#### NO Dependencies Needed , EveryThing Is automated . 

## Requirements
- RHEL/Centos7 with installed YUM Package Manager,Firewalld and SSHd on it.

## Installing from Ansible-Galaxy on the current Directory
 ```sh
 ansible-galaxy install mina_maher.ansible_wordpress_role -p .
```
## Accessing your webiste:
- open the URL of  Targeted Centos Machine which you installed the wordpress on.
```sh
http://<IP-of-Target-Cntos-Machine>
```
 
## Changing The Default Database Vraiables
#### I've already set the Role Vars to default values,If you want to change them
#### edit in `vars/main.yml`
```yml
##Password for MariaDB Root user
mysql_root_password: "123456789"
## WordPress-DatBase Name:
wordpress_db: "wordpress"
##Wordpress DataBase UserName:
wordpress_dbuser: "wordpress"
## WordPress DataBase Password
wordpress_dbpass: "123456789"
```
## License
- BSD 3-Clause License
## How to Contribute
- Take your own Fork.
- Do Your Edits.
- Test your Edits.
- Raise Your PR.
