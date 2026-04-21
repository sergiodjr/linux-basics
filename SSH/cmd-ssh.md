|<< SSH >>|
|-------------|
<br>

#SSH - https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key

*Install SSH Server*
```
apt update
apt install openssh-server -y
```
<br>

*Show SSH service status*
```
sudo systemctl status ssh
```
<br>

*Enable SSH service*
```
systemctl enable --now ssh
```
<br>

*SSH Config file*
```
nano /etc/ssh/sshd_config
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
