
## References
* 

##### Install
```
sudo yum install xclock
```
```c
/*
Loaded plugins: fastestmirror
Setting up Install Process
Loading mirror speeds from cached hostfile
 * base: centos.mirror.nac.net
 * extras: mirror.sesp.northwestern.edu
 * updates: mirror.beyondhosting.net
Resolving Dependencies
--> Running transaction check
---> Package xorg-x11-apps.x86_64 0:7.7-6.el6 will be installed
--> Processing Dependency: libpng12.so.0(PNG12_0)(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libxkbfile.so.1()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libpng12.so.0()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libfontenc.so.1()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libfontconfig.so.1()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libXxf86vm.so.1()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libXt.so.6()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libXrender.so.1()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libXmuu.so.1()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libXmu.so.6()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libXft.so.2()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libXext.so.6()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libXcursor.so.1()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libXaw.so.7()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libX11.so.6()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Processing Dependency: libSM.so.6()(64bit) for package: xorg-x11-apps-7.7-6.el6.x86_64
--> Running transaction check
---> Package fontconfig.x86_64 0:2.8.0-5.el6 will be installed
--> Processing Dependency: freetype >= 2.1.4 for package: fontconfig-2.8.0-5.el6.x86_64
--> Processing Dependency: libfreetype.so.6()(64bit) for package: fontconfig-2.8.0-5.el6.x86_64
---> Package libSM.x86_64 0:1.2.1-2.el6 will be installed
--> Processing Dependency: libICE.so.6()(64bit) for package: libSM-1.2.1-2.el6.x86_64
---> Package libX11.x86_64 0:1.6.0-6.el6 will be installed
--> Processing Dependency: libX11-common = 1.6.0-6.el6 for package: libX11-1.6.0-6.el6.x86_64
--> Processing Dependency: libxcb.so.1()(64bit) for package: libX11-1.6.0-6.el6.x86_64
---> Package libXaw.x86_64 0:1.0.11-2.el6 will be installed
--> Processing Dependency: libXpm.so.4()(64bit) for package: libXaw-1.0.11-2.el6.x86_64
---> Package libXcursor.x86_64 0:1.1.14-2.1.el6 will be installed
--> Processing Dependency: libXfixes.so.3()(64bit) for package: libXcursor-1.1.14-2.1.el6.x86_64
---> Package libXext.x86_64 0:1.3.2-2.1.el6 will be installed
---> Package libXft.x86_64 0:2.3.1-2.el6 will be installed
---> Package libXmu.x86_64 0:1.1.1-2.el6 will be installed
---> Package libXrender.x86_64 0:0.9.8-2.1.el6 will be installed
---> Package libXt.x86_64 0:1.1.4-6.1.el6 will be installed
---> Package libXxf86vm.x86_64 0:1.1.3-2.1.el6 will be installed
---> Package libfontenc.x86_64 0:1.0.5-2.el6 will be installed
---> Package libpng.x86_64 2:1.2.49-2.el6_7 will be installed
---> Package libxkbfile.x86_64 0:1.0.6-1.1.el6 will be installed
--> Running transaction check
---> Package freetype.x86_64 0:2.3.11-15.el6_6.1 will be installed
---> Package libICE.x86_64 0:1.0.6-1.el6 will be installed
---> Package libX11-common.noarch 0:1.6.0-6.el6 will be installed
---> Package libXfixes.x86_64 0:5.0.1-2.1.el6 will be installed
---> Package libXpm.x86_64 0:3.5.10-2.el6 will be installed
---> Package libxcb.x86_64 0:1.9.1-3.el6 will be installed
--> Processing Dependency: libXau.so.6()(64bit) for package: libxcb-1.9.1-3.el6.x86_64
--> Running transaction check
---> Package libXau.x86_64 0:1.0.6-4.el6 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

================================================================================
 Package             Arch         Version                   Repository     Size
================================================================================
Installing:
 xorg-x11-apps       x86_64       7.7-6.el6                 base          276 k
Installing for dependencies:
 fontconfig          x86_64       2.8.0-5.el6               base          186 k
 freetype            x86_64       2.3.11-15.el6_6.1         base          361 k
 libICE              x86_64       1.0.6-1.el6               base           53 k
 libSM               x86_64       1.2.1-2.el6               base           37 k
 libX11              x86_64       1.6.0-6.el6               base          586 k
 libX11-common       noarch       1.6.0-6.el6               base          192 k
 libXau              x86_64       1.0.6-4.el6               base           24 k
 libXaw              x86_64       1.0.11-2.el6              base          178 k
 libXcursor          x86_64       1.1.14-2.1.el6            base           28 k
 libXext             x86_64       1.3.2-2.1.el6             base           35 k
 libXfixes           x86_64       5.0.1-2.1.el6             base           17 k
 libXft              x86_64       2.3.1-2.el6               base           55 k
 libXmu              x86_64       1.1.1-2.el6               base           66 k
 libXpm              x86_64       3.5.10-2.el6              base           51 k
 libXrender          x86_64       0.9.8-2.1.el6             base           24 k
 libXt               x86_64       1.1.4-6.1.el6             base          165 k
 libXxf86vm          x86_64       1.1.3-2.1.el6             base           16 k
 libfontenc          x86_64       1.0.5-2.el6               base           24 k
 libpng              x86_64       2:1.2.49-2.el6_7          updates       182 k
 libxcb              x86_64       1.9.1-3.el6               base          110 k
 libxkbfile          x86_64       1.0.6-1.1.el6             base           74 k

Transaction Summary
================================================================================
Install      22 Package(s)

Total download size: 2.7 M
Installed size: 7.7 M
Is this ok [y/N]: y
Downloading Packages:
(1/22): fontconfig-2.8.0-5.el6.x86_64.rpm                | 186 kB     00:00
(2/22): freetype-2.3.11-15.el6_6.1.x86_64.rpm            | 361 kB     00:00
(3/22): libICE-1.0.6-1.el6.x86_64.rpm                    |  53 kB     00:00
(4/22): libSM-1.2.1-2.el6.x86_64.rpm                     |  37 kB     00:00
(5/22): libX11-1.6.0-6.el6.x86_64.rpm                    | 586 kB     00:00
(6/22): libX11-common-1.6.0-6.el6.noarch.rpm             | 192 kB     00:00
(7/22): libXau-1.0.6-4.el6.x86_64.rpm                    |  24 kB     00:00
(8/22): libXaw-1.0.11-2.el6.x86_64.rpm                   | 178 kB     00:00
(9/22): libXcursor-1.1.14-2.1.el6.x86_64.rpm             |  28 kB     00:00
(10/22): libXext-1.3.2-2.1.el6.x86_64.rpm                |  35 kB     00:00
(11/22): libXfixes-5.0.1-2.1.el6.x86_64.rpm              |  17 kB     00:00
(12/22): libXft-2.3.1-2.el6.x86_64.rpm                   |  55 kB     00:00
(13/22): libXmu-1.1.1-2.el6.x86_64.rpm                   |  66 kB     00:00
(14/22): libXpm-3.5.10-2.el6.x86_64.rpm                  |  51 kB     00:00
(15/22): libXrender-0.9.8-2.1.el6.x86_64.rpm             |  24 kB     00:00
(16/22): libXt-1.1.4-6.1.el6.x86_64.rpm                  | 165 kB     00:00
(17/22): libXxf86vm-1.1.3-2.1.el6.x86_64.rpm             |  16 kB     00:00
(18/22): libfontenc-1.0.5-2.el6.x86_64.rpm               |  24 kB     00:00
(19/22): libpng-1.2.49-2.el6_7.x86_64.rpm                | 182 kB     00:00
(20/22): libxcb-1.9.1-3.el6.x86_64.rpm                   | 110 kB     00:00
(21/22): libxkbfile-1.0.6-1.1.el6.x86_64.rpm             |  74 kB     00:00
(22/22): xorg-x11-apps-7.7-6.el6.x86_64.rpm              | 276 kB     00:00
--------------------------------------------------------------------------------
Total                                           672 kB/s | 2.7 MB     00:04
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing : libICE-1.0.6-1.el6.x86_64                                   1/22
  Installing : libSM-1.2.1-2.el6.x86_64                                    2/22
  Installing : freetype-2.3.11-15.el6_6.1.x86_64                           3/22
  Installing : fontconfig-2.8.0-5.el6.x86_64                               4/22
  Installing : libXau-1.0.6-4.el6.x86_64                                   5/22
  Installing : libxcb-1.9.1-3.el6.x86_64                                   6/22
  Installing : libX11-common-1.6.0-6.el6.noarch                            7/22
  Installing : libX11-1.6.0-6.el6.x86_64                                   8/22
  Installing : libXext-1.3.2-2.1.el6.x86_64                                9/22
  Installing : libXrender-0.9.8-2.1.el6.x86_64                            10/22
  Installing : libXt-1.1.4-6.1.el6.x86_64                                 11/22
  Installing : libXmu-1.1.1-2.el6.x86_64                                  12/22
  Installing : libXft-2.3.1-2.el6.x86_64                                  13/22
  Installing : libXxf86vm-1.1.3-2.1.el6.x86_64                            14/22
  Installing : libXpm-3.5.10-2.el6.x86_64                                 15/22
  Installing : libXaw-1.0.11-2.el6.x86_64                                 16/22
  Installing : libXfixes-5.0.1-2.1.el6.x86_64                             17/22
  Installing : libXcursor-1.1.14-2.1.el6.x86_64                           18/22
  Installing : libxkbfile-1.0.6-1.1.el6.x86_64                            19/22
  Installing : libfontenc-1.0.5-2.el6.x86_64                              20/22
  Installing : 2:libpng-1.2.49-2.el6_7.x86_64                             21/22
  Installing : xorg-x11-apps-7.7-6.el6.x86_64                             22/22
  Verifying  : libXrender-0.9.8-2.1.el6.x86_64                             1/22
  Verifying  : libXpm-3.5.10-2.el6.x86_64                                  2/22
  Verifying  : fontconfig-2.8.0-5.el6.x86_64                               3/22
  Verifying  : libSM-1.2.1-2.el6.x86_64                                    4/22
  Verifying  : libXfixes-5.0.1-2.1.el6.x86_64                              5/22
  Verifying  : 2:libpng-1.2.49-2.el6_7.x86_64                              6/22
  Verifying  : libXext-1.3.2-2.1.el6.x86_64                                7/22
  Verifying  : libXt-1.1.4-6.1.el6.x86_64                                  8/22
  Verifying  : libfontenc-1.0.5-2.el6.x86_64                               9/22
  Verifying  : xorg-x11-apps-7.7-6.el6.x86_64                             10/22
  Verifying  : libX11-1.6.0-6.el6.x86_64                                  11/22
  Verifying  : freetype-2.3.11-15.el6_6.1.x86_64                          12/22
  Verifying  : libXft-2.3.1-2.el6.x86_64                                  13/22
  Verifying  : libxkbfile-1.0.6-1.1.el6.x86_64                            14/22
  Verifying  : libXxf86vm-1.1.3-2.1.el6.x86_64                            15/22
  Verifying  : libX11-common-1.6.0-6.el6.noarch                           16/22
  Verifying  : libxcb-1.9.1-3.el6.x86_64                                  17/22
  Verifying  : libXcursor-1.1.14-2.1.el6.x86_64                           18/22
  Verifying  : libXaw-1.0.11-2.el6.x86_64                                 19/22
  Verifying  : libXau-1.0.6-4.el6.x86_64                                  20/22
  Verifying  : libICE-1.0.6-1.el6.x86_64                                  21/22
  Verifying  : libXmu-1.1.1-2.el6.x86_64                                  22/22

Installed:
  xorg-x11-apps.x86_64 0:7.7-6.el6

Dependency Installed:
  fontconfig.x86_64 0:2.8.0-5.el6        freetype.x86_64 0:2.3.11-15.el6_6.1
  libICE.x86_64 0:1.0.6-1.el6            libSM.x86_64 0:1.2.1-2.el6
  libX11.x86_64 0:1.6.0-6.el6            libX11-common.noarch 0:1.6.0-6.el6
  libXau.x86_64 0:1.0.6-4.el6            libXaw.x86_64 0:1.0.11-2.el6
  libXcursor.x86_64 0:1.1.14-2.1.el6     libXext.x86_64 0:1.3.2-2.1.el6
  libXfixes.x86_64 0:5.0.1-2.1.el6       libXft.x86_64 0:2.3.1-2.el6
  libXmu.x86_64 0:1.1.1-2.el6            libXpm.x86_64 0:3.5.10-2.el6
  libXrender.x86_64 0:0.9.8-2.1.el6      libXt.x86_64 0:1.1.4-6.1.el6
  libXxf86vm.x86_64 0:1.1.3-2.1.el6      libfontenc.x86_64 0:1.0.5-2.el6
  libpng.x86_64 2:1.2.49-2.el6_7         libxcb.x86_64 0:1.9.1-3.el6
  libxkbfile.x86_64 0:1.0.6-1.1.el6

Complete!
*/
```
