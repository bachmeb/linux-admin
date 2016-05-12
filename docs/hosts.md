# hosts

## References
* https://support.rackspace.com/how-to/modify-your-hosts-file/

##### Open the Windows hosts file
* Start > All Programs > Accessories
* Right-click Notepad and select Run as administrator
* Click Continue on the Windows needs your permission UAC window.
* When Notepad opens
  * Click File > Open
  * In the File name field, type C:\Windows\System32\Drivers\etc\hosts
  * Click Open
  * The file looks like this:

```bat
# Copyright (c) 1993-2009 Microsoft Corp.
#
# This is a sample HOSTS file used by Microsoft TCP/IP for Windows.
#
# This file contains the mappings of IP addresses to host names. Each
# entry should be kept on an individual line. The IP address should
# be placed in the first column followed by the corresponding host name.
# The IP address and the host name should be separated by at least one
# space.
#
# Additionally, comments (such as these) may be inserted on individual
# lines or following the machine name denoted by a '#' symbol.
#
# For example:
#
#      102.54.94.97     rhino.acme.com          # source server
#       38.25.63.10     x.acme.com              # x client host

# localhost name resolution is handled within DNS itself.
#	127.0.0.1       localhost
#	::1             localhost
```

##### Edit the hosts file
*Add the correct IP address and hostname for the destination system.*
```
555.555.555.555   hostname
```

##### Save the changes
* File > Save

##### Open a windows command prompt and ping the destination hostname
```
ping hostname
```
