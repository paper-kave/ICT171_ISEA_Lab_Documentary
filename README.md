Documentation for ISEA Labs
Step-by-step on what was done

Additional Services to install
- MariaDB
- Documentation used as guide : https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-20-04
- sudo apt install mariadb-server
- sudo mariadb-secure-installation

Status of MariaDB Service
- sudo systemctl status mariadb
- mariadb -u root -p

Lab-1A
Download of Hyper-V software
- Virtual Box / VMWare Workstation Player
- https://www.techspot.com/downloads/4481-virtualbox.html
- https://www.techspot.com/downloads/189-vmware-workstation-for-windows.html

Download of Ubuntu ISO
- https://ubuntu.com/download/desktop
- Intel or AMD 64-bit architecture

Installing Ubuntu
- est 20-30 mins

Finishing Touches of Installation
- Update & Upgrade OS | sudo apt update && sudo apt upgrade -y 
- Install of tools | sudo apt install net-tools nano open-vm-tools

Installing Apache, NMAP, OpenSSH-Server
- sup apt install apache2 nmap openssh-server -y

Adding Users and Group
- sudo adduser <name>
- sudo groupadd <grpname>

Permission on Directory
- sudo chmod -R 770 /path/to/directory

Permission for Users and Group to File/Directory
- sudo chmod 750 /path/to/directory
- Owner (7 | rwx) , Group (5 | r-x) , Others (0 | ---)

Making a user the owner of a Folder
- sudo chown <user>:<groupname> /path/to/directory

Removal of User from Group
- sudo gpasswd -d <user> <group>

Permission Cheat Sheet (More chmod range in the link below)
- 7 | Read, Write & Execute (rwx) | Full Control
- 6 | Read & Write (rw-) | Modify but cannot execute
- 5 | Read & Execute (r-x) | Read and Execute
- 4 | Read Only (r--) | Read Only
- 0 | Nothing (---) | Cannot Read Write and Execute

Chmod Link Ref - https://www.digitalocean.com/community/tutorials/how-to-set-permissions-linux

Swapping Users within a Terminal
- su - <username>

Adding User to sudo group
- sudo usermod -aG sudo <username>
- sudo ls /root

Lab-1B

Local VM | Creating of Users and Assigning Permission to Users on Folders/Directory
- Create multiple users
- Assigning Users with different permission levels
- Assigning User to be Owner of Folder etc.
- Unassigning User from Folder to prevent access
- Login/Switch user on CLI to verify permission levels
- su - <user> | ls -l <path/to/folder> | groups <user>
- Removal of Shared Folder

Lab-2A

Pricing Calculator for AWS and Azure
- To estimate and consider on which Platform to use for cheapest cost etc

Sign up for Azure/AWS Account
- Create Subscription
- Create a VM with Ubuntu
- SSH Azure VM via PuTTY on Local PC
- Update & Upgrade & Install of Apache

Update apache weblink file
- Adding in URL hyperlink filepath to be reflected on the webpage itself.
- Access of the webpage via ip address to verify clickable link to PDF

Lab-3A
Installing of Apache on Azure VM
- Login to VM via PC PuTTY
- sudo apt install apache2 -y

Register a Domain Name
- DuckDNS
- Sign in with an account
- Register a unique subdomain name for VM
- Input of IPv4 and IPv6
- Back on VM, create the necessary items listed | https://www.duckdns.org/spec.jsp
- nslookup <domainname> | nslookup paperlocalvm58.duckdns.org
- dig <domainname> | dig paperlocalvm58.duckdns.org

Installing Certbot
- sudo apt install certbot python3-certbot-apache
- sudo certbot --apache

Encountered an error while running previous cmd
- sudo ufw allow 'Apache full'
- sudo ufw allow ssh | http | https
- sudo ufw enable
- sudo ufw status

Apache config file lacking of Servername
- sudo nano /etc/apache2/apache2.conf
- ServerName localhost

Verify of Ports open
- nmap -p80,443 systems.social

Local VM Configuration (Main cause for failed Certbot connection)
- was NAT before
- Had to change to Bridged Connection
- Ran certbot CMD again | Successful
- Renew Dry run of Cert Renew | sudo certbot renew --dry-run | successful
