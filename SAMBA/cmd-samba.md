|<< SAMBA >>|
|-------------|

The folder that will be shared on SAMBA must have permission 0777 set.
<br>
<br>

*Install Samba*
```
sudo apt install samba -y
```
<br>

*Verify the installation*
```
samba --version
```
<br>

*Edit Samba configuration*
```
sudo nano /etc/samba/smb.conf
```
<br>

*Show Samba status and configuration*
```
sudo testparm
```
<br>

*Ensure the services are enabled*
```
sudo systemctl enable smbd nmbd

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

*Add Samba User - This command doesn't create the user. It is meant to give the user permission to connect to SAMBA
It set a SAMBA password for the user and the password can be different from the local password.*
```
sudo smbpasswd -a <USERNAME>
```
<br>

*Delete Samba account*
```
sudo smbpasswd -x <USERNAME>
```
<br>

*Verify Samba Users*
```
sudo pdbedit -L
```
<br>

*Access the Share*
```
smbclient //server-ip/Shared -U <USERNAME>
```
<br>

*To connect to a shared folder on Debian GNU, you can use the ```cifs-utils``` package to mount the shared folder.*
```
sudo apt-get install cifs-utils
```
<br>

*Use the ```mount``` command to mount the shared folder. Replace ```//server/share``` with the path to your shared folder, and provide the necessary credentials.*
*For example, if the shared folder requires a username and password:*
```
sudo mount -t cifs //server/share /mnt/shared_folder -o username=your_username,password=your_password
```
<br>


*To mount the shared folder automatically at boot, add an entry to the /etc/fstab file*
```
sudo nano /etc/fstab
```
<br>

Add a line similar to the following, replacing the placeholders with your actual values:
```
//server/share /mnt/shared_folder cifs username=your_username,password=your_password,uid=1000,gid=1000 0 0
```
Here, uid=1000 and gid=1000 set the ownership of the mounted files to the user with ID 1000, which is typically the first user created on a Debian system.
<br>

