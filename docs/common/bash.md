# bash

## References
* http://unix.stackexchange.com/questions/13258/dark-blue-color-in-vim-or-ls-output-in-linux

##### Create a dir_colors file and change the directory color from dark blue to cyan
```
nano ~/.dir_colors
```
```
DIR 01;36 
```

##### Change the command prompt to show your username at the fqdn
	export PS1='[\u@\H \W]\$'

##### Read your .bashrc file
	cat .bashrc
	
##### Add the PS1 command to your .bashrc file
	echo 'PS1="[\u@\H \W]\$ "'>>~/.bashrc

##### Read your .bashrc file
	cat .bashrc
