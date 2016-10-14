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
yum install binutils gcc make patch libgomp glibc-headers glibc-devel kernel-headers kernel-PAE-devel dkms
```

```
sudo yum search virtualbox
```
```c
/*
VirtualBox-3.2.x86_64 : Oracle VM VirtualBox
VirtualBox-4.0.x86_64 : Oracle VM VirtualBox
VirtualBox-4.1.x86_64 : Oracle VM VirtualBox
VirtualBox-4.2.x86_64 : Oracle VM VirtualBox
VirtualBox-4.3.x86_64 : Oracle VM VirtualBox
VirtualBox-5.0.x86_64 : Oracle VM VirtualBox
VirtualBox-5.1.x86_64 : Oracle VM VirtualBox
*/
```
```
sudo yum install VirtualBox-5.1
```

```
/etc/init.d/vboxdrv setup
```
