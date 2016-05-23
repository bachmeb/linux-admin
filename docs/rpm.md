# rpm

## References
* https://www.centos.org/forums/viewtopic.php?t=53593

##### Check the CentOS release
```
rpm -q centos-release
```
```c
/*
centos-release-6-7.el6.centos.12.3.x86_64
*/
```


##### Add a repo package
```
sudo rpm -Uvh mysql57-community-release-el6-8.noarch.rpm
```

##### Find a repo package
```
sudo rpm -qa | grep -i mys
```

##### Remove a repo package
```
sudo rpm -e  mysql57-community-release-el6-8.noarch
```

##### List the files in a RPM file
```
rpm -qpl oracle-instantclient12.1-devel-12.1.0.2.0-1.x86_64.rpm 
```
```c
/*
/usr/include/oracle/12.1/client64/ldap.h
/usr/include/oracle/12.1/client64/nzerror.h
/usr/include/oracle/12.1/client64/nzt.h
/usr/include/oracle/12.1/client64/occi.h
/usr/include/oracle/12.1/client64/occiAQ.h
/usr/include/oracle/12.1/client64/occiCommon.h
/usr/include/oracle/12.1/client64/occiControl.h
/usr/include/oracle/12.1/client64/occiData.h
/usr/include/oracle/12.1/client64/occiObjects.h
/usr/include/oracle/12.1/client64/oci.h
/usr/include/oracle/12.1/client64/oci1.h
/usr/include/oracle/12.1/client64/oci8dp.h
/usr/include/oracle/12.1/client64/ociap.h
/usr/include/oracle/12.1/client64/ociapr.h
/usr/include/oracle/12.1/client64/ocidef.h
/usr/include/oracle/12.1/client64/ocidem.h
/usr/include/oracle/12.1/client64/ocidfn.h
/usr/include/oracle/12.1/client64/ociextp.h
/usr/include/oracle/12.1/client64/ocikpr.h
/usr/include/oracle/12.1/client64/ocixmldb.h
/usr/include/oracle/12.1/client64/ocixstream.h
/usr/include/oracle/12.1/client64/odci.h
/usr/include/oracle/12.1/client64/oratypes.h
/usr/include/oracle/12.1/client64/ori.h
/usr/include/oracle/12.1/client64/orid.h
/usr/include/oracle/12.1/client64/orl.h
/usr/include/oracle/12.1/client64/oro.h
/usr/include/oracle/12.1/client64/ort.h
/usr/include/oracle/12.1/client64/xa.h
/usr/lib/oracle/12.1/client64/lib/libclntsh.so
/usr/lib/oracle/12.1/client64/lib/libclntshcore.so
/usr/lib/oracle/12.1/client64/lib/libocci.so
/usr/lib/oracle/12.1/client64/lib/ottclasses.zip
/usr/share/oracle/12.1/client64/admin/oraaccess.xsd
/usr/share/oracle/12.1/client64/demo/cdemo81.c
/usr/share/oracle/12.1/client64/demo/demo.mk
/usr/share/oracle/12.1/client64/demo/occidemo.sql
/usr/share/oracle/12.1/client64/demo/occidemod.sql
/usr/share/oracle/12.1/client64/demo/occidml.cpp
/usr/share/oracle/12.1/client64/demo/occiobj.cpp
/usr/share/oracle/12.1/client64/demo/occiobj.typ
/usr/share/oracle/12.1/client64/demo/oraaccess.xml
/usr/share/oracle/12.1/client64/demo/ott
/usr/share/oracle/12.1/client64/demo/setuporamysql.sh
*/
```
