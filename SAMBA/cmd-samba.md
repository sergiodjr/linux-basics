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
