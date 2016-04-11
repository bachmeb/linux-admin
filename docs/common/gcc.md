# gcc

## References
* https://gcc.gnu.org/

### Install
##### RHEL 5.11
```
sudo yum install gcc
```
```c
/*
Loaded plugins: product-id, security, subscription-manager
Setting up Install Process
Resolving Dependencies
--> Running transaction check
---> Package gcc.x86_64 0:4.1.2-55.el5 set to be updated
--> Processing Dependency: glibc-devel >= 2.2.90-12 for package: gcc
--> Running transaction check
---> Package glibc-devel.x86_64 0:2.5-123.el5_11.3 set to be updated
--> Processing Dependency: glibc-headers = 2.5-123.el5_11.3 for package: glibc-devel
--> Processing Dependency: glibc-headers for package: glibc-devel
--> Running transaction check
---> Package glibc-headers.x86_64 0:2.5-123.el5_11.3 set to be updated
--> Processing Dependency: kernel-headers >= 2.2.1 for package: glibc-headers
--> Processing Dependency: kernel-headers for package: glibc-headers
--> Running transaction check
---> Package kernel-headers.x86_64 0:2.6.18-409.el5 set to be updated
--> Finished Dependency Resolution

Dependencies Resolved

================================================================================
 Package           Arch      Version                Repository             Size
================================================================================
Installing:
 gcc               x86_64    4.1.2-55.el5           rhel-5-server-rpms    5.3 M
Installing for dependencies:
 glibc-devel       x86_64    2.5-123.el5_11.3       rhel-5-server-rpms    2.4 M
 glibc-headers     x86_64    2.5-123.el5_11.3       rhel-5-server-rpms    602 k
 kernel-headers    x86_64    2.6.18-409.el5         rhel-5-server-rpms    1.5 M

Transaction Summary
================================================================================
Install       4 Package(s)
Upgrade       0 Package(s)

Total download size: 9.8 M
*/
```
```
Is this ok [y/N]: y
```
```c
/*
Downloading Packages:
(1/4): glibc-headers-2.5-123.el5_11.3.x86_64.rpm         | 602 kB     00:00
(2/4): kernel-headers-2.6.18-409.el5.x86_64.rpm          | 1.5 MB     00:00
(3/4): glibc-devel-2.5-123.el5_11.3.x86_64.rpm           | 2.4 MB     00:01
(4/4): gcc-4.1.2-55.el5.x86_64.rpm                       | 5.3 MB     00:01
--------------------------------------------------------------------------------
Total                                           1.8 MB/s | 9.8 MB     00:05
Running rpm_check_debug
Running Transaction Test
Finished Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing     : kernel-headers                                           1/4
  Installing     : glibc-headers                                            2/4
  Installing     : glibc-devel                                              3/4
  Installing     : gcc                                                      4/4

Installed:
  gcc.x86_64 0:4.1.2-55.el5

Dependency Installed:
  glibc-devel.x86_64 0:2.5-123.el5_11.3
  glibc-headers.x86_64 0:2.5-123.el5_11.3
  kernel-headers.x86_64 0:2.6.18-409.el5

Complete!
*/
```
