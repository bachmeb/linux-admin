# p7zip aka 7-zip

## References
* https://www.ibm.com/developerworks/community/blogs/6e6f6d1b-95c3-46df-8a26-b7efd8ee4b57/entry/how_to_use_7zip_on_linux_command_line144?lang=en

## Notes
* DO NOT USE the 7-zip format for backup purpose on Linux/Unix because : 
  * 7-zip does not store the owner/group of the file. 
* On Linux/Unix, in order to backup directories you must use tar : 
  * to backup a directory : tar cf - directory | 7za a -si directory.tar.7z 
  * to restore your backup : 7za x -so directory.tar.7z | tar xf 
* If you want to send files and directories (not the owner of file) to others Unix/MacOS/Windows users, you can use the 7-zip format. 
  * example : 7za a directory.7z directory 
* Do not use "-r" because this flag does not do what you think. 
* Do not use directory/* because of ".*" files (example : "directory/*" does not match "directory/.profile") 

##### Install
```
sudo yum search p7zip
sudo yum install p7zip
```

##### Find 7zip
```
whereis 7z
whereis 7za
whereis 7zr
```
##### Create an archive
```
7z a basic.7z basic
```
##### Extract an archive
```
7z e basic.7z
```
##### List archive details
```
7z l basic.7z
```
##### Test archive integrity
```
7z t basic.7z basic
```
