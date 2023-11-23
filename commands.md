|<< System Related >>|
|-------------|

*Reboots the system immediately*
```
sudo reboot
sudo systemctl reboot
```

*Shuts down the system immediately*
```
sudo halt
```

*Edit your hostname*
```
sudo nano /etc/hostname
```

*Edit your known host*
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

|<< Partitions >>|
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
sudo mount /dev/sda2 /you/pick/thefolder
```
mount | grep external_hardrive
sudo nano /etc/fstab

#UMOUNT
sudo umount /dev/sda2
sudo umount -l /media/external

#MOUNT A EXFAT PARTITION
sudo mount -t exfat /dev/sda2 /media/external






#PARTITIONS USED SPACE
df -T

#PACKAGE MANAGER
sudo apt-get install synaptic gnome-software
dpkg --list
dpkg --list | grep apache

#APT GET
Update the package list by running the command:
sudo apt update

#LIST SERVICES
systemctl list-units --type=service --state=running
systemctl status service-name
sudo systemctl stop service-name
sudo systemctl start service-name

#PORT LISTEN
sudo lsof -iTCP -sTCP:LISTEN -n -P

#SERVICES
ystemctl list-unit-files --state=enabled


**- USER**

#USER
id -u
Comand User ID and group id

#USER LIST
getent passwd
cat /etc/passwd
getent passwd | awk -F: '$3 >= 1000 && $3 < 65534 {print $1}'

#GROUPS
cat /etc/group

*List and install available GUI (Graphical User Interface)*
usermod -a -G <groupaname> <user>

members <groupname>
getent group <groupname>
sudo groupdel <groupname>


**- FOLDER**

#CREATE FOLDER
mkdir
mkdir -p #command you can create sub-directories of a directory
$mkdir hello/goodbye
mkdir:cannot create directory 'hello/goodbye': No such file or directory
$mkdir -p hello/goodbye

#DELETE FOLDER
rm -r
sudo rm -rf /my/locked/directory

#FOLDER CHANGE OWNER AND GROUP
sudo chown owner:group /path/to/folder

#FOLDER PERMISSION CHANGE AND ITS SUBFILES
chmod -R 755








**- SSH**

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





Upgrade the installed packages by running the command:
sudo apt upgrade

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
