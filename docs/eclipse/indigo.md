# eclpise

## References
* http://stackoverflow.com/questions/9258797/what-is-the-yum-command-to-install-eclipse-indigo-for-java-ee-developers
* http://www.if-not-true-then-false.com/2010/linux-install-eclipse-on-fedora-centos-red-hat-rhel/
* http://www.eclipse.org/downloads/packages/release/Indigo/SR2

##### Download Eclipse IDE for Java EE Developers
* http://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/indigosr2

##### 

```
mkdir /opt/eclipse/indigo
```

```
sudo nano /usr/bin/eclipse-indigo
```
```bash
#!/bin/sh
export ECLIPSE_HOME="/opt/eclipse/indigo"

$ECLIPSE_HOME/eclipse $*
```

```
sudo chmod +x /usr/bin/eclipse-indigo
```
