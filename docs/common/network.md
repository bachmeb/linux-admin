
##### Check the hostname 
```
hostname
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
