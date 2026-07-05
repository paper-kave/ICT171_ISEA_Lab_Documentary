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

Lab-1
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

Lab-2

Sign up for Azure/AWS Account
- Create Subscription
- Create a VM with Ubuntu
- Update & Upgrade & Install of Apache
