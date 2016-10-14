# virtualbox

## References
* http://www.if-not-true-then-false.com/2010/install-virtualbox-with-yum-on-fedora-centos-red-hat-rhel/

##### Get the repo
```
cd /etc/yum.repos.d/ 
sudo wget http://download.virtualbox.org/virtualbox/rpm/rhel/virtualbox.repo
 
```
##### Update the repo
```
sudo yum update
```

```
rpm -qa kernel |sort -V |tail -n 1
 
uname -r
```

```
yum install VirtualBox-5.1
```

```
service vboxdrv setup
```
