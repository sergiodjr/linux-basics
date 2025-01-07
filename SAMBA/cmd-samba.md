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
