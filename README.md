# ansible-project-4ASRC

This project aims to :
  - Install apache2 package
  - Copy picture "esgi.jpeg" in /var/www/html
  - Copy template "index.j2" in /var/www/html/index.html
  - Install ntp package
  - Create ntp service configuration file (/etc/ntp.conf)
  - Allow port 80 with iptables
  - Create user list with password and loop for their creation
  - Check URL response and display a message depending on the result
  
# Prerequisites
  
  - Ansible installed
  - Adjust ip address of remote(s) server(s) in "inventory" file
  - Create service account (for playbook execution) 
    - Create user "svc-ansible" and set password in "globalvars/linux.yml"
    - Copy SSH pubkey on remote(s) server(s) in "/home/svc-ansible/.ssh/authorized_keys" 
  - You have to create the vault password file for encrypted files ("globalvars/all.yml" and "globalvars/users.yml") and adjust path in vault_password_file (ansible.cfg) 
    - The actual password is "123AZEqsd"
  
# How to run the project
  
  - Apply all roles : 
    - ``` ansible-playbook projet.yml```
  - Apply specific role :
    - ``` ansible-playbook projet.yml --tags role-name```
    - Example : ``` ansible-playbook projet.yml --tags ntp```
