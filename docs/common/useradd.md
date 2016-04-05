

##### Switch to super user
	sudo su
	
##### Check the default options configured for adding a user on this system
	useradd -D
    
##### Create a non-admin user account for yourself
	useradd [your user account name]
    
##### Set your password
	passwd [your user account name]

##### Edit sudoers file
	vim /etc/sudoers
	:$

##### Add your account to sudoers file
	## LET ME SUDO
	[your user account name] ALL=(ALL) ALL

##### Switch to your user account. Be sure to use the -l switch.
	su -l [your user account name]

##### Ask who am I?
	whoami

##### Echo the value of the $HOME environment variable
	echo $HOME
	
##### Go home
	cd ~
	pwd

##### Change the command prompt to show your username at the fqdn
	export PS1='[\u@\H \W]\$'

##### Read your .bashrc file
	cat .bashrc
	
##### Add the PS1 command to your .bashrc file
	echo 'PS1="[\u@\H \W]\$ "'>>~/.bashrc

##### Read your .bashrc file
	cat .bashrc
