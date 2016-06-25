# yum

## References
* https://access.redhat.com/solutions/253273
* https://access.redhat.com/solutions/1213413
* http://www.tuxradar.com/answers/440
* https://access.redhat.com/sites/default/files/attachments/rh_yum_cheatsheet_1214_jcs_print-1.pdf
* https://access.redhat.com/documentation/en-US/Red_Hat_Subscription_Management/1/html/RHSM/disable-repos.html
* https://www.centos.org/forums/viewtopic.php?t=9554
* https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Deployment_Guide/sec-Yum_Plugins.html

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
[CentOS5Base]
name=CentOS-5-Base
mirrorlist=http://mirrorlist.centos.org/?release=5&arch=$basearch&repo=os
gpgcheck=1
enabled=1
gpgkey=http://mirror.centos.org/centos/RPM-GPG-KEY-CentOS-5
[CentOS5Updates]
name=CentOS-5-Updates
mirrorlist=http://mirrorlist.centos.org/?release=5&arch=$basearch&repo=updates
gpgcheck=1
enabled=1
gpgkey=http://mirror.centos.org/centos/RPM-GPG-KEY-CentOS-5
[CentOS5Plus]
name=CentOS-5-Plus
mirrorlist=http://mirrorlist.centos.org/?release=5&arch=$basearch&repo=centosplus
gpgcheck=1
enabled=1
gpgkey=http://mirror.centos.org/centos/RPM-GPG-KEY-CentOS-5
```

##### List all repos
```
sudo yum repolist all
```
```
/*
Loaded plugins: product-id, security, subscription-manager
This system is registered to Red Hat Subscription Management, but is not receiving updates. You can use subscription-manager to assign subscriptions.
CentOS5Base                                              | 1.1 kB     00:00
CentOS5Base/primary                                      | 1.3 MB     00:00
CentOS5Plus                                              | 1.9 kB     00:00
CentOS5Plus/primary_db                                   |  91 kB     00:00
CentOS5Updates                                           | 1.9 kB     00:00
CentOS5Updates/primary_db                                | 735 kB     00:01
*/
```

##### List installed packages
```
yum list installed
```

##### Disable the Red Hat Subscription Manager repo
```
subscription-manager config --rhsm.manage_repos=0
```

##### Find which package provides mod_access.so
```
yum provides mod_access.so
```

##### See a list of all the installed and available package groups
```
yum grouplist
```

##### List all available packages
```
yum list available
```

##### List available packages and filter by name
```
yum list available | grep java
yum list available | grep openjdk
```

##### List all available packages and enable all repos
```
yum --enablerepo="*" list available
```

##### List all packages available in all *debug* repos
```
sudo yum --enablerepo='*debug* 'list available
```

##### Show yum info
* Note that the plug-in names which follow Loaded plugins are the names you can provide to the --disableplugins=plugin_name option.
```
yum info yum
```

##### List all repos
```
yum repolist all
```

##### Disable a specific repo
```
subscription-manager repos --disable=rhel-6-server-optional-rpms
```

##### Disable RHN plugin
```
sudo nano /etc/yum/pluginconf.d/rhnplugin.conf
```
```
enabled=0
```

##### Disable Subscription Manager
```
sudo nano /etc/yum/pluginconf.d/subscription-manager.conf
```
```
enabled=0
```

##### If you want to disable one or more Yum plug-ins for a single yum command, add the --disableplugin=plugin_name option
```
yum update --disableplugin=presto
```
