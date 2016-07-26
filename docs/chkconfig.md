# chkconfig

##### Check the run level
	runlevel
	
##### See if httpd is set to start for run levels 0 through 6
	chkconfig --list httpd

##### Set httpd to start in run levels 2, 3, 4, and 5
	sudo chkconfig httpd on

##### See if httpd is set to start for run level 3
	chkconfig --list httpd
