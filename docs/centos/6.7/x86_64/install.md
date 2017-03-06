# CentOS 6.7 (x86_x64)

This document describes installing CentOS 6.7 on a Dell desktop PC with 8GB RAM and a 75GB hard drive. Preparation of the installation media was done on a Windows 7 PC.

## References
* http://isoredirect.centos.org/centos/6.7/isos/x86_64/
* http://www.unixmen.com/install-centos-6-5-remotely-using-telnet/

## Requirements
* 1 USB drive (>=1GB)
* CentOS 6.7 netinstall ISO
* 1 PC with an internet connection

## Specifications
*These are the specs of the target machine used to write the initial draft of this document*
* Dell Optiplex 755
* 8 GB RAM
 * DIMM_1 1,024.0MB
 * DIMM_2 1,024.0MB
 * DIMM_3 1,024.0MB
 * DIMM_4 1,024.0MB
* Intel(R) Core(TM)2 Duo CPU E4500 @ 2.20GHz
* CPU Clock Speed 2.2Ghz
* CPU L2 Cache Size 2048
* Drive Size 74.5 GB (80 GB)

##### Download CentOS-6.7-x86_64-netinstall.iso  (241.172480 MB)
* http://isoredirect.centos.org/centos/6.7/isos/x86_64/

##### Format the USB device
* Capacity: 7.21 GB
* File system: FAT32
* Allocation unit size: 64 kilbytes (largest allocation size)
* Format options: Quick Format
* Volume label: CentOS67

##### Download and install Live USB Creator
 * https://fedorahosted.org/liveusb-creator/

##### Run Live USB Creator as Administrator
* Start > Programs > right-mouse click Live USB Creator > select Run as Administrator

##### Create bootable USB using the CD image
 * Use existing Live CD: CentOS-6.7-x86_64-netinstall.iso
 * Target Device: CentOS67

##### Boot the target machine to the USB device
* F12

##### Welcome to CentOS 6.7!
* Install or upgrade an existing system

##### Choose a Language
* English

##### Keyboard Type
* us

##### Installation Method
* URL

##### Configure TCP/IP
* Enable IPv4 support
  * Dynamic IP configuration (DHCP)
* Enable IPv6 support
  * Automatic

##### URL Setup
* Find a local mirror URL
* https://www.centos.org/download/mirrors/
* Example (http://hostname.domain/CentOS/6.7/os/x86_64)

##### CentOS
* Next

##### What type of devices will your installation involve?
* Basic Storage Devices

##### Please name this computer
* Hostname: something

##### Please selct the nearest city in your time zone
* America/New York
* System clock uses UTC: No 

##### Enter a password for the root user
* Password
* Password (confirm)
 
##### Which type of installation would you like?
* Use All Space
* Review and modify partitioning layout

##### Install Target Devices
* ATA WDC WD800JD-75MS 
  * Boot Loader: YES

##### Please Select A Device
```
* LVM Volume Groups
  * vg_hostname 75788
    * lv_root   51200   /           ext4                    format
    * lv_home   16960   /home       ext4                    format
    * lv_swap   7628                swap                    format
* Hard Drives
    * sdb
        * sdb1  500     /boot       ext4    format
        * sdb2  75792   vg_hostname physical volume (LVM)   format
```
##### Writing storage configuration to disk
* Write changes to disk

##### Boot loader operating system list
* CentOS 6 /dev/mapper/vg_hostname-lv_root
* Install boot leader on /dev/sdb

##### The default installation of CentOS is a minimal install
* Minimal

##### Please select any additional repositories that you want to use for software installation
* CentOS

##### Installing packages...

##### Congratulations, your CentOS installation is complete.
* Reboot

##### Login with the root account and check the IP address
```
ifconfig
```

##### Connect via SSH
* [ssh](/docs/ssh.md)

##### Create a new user account
* [useradd](/docs/useradd.md)

##### Disconnect
```
exit
```

##### Re-connect via SSH
* [ssh](/docs/ssh.md)

##### Configure bash
* [bash](/docs/bash.md)

##### Check the Linux distro version
* [cat /proc/version](/docs/version.md)

##### Check the date and timezone
* [date](/docs/date.md)

##### Check the network settings
* [network](/docs/network.md)

##### Install system updates
* [yum](/docs/yum.md)

