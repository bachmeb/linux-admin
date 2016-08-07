# cvs

## References
* http://stackoverflow.com/questions/354599/how-to-find-all-commitsfilescomments-by-a-person-in-cvs
* https://www.youtube.com/watch?v=G7BXtugVGqY
* https://www.youtube.com/watch?v=odNgQuX47eI
* http://www.thegeekstuff.com/2011/10/create-cvs-repository/
* http://www.fisica.uniud.it/~glast/sw/cvs/cvsintro.html

##### How to find all commits(files&comments) by a person in cvs
```
cvs log -t -wJellyJoe
```

##### Install
```
sudo yum search cvs
sudo yum install cvs
```

##### Create CVS User and Groups
```
sudo useradd cvs
```
```
sudo passwd cvs
```

##### Create developers group
```
sudo groupadd developers
```

##### Add your account to the devleopers group
```
sudo usermod -a -G developers [your user account]
```

##### Switch to the cvs user
```
su cvs
```

##### Create CVS Repository Directory
```
cd /home/cvs
mkdir project1
```

##### Exit the cvs user
```
exit
```

##### Make the cvs home directory group-searchable
```
sudo ls -la /home
sudo chmod g+x /home/cvs
```

##### Give the developers group permission to the project directory
```
sudo ls -la /home/cvs
sudo chgrp developers /home/cvs/project1
```

##### Set the group permissions on the directory
```
sudo chmod g+srwx /home/cvs/project1
ls -la /home/cvs/project1
```

##### Initialize the CVS Repository
```
cvs -d /home/cvs/project1 init
```

##### See the CVSROOT directory created under the CVS repository
```
ls -la /home/cvs/project1/
```
```
total 12
drwxrwxr-x 3 cvs developers 3096 Aug 21 15:11 .
drwx------ 4 cvs cvs        3096 Aug 21 15:10 ..
drwxrwxr-x 3 cvs cvs        3096 Aug 21 15:11 CVSROOT
```

##### Set the CVSROOT environment variable for your user account
```
CVSROOT=/home/cvs/project1/
export CVSROOT
```














##### Make a new directory in your home directory
```
cd ~
mkdir src
cd src
echo hello > hello.txt
```

##### Go to the root directory of the new project
```
cd ~/src
pwd
```

##### Import the project
```
cvs import src VEND tag1
```
```

CVS: ----------------------------------------------------------------------
CVS: Enter Log.  Lines beginning with `CVS:' are removed automatically
CVS:
CVS: ----------------------------------------------------------------------
~                                                                               
~                                                                               
~           
```
```
Log message unchanged or not specified
a)bort, c)ontinue, e)dit, !)reuse this message unchanged for remaining dirs
Action: (continue) 
N project2/hello.txt
cvs import: Importing /home/cvs/project1/project2/subdir

No conflicts created by this import
```
