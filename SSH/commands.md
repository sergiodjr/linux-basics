|<< SSH >>|
|-------------|
<br>

#SSH - https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key

*Show SSH service status*
```
sudo systemctl status ssh
```
<br>

*Show your SSH keys*
```
cd ~
cd .ssh
cat authorized_keys
```
<br>

*Change SSH key passcode*
```
cd ~/.ssh
ssh-keygen -p -f <keyfile>
```
<br>

*Show SSH key encrypted information (not readable)*
```
cd ~/.ssh
ls
cat <file name>
```
<br>

*Create a SSH pair key*
```
ssh-keygen -t rsa
```
<br>

*SSH pair key with server*
```
ssh-copy-id yourUsername@ <ip>
```

<br>
<br>
