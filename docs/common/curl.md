# curl

## References
* http://stackoverflow.com/questions/8329485/git-clone-fatal-unable-to-find-remote-helper-for-https

### Install 
```
sudo yum install curl
```
```c
/*
Loaded plugins: product-id, security, subscription-manager
Setting up Install Process
Resolving Dependencies
--> Running transaction check
---> Package curl-devel.i386 0:7.15.5-17.el5_9 set to be updated
--> Processing Dependency: openssl-devel for package: curl-devel
--> Processing Dependency: libidn-devel for package: curl-devel
---> Package curl-devel.x86_64 0:7.15.5-17.el5_9 set to be updated
--> Running transaction check
---> Package libidn-devel.x86_64 0:0.6.5-1.1 set to be updated
---> Package openssl-devel.x86_64 0:0.9.8e-39.el5_11 set to be updated
--> Processing Dependency: krb5-devel for package: openssl-devel
--> Running transaction check
---> Package krb5-devel.x86_64 0:1.6.1-80.el5_11 set to be updated
--> Processing Dependency: libselinux-devel for package: krb5-devel
--> Processing Dependency: keyutils-libs-devel for package: krb5-devel
--> Processing Dependency: e2fsprogs-devel for package: krb5-devel
--> Running transaction check
---> Package e2fsprogs-devel.x86_64 0:1.39-37.el5 set to be updated
---> Package keyutils-libs-devel.x86_64 0:1.2-1.el5 set to be updated
---> Package libselinux-devel.x86_64 0:1.33.4-5.7.el5 set to be updated
--> Processing Dependency: libsepol-devel >= 1.15.2-1 for package: libselinux-devel
--> Running transaction check
---> Package libsepol-devel.x86_64 0:1.15.2-3.el5 set to be updated
--> Finished Dependency Resolution

Dependencies Resolved

================================================================================
 Package               Arch     Version              Repository            Size
================================================================================
Installing:
 curl-devel            i386     7.15.5-17.el5_9      rhel-5-server-rpms   310 k
 curl-devel            x86_64   7.15.5-17.el5_9      rhel-5-server-rpms   319 k
Installing for dependencies:
 e2fsprogs-devel       x86_64   1.39-37.el5          rhel-5-server-rpms   639 k
 keyutils-libs-devel   x86_64   1.2-1.el5            rhel-5-server-rpms    27 k
 krb5-devel            x86_64   1.6.1-80.el5_11      rhel-5-server-rpms   1.9 M
 libidn-devel          x86_64   0.6.5-1.1            rhel-5-server-rpms   240 k
 libselinux-devel      x86_64   1.33.4-5.7.el5       rhel-5-server-rpms   149 k
 libsepol-devel        x86_64   1.15.2-3.el5         rhel-5-server-rpms   192 k
 openssl-devel         x86_64   0.9.8e-39.el5_11     rhel-5-server-rpms   1.9 M

Transaction Summary
================================================================================
Install       9 Package(s)
Upgrade       0 Package(s)

Total download size: 5.6 M
*/
```
```
Is this ok [y/N]: y
```
```c
/*
Downloading Packages:
(1/9): keyutils-libs-devel-1.2-1.el5.x86_64.rpm          |  27 kB     00:00
(2/9): libselinux-devel-1.33.4-5.7.el5.x86_64.rpm        | 149 kB     00:00
(3/9): libsepol-devel-1.15.2-3.el5.x86_64.rpm            | 192 kB     00:00
(4/9): libidn-devel-0.6.5-1.1.x86_64.rpm                 | 240 kB     00:00
(5/9): curl-devel-7.15.5-17.el5_9.i386.rpm               | 310 kB     00:00
(6/9): curl-devel-7.15.5-17.el5_9.x86_64.rpm             | 319 kB     00:00
(7/9): e2fsprogs-devel-1.39-37.el5.x86_64.rpm            | 639 kB     00:00
(8/9): openssl-devel-0.9.8e-39.el5_11.x86_64.rpm         | 1.9 MB     00:01
(9/9): krb5-devel-1.6.1-80.el5_11.x86_64.rpm             | 1.9 MB     00:00
--------------------------------------------------------------------------------
Total                                           818 kB/s | 5.6 MB     00:06
Running rpm_check_debug
Running Transaction Test
Finished Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing     : libidn-devel                                             1/9
  Installing     : e2fsprogs-devel                                          2/9
  Installing     : keyutils-libs-devel                                      3/9
  Installing     : libsepol-devel                                           4/9
  Installing     : libselinux-devel                                         5/9
  Installing     : krb5-devel                                               6/9
  Installing     : openssl-devel                                            7/9
  Installing     : curl-devel                                               8/9
  Installing     : curl-devel                                               9/9

Installed:
  curl-devel.i386 0:7.15.5-17.el5_9     curl-devel.x86_64 0:7.15.5-17.el5_9

Dependency Installed:
  e2fsprogs-devel.x86_64 0:1.39-37.el5
  keyutils-libs-devel.x86_64 0:1.2-1.el5
  krb5-devel.x86_64 0:1.6.1-80.el5_11
  libidn-devel.x86_64 0:0.6.5-1.1
  libselinux-devel.x86_64 0:1.33.4-5.7.el5
  libsepol-devel.x86_64 0:1.15.2-3.el5
  openssl-devel.x86_64 0:0.9.8e-39.el5_11

Complete!
*/
```
