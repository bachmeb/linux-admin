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
