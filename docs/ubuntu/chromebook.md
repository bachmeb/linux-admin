# chromebook ubuntu linux

## References
* https://support.google.com/chromebook/answer/1080595?hl=en
* https://www.linux.com/learn/tutorials/795730-how-to-easily-install-ubuntu-on-chromebook-with-crouton
* http://www.codeapex.com/restore-an-acer-c720-chromebook-to-stock-after-installing-linux-on-it/
* http://lifehacker.com/how-to-install-linux-on-a-chromebook-and-unlock-its-ful-509039343
* https://training.linuxfoundation.org/why-our-linux-training/blogs/lftstaff/846-use-linux-on-your-chromebook
* https://github.com/dnschneid/crouton

### Requirements
* Chromebook
* 4GB USB stick

##### Back up any files stored on the Chromebook
All local files will be deleted while enabling developer mode.

##### Use the Recovery Utility to create a restore image
* https://support.google.com/chromebook/answer/6002417?hl=en&source=genius-rts

##### Enable developer mode
* Hit Esc-Refresh-Power
* The machine will reboot
* Hit Ctrl-D
* Hit Enter
* Wait about 10 minutes
* Let the system reboot

##### Download Crouton 
* https://github.com/dnschneid/crouton
* https://goo.gl/fd3zc

##### Open a terminal tab
* Ctrl+Alt+T

##### Open a bash shell
```
shell
```
##### See where you are
```
pwd
```

##### See who you are
```
whoami
```

##### Install Crouton with xfce
```
sudo sh -e ~/Downloads/crouton -t xfce
```

##### Wait for all of the packages to be downloaded and installed
...about ten mintes.

##### Have fun
...

##### Delete crouton
```
sudo rm -fr /usr/local/bin
sudo rm -fr /usr/local/chroots/
```
