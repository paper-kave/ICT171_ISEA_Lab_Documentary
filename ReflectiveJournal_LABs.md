KAPLAN ID : CT0391973
MURDOCH ID : 36163245
Name: Lam Yiin Jia

Subject: Introduction to Server Environments and Architecture

Activities involve creating a GitHub Repo
URL: https://github.com/paper-kave/ICT171_ISEA_Lab_Documentary.git

- Access to Github.com
- Create/Sign in to Account
- Click on Repositories
- Click on New | Fill in the Blanks
- Create Repository

Create Folders according to Labs in the Repository
- Click into Repo
- Click Add File
- Make sure <filename>/ to create a folder, then a readme.md for a placeholder | As GitHub does not recognise blank folders
- Documentation pathway complete

Activities to Create an Ubuntu VM on Local PC
- Download VMware Workstation: https://www.techspot.com/downloads/189-vmware-workstation-for-windows.html
- Download Ubuntu ISO: https://ubuntu.com/download/desktop | Intel or AMD 64-bit architecture
- Install VMware Workstation
- Followed the steps on VMware Workstation to create a VM
- Allocation of Space, RAM and selection of ISO for OS
- Installation time: 20-30 mins

After the Ubuntu VM has completed its installation
- Opens up the terminal to run for updates
- sudo apt update && sudo apt upgrade -y | Update & Upgrade OS
- sudo apt install net-tools nano open-vm-tools | Install additional tools for troubleshooting on the other activities

CMDs used for farmiliazation
- mkdir
- cp <filename> <path/to/directory>
- mv <filename> <path/to/directory>
- systemctl list-units --type=service | --state=running
- pwd
- grep | find
- chmod ***
- chown *** 
- chgrp
- groups <user>
- nslookup
- ip a
- crontab -e
- ls -al
- lsblk
- fdisk
- sudo su
- apt install | upgrade | update
- nmap

Cloud Infrastructure > Azure Platform

Using Pricing Calculate between different platform to see estimate cost by Month
- AWS
- Azure
- Google
- Oracle
- IBM
- Alibaba

Choose Azure instead of AWS
- Prior experience with provisioning on Azure itself
- Create a Virtual Machine with the steps provided on Azure
- Open Port 22, 80, 443
- Create an admin account to log in from PuTTY
- Do the same steps with the Ubuntu VM before updating OS packages, and install Apache

DNS Setup

Using DuckDNS as they are a free dynamic host
- URL: https://www.duckdns.org/
- Create an account
- Create a subdomain | Two subdomain, one for Azure VM, one for Local PC VM
- Follow the steps on Install tab on URL to create a script and cronjob to have it refresh every 5 mins

Let's Encrypt + Certbot
- Applied on both Azure VM and Local PC VM
- Followed the steps to apply SSL to both VMs
- Succeeded first try on Azure VM
- Did not succeeded on Local PC
- Error code: timed out (likely firewall problem)
- Searched error line on Google to find resolution

 Steps of Resolution
 - sudo ufw allow 'Apache Full'
 - sudo ufw status verbose
 - sudo ufw enable
 - sudo ufw allow 80/tcp
 - Restart VM | Still having error after restarting, search for different resolution
 - Found that settings of Local VM needs to change from NAT to Bridged
 - Power off VM, Changed settings, Power on VM
 - sudo certbot --apache | Successfully SSL certified the domain

Automation Scripts & cronjobs | Scripts are mainly the complicated/daily/time-consuming task to be run everyday, weekly, etc. Cronjob is to schedule it.
- Created scripts as per lab mentioned
- Schedule the cronjobs within crontab -e

Additional Services to install on LocalVM
- MariaDB
- Guide used: https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-20-04
- sudo apt install mariadb-server
- sudo mariadb-secure-installation

Following questions when securing MariaDB installation
- Switch to unix_socket authentication? (Y)
- Change the root password? (Y)
- Remove anonymous users? (Y)
- Disallow root login remotely? (Y)
- Remove test database and access to it? (Y)
- Reload privilege tables now? (Y)

End steps to confirm MariaDB
- sudo systemctl status mariadb | Check status of MariaDB
- mariadb -u root -p | Confirm root can access to MariaDB
