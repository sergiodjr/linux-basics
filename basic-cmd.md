|<< SYSTEM >>|
|-------------|

*Check the Debian version*
```
lsb_release -a
```

*Reboots the system immediately*
```
sudo reboot
sudo systemctl reboot
```

*Shuts down the system immediately*
```
sudo halt
```

*Edit hostname*
```
sudo nano /etc/hostname
```

*Edit known host*
```
sudo nano /etc/hosts
```

*Syslog live log (stop pressing ctrl+c)* 
```
sudo tail -f /var/log/syslog
```

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

|<< PARTITIONS >>|
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

|<< USERS & GROUPS >>|
|-------------|

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

*Delete a group*
```
sudo groupdel groupname
```

<br>
<be>

|<< FOLDER >>|
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
sudo systemctl status ssh

#SSH KEYS
cd ~
cd .ssh
cat authorized_keys

#SSH KEYS PASS CHANGE
cd ~/.ssh
ssh-keygen -p -f <keyfile>

#SSH keys
cd ~/.ssh
ls
cat <file name>

#SSH create a ssh key pair
ssh-keygen -t rsa

#SSH a key from server
ssh-copy-id zima@192.168.5.200



#DOCKER
sudo docker compose up -d
docker network create #NomeDaNetwork#
docker network ls

#NORD VPN
sudo nordvpn restart
nordvpn status
nordvpn connect Brazil









#APPLE - MACBOOK
Flush DNS
sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder

/etc/samba/smb.conf

#SAMBA - 
sudo systemctl restart smbd
sudo service smbd stop
/etc/samba/smb.conf
sudo testparm

#SAMBA USER PASSWD CHANGE
sudo smbpasswd -a your_user

[zima-share]
comment = Private Folder
path = /home/zima/Desktop/public_share
browseable = yes
guest ok = no
read only = no
create mask = 0700
directory mask = 0700
valid users = sambauser
writable = yes   

[zima-HDD]
comment = Private Folder
path = /media/external
browseable = yes
guest ok = no
read only = no
create mask = 0700
directory mask = 0700
valid users = sambauser
writable = yes

[rasp-share]
path = /home/berry/Desktop/share
browseable = yes
writeable = yes
only guest = no
create mask = 0777
directory mask = 0777
public = yes
force user = root

[RASPBERRY]
sudo raspi-config
