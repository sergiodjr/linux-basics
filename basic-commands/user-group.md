|<< USERS and GROUPS >>|
|-------------|
<br>

*Login with root*
```
su
```
<br>

*Add the User*
```
sudo adduser <USERNAME>
```
<br>

*Verify the User*
```
getent passwd <USERNAME>
```
<br>

*Change user password*
```
sudo passwd <USERNAME>
```
<br>

*Delete a user*
```
userdel -r <USERNAME>
```
<br>

*To view a list of all groups a user belongs t*
```
groups <USERNAME>
```
<br>

*Show user account ID*
```
id -u
cat /etc/passwd
```
<br>

*To find the PGID (Primary Group ID)*
```
id -g <USERNAME>
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

*Delete a group*
```
sudo groupdel <GROUPNAME>
```
<br>

*Add a user to a group*
```
usermod -a -G <GROUPNAME> <USERNAME>
```
<br>

*Remove user from group*
```
sudo deluser <USERNAME> <GROUPNAME>
```
<br>

*Show groups members*
```
members <GROUPNAME>
```
<br>

*Query information about a specific group*
```
getent group <GROUPNAME>
```
<br>
