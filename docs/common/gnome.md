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
*/
