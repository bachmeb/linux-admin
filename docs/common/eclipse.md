# eclipse

## References
* https://eclipse.org/downloads/
* https://access.redhat.com/documentation/en-US/Red_Hat_Developer_Toolset/1/html/User_Guide/chap-Eclipse.html

##### Install all of the eclipse packages in yum
```
sudo install eclipse-/*
```
```
/*
Loaded plugins: product-id, security, subscription-manager
Setting up Install Process
Resolving Dependencies
--> Running transaction check
---> Package eclipse-ecj.x86_64 1:3.2.1-19.el5 set to be updated
---> Package eclipse-jdt.x86_64 1:3.2.1-19.el5 set to be updated
--> Processing Dependency: junit >= 3.8.1-3jpp for package: eclipse-jdt
---> Package eclipse-jdt-sdk.x86_64 1:3.2.1-19.el5 set to be updated
--> Processing Dependency: java-javadoc for package: eclipse-jdt-sdk
---> Package eclipse-pde.x86_64 1:3.2.1-19.el5 set to be updated
---> Package eclipse-pde-runtime.x86_64 1:3.2.1-19.el5 set to be updated
---> Package eclipse-pde-sdk.x86_64 1:3.2.1-19.el5 set to be updated
---> Package eclipse-platform.x86_64 1:3.2.1-19.el5 set to be updated
--> Processing Dependency: tomcat5-servlet-2.4-api >= 5.5.17 for package: eclipse-platform
--> Processing Dependency: tomcat5-jasper >= 5.5.17 for package: eclipse-platform
--> Processing Dependency: tomcat5 >= 5.5.17 for package: eclipse-platform
--> Processing Dependency: mx4j >= 2.1 for package: eclipse-platform
--> Processing Dependency: regexp for package: eclipse-platform
--> Processing Dependency: lucene for package: eclipse-platform
--> Processing Dependency: jakarta-commons-pool for package: eclipse-platform
--> Processing Dependency: jakarta-commons-modeler for package: eclipse-platform
--> Processing Dependency: jakarta-commons-logging for package: eclipse-platform
--> Processing Dependency: jakarta-commons-launcher for package: eclipse-platform
--> Processing Dependency: jakarta-commons-fileupload for package: eclipse-platform
--> Processing Dependency: jakarta-commons-el for package: eclipse-platform
--> Processing Dependency: jakarta-commons-digester for package: eclipse-platform
--> Processing Dependency: jakarta-commons-dbcp for package: eclipse-platform
--> Processing Dependency: jakarta-commons-collections for package: eclipse-platform
--> Processing Dependency: jakarta-commons-beanutils for package: eclipse-platform
--> Processing Dependency: ant-trax for package: eclipse-platform
--> Processing Dependency: ant-swing for package: eclipse-platform
--> Processing Dependency: ant-nodeps for package: eclipse-platform
--> Processing Dependency: ant-junit for package: eclipse-platform
--> Processing Dependency: ant-jsch for package: eclipse-platform
--> Processing Dependency: ant-jdepend for package: eclipse-platform
--> Processing Dependency: ant-javamail for package: eclipse-platform
--> Processing Dependency: ant-commons-logging for package: eclipse-platform
--> Processing Dependency: ant-apache-resolver for package: eclipse-platform
--> Processing Dependency: ant-apache-regexp for package: eclipse-platform
--> Processing Dependency: ant-apache-oro for package: eclipse-platform
--> Processing Dependency: ant-apache-log4j for package: eclipse-platform
--> Processing Dependency: ant-apache-bcel for package: eclipse-platform
--> Processing Dependency: ant-antlr for package: eclipse-platform
--> Processing Dependency: /usr/lib64/eclipse/plugins/org.eclipse.swt.gtk.linux.x86_64_3.2.1.v3235.jar for package: eclipse-platform
---> Package eclipse-platform-sdk.x86_64 1:3.2.1-19.el5 set to be updated
---> Package eclipse-rcp.x86_64 1:3.2.1-19.el5 set to be updated
---> Package eclipse-rcp-sdk.x86_64 1:3.2.1-19.el5 set to be updated
---> Package eclipse-sdk.x86_64 1:3.2.1-19.el5 set to be updated
--> Running transaction check
---> Package ant-antlr.x86_64 0:1.6.5-2jpp.2 set to be updated
--> Processing Dependency: ant = 1.6.5-2jpp.2 for package: ant-antlr
---> Package ant-apache-bcel.x86_64 0:1.6.5-2jpp.2 set to be updated
--> Processing Dependency: bcel for package: ant-apache-bcel
---> Package ant-apache-log4j.x86_64 0:1.6.5-2jpp.2 set to be updated
--> Processing Dependency: log4j for package: ant-apache-log4j
---> Package ant-apache-oro.x86_64 0:1.6.5-2jpp.2 set to be updated
--> Processing Dependency: oro for package: ant-apache-oro
---> Package ant-apache-regexp.x86_64 0:1.6.5-2jpp.2 set to be updated
---> Package ant-apache-resolver.x86_64 0:1.6.5-2jpp.2 set to be updated
--> Processing Dependency: xml-commons-resolver for package: ant-apache-resolver
---> Package ant-commons-logging.x86_64 0:1.6.5-2jpp.2 set to be updated
---> Package ant-javamail.x86_64 0:1.6.5-2jpp.2 set to be updated
--> Processing Dependency: javamail >= 1.2-5jpp for package: ant-javamail
--> Processing Dependency: jaf >= 1.0.1-5jpp for package: ant-javamail
---> Package ant-jdepend.x86_64 0:1.6.5-2jpp.2 set to be updated
--> Processing Dependency: jdepend for package: ant-jdepend
---> Package ant-jsch.x86_64 0:1.6.5-2jpp.2 set to be updated
--> Processing Dependency: jsch for package: ant-jsch
---> Package ant-junit.x86_64 0:1.6.5-2jpp.2 set to be updated
---> Package ant-nodeps.x86_64 0:1.6.5-2jpp.2 set to be updated
---> Package ant-swing.x86_64 0:1.6.5-2jpp.2 set to be updated
---> Package ant-trax.x86_64 0:1.6.5-2jpp.2 set to be updated
--> Processing Dependency: jaxp_transform_impl for package: ant-trax
---> Package jakarta-commons-beanutils.x86_64 0:1.7.0-5jpp.1 set to be updated
---> Package jakarta-commons-collections.x86_64 0:3.2-2jpp.4 set to be updated
---> Package jakarta-commons-dbcp.x86_64 0:1.2.1-7jpp.1 set to be updated
---> Package jakarta-commons-digester.x86_64 0:1.7-5jpp.1 set to be updated
---> Package jakarta-commons-el.x86_64 0:1.0-7jpp.1 set to be updated
---> Package jakarta-commons-fileupload.x86_64 1:1.0-6jpp.1 set to be updated
---> Package jakarta-commons-launcher.x86_64 0:0.9-6jpp.1 set to be updated
---> Package jakarta-commons-logging.x86_64 0:1.0.4-6jpp.1 set to be updated
---> Package jakarta-commons-modeler.x86_64 0:1.1-8jpp.3.el5 set to be updated
--> Processing Dependency: xml-commons-apis for package: jakarta-commons-modeler
---> Package jakarta-commons-pool.x86_64 0:1.3-5jpp.1 set to be updated
---> Package java-1.6.0-openjdk-javadoc.x86_64 1:1.6.0.38-1.13.10.0.el5_11 set to be updated
---> Package junit.x86_64 0:3.8.2-3jpp.1 set to be updated
---> Package libswt3-gtk2.x86_64 1:3.2.1-19.el5 set to be updated
---> Package lucene.x86_64 0:1.4.3-1jpp.16 set to be updated
---> Package mx4j.x86_64 1:3.0.1-6jpp.4 set to be updated
--> Processing Dependency: axis >= 1.1 for package: mx4j
--> Processing Dependency: xml-commons for package: mx4j
---> Package regexp.x86_64 0:1.4-2jpp.2 set to be updated
---> Package tomcat5.x86_64 0:5.5.23-0jpp.40.el5_9 set to be updated
--> Processing Dependency: tomcat5-server-lib = 5.5.23-0jpp.40.el5_9 for package: tomcat5
--> Processing Dependency: tomcat5-server-lib = 5.5.23-0jpp.40.el5_9 for package: tomcat5
--> Processing Dependency: tomcat5-common-lib = 5.5.23-0jpp.40.el5_9 for package: tomcat5
--> Processing Dependency: tomcat5-common-lib = 5.5.23-0jpp.40.el5_9 for package: tomcat5
--> Processing Dependency: xerces-j2 >= 2.7.1 for package: tomcat5
--> Processing Dependency: jakarta-commons-daemon >= 1.0.1 for package: tomcat5
---> Package tomcat5-jasper.x86_64 0:5.5.23-0jpp.40.el5_9 set to be updated
---> Package tomcat5-servlet-2.4-api.x86_64 0:5.5.23-0jpp.40.el5_9 set to be updated
--> Running transaction check
---> Package ant.x86_64 0:1.6.5-2jpp.2 set to be updated
---> Package axis.x86_64 0:1.2.1-2jpp.8.el5_10 set to be updated
--> Processing Dependency: wsdl4j for package: axis
--> Processing Dependency: jakarta-commons-httpclient for package: axis
--> Processing Dependency: jakarta-commons-discovery for package: axis
---> Package bcel.x86_64 0:5.1-8jpp.1 set to be updated
---> Package classpathx-jaf.x86_64 0:1.0-9jpp.1 set to be updated
---> Package classpathx-mail.x86_64 0:1.1.1-4jpp.2 set to be updated
---> Package jakarta-commons-daemon.x86_64 1:1.0.1-6jpp.1 set to be updated
---> Package jakarta-oro.x86_64 0:2.0.8-3jpp.1 set to be updated
---> Package jdepend.x86_64 0:2.6-6jpp.2 set to be updated
---> Package jsch.x86_64 0:0.1.28-1jpp.5 set to be updated
--> Processing Dependency: jzlib >= 1.0.5 for package: jsch
---> Package log4j.x86_64 0:1.2.13-3jpp.2 set to be updated
---> Package tomcat5-common-lib.x86_64 0:5.5.23-0jpp.40.el5_9 set to be updated
--> Processing Dependency: tomcat5-jsp-2.0-api = 5.5.23-0jpp.40.el5_9 for package: tomcat5-common-lib
--> Processing Dependency: tomcat5-jsp-2.0-api = 5.5.23-0jpp.40.el5_9 for package: tomcat5-common-lib
--> Processing Dependency: jta >= 1.0.1 for package: tomcat5-common-lib
--> Processing Dependency: jta >= 1.0.1 for package: tomcat5-common-lib
---> Package tomcat5-server-lib.x86_64 0:5.5.23-0jpp.40.el5_9 set to be updated
---> Package xalan-j2.x86_64 0:2.7.0-6jpp.2 set to be updated
---> Package xerces-j2.x86_64 0:2.7.1-7jpp.2.el5_4.2 set to be updated
---> Package xml-commons.x86_64 0:1.3.02-0.b2.7jpp.10 set to be updated
---> Package xml-commons-apis.x86_64 0:1.3.02-0.b2.7jpp.10 set to be updated
---> Package xml-commons-resolver.x86_64 0:1.1-1jpp.12 set to be updated
--> Running transaction check
---> Package geronimo-specs-compat.x86_64 0:1.0-0.M2.2jpp.12 set to be updated
--> Processing Dependency: geronimo-specs = 1.0-0.M2.2jpp.12 for package: geronimo-specs-compat
---> Package jakarta-commons-discovery.x86_64 1:0.3-4jpp.1 set to be updated
---> Package jakarta-commons-httpclient.x86_64 1:3.0-7jpp.4.el5_10 set to be updated
---> Package jzlib.x86_64 0:1.0.7-4jpp.1 set to be updated
---> Package tomcat5-jsp-2.0-api.x86_64 0:5.5.23-0jpp.40.el5_9 set to be updated
---> Package wsdl4j.x86_64 0:1.5.2-4jpp.1 set to be updated
--> Running transaction check
---> Package geronimo-specs.x86_64 0:1.0-0.M2.2jpp.12 set to be updated
--> Finished Dependency Resolution

Dependencies Resolved

================================================================================
 Package                   Arch   Version              Repository          Size
================================================================================
Installing:
 eclipse-ecj               x86_64 1:3.2.1-19.el5       rhel-5-server-rpms 9.0 M
 eclipse-jdt               x86_64 1:3.2.1-19.el5       rhel-5-server-rpms  28 M
 eclipse-jdt-sdk           x86_64 1:3.2.1-19.el5       rhel-5-server-rpms  12 M
 eclipse-pde               x86_64 1:3.2.1-19.el5       rhel-5-server-rpms  11 M
 eclipse-pde-runtime       x86_64 1:3.2.1-19.el5       rhel-5-server-rpms 266 k
 eclipse-pde-sdk           x86_64 1:3.2.1-19.el5       rhel-5-server-rpms 2.0 M
 eclipse-platform          x86_64 1:3.2.1-19.el5       rhel-5-server-rpms  36 M
 eclipse-platform-sdk      x86_64 1:3.2.1-19.el5       rhel-5-server-rpms  27 M
 eclipse-rcp               x86_64 1:3.2.1-19.el5       rhel-5-server-rpms  17 M
 eclipse-rcp-sdk           x86_64 1:3.2.1-19.el5       rhel-5-server-rpms 7.0 M
 eclipse-sdk               x86_64 1:3.2.1-19.el5       rhel-5-server-rpms  88 k
Installing for dependencies:
 ant                       x86_64 1.6.5-2jpp.2         rhel-5-server-rpms 2.3 M
 ant-antlr                 x86_64 1.6.5-2jpp.2         rhel-5-server-rpms  36 k
 ant-apache-bcel           x86_64 1.6.5-2jpp.2         rhel-5-server-rpms  38 k
 ant-apache-log4j          x86_64 1.6.5-2jpp.2         rhel-5-server-rpms  28 k
 ant-apache-oro            x86_64 1.6.5-2jpp.2         rhel-5-server-rpms 124 k
 ant-apache-regexp         x86_64 1.6.5-2jpp.2         rhel-5-server-rpms  29 k
 ant-apache-resolver       x86_64 1.6.5-2jpp.2         rhel-5-server-rpms  30 k
 ant-commons-logging       x86_64 1.6.5-2jpp.2         rhel-5-server-rpms  31 k
 ant-javamail              x86_64 1.6.5-2jpp.2         rhel-5-server-rpms  37 k
 ant-jdepend               x86_64 1.6.5-2jpp.2         rhel-5-server-rpms  46 k
 ant-jsch                  x86_64 1.6.5-2jpp.2         rhel-5-server-rpms  72 k
 ant-junit                 x86_64 1.6.5-2jpp.2         rhel-5-server-rpms 179 k
 ant-nodeps                x86_64 1.6.5-2jpp.2         rhel-5-server-rpms 903 k
 ant-swing                 x86_64 1.6.5-2jpp.2         rhel-5-server-rpms  28 k
 ant-trax                  x86_64 1.6.5-2jpp.2         rhel-5-server-rpms 177 k
 axis                      x86_64 1.2.1-2jpp.8.el5_10  rhel-5-server-rpms 3.6 M
 bcel                      x86_64 5.1-8jpp.1           rhel-5-server-rpms 1.1 M
 classpathx-jaf            x86_64 1.0-9jpp.1           rhel-5-server-rpms 111 k
 classpathx-mail           x86_64 1.1.1-4jpp.2         rhel-5-server-rpms 1.2 M
 geronimo-specs            x86_64 1.0-0.M2.2jpp.12     rhel-5-server-rpms 259 k
 geronimo-specs-compat     x86_64 1.0-0.M2.2jpp.12     rhel-5-server-rpms 5.5 k
 jakarta-commons-beanutils x86_64 1.7.0-5jpp.1         rhel-5-server-rpms 571 k
 jakarta-commons-collections
                           x86_64 3.2-2jpp.4           rhel-5-server-rpms 1.2 M
 jakarta-commons-daemon    x86_64 1:1.0.1-6jpp.1       rhel-5-server-rpms  46 k
 jakarta-commons-dbcp      x86_64 1.2.1-7jpp.1         rhel-5-server-rpms 279 k
 jakarta-commons-digester  x86_64 1.7-5jpp.1           rhel-5-server-rpms 350 k
 jakarta-commons-discovery x86_64 1:0.3-4jpp.1         rhel-5-server-rpms 151 k
 jakarta-commons-el        x86_64 1.0-7jpp.1           rhel-5-server-rpms 269 k
 jakarta-commons-fileupload
                           x86_64 1:1.0-6jpp.1         rhel-5-server-rpms  53 k
 jakarta-commons-httpclient
                           x86_64 1:3.0-7jpp.4.el5_10  rhel-5-server-rpms 606 k
 jakarta-commons-launcher  x86_64 0.9-6jpp.1           rhel-5-server-rpms  97 k
 jakarta-commons-logging   x86_64 1.0.4-6jpp.1         rhel-5-server-rpms 116 k
 jakarta-commons-modeler   x86_64 1.1-8jpp.3.el5       rhel-5-server-rpms 260 k
 jakarta-commons-pool      x86_64 1.3-5jpp.1           rhel-5-server-rpms 143 k
 jakarta-oro               x86_64 2.0.8-3jpp.1         rhel-5-server-rpms 195 k
 java-1.6.0-openjdk-javadoc
                           x86_64 1:1.6.0.38-1.13.10.0.el5_11
                                                       rhel-5-server-rpms  20 M
 jdepend                   x86_64 2.6-6jpp.2           rhel-5-server-rpms 259 k
 jsch                      x86_64 0.1.28-1jpp.5        rhel-5-server-rpms 348 k
 junit                     x86_64 3.8.2-3jpp.1         rhel-5-server-rpms 338 k
 jzlib                     x86_64 1.0.7-4jpp.1         rhel-5-server-rpms 141 k
 libswt3-gtk2              x86_64 1:3.2.1-19.el5       rhel-5-server-rpms 3.8 M
 log4j                     x86_64 1.2.13-3jpp.2        rhel-5-server-rpms 731 k
 lucene                    x86_64 1.4.3-1jpp.16        rhel-5-server-rpms 771 k
 mx4j                      x86_64 1:3.0.1-6jpp.4       rhel-5-server-rpms 2.7 M
 regexp                    x86_64 1.4-2jpp.2           rhel-5-server-rpms 102 k
 tomcat5                   x86_64 5.5.23-0jpp.40.el5_9 rhel-5-server-rpms 395 k
 tomcat5-common-lib        x86_64 5.5.23-0jpp.40.el5_9 rhel-5-server-rpms 227 k
 tomcat5-jasper            x86_64 5.5.23-0jpp.40.el5_9 rhel-5-server-rpms 1.1 M
 tomcat5-jsp-2.0-api       x86_64 5.5.23-0jpp.40.el5_9 rhel-5-server-rpms 106 k
 tomcat5-server-lib        x86_64 5.5.23-0jpp.40.el5_9 rhel-5-server-rpms 4.1 M
 tomcat5-servlet-2.4-api   x86_64 5.5.23-0jpp.40.el5_9 rhel-5-server-rpms 166 k
 wsdl4j                    x86_64 1.5.2-4jpp.1         rhel-5-server-rpms 430 k
 xalan-j2                  x86_64 2.7.0-6jpp.2         rhel-5-server-rpms 4.5 M
 xerces-j2                 x86_64 2.7.1-7jpp.2.el5_4.2 rhel-5-server-rpms 3.1 M
 xml-commons               x86_64 1.3.02-0.b2.7jpp.10  rhel-5-server-rpms  19 k
 xml-commons-apis          x86_64 1.3.02-0.b2.7jpp.10  rhel-5-server-rpms 388 k
 xml-commons-resolver      x86_64 1.1-1jpp.12          rhel-5-server-rpms 171 k

Transaction Summary
================================================================================
Install      68 Package(s)
Upgrade       0 Package(s)

Total download size: 207 M
*/
```
```
Is this ok [y/N]: y
```
```c
/*
Downloading Packages:
(1/68): geronimo-specs-compat-1.0-0.M2.2jpp.12.x86_64.rp | 5.5 kB     00:00
(2/68): xml-commons-1.3.02-0.b2.7jpp.10.x86_64.rpm       |  19 kB     00:00
(3/68): ant-swing-1.6.5-2jpp.2.x86_64.rpm                |  28 kB     00:00
(4/68): ant-apache-log4j-1.6.5-2jpp.2.x86_64.rpm         |  28 kB     00:00
(5/68): ant-apache-regexp-1.6.5-2jpp.2.x86_64.rpm        |  29 kB     00:00
(6/68): ant-apache-resolver-1.6.5-2jpp.2.x86_64.rpm      |  30 kB     00:00
(7/68): ant-commons-logging-1.6.5-2jpp.2.x86_64.rpm      |  31 kB     00:00
(8/68): ant-antlr-1.6.5-2jpp.2.x86_64.rpm                |  36 kB     00:00
(9/68): ant-javamail-1.6.5-2jpp.2.x86_64.rpm             |  37 kB     00:00
(10/68): ant-apache-bcel-1.6.5-2jpp.2.x86_64.rpm         |  38 kB     00:00
(11/68): jakarta-commons-daemon-1.0.1-6jpp.1.x86_64.rpm  |  46 kB     00:00
(12/68): ant-jdepend-1.6.5-2jpp.2.x86_64.rpm             |  46 kB     00:00
(13/68): jakarta-commons-fileupload-1.0-6jpp.1.x86_64.rp |  53 kB     00:00
(14/68): ant-jsch-1.6.5-2jpp.2.x86_64.rpm                |  72 kB     00:00
(15/68): eclipse-sdk-3.2.1-19.el5.x86_64.rpm             |  88 kB     00:00
(16/68): jakarta-commons-launcher-0.9-6jpp.1.x86_64.rpm  |  97 kB     00:00
(17/68): regexp-1.4-2jpp.2.x86_64.rpm                    | 102 kB     00:00
(18/68): tomcat5-jsp-2.0-api-5.5.23-0jpp.40.el5_9.x86_64 | 106 kB     00:00
(19/68): classpathx-jaf-1.0-9jpp.1.x86_64.rpm            | 111 kB     00:00
(20/68): jakarta-commons-logging-1.0.4-6jpp.1.x86_64.rpm | 116 kB     00:00
(21/68): ant-apache-oro-1.6.5-2jpp.2.x86_64.rpm          | 124 kB     00:00
(22/68): jzlib-1.0.7-4jpp.1.x86_64.rpm                   | 141 kB     00:00
(23/68): jakarta-commons-pool-1.3-5jpp.1.x86_64.rpm      | 143 kB     00:00
(24/68): jakarta-commons-discovery-0.3-4jpp.1.x86_64.rpm | 151 kB     00:00
(25/68): tomcat5-servlet-2.4-api-5.5.23-0jpp.40.el5_9.x8 | 166 kB     00:00
(26/68): xml-commons-resolver-1.1-1jpp.12.x86_64.rpm     | 171 kB     00:00
(27/68): ant-trax-1.6.5-2jpp.2.x86_64.rpm                | 177 kB     00:00
(28/68): ant-junit-1.6.5-2jpp.2.x86_64.rpm               | 179 kB     00:00
(29/68): jakarta-oro-2.0.8-3jpp.1.x86_64.rpm             | 195 kB     00:00
(30/68): tomcat5-common-lib-5.5.23-0jpp.40.el5_9.x86_64. | 227 kB     00:00
(31/68): jdepend-2.6-6jpp.2.x86_64.rpm                   | 259 kB     00:00
(32/68): geronimo-specs-1.0-0.M2.2jpp.12.x86_64.rpm      | 259 kB     00:00
(33/68): jakarta-commons-modeler-1.1-8jpp.3.el5.x86_64.r | 260 kB     00:00
(34/68): eclipse-pde-runtime-3.2.1-19.el5.x86_64.rpm     | 266 kB     00:00
(35/68): jakarta-commons-el-1.0-7jpp.1.x86_64.rpm        | 269 kB     00:00
(36/68): jakarta-commons-dbcp-1.2.1-7jpp.1.x86_64.rpm    | 279 kB     00:00
(37/68): junit-3.8.2-3jpp.1.x86_64.rpm                   | 338 kB     00:00
(38/68): jsch-0.1.28-1jpp.5.x86_64.rpm                   | 348 kB     00:00
(39/68): jakarta-commons-digester-1.7-5jpp.1.x86_64.rpm  | 350 kB     00:00
(40/68): xml-commons-apis-1.3.02-0.b2.7jpp.10.x86_64.rpm | 388 kB     00:00
(41/68): tomcat5-5.5.23-0jpp.40.el5_9.x86_64.rpm         | 395 kB     00:00
(42/68): wsdl4j-1.5.2-4jpp.1.x86_64.rpm                  | 430 kB     00:00
(43/68): jakarta-commons-beanutils-1.7.0-5jpp.1.x86_64.r | 571 kB     00:00
(44/68): jakarta-commons-httpclient-3.0-7jpp.4.el5_10.x8 | 606 kB     00:00
(45/68): log4j-1.2.13-3jpp.2.x86_64.rpm                  | 731 kB     00:00
(46/68): lucene-1.4.3-1jpp.16.x86_64.rpm                 | 771 kB     00:00
(47/68): ant-nodeps-1.6.5-2jpp.2.x86_64.rpm              | 903 kB     00:00
(48/68): tomcat5-jasper-5.5.23-0jpp.40.el5_9.x86_64.rpm  | 1.1 MB     00:00
(49/68): bcel-5.1-8jpp.1.x86_64.rpm                      | 1.1 MB     00:00
(50/68): jakarta-commons-collections-3.2-2jpp.4.x86_64.r | 1.2 MB     00:01
(51/68): classpathx-mail-1.1.1-4jpp.2.x86_64.rpm         | 1.2 MB     00:00
(52/68): eclipse-pde-sdk-3.2.1-19.el5.x86_64.rpm         | 2.0 MB     00:01
(53/68): ant-1.6.5-2jpp.2.x86_64.rpm                     | 2.3 MB     00:00
(54/68): mx4j-3.0.1-6jpp.4.x86_64.rpm                    | 2.7 MB     00:01
(55/68): xerces-j2-2.7.1-7jpp.2.el5_4.2.x86_64.rpm       | 3.1 MB     00:01
(56/68): axis-1.2.1-2jpp.8.el5_10.x86_64.rpm             | 3.6 MB     00:01
(57/68): libswt3-gtk2-3.2.1-19.el5.x86_64.rpm            | 3.8 MB     00:02
(58/68): tomcat5-server-lib-5.5.23-0jpp.40.el5_9.x86_64. | 4.1 MB     00:02
(59/68): xalan-j2-2.7.0-6jpp.2.x86_64.rpm                | 4.5 MB     00:02
(60/68): eclipse-rcp-sdk-3.2.1-19.el5.x86_64.rpm         | 7.0 MB     00:04
(61/68): eclipse-ecj-3.2.1-19.el5.x86_64.rpm             | 9.0 MB     00:02
(62/68): eclipse-pde-3.2.1-19.el5.x86_64.rpm             |  11 MB     00:06
(63/68): eclipse-jdt-sdk-3.2.1-19.el5.x86_64.rpm         |  12 MB     00:24
(64/68): eclipse-rcp-3.2.1-19.el5.x86_64.rpm             |  17 MB     00:07
(65/68): java-1.6.0-openjdk-javadoc-1.6.0.38-1.13.10.0.e |  20 MB     00:08
(66/68): eclipse-platform-sdk-3.2.1-19.el5.x86_64.rpm    |  27 MB     00:12
(67/68): eclipse-jdt-3.2.1-19.el5.x86_64.rpm             |  28 MB     00:17
(68/68): eclipse-platform-3.2.1-19.el5.x86_64.rpm        |  36 MB     00:12
--------------------------------------------------------------------------------
Total                                           1.3 MB/s | 207 MB     02:45
Running rpm_check_debug
Running Transaction Test
Finished Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing     : jakarta-commons-logging                                 1/68
  Installing     : tomcat5-servlet-2.4-api                                 2/68
  Installing     : classpathx-jaf                                          3/68
  Installing     : jakarta-commons-collections                             4/68
  Installing     : jakarta-commons-beanutils                               5/68
  Installing     : classpathx-mail                                         6/68
  Installing     : regexp                                                  7/68
  Installing     : jakarta-commons-digester                                8/68
  Installing     : tomcat5-jasper                                          9/68
  Installing     : jakarta-commons-pool                                   10/68
  Installing     : jakarta-commons-el                                     11/68
  Installing     : jakarta-commons-dbcp                                   12/68
  Installing     : bcel                                                   13/68
  Installing     : jakarta-commons-fileupload                             14/68
  Installing     : junit                                                  15/68
  Installing     : eclipse-ecj                                            16/68
  Installing     : jakarta-commons-launcher                               17/68
  Installing     : libswt3-gtk2                                           18/68
  Installing     : eclipse-rcp                                            19/68
  Installing     : xml-commons                                            20/68
  Installing     : xml-commons-apis                                       21/68
  Installing     : java-1.6.0-openjdk-javadoc                             22/68
  Installing     : tomcat5-jsp-2.0-api                                    23/68
  Installing     : jakarta-commons-httpclient                             24/68
  Installing     : jakarta-commons-discovery                              25/68
  Installing     : jzlib                                                  26/68
  Installing     : jsch                                                   27/68
  Installing     : lucene                                                 28/68
  Installing     : jakarta-oro                                            29/68
  Installing     : jakarta-commons-daemon                                 30/68
  Installing     : jdepend                                                31/68
  Installing     : eclipse-rcp-sdk                                        32/68
  Installing     : xerces-j2                                              33/68
  Installing     : ant                                                    34/68
  Installing     : log4j                                                  35/68
  Installing     : xml-commons-resolver                                   36/68
  Installing     : xalan-j2                                               37/68
  Installing     : ant-trax                                               38/68
  Installing     : ant-apache-resolver                                    39/68
  Installing     : ant-apache-log4j                                       40/68
  Installing     : ant-jsch                                               41/68
  Installing     : ant-swing                                              42/68
  Installing     : ant-javamail                                           43/68
  Installing     : ant-jdepend                                            44/68
  Installing     : ant-nodeps                                             45/68
  Installing     : ant-commons-logging                                    46/68
  Installing     : ant-apache-bcel                                        47/68
  Installing     : ant-junit                                              48/68
  Installing     : ant-antlr                                              49/68
  Installing     : ant-apache-regexp                                      50/68
  Installing     : ant-apache-oro                                         51/68
  Installing     : wsdl4j                                                 52/68
  Installing     : axis                                                   53/68
  Installing     : mx4j                                                   54/68
  Installing     : jakarta-commons-modeler                                55/68
  Installing     : tomcat5-server-lib                                     56/68
  Installing     : geronimo-specs                                         57/68
  Installing     : geronimo-specs-compat                                  58/68
  Installing     : tomcat5-common-lib                                     59/68
  Installing     : tomcat5                                                60/68
  Installing     : eclipse-platform                                       61/68
  Installing     : eclipse-platform-sdk                                   62/68
  Installing     : eclipse-jdt                                            63/68
  Installing     : eclipse-pde-runtime                                    64/68
  Installing     : eclipse-jdt-sdk                                        65/68
  Installing     : eclipse-pde                                            66/68
  Installing     : eclipse-pde-sdk                                        67/68
  Installing     : eclipse-sdk                                            68/68

Installed:
  eclipse-ecj.x86_64 1:3.2.1-19.el5
  eclipse-jdt.x86_64 1:3.2.1-19.el5
  eclipse-jdt-sdk.x86_64 1:3.2.1-19.el5
  eclipse-pde.x86_64 1:3.2.1-19.el5
  eclipse-pde-runtime.x86_64 1:3.2.1-19.el5
  eclipse-pde-sdk.x86_64 1:3.2.1-19.el5
  eclipse-platform.x86_64 1:3.2.1-19.el5
  eclipse-platform-sdk.x86_64 1:3.2.1-19.el5
  eclipse-rcp.x86_64 1:3.2.1-19.el5
  eclipse-rcp-sdk.x86_64 1:3.2.1-19.el5
  eclipse-sdk.x86_64 1:3.2.1-19.el5

Dependency Installed:
  ant.x86_64 0:1.6.5-2jpp.2
  ant-antlr.x86_64 0:1.6.5-2jpp.2
  ant-apache-bcel.x86_64 0:1.6.5-2jpp.2
  ant-apache-log4j.x86_64 0:1.6.5-2jpp.2
  ant-apache-oro.x86_64 0:1.6.5-2jpp.2
  ant-apache-regexp.x86_64 0:1.6.5-2jpp.2
  ant-apache-resolver.x86_64 0:1.6.5-2jpp.2
  ant-commons-logging.x86_64 0:1.6.5-2jpp.2
  ant-javamail.x86_64 0:1.6.5-2jpp.2
  ant-jdepend.x86_64 0:1.6.5-2jpp.2
  ant-jsch.x86_64 0:1.6.5-2jpp.2
  ant-junit.x86_64 0:1.6.5-2jpp.2
  ant-nodeps.x86_64 0:1.6.5-2jpp.2
  ant-swing.x86_64 0:1.6.5-2jpp.2
  ant-trax.x86_64 0:1.6.5-2jpp.2
  axis.x86_64 0:1.2.1-2jpp.8.el5_10
  bcel.x86_64 0:5.1-8jpp.1
  classpathx-jaf.x86_64 0:1.0-9jpp.1
  classpathx-mail.x86_64 0:1.1.1-4jpp.2
  geronimo-specs.x86_64 0:1.0-0.M2.2jpp.12
  geronimo-specs-compat.x86_64 0:1.0-0.M2.2jpp.12
  jakarta-commons-beanutils.x86_64 0:1.7.0-5jpp.1
  jakarta-commons-collections.x86_64 0:3.2-2jpp.4
  jakarta-commons-daemon.x86_64 1:1.0.1-6jpp.1
  jakarta-commons-dbcp.x86_64 0:1.2.1-7jpp.1
  jakarta-commons-digester.x86_64 0:1.7-5jpp.1
  jakarta-commons-discovery.x86_64 1:0.3-4jpp.1
  jakarta-commons-el.x86_64 0:1.0-7jpp.1
  jakarta-commons-fileupload.x86_64 1:1.0-6jpp.1
  jakarta-commons-httpclient.x86_64 1:3.0-7jpp.4.el5_10
  jakarta-commons-launcher.x86_64 0:0.9-6jpp.1
  jakarta-commons-logging.x86_64 0:1.0.4-6jpp.1
  jakarta-commons-modeler.x86_64 0:1.1-8jpp.3.el5
  jakarta-commons-pool.x86_64 0:1.3-5jpp.1
  jakarta-oro.x86_64 0:2.0.8-3jpp.1
  java-1.6.0-openjdk-javadoc.x86_64 1:1.6.0.38-1.13.10.0.el5_11
  jdepend.x86_64 0:2.6-6jpp.2
  jsch.x86_64 0:0.1.28-1jpp.5
  junit.x86_64 0:3.8.2-3jpp.1
  jzlib.x86_64 0:1.0.7-4jpp.1
  libswt3-gtk2.x86_64 1:3.2.1-19.el5
  log4j.x86_64 0:1.2.13-3jpp.2
  lucene.x86_64 0:1.4.3-1jpp.16
  mx4j.x86_64 1:3.0.1-6jpp.4
  regexp.x86_64 0:1.4-2jpp.2
  tomcat5.x86_64 0:5.5.23-0jpp.40.el5_9
  tomcat5-common-lib.x86_64 0:5.5.23-0jpp.40.el5_9
  tomcat5-jasper.x86_64 0:5.5.23-0jpp.40.el5_9
  tomcat5-jsp-2.0-api.x86_64 0:5.5.23-0jpp.40.el5_9
  tomcat5-server-lib.x86_64 0:5.5.23-0jpp.40.el5_9
  tomcat5-servlet-2.4-api.x86_64 0:5.5.23-0jpp.40.el5_9
  wsdl4j.x86_64 0:1.5.2-4jpp.1
  xalan-j2.x86_64 0:2.7.0-6jpp.2
  xerces-j2.x86_64 0:2.7.1-7jpp.2.el5_4.2
  xml-commons.x86_64 0:1.3.02-0.b2.7jpp.10
  xml-commons-apis.x86_64 0:1.3.02-0.b2.7jpp.10
  xml-commons-resolver.x86_64 0:1.1-1jpp.12

Complete!
*/
```
