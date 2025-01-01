|<< SYSTEM >>|
|-------------|
<br>

*Check the Debian version*
```
lsb_release -a
```
<br>

*Reboots the system immediately*
```
sudo reboot
sudo systemctl reboot
```
<br>

*Shuts down the system immediately*
```
sudo halt
```
<br>

*Edit hostname*
```
sudo nano /etc/hostname
```
<br>

*Edit known host*
```
sudo nano /etc/hosts
```
<br>

*Syslog live log (stop pressing ctrl+c)* 
```
sudo tail -f /var/log/syslog
```
<br>

*List and install available GUI (Graphical User Interface)*
```
tasksel
```
<br>

*List all running services*
```
systemctl list-units --type=service --state=running
```
<br>

*List files with enabled status*
```
systemctl list-unit-files --state=enabled
```
<br>

*Show service status*
```
systemctl status service-name
```
<br>

*Start service*
```
sudo systemctl start service-name
```
<br>

*Stop service*
```
sudo systemctl stop service-name
```
<br>

*List all open TCP ports*
```
sudo lsof -iTCP -sTCP:LISTEN -n -P
```

<br>
<br>

|<< PACKAGE MANAGMENT >>|
|-------------|
<br>

*Update the repositories/packages*
```
sudo apt-get update
```
<br>

*Apply the updates*
```
sudo apt-get upgrade
```
<br>

*List all installed packages along with their status and other information*
```
dpkg --list
```
<br>

*Keep in mind that the output may be quite extensive, depending on the number of installed packages on your system.* 
*If you want to search for a specific package, you can pipe the output to grep*
```
dpkg --list | grep packagename
```
<br>

*Installs Synaptic Package Manager, friendly interface for package management*
```
sudo apt-get install synaptic 
```

<br>
<br>

|<< USERS and GROUPS >>|
|-------------|
<br>

*Login with root*
```
su -
```
<br>

*Show user account ID*
```
id -u
cat /etc/passwd
```
<br>

*List all users that have password set*
```
getent passwd | awk -F: '$3 >= 1000 && $3 < 65534 {print $1}'
```
<br>

*List all groups*
```
cat /etc/group
```
<br>

*Add a user to a group*
```
usermod -a -G groupaname user
```
<br>

*Show groups members*
```
members groupname
```
<br>

*Query information about a specific group*
```
getent group groupname
```
<br>

*Delete an user*
```
userdel -r username
```
<br>

*Delete a group*
```
sudo groupdel groupname
```

<br>
<be>

|<< FOLDER and FILES >>|
|-------------|
<br>

*Create a folder*
```
mkdir foldername
```
<br>

*You can create sub-directories of a director*
```
mkdir -p foldername/subdirectory
```
<br>

*Remove a directory and its contents*
```
rm -r foldername
```
<br>

*Remove a directory prompting for confirmation*
```
rm -ri foldername
```
<br>

*Force removal without confirmation*
```
rm -rf foldername
```
<br>

*Change owner and group*
```
sudo chown owner:groupname /path/to/folder
```
<br>

*Change folder permission*
```
chmod -R 755 /path/to/folder
```

<br>
<br>

|<< SSH >>|
|-------------|
<br>

#SSH - https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key

*Show SSH service status*
```
sudo systemctl status ssh
```
<br>

*Show your SSH keys*
```
cd ~
cd .ssh
cat authorized_keys
```
<br>

*Change SSH key passcode*
```
cd ~/.ssh
ssh-keygen -p -f <keyfile>
```
<br>

*Show SSH key encrypted information (not readable)*
```
cd ~/.ssh
ls
cat <file name>
```
<br>

*Create a SSH pair key*
```
ssh-keygen -t rsa
```
<br>

*SSH pair key with server*
```
ssh-copy-id yourUsername@ <ip>
```

<br>
<br>

|<< DOCKER >>|
|-------------|
<br>

*Execute the .yml under the local folder*
```
sudo docker compose up -d
```
<br>

*List all Networks*
```
docker network ls
```
<br>

*Create a Network*
```
docker network create <Network-Name>
```

<br>
<br>

|<< SAMBA >>|
|-------------|
<br>

*Samba configuration path*
```
/etc/samba/smb.conf
```
<br>

*Show Samba status and configuration*
```
sudo testparm
```
<br>

*Restart Samba service*
```
sudo systemctl restart smbd
```
<br>

*Stop Samba service*
```
sudo service smbd stop
```
<br>

*Change a samba user password*
```
sudo smbpasswd -a yourUsername
```
<br>
