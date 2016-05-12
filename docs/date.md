
##### Check the time
	date
	
##### List the available time zones
	ls /usr/share/zoneinfo/

##### Update the /etc/sysconfig/clock file with your time zone
	sudo nano /etc/sysconfig/clock
```
ZONE="America/New_York"
UTC=false
```
##### Create a symbolic link between /etc/localtime and your time zone file
	sudo ln -sf /usr/share/zoneinfo/America/New_York /etc/localtime

##### Check the time
	date

##### Reboot the system to pick up the new time zone information in all services and applications
	sudo reboot
