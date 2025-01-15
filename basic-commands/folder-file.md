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

*Make the Script Executable*
```
chmod +x SCRIPT.sh
```
<br>

|<< PERMISSION >>|
|-------------|
<br>

**r:** Read permission.<br>
**w:** Write permission.<br>
**x:** Execute permission.<br>
<br>

**The permissions are displayed for three different categories:**<br>
User (u): The owner of the file.<br>
Group (g): The group to which the file belongs.<br>
Others (o): Everyone else.<br>
<br>

```
-rwxr-xr-x 1 user user 1234 Jul 21 12:34 script.sh
```
<br>

**In the example above, ```-rwxr-xr-x``` means:**<br>
The owner (user) can read, write, and execute (```rwx```).<br>
The group can read and execute (```r-x```).<br>
Others can read and execute (```r-x```).<br>
<br>

|<< MOVING AND COPYING FILES >>|
|-------------|
<br>

*To move a directory from one location to another, use the mv command.*
```
mv /path/to/source_directory /path/to/destination_directory
```
<br>

*To copy a directory (and its contents), use the cp command with the -r (recursive) option.*
```
cp -r /path/to/source_directory /path/to/destination_directory
```
<br>

*Preserve file attributes: Use -a (archive) with cp to preserve permissions, timestamps, and symbolic links*
```
cp -ar /path/to/source_directory /path/to/destination_directory
```
<br>

*To monitor the copying progress use ```pv``` to monitor the progress of data through a pipe.*<br>
```
sudo apt-get install pv
```
<br>

*To copy a file and show progress, you can use:*
```
pv source_file > destination_file
```
<br>

*For copying directories, you can combine ```tar``` with ```pv```:*
```
tar -cf - source_directory | pv | tar -xf - -C destination_directory
```
<br>
