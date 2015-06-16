[![Build Status](https://travis-ci.org/HardieBoeve/ansible-zend-server.svg)](https://travis-ci.org/HardieBoeve/ansible-zend-server)

# Ansible playbook for Zend Server

Complete playbook for installing Zend Server and a MySQL server instance on Ubuntu 14.04 +.


## Requirements

- Ansible
- Zend Server license


## Roles

This playbook is seperated in 3 roles for clarity, below you find an small description what each role does.


### Common

Role that performs the general tasks and prepares the server for installation of Zend Server, for a full list of 
settings (see `vars/main.yml`).

This role will execute the following tasks:
  - Updates apt cache.
  - Upgrade apt packages.
  - Installs required packages.
  - When reboot is required after update, it will reboot the server.
  - Opens by default the ports 22, 80, 10081, 10082.


### MySQL

Role that install MySQL server and configures it, for a full list of settings (see `vars/main.yml`).


### Zend Server

This role will install Zend Server stable or ea with an Nginx or Apache webserver, depending on your settings. For a 
full list of of settings (see `vars/main.yml`).


## Usage

Change the settings of (zend-server.yml `zend-server.yml) to the correct ones that match your server, and run it like this:
```code
ansible-playbook zend-server.yml -K
```


## TODO

  - Cleanup roles.
  - Add more descriptive task names.
  - Add support for other operating systems?

  - MySQL: Improve the cleanup off the default installation.
  - MySQL: Needs my.cnf more options?
  
  - Zend Server: Add option to add server certificate.
  - Zend Server: Add licence after installation (if possible??).
  - Zend Server: Set user/admin accounts after installation with Ansible (if possible??).
