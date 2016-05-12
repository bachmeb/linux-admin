# rpm

## References
* https://www.centos.org/forums/viewtopic.php?t=53593

##### Check the CentOS release
```
rpm -q centos-release
```
```c
/*
centos-release-6-7.el6.centos.12.3.x86_64
*/
```


##### Add a repo package
```
sudo rpm -Uvh mysql57-community-release-el6-8.noarch.rpm
```

##### Find a repo package
```
sudo rpm -qa | grep -i mys
```

##### Remove a repo package
```
sudo rpm -e  mysql57-community-release-el6-8.noarch
```
