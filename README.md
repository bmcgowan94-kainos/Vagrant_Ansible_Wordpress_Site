# Simple Vagrant file with Ansible Provisioner

This project configures Vagrant for local development, and uses Ansible as the provisioner. 

It defines two hosts, a proxy and a wordpress vm, grouped logically. 

A LAMP stack is installed onto the proxy server using Ansible. While the repo-epel is installed on all servers.  

## Vagrant

This project includes a simple Vagrantfile which configures Virtual Machines to...

- Use the Centos/7 Operating System
- Use the hostname as defined in 'hosts' section
- Use Ansible as the provisioner for the VMs
- Set 'site.yml' as the primary/master playbook
- Group these VMs logically - e.g. webserver or wordpress server 
- Assign VirtualBox as the local provider

-----------------------------------------------------------------------------

## Ansible

All roles along with version number are specified in the 'requirements.yml' file, for example...

        - src: geerlingguy.mysql
          version: 2.9.2

If a new developer came onto the project for example, they could simply run the below command to install all of the roles included in the requirements file...

        ansible-galaxy install -r requirements.yml

To also install the roles so that they show up in your visual studio code repo, add these options to the command...

        ansible-galaxy install -r requirements.yml -p roles_galaxy

This will install the roles into a 'roles_galaxy' folder in your VS repo.

But make sure to include them in a git ignore file so that you dont push them up to github every time which would be uneccessary and time consuming.





