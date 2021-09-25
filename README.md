# Command_Line
The command line is a text interface for the computer’s operating system. You can use it to traverse and edit your computer’s filesystem. Through the command line, you can create new files, edit the contents of those files, delete files, and more!
On Mac and Linux systems, we access the command line through something called Bash.

## 1. Navigation

### A. Filesystem
A filesystem organizes a computer’s files and directories into a tree structure:
![Filesystem](https://user-images.githubusercontent.com/62128029/134777967-9d896d41-5dcb-44e7-8017-96a40883badd.png)
1. The first directory in the filesystem is the root directory. It is the parent of all other directories and files in the filesystem.
<br/>
2. Each parent directory can contain more child directories and files. In the filesystem on the right, blog/ is the parent of 2014/, 2015/, and hardware.txt.
<br/>
3. Each directory can contain more files and child directories. The parent-child relationship continues as long as directories and files are nested.
<br/>

You’re probably already familiar with this tree structure - Mac Finder and Windows Explorer represent the filesystem as trees as well.

#### ls - List
```
$ ls Desktop
resume.pdf
photo.png

```
The shell command ls is used to list the contents of a directory. If no arguments are given, it will list the contents of the current working directory.

#### pwd - Print Working Directory
```
$ pwd
/Users/sonny/Downloads
```
The shell command pwd displays the file path from the root directory to the current working directory.

#### mkdir - Make Directory
```
$ mkdir new-directory
$ ls 
old-directory    new-directory
```
The shell command mkdir is used to make a new directory in the filesystem according to its argument. If a file path is given, the new directory will be placed at the end. Otherwise, it will create a new directory in the current working directory.
#### cd - Change Directory
```
$ cd some-directory
$ cd ..
```
The shell command cd is used to move throughout the filesystem of a computer. It accepts a variety of arguments:
* Full file paths.
* Names of children of the current directory.
* .. the parent of the current directory.


#### 
## 2. Manipulation
## 3. Redirection
## 4. Configuration


