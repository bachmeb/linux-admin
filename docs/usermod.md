# usermod

## References
* http://man7.org/linux/man-pages/man8/usermod.8.html

Add your user account to the dba group
```
sudo usermod -a -G mailman [your user account]
```

##### Exit your user sesison and switch back to your account to get Linux to recognize your account as a member of the mailman group
```
exit
sudo su -l [your user account]
```
