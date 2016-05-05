# yum

## References
* https://access.redhat.com/solutions/253273
* https://access.redhat.com/solutions/1213413
* http://www.tuxradar.com/answers/440
* https://access.redhat.com/sites/default/files/attachments/rh_yum_cheatsheet_1214_jcs_print-1.pdf

##### Register the system with Red Hat Subscription Management
```
subscription-manager register --username [YOUR RH USERNAME] --password [YOUR RH PASSWORD] --auto-attach
```
```c
/*
You are attempting to run "subscription-manager" which requires administrative
privileges, but more information is needed in order to do so.
Password for root:
The system has been registered with ID: asdfasdf-asdf-asdf-asdf-asdfasdfasdfasdf
Installed Product Current Status:
Product Name: Red Hat Enterprise Linux Server
Status:       Subscribed
*/
```

##### Install system updates
```
sudo yum update
```

##### List all repos
```
yum repolist all
```
```c
/*
Loaded plugins: product-id, security, subscription-manager
repo id           repo name                                             status
rhel-debuginfo    Red Hat Enterprise Linux 5Server - x86_64 - Debug     disabled
repolist: 0
*/
```

### Configure yum to use the CentOS repo
##### Edit yum.conf
```
sudo nano /etc/yum.conf
```

##### For CentOS 5, add these lines
```
[CentOS5 base]
name=CentOS-5-Base
mirrorlist=http://mirrorlist.centos.org/?release=5&arch=$basearch&repo=os
gpgcheck=1
enabled=1
gpgkey=http://mirror.centos.org/centos/RPM-GPG-KEY-CentOS-5
[CentOS5 updates]
name=CentOS-5-Updates
mirrorlist=http://mirrorlist.centos.org/?release=5&arch=$basearch&repo=updates
gpgcheck=1
enabled=1
gpgkey=http://mirror.centos.org/centos/RPM-GPG-KEY-CentOS-5
[CentOS5plus]
name=CentOS-5-Plus
mirrorlist=http://mirrorlist.centos.org/?release=5&arch=$basearch&repo=centosplus
gpgcheck=1
enabled=1
gpgkey=http://mirror.centos.org/centos/RPM-GPG-KEY-CentOS-5
```

##### List installed packages
```
yum list installed
```
