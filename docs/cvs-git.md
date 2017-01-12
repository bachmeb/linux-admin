# cvs-git

## References
* http://sleepyhead.de/howto/?href=cvs

```
export CVSROOT=:ext:user@cvsserver:/path/to/repo
export CVS_RSH ssh    
mkdir ~/newrepo
cd ~/newrepo
cvs init
git cvsimport remoterepo
```
