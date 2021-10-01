# Command_Line
The command line is a text interface for the computer’s operating system. You can use it to traverse and edit your computer’s filesystem. Through the command line, you can create new files, edit the contents of those files, delete files, and more!
On Mac and Linux systems, we access the command line through something called Bash.

## 1. Navigation

### A. Filesystem
A filesystem organizes a computer’s files and directories into a tree structure:
![Filesystem](https://user-images.githubusercontent.com/62128029/134777967-9d896d41-5dcb-44e7-8017-96a40883badd.png)

1. The first directory in the filesystem is the root directory. It is the parent of all other directories and files in the filesystem.
2. Each parent directory can contain more child directories and files. In the filesystem on the right, blog/ is the parent of 2014/, 2015/, and hardware.txt.
3. Each directory can contain more files and child directories. The parent-child relationship continues as long as directories and files are nested.
You’re probably already familiar with this tree structure - Mac Finder and Windows Explorer represent the filesystem as trees as well.

### ls - List
```
$ ls Desktop
resume.pdf
photo.png
```
The shell command ls is used to list the contents of a directory. If no arguments are given, it will list the contents of the current working directory.

### pwd - Print Working Directory
```
$ pwd
/Users/sonny/Downloads
```
The shell command pwd displays the file path from the root directory to the current working directory.

### mkdir - Make Directory
```
$ mkdir new-directory
$ ls 
old-directory    new-directory
```
The shell command mkdir is used to make a new directory in the filesystem according to its argument. If a file path is given, the new directory will be placed at the end. Otherwise, it will create a new directory in the current working directory.
### cd - Change Directory
```
$ cd some-directory
$ cd ..
```
The shell command cd is used to move throughout the filesystem of a computer. It accepts a variety of arguments:
* Full file paths.
* Names of children of the current directory.
* .. the parent of the current directory.


### touch - Make file 
The touch command is a standard command used in UNIX/Linux operating system which is used to create, change and modify timestamps of a file.
```
$ touch keyboard.txt
```
### clear
clear is used to clear your terminal, which is useful when it’s full of previous commands and outputs. It doesn’t change or undo your previous commands, it just clears them from the view. You can scroll upwards to see them at any time.
```
clear
```
### tab
tab can be used to autocomplete your command. When you are typing the name of an existing file or directory, you can use tab to finish the rest of the name.

### up and down arrows
The up and down arrows (↑ and ↓) can be used to cycle through your previous commands. ↑ will take you up through your most recent commands, and ↓ will take you back through to the most recent one.



## 2. Manipulation
### ls, revisited
We can use ls as is, or attach an option. Options modify the behavior of commands.
```
ls -a
```
The command above displays the contents of the working directory in more detail. This command displays all the files and directories, including those starting with a dot (.). Files starting with a dot are normally hidden, and don’t appear when using ls alone.
The -a is called an option. Options modify the behavior of commands.
We can also use 
```
ls -l
```
Lists all contents of a directory in long format, as well as the file permissions.
```
ls -t
```
Orders files and directories by the time they were last modified.

### cat
The cat command outputs the contents of a specified file.
```
cat action/superwoman.txt
```
This will output all the text from superwoman.txt. This is a useful command for peeking at files without opening them, and confirming the result of other commands that change the contents of files.

### cp
The cp command copies files or directories. Below, we copy the contents of a source file into a destination file.
```
cp source.txt destination.txt 
```
We could also copy a file to a destination directory.
```
cp source.txt destination/
```
To copy multiple files into a directory, use cp with a list of source files as the first arguments, and the destination directory as the last argument. Here, we copy the files file1.txt and file2.txt into the same directory.

```
cp file1.txt file2.txt my_directory/ 
```
### Wildcards
In addition to using exact filenames as arguments, we can use special characters like * to select groups of files. These special characters are called wildcards. For example, here we use cp to copy all files in the current working directory into another directory.
```
cp *my_directory
```
Here, w*.txt selects all files in the working directory starting with “w” (prefix) and ending with “.txt” (suffix), and copies them to my_directory/.
```
cp w*.txt my_directory/
```
### mv - move
The mv command moves files. It’s similar to cp in its usage, except mv moves a file without making a copy.
```
mv my_file.txt my_directory/
```
Here we move my_file.txt into my_directory/.
```
mv my_file_1.txt my_file_2.txt my_directory/
```
To move multiple files into a directory, use mv with a list of source files as the first arguments, and the destination directory as the last argument. Here, we move my_file_1.txt and my_file_2.txt into my_directory/.
```
mv file_origin.txt file_renamed.txt
```
To rename a file, use mv with the old file as the first argument and the new file as the second argument. By moving file_original.txt into file_renamed.txt, we rename the file as file_renamed.txt.

### rm - remove
The rm command deletes files and directories. Here we remove the file unwanted_file.txt from the filesystem.
```
rm unwanted_file.txt
```
The -r is an option that modifies the behavior of the rm command. The -r stands for “recursive,” and it’s used to delete a directory and all of its child directories.
```
rm -r unwanted_directory
```
Be careful when you use rm! It deletes files and directories permanently. There isn’t an undelete command, so once you delete a file or directory with rm, it’s gone.

## 3. Redirection
## 4. Configuration


