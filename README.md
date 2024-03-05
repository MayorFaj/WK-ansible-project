# Brief Overview
This documentation outlines the setup outlined the setup of 2 web servers  using Apache as the backend web server and HAProxy as the load balancer. Several hardening techniques was performed on the priovided Linux machines to enhance security and protect against common threats.

### Why Apache for backend webservers?
A server running on Apache is a great choice for most websites. It’s easy to use, customizable, and has a vast library of resources for users to take advantage of.
Depending on the nature and size of the website, another option may be better.

### Why HAProxy for loadbalancer?
HAProxy has built-in reliability features, such as server health checks, connection queuing, and session persistence, contribute to its reputation for fault tolerance. Although this setup is just a basic setup, HAProxy performs well in benchmarks as well.

## Hardening techniques

###  Keep Linux Kernel and Software Up to Date;
Applying security patches is an important part of maintaining Linux server, regularly updating the Linux kernel and software packages is essential to address vulnerabilities 

## OS hardening by secure SSH
- Change SSH default port from 22 to 2222

## Disable root login
I disallowed root login to add an extra layer of security to prevent unauthorized access.
sudo does greatly enhances the security of the system without sharing root password with other users and admins.

## Setup firewall using firewalld
I configured firewall rules to control incoming and outgoing network traffic

## No Non-Root Accounts Have UID Set To 0
I confirmed that only root account have UID 0 with full permissions to access the system.

Commands

`ansible-playbook -i inventory/dev playbooks/site.yml -b`