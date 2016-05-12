# ius repository

## References
* https://ius.io/Packages/
* https://ius.io/GettingStarted/
* https://fedoraproject.org/wiki/EPEL#How_can_I_use_these_extra_packages.3F
* http://serverfault.com/questions/759828/error-while-installing-mysql-on-centos-6-7

##### CentOS 6.7
* https://dl.iuscommunity.org/pub/ius/stable/CentOS/6/x86_64/repoview/

##### Install EPEL
```
sudo yum install epel-release
```

##### Download IUS-COMMUNITY-GPG-KEY
```
sudo wget https://dl.iuscommunity.org/pub/ius/IUS-COMMUNITY-GPG-KEY -O /etc/pki/rpm-gpg/IUS-COMMUNITY-GPG-KEY
```

##### Import the GPG key
```
sudo rpm --import /etc/pki/rpm-gpg/IUS-COMMUNITY-GPG-KEY
```

##### Find a URL to download ius-release-1.0-14.ius.centos6.noarch.rpm
* https://dl.iuscommunity.org/pub/ius/stable/CentOS/6/x86_64/

##### Download ius-release-1.0-14.ius.centos6.noarch.rpm
```
cd ~
wget https://dl.iuscommunity.org/pub/ius/stable/CentOS/6/x86_64/ius-release-1.0-14.ius.centos6.noarch.rpm
```

##### Add the IUS repo
```
sudo rpm -Uvh ius-release-1.0-14.ius.centos6.noarch.rpm
```
```
/*
Preparing...                ########################################### [100%]
   1:ius-release            ########################################### [100%]
*/
```

##### List all repos
```
sudo yum repolist all
```

