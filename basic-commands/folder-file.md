|<< FOLDER and FILES >>|
|-------------|
<br>

*Create a folder*
```
mkdir foldername
```
<br>

*You can create sub-directories of a director*
```
mkdir -p foldername/subdirectory
```
<br>

*Remove a directory and its contents*
```
rm -r foldername
```
<br>

*Remove a directory prompting for confirmation*
```
rm -ri foldername
```
<br>

*Force removal without confirmation*
```
rm -rf foldername
```
<br>

*Change both the owner and group of a folder or file*
```
sudo chown owner:groupname /path/to/folder
```
<br>

*Change the owner of a file to a specific user*
```
chown <USERNAME> <FILENAME>
```
<br>

*Recursively change ownership for all files and directories within a directory*
```
chown -R username:groupname directoryname
```
<br>

*Change folder permission*
```
chmod -R 755 /path/to/folder
```
<br>
