# yum

## References
* https://access.redhat.com/solutions/253273
* https://access.redhat.com/solutions/1213413

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
```c
/*
[sudo] password for bachmeb:
Loaded plugins: product-id, security, subscription-manager
rhel-5-server-cf-tools-1-rpms                            | 3.1 kB     00:00
rhel-5-server-cf-tools-1-rpms/primary_db                 |  18 kB     00:00
rhel-5-server-rpms                                       | 3.7 kB     00:00
rhel-5-server-rpms/primary_db                            | 8.4 MB     00:11
Skipping security plugin, no data
Setting up Update Process
Resolving Dependencies
Skipping security plugin, no data
--> Running transaction check
---> Package at.x86_64 0:3.1.8-84.el5_11.1 set to be updated
---> Package bash.x86_64 0:3.2-33.el5_11.4 set to be updated
---> Package bind-libs.x86_64 30:9.3.6-25.P1.el5_11.8 set to be updated
---> Package bind-utils.x86_64 30:9.3.6-25.P1.el5_11.8 set to be updated
---> Package crash.x86_64 0:5.1.8-3.el5_11 set to be updated
---> Package cups.x86_64 1:1.3.7-32.el5_11 set to be updated
---> Package cups-libs.i386 1:1.3.7-32.el5_11 set to be updated
---> Package cups-libs.x86_64 1:1.3.7-32.el5_11 set to be updated
---> Package device-mapper.i386 0:1.02.67-2.el5_11.1 set to be updated
---> Package device-mapper.x86_64 0:1.02.67-2.el5_11.1 set to be updated
---> Package device-mapper-event.x86_64 0:1.02.67-2.el5_11.1 set to be updated
---> Package device-mapper-multipath.x86_64 0:0.4.7-64.el5_11 set to be updated
---> Package dhcpv6-client.x86_64 0:1.0.10-22.el5_11 set to be updated
---> Package firefox.i386 0:38.7.0-1.el5_11 set to be updated
--> Processing Dependency: libXcomposite.so.1 for package: firefox
---> Package firefox.x86_64 0:38.7.0-1.el5_11 set to be updated
--> Processing Dependency: libXcomposite.so.1()(64bit) for package: firefox
---> Package glibc.i686 0:2.5-123.el5_11.3 set to be updated
---> Package glibc.x86_64 0:2.5-123.el5_11.3 set to be updated
---> Package glibc-common.x86_64 0:2.5-123.el5_11.3 set to be updated
---> Package irqbalance.x86_64 2:0.55-16.el5_11 set to be updated
---> Package kernel.x86_64 0:2.6.18-409.el5 set to be installed
---> Package kpartx.x86_64 0:0.4.7-64.el5_11 set to be updated
---> Package krb5-libs.i386 0:1.6.1-80.el5_11 set to be updated
---> Package krb5-libs.x86_64 0:1.6.1-80.el5_11 set to be updated
---> Package krb5-workstation.x86_64 0:1.6.1-80.el5_11 set to be updated
---> Package ksh.x86_64 0:20100621-24.el5_11 set to be updated
---> Package libXfont.x86_64 0:1.2.2-1.0.6.el5_11 set to be updated
---> Package libgomp.x86_64 0:4.4.7-11.el5_11 set to be updated
---> Package libvolume_id.i386 0:095-14.33.el5_11 set to be updated
---> Package libvolume_id.x86_64 0:095-14.33.el5_11 set to be updated
---> Package libxml2.i386 0:2.6.26-2.1.25.el5_11 set to be updated
---> Package libxml2.x86_64 0:2.6.26-2.1.25.el5_11 set to be updated
---> Package libxml2-python.x86_64 0:2.6.26-2.1.25.el5_11 set to be updated
---> Package net-snmp-libs.x86_64 1:5.3.2.2-25.el5_11 set to be updated
---> Package nfs-utils.x86_64 1:1.0.9-71.el5_11 set to be updated
---> Package nscd.x86_64 0:2.5-123.el5_11.3 set to be updated
---> Package nspr.i386 0:4.10.8-2.el5_11 set to be updated
---> Package nspr.x86_64 0:4.10.8-2.el5_11 set to be updated
---> Package nss.i386 0:3.19.1-4.el5_11 set to be updated
---> Package nss.x86_64 0:3.19.1-4.el5_11 set to be updated
---> Package nss-tools.x86_64 0:3.19.1-4.el5_11 set to be updated
---> Package nss_db.i386 0:2.2-38.el5_11 set to be updated
---> Package nss_db.x86_64 0:2.2-38.el5_11 set to be updated
---> Package nss_ldap.i386 0:253-52.el5_11.2 set to be updated
---> Package nss_ldap.x86_64 0:253-52.el5_11.2 set to be updated
---> Package ntp.x86_64 0:4.2.2p1-18.el5_11 set to be updated
---> Package openldap.i386 0:2.3.43-29.el5_11 set to be updated
---> Package openldap.x86_64 0:2.3.43-29.el5_11 set to be updated
---> Package openssl.i686 0:0.9.8e-39.el5_11 set to be updated
---> Package openssl.x86_64 0:0.9.8e-39.el5_11 set to be updated
---> Package pam.i386 0:0.99.6.2-14.el5_11 set to be updated
---> Package pam.x86_64 0:0.99.6.2-14.el5_11 set to be updated
---> Package perl.x86_64 4:5.8.8-43.el5_11 set to be updated
---> Package popt.i386 0:1.10.2.3-36.el5_11 set to be updated
---> Package popt.x86_64 0:1.10.2.3-36.el5_11 set to be updated
---> Package procmail.x86_64 0:3.22-17.1.2 set to be updated
---> Package redhat-release.x86_64 0:5Server-5.11.0.3 set to be updated
---> Package rpm.x86_64 0:4.4.2.3-36.el5_11 set to be updated
---> Package rpm-libs.x86_64 0:4.4.2.3-36.el5_11 set to be updated
---> Package rpm-python.x86_64 0:4.4.2.3-36.el5_11 set to be updated
---> Package rsync.x86_64 0:3.0.6-6.el5_11 set to be updated
---> Package sendmail.x86_64 0:8.13.8-10.el5_11 set to be updated
---> Package setroubleshoot.noarch 0:2.0.5-7.el5_11 set to be updated
---> Package setroubleshoot-server.noarch 0:2.0.5-7.el5_11 set to be updated
---> Package stunnel.x86_64 0:4.15-2.el5.2 set to be updated
---> Package subscription-manager.x86_64 0:1.11.3-14.el5_11 set to be updated
---> Package subscription-manager-firstboot.x86_64 0:1.11.3-14.el5_11 set to be updated
---> Package subscription-manager-gui.x86_64 0:1.11.3-14.el5_11 set to be updated
---> Package tzdata.x86_64 0:2016c-1.el5 set to be updated
---> Package udev.x86_64 0:095-14.33.el5_11 set to be updated
---> Package xorg-x11-server-Xnest.x86_64 0:1.1.1-48.107.el5_11 set to be updated
---> Package xorg-x11-server-Xorg.x86_64 0:1.1.1-48.107.el5_11 set to be updated
--> Running transaction check
---> Package libXcomposite.i386 0:0.3-5.1 set to be updated
---> Package libXcomposite.x86_64 0:0.3-5.1 set to be updated
rhel-5-server-cf-tools-1-rpms/filelists_db               |  11 kB     00:00
rhel-5-server-rpms/filelists_db                          |  24 MB     00:07
--> Finished Dependency Resolution

Dependencies Resolved

================================================================================
 Package               Arch   Version                  Repository          Size
================================================================================
Installing:
 firefox               i386   38.7.0-1.el5_11          rhel-5-server-rpms  79 M
     replacing  firefox.i386 24.7.0-1.el5_10

 firefox               x86_64 38.7.0-1.el5_11          rhel-5-server-rpms  80 M
     replacing  firefox.x86_64 24.7.0-1.el5_10

 kernel                x86_64 2.6.18-409.el5           rhel-5-server-rpms  22 M
Updating:
 at                    x86_64 3.1.8-84.el5_11.1        rhel-5-server-rpms  58 k
 bash                  x86_64 3.2-33.el5_11.4          rhel-5-server-rpms 1.8 M
 bind-libs             x86_64 30:9.3.6-25.P1.el5_11.8  rhel-5-server-rpms 901 k
 bind-utils            x86_64 30:9.3.6-25.P1.el5_11.8  rhel-5-server-rpms 181 k
 crash                 x86_64 5.1.8-3.el5_11           rhel-5-server-rpms 2.3 M
 cups                  x86_64 1:1.3.7-32.el5_11        rhel-5-server-rpms 3.1 M
 cups-libs             i386   1:1.3.7-32.el5_11        rhel-5-server-rpms 201 k
 cups-libs             x86_64 1:1.3.7-32.el5_11        rhel-5-server-rpms 197 k
 device-mapper         i386   1.02.67-2.el5_11.1       rhel-5-server-rpms 804 k
 device-mapper         x86_64 1.02.67-2.el5_11.1       rhel-5-server-rpms 832 k
 device-mapper-event   x86_64 1.02.67-2.el5_11.1       rhel-5-server-rpms  24 k
 device-mapper-multipath
                       x86_64 0.4.7-64.el5_11          rhel-5-server-rpms 3.0 M
 dhcpv6-client         x86_64 1.0.10-22.el5_11         rhel-5-server-rpms 124 k
 glibc                 i686   2.5-123.el5_11.3         rhel-5-server-rpms 5.4 M
 glibc                 x86_64 2.5-123.el5_11.3         rhel-5-server-rpms 4.8 M
 glibc-common          x86_64 2.5-123.el5_11.3         rhel-5-server-rpms  16 M
 irqbalance            x86_64 2:0.55-16.el5_11         rhel-5-server-rpms  21 k
 kpartx                x86_64 0.4.7-64.el5_11          rhel-5-server-rpms 446 k
 krb5-libs             i386   1.6.1-80.el5_11          rhel-5-server-rpms 670 k
 krb5-libs             x86_64 1.6.1-80.el5_11          rhel-5-server-rpms 683 k
 krb5-workstation      x86_64 1.6.1-80.el5_11          rhel-5-server-rpms 919 k
 ksh                   x86_64 20100621-24.el5_11       rhel-5-server-rpms 1.3 M
 libXfont              x86_64 1.2.2-1.0.6.el5_11       rhel-5-server-rpms 247 k
 libgomp               x86_64 4.4.7-11.el5_11          rhel-5-server-rpms  86 k
 libvolume_id          i386   095-14.33.el5_11         rhel-5-server-rpms  45 k
 libvolume_id          x86_64 095-14.33.el5_11         rhel-5-server-rpms  43 k
 libxml2               i386   2.6.26-2.1.25.el5_11     rhel-5-server-rpms 799 k
 libxml2               x86_64 2.6.26-2.1.25.el5_11     rhel-5-server-rpms 811 k
 libxml2-python        x86_64 2.6.26-2.1.25.el5_11     rhel-5-server-rpms 715 k
 net-snmp-libs         x86_64 1:5.3.2.2-25.el5_11      rhel-5-server-rpms 1.3 M
 nfs-utils             x86_64 1:1.0.9-71.el5_11        rhel-5-server-rpms 410 k
 nscd                  x86_64 2.5-123.el5_11.3         rhel-5-server-rpms 178 k
 nspr                  i386   4.10.8-2.el5_11          rhel-5-server-rpms 124 k
 nspr                  x86_64 4.10.8-2.el5_11          rhel-5-server-rpms 123 k
 nss                   i386   3.19.1-4.el5_11          rhel-5-server-rpms 1.3 M
 nss                   x86_64 3.19.1-4.el5_11          rhel-5-server-rpms 1.3 M
 nss-tools             x86_64 3.19.1-4.el5_11          rhel-5-server-rpms 769 k
 nss_db                i386   2.2-38.el5_11            rhel-5-server-rpms 759 k
 nss_db                x86_64 2.2-38.el5_11            rhel-5-server-rpms 747 k
 nss_ldap              i386   253-52.el5_11.2          rhel-5-server-rpms 1.4 M
 nss_ldap              x86_64 253-52.el5_11.2          rhel-5-server-rpms 1.4 M
 ntp                   x86_64 4.2.2p1-18.el5_11        rhel-5-server-rpms 1.3 M
 openldap              i386   2.3.43-29.el5_11         rhel-5-server-rpms 298 k
 openldap              x86_64 2.3.43-29.el5_11         rhel-5-server-rpms 306 k
 openssl               i686   0.9.8e-39.el5_11         rhel-5-server-rpms 1.7 M
 openssl               x86_64 0.9.8e-39.el5_11         rhel-5-server-rpms 1.7 M
 pam                   i386   0.99.6.2-14.el5_11       rhel-5-server-rpms 983 k
 pam                   x86_64 0.99.6.2-14.el5_11       rhel-5-server-rpms 982 k
 perl                  x86_64 4:5.8.8-43.el5_11        rhel-5-server-rpms  12 M
 popt                  i386   1.10.2.3-36.el5_11       rhel-5-server-rpms  77 k
 popt                  x86_64 1.10.2.3-36.el5_11       rhel-5-server-rpms  79 k
 procmail              x86_64 3.22-17.1.2              rhel-5-server-rpms 171 k
 redhat-release        x86_64 5Server-5.11.0.3         rhel-5-server-rpms  65 k
 rpm                   x86_64 4.4.2.3-36.el5_11        rhel-5-server-rpms 1.2 M
 rpm-libs              x86_64 4.4.2.3-36.el5_11        rhel-5-server-rpms 927 k
 rpm-python            x86_64 4.4.2.3-36.el5_11        rhel-5-server-rpms  65 k
 rsync                 x86_64 3.0.6-6.el5_11           rhel-5-server-rpms 347 k
 sendmail              x86_64 8.13.8-10.el5_11         rhel-5-server-rpms 638 k
 setroubleshoot        noarch 2.0.5-7.el5_11           rhel-5-server-rpms 134 k
 setroubleshoot-server noarch 2.0.5-7.el5_11           rhel-5-server-rpms 1.2 M
 stunnel               x86_64 4.15-2.el5.2             rhel-5-server-rpms 112 k
 subscription-manager  x86_64 1.11.3-14.el5_11         rhel-5-server-rpms 1.1 M
 subscription-manager-firstboot
                       x86_64 1.11.3-14.el5_11         rhel-5-server-rpms 128 k
 subscription-manager-gui
                       x86_64 1.11.3-14.el5_11         rhel-5-server-rpms 545 k
 tzdata                x86_64 2016c-1.el5              rhel-5-server-rpms 774 k
 udev                  x86_64 095-14.33.el5_11         rhel-5-server-rpms 2.4 M
 xorg-x11-server-Xnest x86_64 1.1.1-48.107.el5_11      rhel-5-server-rpms 1.4 M
 xorg-x11-server-Xorg  x86_64 1.1.1-48.107.el5_11      rhel-5-server-rpms 3.4 M
Installing for dependencies:
 libXcomposite         i386   0.3-5.1                  rhel-5-server-rpms  11 k
 libXcomposite         x86_64 0.3-5.1                  rhel-5-server-rpms  12 k

Transaction Summary
================================================================================
Install       5 Package(s)
Upgrade      68 Package(s)

Total download size: 272 M
*/
```
```
Is this ok [y/N]: y
```
```c
/*

Downloading Packages:
(1/73): libXcomposite-0.3-5.1.i386.rpm                   |  11 kB     00:00
(2/73): libXcomposite-0.3-5.1.x86_64.rpm                 |  12 kB     00:00
(3/73): irqbalance-0.55-16.el5_11.x86_64.rpm             |  21 kB     00:00
(4/73): device-mapper-event-1.02.67-2.el5_11.1.x86_64.rp |  24 kB     00:00
(5/73): libvolume_id-095-14.33.el5_11.x86_64.rpm         |  43 kB     00:00
(6/73): libvolume_id-095-14.33.el5_11.i386.rpm           |  45 kB     00:00
(7/73): at-3.1.8-84.el5_11.1.x86_64.rpm                  |  58 kB     00:00
(8/73): redhat-release-5Server-5.11.0.3.x86_64.rpm       |  65 kB     00:00
(9/73): rpm-python-4.4.2.3-36.el5_11.x86_64.rpm          |  65 kB     00:00
(10/73): popt-1.10.2.3-36.el5_11.i386.rpm                |  77 kB     00:00
(11/73): popt-1.10.2.3-36.el5_11.x86_64.rpm              |  79 kB     00:00
(12/73): libgomp-4.4.7-11.el5_11.x86_64.rpm              |  86 kB     00:00
(13/73): stunnel-4.15-2.el5.2.x86_64.rpm                 | 112 kB     00:00
(14/73): nspr-4.10.8-2.el5_11.x86_64.rpm                 | 123 kB     00:00
(15/73): nspr-4.10.8-2.el5_11.i386.rpm                   | 124 kB     00:00
(16/73): dhcpv6-client-1.0.10-22.el5_11.x86_64.rpm       | 124 kB     00:00
(17/73): subscription-manager-firstboot-1.11.3-14.el5_11 | 128 kB     00:00
(18/73): setroubleshoot-2.0.5-7.el5_11.noarch.rpm        | 134 kB     00:00
(19/73): procmail-3.22-17.1.2.x86_64.rpm                 | 171 kB     00:00
(20/73): nscd-2.5-123.el5_11.3.x86_64.rpm                | 178 kB     00:00
(21/73): bind-utils-9.3.6-25.P1.el5_11.8.x86_64.rpm      | 181 kB     00:00
(22/73): cups-libs-1.3.7-32.el5_11.x86_64.rpm            | 197 kB     00:00
(23/73): cups-libs-1.3.7-32.el5_11.i386.rpm              | 201 kB     00:00
(24/73): libXfont-1.2.2-1.0.6.el5_11.x86_64.rpm          | 247 kB     00:00
(25/73): openldap-2.3.43-29.el5_11.i386.rpm              | 298 kB     00:00
(26/73): openldap-2.3.43-29.el5_11.x86_64.rpm            | 306 kB     00:00
(27/73): rsync-3.0.6-6.el5_11.x86_64.rpm                 | 347 kB     00:00
(28/73): nfs-utils-1.0.9-71.el5_11.x86_64.rpm            | 410 kB     00:00
(29/73): kpartx-0.4.7-64.el5_11.x86_64.rpm               | 446 kB     00:00
(30/73): subscription-manager-gui-1.11.3-14.el5_11.x86_6 | 545 kB     00:00
(31/73): sendmail-8.13.8-10.el5_11.x86_64.rpm            | 638 kB     00:00
(32/73): krb5-libs-1.6.1-80.el5_11.i386.rpm              | 670 kB     00:00
(33/73): krb5-libs-1.6.1-80.el5_11.x86_64.rpm            | 683 kB     00:00
(34/73): libxml2-python-2.6.26-2.1.25.el5_11.x86_64.rpm  | 715 kB     00:00
(35/73): nss_db-2.2-38.el5_11.x86_64.rpm                 | 747 kB     00:00
(36/73): nss_db-2.2-38.el5_11.i386.rpm                   | 759 kB     00:00
(37/73): nss-tools-3.19.1-4.el5_11.x86_64.rpm            | 769 kB     00:00
(38/73): tzdata-2016c-1.el5.x86_64.rpm                   | 774 kB     00:00
(39/73): libxml2-2.6.26-2.1.25.el5_11.i386.rpm           | 799 kB     00:00
(40/73): device-mapper-1.02.67-2.el5_11.1.i386.rpm       | 804 kB     00:00
(41/73): libxml2-2.6.26-2.1.25.el5_11.x86_64.rpm         | 811 kB     00:00
(42/73): device-mapper-1.02.67-2.el5_11.1.x86_64.rpm     | 832 kB     00:00
(43/73): bind-libs-9.3.6-25.P1.el5_11.8.x86_64.rpm       | 901 kB     00:00
(44/73): krb5-workstation-1.6.1-80.el5_11.x86_64.rpm     | 919 kB     00:00
(45/73): rpm-libs-4.4.2.3-36.el5_11.x86_64.rpm           | 927 kB     00:00
(46/73): pam-0.99.6.2-14.el5_11.x86_64.rpm               | 982 kB     00:00
(47/73): pam-0.99.6.2-14.el5_11.i386.rpm                 | 983 kB     00:00
(48/73): subscription-manager-1.11.3-14.el5_11.x86_64.rp | 1.1 MB     00:00
(49/73): rpm-4.4.2.3-36.el5_11.x86_64.rpm                | 1.2 MB     00:00
(50/73): setroubleshoot-server-2.0.5-7.el5_11.noarch.rpm | 1.2 MB     00:00
(51/73): ksh-20100621-24.el5_11.x86_64.rpm               | 1.3 MB     00:00
(52/73): nss-3.19.1-4.el5_11.i386.rpm                    | 1.3 MB     00:00
(53/73): nss-3.19.1-4.el5_11.x86_64.rpm                  | 1.3 MB     00:00
(54/73): net-snmp-libs-5.3.2.2-25.el5_11.x86_64.rpm      | 1.3 MB     00:00
(55/73): ntp-4.2.2p1-18.el5_11.x86_64.rpm                | 1.3 MB     00:00
(56/73): nss_ldap-253-52.el5_11.2.x86_64.rpm             | 1.4 MB     00:00
(57/73): xorg-x11-server-Xnest-1.1.1-48.107.el5_11.x86_6 | 1.4 MB     00:00
(58/73): nss_ldap-253-52.el5_11.2.i386.rpm               | 1.4 MB     00:00
(59/73): openssl-0.9.8e-39.el5_11.i686.rpm               | 1.7 MB     00:00
(60/73): openssl-0.9.8e-39.el5_11.x86_64.rpm             | 1.7 MB     00:00
(61/73): bash-3.2-33.el5_11.4.x86_64.rpm                 | 1.8 MB     00:00
(62/73): crash-5.1.8-3.el5_11.x86_64.rpm                 | 2.3 MB     00:01
(63/73): udev-095-14.33.el5_11.x86_64.rpm                | 2.4 MB     00:01
(64/73): device-mapper-multipath-0.4.7-64.el5_11.x86_64. | 3.0 MB     00:01
(65/73): cups-1.3.7-32.el5_11.x86_64.rpm                 | 3.1 MB     00:01
(66/73): xorg-x11-server-Xorg-1.1.1-48.107.el5_11.x86_64 | 3.4 MB     00:01
(67/73): glibc-2.5-123.el5_11.3.x86_64.rpm               | 4.8 MB     00:01
(68/73): glibc-2.5-123.el5_11.3.i686.rpm                 | 5.4 MB     00:02
(69/73): perl-5.8.8-43.el5_11.x86_64.rpm                 |  12 MB     00:06
(70/73): glibc-common-2.5-123.el5_11.3.x86_64.rpm        |  16 MB     00:06
(71/73): kernel-2.6.18-409.el5.x86_64.rpm                |  22 MB     00:08
(72/73): firefox-38.7.0-1.el5_11.i386.rpm                |  79 MB     00:29
(73/73): firefox-38.7.0-1.el5_11.x86_64.rpm              |  80 MB     00:19
--------------------------------------------------------------------------------
Total                                           1.7 MB/s | 272 MB     02:36
warning: rpmts_HdrFromFdno: Header V3 DSA signature: NOKEY, key ID 37017186
rhel-5-server-rpms/gpgkey                                | 1.1 kB     00:00
Importing GPG key 0x37017186 "Red Hat, Inc. (release key) <security@redhat.com>" from /etc/pki/rpm-gpg/RPM-GPG-KEY-redhat-release
*/
```
```
Is this ok [y/N]: y
```
