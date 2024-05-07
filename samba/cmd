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
