# ubuntu macbook air

## References
* http://www.ubuntu.com/download/desktop/create-a-usb-stick-on-mac-osx
* http://ubuntuforums.org/showthread.php?t=2231441

##### Download Ubuntu Desktop

##### Open the Terminal (in /Applications/Utilities/ or query Terminal in Spotlight).

##### Convert the .iso file to .img using the convert option of hdiutil e.g.,
```
hdiutil convert -format UDRW -o ~/path/to/target.img ~/path/to/ubuntu.iso
```
*Note: OS X tends to put the .dmg ending on the output file automatically.*

##### Get the current list of disks
```
diskutil list
```

##### Insert your flash media.

##### Get the current list of disks again and determine the device node assigned to your flash media (e.g. /dev/disk2).

##### Unmount the USB device
```
diskutil unmountDisk /dev/diskN
```
(replace N with the disk number from the last command; in the previous example, N would be 2).

##### Copy the contents of the Ubuntu image to the USB device. This will erase any contents of the USB device. 
```
sudo dd if=/path/to/downloaded.img of=/dev/rdiskN bs=1m
```
(replace /path/to/downloaded.img with the path where the image file is located; for example, ./ubuntu.img or ./ubuntu.dmg).
Using /dev/rdisk instead of /dev/disk may be faster

##### Eject the disk
```
diskutil eject /dev/diskN
```

##### Restart your Mac and press alt/option key while the Mac is restarting to choose the USB stick.

##### Look for the wifi adapter
```
lspci -nnk | grep -iA2 net
```
