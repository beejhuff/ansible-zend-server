[![Build Status](https://travis-ci.org/HardieBoeve/ansible-zend-server.svg)](https://travis-ci.org/HardieBoeve/ansible-zend-server)

# Ansible playbook for Zend Server

Playbook for installing Zend Server and a MySQL server instance on Ubuntu 14.04 +.

This playbook is an work in progress, 


## Requirements

- Ansible
- Zend Server license


## Roles

This playbook is seperated in 3 roles for clarity, below you find an small description what each role does.


### Common

Role that performs the general tasks and prepares the server for installation of Zend Server, for a full list of 
settings [see]('https://github.com/boeve-web-development/ansible-zend-server/blob/master/roles/common/defaults/main.yml').

This role will execute the following tasks:
  - Updates apt cache.
  - Upgrade apt packages.
  - Installs required packages.
  - When reboot is required after update, it will reboot the server.
  - Opens by default the ports 22, 80, 10081, 10082.


### MySQL

Role that install MySQL server and configures it, for a full list of settings [see]('https://github.com/boeve-web-development/ansible-zend-server/blob/master/roles/mysql/defaults/main.yml').


### Zend Server

This role will install Zend Server stable or ea with an Nginx or Apache webserver, depending on your settings. For a 
full list of of settings [see]('https://github.com/boeve-web-development/ansible-zend-server/blob/master/roles/zend-server/defaults/main.yml').


## Usage

Customize the settings of (zend-server.yml `zend-server.yml) to the correct ones that match your server, and run it like this:
```code
ansible-playbook zend-server.yml -K
```


## TODO

  - Cleanup roles.
  - Add better docs. 
  - Add better descriptive task names.
  - Test on Docker container(s).
  - Add cluster setup option??.
  - Add support for other operating systems??
  - Create tests for Travis.
  - Make MySQL optional, and add more options like MongoDB, PostgreSQL.
  - Create role for Redis, MongoDB, PostgreSQL.

  - MySQL: Improve the cleanup off the default installation.
  - MySQL: Needs my.cnf more options?
  
  - Zend Server: Add option to add server certificate.
  - Zend Server: Add licence after installation (if possible??).
  - Zend Server: Set user/admin accounts after installation with Ansible (if possible??).
