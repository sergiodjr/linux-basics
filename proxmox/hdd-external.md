Mount the HDDs on the Proxmox Host
Identify the devices using lsblk or fdisk -l to confirm their device names (e.g., /dev/sdb1, /dev/sdc1).

Create mount points on the Proxmox host, such as
```
mkdir -p /mnt/hdd1
mkdir -p /mnt/hdd2
```

Mount the drivers
```
mount /dev/sdb1 /mnt/hdd1
mount /dev/sdc1 /mnt/hdd2
```


Edit the LXC Container Configuration
For each LXC container that needs access, edit its configuration file located at ```/etc/pve/lxc/<CTID>.conf```
 
Add lines to bind the directories into the container:
```
mp0: /shared/hdd1,mp=/mnt/hdd1
mp1: /shared/hdd2,mp=/mnt/hdd2
```
