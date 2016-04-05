
##### Check the hostname 
```
hostname
```
##### Check the fully qualified domain name
```
hostname -f
```

##### Check the DNS domain name
```
dnsdomainname
```

##### Get the IP address of the internal name server
```
cat /etc/resolv.conf
```

##### Check the routing table
```
route
```

##### Check the internal IP address
```
/sbin/ifconfig
```

##### Check the external IP address
```
wget http://ipinfo.io/ip -qO -
```

##### Run a speed test (just for fun)
```
mkdir ~/speedtest
cd ~/speedtest
wget https://raw.github.com/sivel/speedtest-cli/master/speedtest_cli.py
chmod +x speedtest_cli.py
./speedtest_cli.py
```
##### Read the hosts file
```
sudo cat /etc/hosts
```
```c
/*
# Do not remove the following line, or various programs
# that require network functionality will fail.
127.0.0.1               localhost.localdomain localhost
::1             localhost6.localdomain6 localhost6
*/
```

##### Edit the sysconfig network file
```
sudo nano /etc/sysconfig/network
```

##### Set the HOSTNAME to be any name you would like for the virtual server
```
HOSTNAME=[somehost].localdomain
```
Edit the hosts file

sudo nano /etc/hosts
127.0.0.1  [somehost] [somehost].localdomain localhost localhost.localdomain
Reboot the system to pick up the new hostname and time zone information in all services and applications

sudo reboot
