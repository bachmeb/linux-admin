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
