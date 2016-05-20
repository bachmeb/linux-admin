# history

## References
* http://unix.stackexchange.com/questions/203290/how-do-i-clear-the-terminal-history
* http://askubuntu.com/questions/391082/how-to-see-time-stamps-in-bash-history

##### Clear history
```
history -c
```

##### Display history with date and time stamps
```
HISTTIMEFORMAT="%Y-%m-%d %T "
history
```

##### Add HISTTIMEFORMAT setting to bash profile
```
echo 'export HISTTIMEFORMAT="%Y-%m-%d %T "' >> ~/.bash_profile ; source ~/.bash_profile
```

##### Check the current setting for history size
```
echo "$HISTSIZE $HISTFILESIZE"
```

##### Set the history size
```
echo 'export HISTSIZE=5000' >> ~/.bash_profile ; source ~/.bash_profile
echo 'export HISTFILESIZE=5000' >> ~/.bash_profile ; source ~/.bash_profile
```
