|<< DISK and PARTITIONS >>|
|-------------|
<br>

*List available disk/partitions showing its name, size and mount point:*
```
lsblk
```
<br>

*List and show more details of disk/partitions:*
```
lsblk -f
```
<br>

*This shows disk space usage along with mounted filesystems:*
```
df -h
```
<br>

*List available disk/partitions showing its FSTYPE, and mount point:*
```
sudo lsblk -o NAME,FSTYPE,MOUNTPOINT
```
<br>

*List all disk/partitions information:*
```
sudo fdisk -l
```
<br>

*Mount a drive on a desire folder:*
```
sudo mount /dev/YouPickTheDrive /you/pick/thefolder
```
<br>

*Unmount the device on /dev/sda2:*
```
sudo umount /dev/YouPickTheDrive /you/pick/thefolder
```
<br>

*Force unmount the device on /dev/sda2:*
```
sudo umount -f /dev/YouPickTheDrive
```
<br>

*Mount exFat partition:*
```
sudo mount -t exfat /dev/sda2 /you/pick/thefolder
```
<br>

*Shows devices, filesystem, type, used and available space, also the mount location:*
```
df -T
```
<br>

*Format the entire disk as ext4. Example /dev/sdb2:*
```
sudo mkfs.ext4 /dev/sdb2
```
<br>

*Use the e2label command to label the filesystem - Unmount it FIRST:*
```
sudo e2label /dev/<DISK> <MY-DRIVE>
```
<br>
