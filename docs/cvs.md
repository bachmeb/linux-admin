# cvs

## References
* http://stackoverflow.com/questions/354599/how-to-find-all-commitsfilescomments-by-a-person-in-cvs
* https://www.youtube.com/watch?v=G7BXtugVGqY
* https://www.youtube.com/watch?v=odNgQuX47eI
* http://www.thegeekstuff.com/2011/10/create-cvs-repository/
* http://www.fisica.uniud.it/~glast/sw/cvs/cvsintro.html
* http://www.linuxhowtos.org/System/cvs_tutorial.htm
* http://owen.sj.ca.us/~rk/howto/cvs.html#access
* http://www-mrsrl.stanford.edu/~brian/cvstutorial/
* http://www.thathost.com/wincvs-howto/cvsdoc/cvs_2.html

##### See if cvs is installed
```
cvs
```

##### Install cvs
```
sudo yum search cvs
sudo yum install cvs
```

##### Create CVS User and Groups
```
sudo useradd cvs
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
mkdir cvsroot
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
sudo chgrp developers /home/cvs/cvsroot
```

##### Set the group permissions on the directory
```
sudo chmod g+srwx /home/cvs/cvsroot
ls -la /home/cvs/cvsroot
```

##### Set the CVSROOT environment variable for your user account
```
export CVSROOT=/home/cvs/cvsroot
```

##### Initialize the CVS repository
*CVS initializes as a repository the directory set in the CVSROOT environment variable*
```
cvs init
```

##### See the CVSROOT directory created in the CVS repository
```
ls -la /home/cvs/cvsroot
```
```
total 12
drwxrwxr-x 3 cvs developers 3096 Aug 21 15:11 .
drwx------ 4 cvs cvs        3096 Aug 21 15:10 ..
drwxrwxr-x 3 cvs cvs        3096 Aug 21 15:11 CVSROOT
```

##### Go to your home directory and create a project directory
```
cd ~
mkdir project1
cd project1/
```

##### Create a file in the project directory
```
nano hello.txt
```

##### Import the project to the repository
```
pwd
cvs import -m "hello there" ABC XYZ start
```

##### Delete the project
```
cd ..
pwd
rm -fr project1/
```

##### Check the project back out from cvs
```
cd ~
pwd
cvs co ABC
```
```
cvs checkout: Updating ABC
U ABC/hello.txt
```

##### Check the log
```
cvs log
```
```
cvs log: Logging ABC

RCS file: /home/cvs/cvsroot/ABC/hello.txt,v
Working file: ABC/hello.txt
head: 1.1
branch: 1.1.1
locks: strict
access list:
symbolic names:
	start: 1.1.1.1
	XYZ: 1.1.1
keyword substitution: kv
total revisions: 2;	selected revisions: 2
description:
----------------------------
revision 1.1
date: 2016/08/07 15:29:22;  author: bachmeb;  state: Exp;
branches:  1.1.1;
Initial revision
----------------------------
revision 1.1.1.1
date: 2016/08/07 15:29:22;  author: bachmeb;  state: Exp;  lines: +0 -0
hello there
=============================================================================
```

##### Find all commits(files&comments) by a person in cvs
```
cvs log -t -wJellyJoe
```
