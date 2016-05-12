# xming

This document explains how to run graphical applications on a remote Linux machine and forward the windows to a Windows PC running xming and putty.

## References
* http://www.straightrunning.com/XmingNotes/
* http://www.geo.mtu.edu/geoschem/docs/putty_install.html
* http://superuser.com/questions/310197/how-do-i-fix-a-cannot-open-display-error-when-opening-an-x-program-after-sshi

##### Download and install Putty
* http://www.putty.org/

##### Download and install xming
* https://sourceforge.net/projects/xming/files/

##### Launch and configure Putty
* Session
  * Hostname: [remote pc]
  * Port: 22
  * Connection type: SSH
  * Saved Sessions: [give the session a name]
* Window
  * Columns: 80
  * Rows: 40
* Connection
  * Auto-login username: [your username]
  * Terminal-type string: xterm
  * SSH
    * X11
      * Enable X11 forwarding: YES
      * X display location: localhost:0

##### Connect to the remote machine via SSH using putty
* Click Open

##### Make sure X11Forwarding is set to yes on the remote machine
```
sudo cat /etc/ssh/sshd_config
```
```
X11Forwarding yes
```

##### Launch firefox on the remote machine
```
firefox
```

The Firefox window should be displayed on your local machine. 
