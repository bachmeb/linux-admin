# ius repository

## References
* https://ius.io/Packages/
* https://ius.io/GettingStarted/
* https://fedoraproject.org/wiki/EPEL#How_can_I_use_these_extra_packages.3F
* http://serverfault.com/questions/759828/error-while-installing-mysql-on-centos-6-7
* https://support.rackspace.com/how-to/install-epel-and-additional-repositories-on-centos-and-red-hat/

##### CentOS 6.7
* https://dl.iuscommunity.org/pub/ius/stable/CentOS/6/x86_64/repoview/

##### Install EPEL
```
sudo yum install epel-release
```

##### If that command doesn’t work, perhaps because the CentOS Extras repository is disabled, use the following manual installation instructions based on your distribution version
```
wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm
sudo rpm -Uvh epel-release-6*.rpm
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
```c
/*

Loaded plugins: fastestmirror, refresh-packagekit
Loading mirror speeds from cached hostfile
 * base: chicago.gaminghost.co
 * epel: mirror.steadfast.net
 * extras: bay.uchicago.edu
 * ius: mirror.symnds.com
 * updates: mirror.steadfast.net
ius                                                                                                                                     | 2.2 kB     00:00
ius/primary_db                                                                                                                          | 199 kB     00:01
repo id                                        repo name                                                                                        status
C6.0-base                                      CentOS-6.0 - Base                                                                                disabled
C6.0-centosplus                                CentOS-6.0 - CentOSPlus                                                                          disabled
C6.0-contrib                                   CentOS-6.0 - Contrib                                                                             disabled
C6.0-extras                                    CentOS-6.0 - Extras                                                                              disabled
C6.0-updates                                   CentOS-6.0 - Updates                                                                             disabled
C6.1-base                                      CentOS-6.1 - Base                                                                                disabled
C6.1-centosplus                                CentOS-6.1 - CentOSPlus                                                                          disabled
C6.1-contrib                                   CentOS-6.1 - Contrib                                                                             disabled
C6.1-extras                                    CentOS-6.1 - Extras                                                                              disabled
C6.1-updates                                   CentOS-6.1 - Updates                                                                             disabled
C6.2-base                                      CentOS-6.2 - Base                                                                                disabled
C6.2-centosplus                                CentOS-6.2 - CentOSPlus                                                                          disabled
C6.2-contrib                                   CentOS-6.2 - Contrib                                                                             disabled
C6.2-extras                                    CentOS-6.2 - Extras                                                                              disabled
C6.2-updates                                   CentOS-6.2 - Updates                                                                             disabled
C6.3-base                                      CentOS-6.3 - Base                                                                                disabled
C6.3-centosplus                                CentOS-6.3 - CentOSPlus                                                                          disabled
C6.3-contrib                                   CentOS-6.3 - Contrib                                                                             disabled
C6.3-extras                                    CentOS-6.3 - Extras                                                                              disabled
C6.3-updates                                   CentOS-6.3 - Updates                                                                             disabled
C6.4-base                                      CentOS-6.4 - Base                                                                                disabled
C6.4-centosplus                                CentOS-6.4 - CentOSPlus                                                                          disabled
C6.4-contrib                                   CentOS-6.4 - Contrib                                                                             disabled
C6.4-extras                                    CentOS-6.4 - Extras                                                                              disabled
C6.4-updates                                   CentOS-6.4 - Updates                                                                             disabled
C6.5-base                                      CentOS-6.5 - Base                                                                                disabled
C6.5-centosplus                                CentOS-6.5 - CentOSPlus                                                                          disabled
C6.5-contrib                                   CentOS-6.5 - Contrib                                                                             disabled
C6.5-extras                                    CentOS-6.5 - Extras                                                                              disabled
C6.5-updates                                   CentOS-6.5 - Updates                                                                             disabled
C6.6-base                                      CentOS-6.6 - Base                                                                                disabled
C6.6-centosplus                                CentOS-6.6 - CentOSPlus                                                                          disabled
C6.6-contrib                                   CentOS-6.6 - Contrib                                                                             disabled
C6.6-extras                                    CentOS-6.6 - Extras                                                                              disabled
C6.6-updates                                   CentOS-6.6 - Updates                                                                             disabled
base                                           CentOS-6 - Base                                                                                  enabled:  6,575
base-debuginfo                                 CentOS-6 - Debuginfo                                                                             disabled
c6-media                                       CentOS-6 - Media                                                                                 disabled
centosplus                                     CentOS-6 - Plus                                                                                  disabled
contrib                                        CentOS-6 - Contrib                                                                               disabled
epel                                           Extra Packages for Enterprise Linux 6 - x86_64                                                   enabled: 12,245
epel-debuginfo                                 Extra Packages for Enterprise Linux 6 - x86_64 - Debug                                           disabled
epel-source                                    Extra Packages for Enterprise Linux 6 - x86_64 - Source                                          disabled
epel-testing                                   Extra Packages for Enterprise Linux 6 - Testing - x86_64                                         disabled
epel-testing-debuginfo                         Extra Packages for Enterprise Linux 6 - Testing - x86_64 - Debug                                 disabled
epel-testing-source                            Extra Packages for Enterprise Linux 6 - Testing - x86_64 - Source                                disabled
extras                                         CentOS-6 - Extras                                                                                enabled:     62
fasttrack                                      CentOS-6 - fasttrack                                                                             disabled
ius                                            IUS Community Packages for Enterprise Linux 6 - x86_64                                           enabled:    370
ius-archive                                    IUS Community Packages for Enterprise Linux 6 - x86_64 - Archive                                 disabled
ius-archive-debuginfo                          IUS Community Packages for Enterprise Linux 6 - x86_64 - Archive Debug                           disabled
ius-archive-source                             IUS Community Packages for Enterprise Linux 6 - x86_64 - Archive Source                          disabled
ius-debuginfo                                  IUS Community Packages for Enterprise Linux 6 - x86_64 - Debug                                   disabled
ius-dev                                        IUS Community Packages for Enterprise Linux 6 - x86_64 - Dev                                     disabled
ius-dev-debuginfo                              IUS Community Packages for Enterprise Linux 6 - x86_64 - Dev Debug Info                          disabled
ius-dev-source                                 IUS Community Packages for Enterprise Linux 6 - x86_64 - Dev Source                              disabled
ius-source                                     IUS Community Packages for Enterprise Linux 6 - x86_64 - Source                                  disabled
ius-testing                                    IUS Community Packages for Enterprise Linux 6 - x86_64 - Testing                                 disabled
ius-testing-debuginfo                          IUS Community Packages for Enterprise Linux 6 - x86_64 - Testing Debug                           disabled
ius-testing-source                             IUS Community Packages for Enterprise Linux 6 - x86_64 - Testing Source                          disabled
updates                                        CentOS-6 - Updates                                                                               enabled:  1,622
repolist: 20,874
*/
```

