# tune2fs

## References
* http://unix.stackexchange.com/questions/9971/how-do-i-find-how-long-ago-a-linux-system-was-installed

##### See when the /dev/sda1 filesystem was created
```
sudo tune2fs -l /dev/sda1 | grep 'Filesystem created'
```
```c
/*
Filesystem created:       Mon May  9 17:04:00 2016
*/
```
