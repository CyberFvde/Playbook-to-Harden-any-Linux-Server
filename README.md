# Playbook-to-Harden-any-Linux-Server
Easy steps to harden any Linux server

Enable automatic updates: sudo apt-get install unattended-upgrades
Configure the automatic updates: /etc/apt/apt.conf.d/50unattended-upgrades

Schedule regular update checks:
Create a cron job: sudo crontab -e
Add the following line to run daily updates: 0 0 * * * /usr/bin/apt-get update && /usr/bin/apt-get upgrade -y

Install UFW (Uncomplicated Firewall): sudo apt-get install ufw
Set the default firewall policy to deny incoming traffic: sudo ufw default deny incoming
Allow incoming SSH traffic: sudo ufw allow ssh
Enable the firewall: sudo ufw enable

Enable OS-Built-in IDS
Install AIDE (Advanced Intrusion Detection Environment): sudo apt-get install aide
Initialize the AIDE database: sudo aide --init
Schedule regular scans:
Create a cron job: sudo crontab -e
Add the following line to run daily scans: 0 0 * * * /usr/bin/aide --check

Creating a new non-root user
Create a new user: sudo adduser <new_user>
Add the new user to the sudo group: sudo usermod -aG sudo <new_user>

Lastly, DONT FORGOT ENCRYPT SECRETS!
