# yum

## References
* https://access.redhat.com/solutions/253273
* https://access.redhat.com/solutions/1213413

##### Register the system with Red Hat Subscription Management
```
subscription-manager register --username [YOUR RH USERNAME] --password [YOUR RH PASSWORD] --auto-attach
```
```c
/*
You are attempting to run "subscription-manager" which requires administrative
privileges, but more information is needed in order to do so.
Password for root:
The system has been registered with ID: asdfasdf-asdf-asdf-asdf-asdfasdfasdfasdf
Installed Product Current Status:
Product Name: Red Hat Enterprise Linux Server
Status:       Subscribed
*/
```

##### Install system updates
```
sudo yum update
```

