|<< SYSTEM >>|
|-------------|
<br>

*Check the Debian version*
```
lsb_release -a
```
<br>

*Reboots the system immediately*
```
sudo reboot
sudo systemctl reboot
```
<br>

*Shuts down the system immediately*
```
sudo halt
```
<br>

*Edit hostname*
```
sudo nano /etc/hostname
```
<br>

*Edit known host*
```
sudo nano /etc/hosts
```
<br>

*Syslog live log (stop pressing ctrl+c)* 
```
sudo tail -f /var/log/syslog
```
<br>

*Check for Shutdown Logsg* 
```
sudo journalctl -b -1 -e
```
<br>

*Specific Shutdown and Reboot Events* 
```
sudo journalctl --unit=systemd-shutdown
```
<br>

*Viewing Specific Time Range:*
```
sudo journalctl --since "2024-06-17 10:00:00" --until "2024-06-17 10:30:00"
```

*List and install available GUI (Graphical User Interface)*
```
tasksel
```
<br>

*List all running services*
```
systemctl list-units --type=service --state=running
```
<br>

*List files with enabled status*
```
systemctl list-unit-files --state=enabled
```
<br>

*Show service status*
```
systemctl status service-name
```
<br>

*Start service*
```
sudo systemctl start service-name
```
<br>

*Stop service*
```
sudo systemctl stop service-name
```
<br>

*List all open TCP ports*
```
sudo lsof -iTCP -sTCP:LISTEN -n -P
```
<br>
