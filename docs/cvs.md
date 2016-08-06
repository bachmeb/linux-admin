# cvs

## References
* http://stackoverflow.com/questions/354599/how-to-find-all-commitsfilescomments-by-a-person-in-cvs
* https://www.youtube.com/watch?v=G7BXtugVGqY
* https://www.youtube.com/watch?v=odNgQuX47eI
* http://www.thegeekstuff.com/2011/10/create-cvs-repository/

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
Create cvs user as shown below.
```
useradd cvs
```
```
passwd cvs
```
If you want only developers to access the CVS repository, create a developers group as shown below.

```
groupadd developers
```

Create CVS Repository Directory

If you are planning to create a CVS repository for project1, create the following /home/cvs/project1 directory and assign appropriate privileges.

```
cd /home/cvs
```

```
mkdir project1
```

As root, do the following to assign developers group to this directory, also make sure group has full privilege on this project1 directory.

```
chgrp developers /home/cvs/project1/
```

```
chmod g+srwx /home/cvs/project1
```

Initialize the CVS Repository

Currently the /home/cvs/project1 is just an empty directory. To make this as a CVS repository, you should initialize it as shown below.

```
cvs -d /home/cvs/project1 init
```
Once initialized, you’ll see CVSROOT directory created under the CVS repository.

```
ls -la /home/cvs/project1/
```
```
total 12
drwxrwxr-x 3 cvs developers 3096 Aug 21 15:11 .
drwx------ 4 cvs cvs        3096 Aug 21 15:10 ..
drwxrwxr-x 3 cvs cvs        3096 Aug 21 15:11 CVSROOT
```
Now you can start checking in your source code to the /home/cvs/project1 CVS repository.
