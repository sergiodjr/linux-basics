|<< SYSTEM >>|
|-------------|

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

*List all running services*
```
systemctl list-units --type=service --state=running
```

*List files with enabled status*
```
systemctl list-unit-files --state=enabled
```

*Show service status*
```
systemctl status service-name
```

*Start service*
```
sudo systemctl start service-name
```

*Stop service*
```
sudo systemctl stop service-name
```

*List all open TCP ports*
```
sudo lsof -iTCP -sTCP:LISTEN -n -P
```

<br>
<br>

|<< PARTITIONS and DISK >>|
|-------------|

*List available disk/partitions showing its name, size and mount point*
```
lsblk
```

*List available disk/partitions showing its FSTYPE, and mount point*
```
sudo lsblk -o NAME,FSTYPE,MOUNTPOINT
```

*List all disk/partitions information*
```
sudo fdisk -l
```

*Mount a drive on a desire folder*
```
sudo mount /dev/YouPickTheDrive /you/pick/thefolder
```

*Unmount the device on /dev/sda2*
```
sudo umount /dev/YouPickTheDrive /you/pick/thefolder
```

*Force unmount the device on /dev/sda2*
```
sudo umount -l /dev/YouPickTheDrive
```

*Mount exFat partition*
```
sudo mount -t exfat /dev/sda2 /you/pick/thefolder
```

*Shows devices, filesystem, type, used and available space, also the mount location*
```
df -T
```

*Create file system ext4 on /dev/sdb2*
```
sudo mkfs.ext4 /dev/sdb2
```

<br>
<br>

|<< PACKAGE MANAGMENT >>|
|-------------|

*Update the repositories/packages*
```
sudo apt-get update
```

*Apply the updates*
```
sudo apt-get upgrade
```

*List all installed packages along with their status and other information*
```
dpkg --list
```

*Keep in mind that the output may be quite extensive, depending on the number of installed packages on your system.* 
*If you want to search for a specific package, you can pipe the output to grep*
```
dpkg --list | grep packagename
```

*Installs Synaptic Package Manager, friendly interface for package management*
```
sudo apt-get install synaptic 
```

<br>
<br>

|<< USERS and GROUPS >>|
|-------------|

*Login with root*
```
su -
```

*Show user account ID*
```
id -u
cat /etc/passwd
```

*List all users that have password set*
```
getent passwd | awk -F: '$3 >= 1000 && $3 < 65534 {print $1}'
```

*List all groups*
```
cat /etc/group
```

*Add a user to a group*
```
usermod -a -G groupaname user
```

*Show groups members*
```
members groupname
```

*Query information about a specific group*
```
getent group groupname
```

*Delete an user*
```
userdel -r username
```

*Delete a group*
```
sudo groupdel groupname
```

<br>
<be>

|<< FOLDER and FILES >>|
|-------------|

*Create a folder*
```
mkdir foldername
```

*You can create sub-directories of a director*
```
mkdir -p foldername/subdirectory
```

*Remove a directory and its contents*
```
rm -r foldername
```

*Remove a directory prompting for confirmation*
```
rm -ri foldername
```

*Force removal without confirmation*
```
rm -rf foldername
```

*Change owner and group*
```
sudo chown owner:groupname /path/to/folder
```

*Change folder permission*
```
chmod -R 755 /path/to/folder
```

<br>
<br>

|<< SSH >>|
|-------------|

#SSH - https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key

*Show SSH service status*
```
sudo systemctl status ssh
```

*Show your SSH keys*
```
cd ~
cd .ssh
cat authorized_keys
```

*Change SSH key passcode*
```
cd ~/.ssh
ssh-keygen -p -f <keyfile>
```

*Show SSH key encrypted information (not readable)*
```
cd ~/.ssh
ls
cat <file name>
```

*Create a SSH pair key*
```
ssh-keygen -t rsa
```

*SSH pair key with server*
```
ssh-copy-id yourUsername@ <ip>
```

<br>
<br>

|<< DOCKER >>|
|-------------|

*Execute the .yml under the local folder*
```
sudo docker compose up -d
```

*List all Networks*
```
docker network ls
```

*Create a Network*
```
docker network create <Network-Name>
```

<br>
<br>

|<< SAMBA >>|
|-------------|

*Samba configuration path*
```
/etc/samba/smb.conf
```

*Show Samba status and configuration*
```
sudo testparm
```

*Restart Samba service*
```
sudo systemctl restart smbd
```

*Stop Samba service*
```
sudo service smbd stop
```

*Change a samba user password*
```
sudo smbpasswd -a yourUsername
```
