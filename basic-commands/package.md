|<< PACKAGE MANAGMENT >>|
|-------------|
<br>

*Update the repositories/packages*
```
sudo apt-get update
```
<br>

*Apply the updates*
```
sudo apt-get upgrade
```
<br>

*List all installed packages along with their status and other information*
```
dpkg --list
```
<br>

*Keep in mind that the output may be quite extensive, depending on the number of installed packages on your system.* 
*If you want to search for a specific package, you can pipe the output to grep*
```
dpkg --list | grep packagename
```
<br>

*Installs Synaptic Package Manager, friendly interface for package management*
```
sudo apt-get install synaptic 
```
<br>
