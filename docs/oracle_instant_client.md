# oracle instant client

## References
* http://www.oracle.com/technetwork/articles/dsl/technote-php-instant-12c-2088811.html

##### Download
* http://www.oracle.com/technetwork/topics/linuxx86-64soft-092277.html
```
oracle-instantclient12.1-basic-12.1.0.2.0-1.x86_64.rpm
oracle-instantclient12.1-devel-12.1.0.2.0-1.x86_64.rpm 
```

##### Install basic and devel
```
rpm -Uvh oracle-instantclient12.1-basic-12.1.0.1.0-1.x86_64.rpm
rpm -Uvh oracle-instantclient12.1-devel-12.1.0.1.0-1.x86_64.rpm
```

##### Install oci8
```
pecl install oci8
```

##### Enable the PHP OCI8 extension 
```
sudo nano /etc/php.ini
```
```
extension=oci8.so
```
Also confirm extension_dir points to the directory the oci8.so file was copied into during the build.

##### Configure environment variables
Ensure Instant Client libraries are found by adding the Instant Client directory to /etc/ld.so.conf
```
```
Or manually set LD_LIBRARY_PATH to /usr/lib/oracle/12.1/client64/lib. You might also want to set standard Oracle environment variables such as TNS_ADMIN and NLS_LANG. If NLS_LANG is not set, a default local environment will be assumed.

It is important to set all Oracle environment variables before starting Apache so that the OCI8 process environment is correctly initialized. Setting environment variables in PHP scripts can lead to obvious or non-obvious problems. On Oracle Linux, export environment variables in /etc/sysconfig/httpd, for example:

##### Restart Apache
```c
# service httpd restart
```
