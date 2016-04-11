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
*/
```
