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
