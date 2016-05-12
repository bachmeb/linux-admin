# gnome

## References
* https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Installation_Guide/sn-switching-to-gui-login.html

##### Install the X Window System group
```
yum groupinstall "X Window System" Desktop
```
```
/*
Loaded plugins: product-id, security, subscription-manager
You need to be root to perform this command.
[bachmeb@99700hlzx6g1 datavault]$ sudo yum groupinstall "X Window System" Desktop
Loaded plugins: product-id, security, subscription-manager
This system is registered to Red Hat Subscription Management, but is not receiving updates. You can use subscription-manager to assign subscriptions.
Setting up Group Process
Package xorg-x11-fonts-misc-7.1-2.1.el5.noarch already installed and latest version
Package matching xorg-x11-server-Xorg-1.1.1-48.107.el5.centos.x86_64 already installed. Checking for update.
Package xorg-x11-fonts-ISO8859-1-75dpi-7.1-2.1.el5.noarch already installed and latest version
Package xorg-x11-fonts-100dpi-7.1-2.1.el5.noarch already installed and latest version
Package xorg-x11-fonts-75dpi-7.1-2.1.el5.noarch already installed and latest version
Package 1:xorg-x11-xauth-1.0.1-2.1.x86_64 already installed and latest version
Package xorg-x11-fonts-ISO8859-1-100dpi-7.1-2.1.el5.noarch already installed and latest version
Package xorg-x11-xinit-1.0.2-15.el5.x86_64 already installed and latest version
Package xorg-x11-fonts-Type1-7.1-2.1.el5.noarch already installed and latest version
Package 1:xorg-x11-xfs-1.0.2-5.el5_6.1.x86_64 already installed and latest version
Package xorg-x11-fonts-truetype-7.1-2.1.el5.noarch already installed and latest version
Package bitmap-fonts-0.3-5.1.1.noarch already installed and latest version
Package xorg-x11-drivers-7.1-4.2.el5.x86_64 already installed and latest version
Package 1:xorg-x11-twm-1.0.1-3.1.x86_64 already installed and latest version
Package xorg-x11-apps-7.1-4.0.1.el5.x86_64 already installed and latest version
Package openssh-askpass-4.3p2-82.el5.x86_64 already installed and latest version
Package liberation-fonts-1.0-1.el5.noarch already installed and latest version
Package system-config-display-1.0.48-4.el5.noarch already installed and latest version
Package freeglut-2.4.0-7.1.el5.x86_64 already installed and latest version
Package freeglut-2.4.0-7.1.el5.i386 already installed and latest version
Package matching 1:gdm-2.16.0-59.el5.centos.1.x86_64 already installed. Checking for update.
Package policycoreutils-gui-1.33.12-14.13.el5.x86_64 already installed and latest version
Package synaptics-0.14.4-8.fc6.x86_64 already installed and latest version
Package krb5-auth-dialog-0.7-1.x86_64 already installed and latest version
Package system-config-soundcard-2.0.6-1.el5.noarch already installed and latest version
Package xterm-215-8.el5_4.1.x86_64 already installed and latest version
Package dejavu-lgc-fonts-2.10-1.noarch already installed and latest version
Package linuxwacom-0.7.8.3-11.2.el5_8.x86_64 already installed and latest version
Package system-config-services-0.9.4-5.el5.noarch already installed and latest version
Package vnc-server-4.1.2-14.el5_6.6.x86_64 already installed and latest version
Package glx-utils-6.5.1-7.11.el5_9.x86_64 already installed and latest version
Package wdaemon-0.14-8.x86_64 already installed and latest version
Package authconfig-gtk-5.3.21-7.el5.x86_64 already installed and latest version
Package system-config-printer-0.7.32.10-3.el5.x86_64 already installed and latest version
Package system-config-network-1.3.99.23-1.el5.noarch already installed and latest version
Package bitstream-vera-fonts-1.10-7.noarch already installed and latest version
Package system-config-users-1.2.51-7.el5.noarch already installed and latest version
Warning: Group Desktop does not exist.
Resolving Dependencies
--> Running transaction check
---> Package desktop-backgrounds-basic.noarch 0:2.0-41.el5.centos set to be updated
---> Package firstboot.x86_64 0:1.4.27.9-1.el5.centos set to be updated
---> Package launchmail.noarch 0:4.0.0-2.el5 set to be updated
---> Package pirut.noarch 0:1.3.28-20.el5.centos set to be updated
---> Package rhgb.x86_64 0:0.16.4-8.el5.centos.3 set to be updated
---> Package system-config-date.noarch 0:1.8.12-5.el5.centos set to be updated
--> Finished Dependency Resolution

Dependencies Resolved

================================================================================
 Package                    Arch    Version                  Repository    Size
================================================================================
Installing:
 launchmail                 noarch  4.0.0-2.el5              CentOS5Base  4.2 k
Updating:
 desktop-backgrounds-basic  noarch  2.0-41.el5.centos        CentOS5Base  6.4 M
 firstboot                  x86_64  1.4.27.9-1.el5.centos    CentOS5Base  377 k
 pirut                      noarch  1.3.28-20.el5.centos     CentOS5Base  352 k
 rhgb                       x86_64  0.16.4-8.el5.centos.3    CentOS5Base  161 k
 system-config-date         noarch  1.8.12-5.el5.centos      CentOS5Base  1.5 M

Transaction Summary
================================================================================
Install       1 Package(s)
Upgrade       5 Package(s)

Total download size: 8.7 M
Is this ok [y/N]: y

Downloading Packages:
(1/6): launchmail-4.0.0-2.el5.noarch.rpm                 | 4.2 kB     00:00
(2/6): rhgb-0.16.4-8.el5.centos.3.x86_64.rpm             | 161 kB     00:00
(3/6): pirut-1.3.28-20.el5.centos.noarch.rpm             | 352 kB     00:01
(4/6): firstboot-1.4.27.9-1.el5.centos.x86_64.rpm        | 377 kB     00:02
(5/6): system-config-date-1.8.12-5.el5.centos.noarch.rpm | 1.5 MB     00:03
(6/6): desktop-backgrounds-basic-2.0-41.el5.centos.noarc | 6.4 MB     00:06
--------------------------------------------------------------------------------
Total                                           585 kB/s | 8.7 MB     00:15
Running rpm_check_debug
Running Transaction Test
Finished Transaction Test


Transaction Check Error:
  file /usr/share/locale/af/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/am/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/ar/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/as/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/be/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/bg/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/bn/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/bn_IN/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/ca/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/cs/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/cy/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/da/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/de/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/el/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/en_GB/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/es/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/et/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/fa/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/fi/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/fr/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/gu/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/he/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/hi/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/hr/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/hy/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/id/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/ilo/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/is/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/it/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/ja/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/kn/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/ko/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/lt/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/lv/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/mk/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/ml/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/mr/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/ms/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/nb/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/nl/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/no/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/nso/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/or/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/pa/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/pl/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/pt/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/pt_BR/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/ro/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/ru/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/si/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/sk/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/sl/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/sr/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/sr@Latn/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/sv/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/ta/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/te/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/th/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/tr/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/uk/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/ur/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/vi/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/zh_CN/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/zh_TW/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/locale/zu/LC_MESSAGES/firstboot.mo from install of firstboot-1.4.27.9-1.el5.centos.x86_64 conflicts with file from package firstboot-tui-1.4.27.9-1.el5.x86_64
  file /usr/share/backgrounds/images/default-5_4.jpg from install of desktop-backgrounds-basic-2.0-41.el5.centos.noarch conflicts with file from package redhat-logos-4.9.16-1.noarch
  file /usr/share/backgrounds/images/default-dual-wide.jpg from install of desktop-backgrounds-basic-2.0-41.el5.centos.noarch conflicts with file from package redhat-logos-4.9.16-1.noarch
  file /usr/share/backgrounds/images/default-dual.jpg from install of desktop-backgrounds-basic-2.0-41.el5.centos.noarch conflicts with file from package redhat-logos-4.9.16-1.noarch
  file /usr/share/backgrounds/images/default-wide.jpg from install of desktop-backgrounds-basic-2.0-41.el5.centos.noarch conflicts with file from package redhat-logos-4.9.16-1.noarch
  file /usr/share/backgrounds/images/default.jpg from install of desktop-backgrounds-basic-2.0-41.el5.centos.noarch conflicts with file from package redhat-logos-4.9.16-1.noarch

Error Summary
-------------
*/

##### Remove the X Window System group
```
sudo yum groupremove "X Window System" Desktop
```
