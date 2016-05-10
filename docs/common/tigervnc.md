# tigervnc

## References
* http://tigervnc.org/
* https://github.com/TigerVNC/tigervnc/releases
* https://github.com/TigerVNC/tigervnc/releases/tag/v1.6.0
* https://bintray.com/tigervnc/stable/tigervnc/1.6.0
* https://wiki.centos.org/HowTos/VNC-Server
* https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/System_Administrators_Guide/ch-TigerVNC.html
* https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Deployment_Guide/chap-TigerVNC.html


##### Search repo for vnc
```
yum search vnc
```

##### Install
```
sudo yum install tigervnc-server
```

##### Ask where is vncserver
```
whereis vncserver
```

##### Check the status of the service
```
sudo /sbin/service vncserver status
```
```c
/*
Xvnc is stopped
*/
```

##### Read the vncservers sysconfig file
```
cat /etc/sysconfig/vncservers
```
```bash
# The VNCSERVERS variable is a list of display:user pairs.
#
# Uncomment the lines below to start a VNC server on display :2
# as my 'myusername' (adjust this to your own).  You will also
# need to set a VNC password; run 'man vncpasswd' to see how
# to do that.
#
# DO NOT RUN THIS SERVICE if your local area network is
# untrusted!  For a secure way of using VNC, see this URL:
# https://access.redhat.com/knowledge/solutions/7027

# Use "-nolisten tcp" to prevent X connections to your VNC server via TCP.

# Use "-localhost" to prevent remote VNC clients connecting except when
# doing so through a secure tunnel.  See the "-via" option in the
# `man vncviewer' manual page.

# VNCSERVERS="2:myusername"
# VNCSERVERARGS[2]="-geometry 800x600 -nolisten tcp -localhost"
```

##### Edit the configuration file
```
sudo vi /etc/sysconfig/vncservers
```

##### Configure display number 3 for user joe
```bash
VNCSERVERS="3:joe"
```

