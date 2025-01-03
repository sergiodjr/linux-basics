|<< USERS and GROUPS >>|
|-------------|
<br>

*Login with root*
```
su -
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
id -g <username>
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

*Add a user to a group*
```
usermod -a -G groupaname user
```
<br>

*Show groups members*
```
members groupname
```
<br>

*Query information about a specific group*
```
getent group groupname
```
<br>

*Delete an user*
```
userdel -r username
```
<br>

*Delete a group*
```
sudo groupdel groupname
```

<br>
<br>
