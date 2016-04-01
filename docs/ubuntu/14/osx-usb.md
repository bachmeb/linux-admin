# ubuntu 14 usb

## References
* http://www.ubuntu.com/download/desktop/create-a-usb-stick-on-mac-osx
* http://ubuntuforums.org/showthread.php?t=2231441

##### Download Ubuntu Desktop
* http://ubuntu.com

##### Open the OSX Terminal
* /Applications/Utilities/Terminal

##### Convert the .iso file to .img using the convert option of hdiutil e.g.,
```
hdiutil convert -format UDRW -o ~/path/to/target.img ~/path/to/ubuntu.iso
```
*Note: OS X tends to put the .dmg ending on the output file automatically.*

##### Get the current list of disks
```
diskutil list
```

##### Insert the USB stick

##### Get the current list of disks again 
*figure out which device node has been assigned to the USB storage device (e.g. /dev/disk2)*
```
diskutil list
```

##### Unmount the USB device (replace N with the disk number from the last command)
```
diskutil unmountDisk /dev/diskN
```

##### Copy the contents of the Ubuntu image to the USB device. This will erase any contents of the USB device.
*Using /dev/rdisk instead of /dev/disk may be faster*
```
sudo dd if=/path/to/downloaded.img.dmg of=/dev/rdiskN bs=1m
```

##### Eject the disk
```
diskutil eject /dev/diskN
```

##### Restart the machine
* Apple > Restart

##### Choose the USB device as the startup device
* Press and hold Alt-Option before the Apple icon appears during reboot

##### Look for the wifi adapter
```
lspci -nnk | grep -iA2 net
```
