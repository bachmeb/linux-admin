# read

## References
* http://stackoverflow.com/questions/92802/what-is-the-linux-equivalent-to-dos-pause
* http://tldp.org/LDP/Bash-Beginners-Guide/html/sect_08_02.html

##### Pause the script for user input
```
read -n1 -r -p "Press any key to continue..." key
```

##### Read user input to a script variable
```
echo What is your name?
read name
echo "Hi $name"
```
