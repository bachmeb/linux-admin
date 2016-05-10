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

##### Configure display number 3 for your account
```bash
VNCSERVERS="3:[YOUR ACCOUNT NAME]"
```

##### Set the VNC password for your account
```
vncpasswd
```

##### Set the VNC password for another account
```
su - user
vncpasswd
```

* *The stored password is not encrypted; anyone who has access to the password file can find the plain-text password.* (https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Deployment_Guide/chap-TigerVNC.html)

##### Start the VNC server
```
sudo /sbin/service vncserver start
```

##### Read the iptables sysconfig file
```
sudo cat /etc/sysconfig/iptables
```
```bash
# Firewall configuration written by system-config-firewall
# Manual customization of this file is not recommended.
*filter
:INPUT ACCEPT [0:0]
:FORWARD ACCEPT [0:0]
:OUTPUT ACCEPT [0:0]
-A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
-A INPUT -p icmp -j ACCEPT
-A INPUT -i lo -j ACCEPT
-A INPUT -m state --state NEW -m tcp -p tcp --dport 22 -j ACCEPT
-A INPUT -j REJECT --reject-with icmp-host-prohibited
-A FORWARD -j REJECT --reject-with icmp-host-prohibited
COMMIT
```

##### Add a rule to allow tcp traffic on port 22
```
sudo /sbin/iptables -A INPUT -m state --state NEW -m tcp -p tcp --dport 22 -j ACCEPT
```

##### Confirm that the rule was added
```
sudo iptables -vnL
```

##### Save the rule
```
sudo /etc/init.d/iptables save
```

##### Confirm that the rule was added to the iptables file in sysconfig
```
sudo cat /etc/sysconfig/iptables
```

##### Add a rule to allow TCP traffic on additional ports
```
sudo /sbin/iptables -A INPUT -m state --state NEW -m tcp -p tcp -m multiport --dports 5901:5903,6001:6003 -j ACCEPT
```

##### Install a vnc viewer on the client machine
* Windows 7
  * https://github.com/TigerVNC/tigervnc/releases/tag/v1.6.0

