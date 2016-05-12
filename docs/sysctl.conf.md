# /etc/sysctl.conf

## References
* https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/5/html/Tuning_and_Optimizing_Red_Hat_Enterprise_Linux_for_Oracle_9i_and_10g_Databases/sect-Oracle_9i_and_10g_Tuning_Guide-Setting_Semaphores-Setting_Semaphore_Parameters.html

##### Determine the values of the four described semaphore parameters
```
cat /proc/sys/kernel/sem
```
* These values represent SEMMSL, SEMMNS, SEMOPM, and SEMMNI.
```c
/*
250     32000   32      128
*/
```

##### Use sysctl(8) to change the semaphore parameters
```
sysctl -w kernel.sem="250 32000 100 128"
```

##### Edit sysctl.conf to make the changes permanent
* This file is used during the boot process
```
/etc/sysctl.conf
```
```
kernel.sem=250 32000 100 128
```
