# cvs2svn

## References
* http://cvs2svn.tigris.org/cvs2git.html
* http://cvs2svn.tigris.org/
* http://stackoverflow.com/questions/20869710/migrate-from-cvs-to-git-without-losing-history

##### Download
```
cd ~
svn co --username=guest --password="" http://cvs2svn.tigris.org/svn/cvs2svn/trunk cvs2svn-trunk
```

##### Make the manual pages
```
make man
```
```
./cvs2svn --man >cvs2svn.1
./cvs2git --man >cvs2git.1
./cvs2bzr --man >cvs2bzr.1
```

##### Check
```
make check
```
```

```
