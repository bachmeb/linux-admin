# 

## References
* https://success.mocana.com/hc/en-us/articles/203661378-Error-When-Trying-to-start-Apache-services-httpd-

##### Edit the selinux file
```
sudo nano /etc/sysconfig/selinux
```

##### Disable SELINUX
```
SELINUX=disabled
```

* *Reboot after setting SELINUX=disabled*
