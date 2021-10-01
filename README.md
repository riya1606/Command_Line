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
Through redirection you can direct the input and output of a command to and from other files and programs, and chain commands together in a pipeline.
### echo
```
$ echo "Hello"
```
The echo command accepts the string “Hello” as standard input, and echoes the string “Hello” back to the terminal as standard output.
Let’s learn more about standard input, standard output, and standard error:

* standard input, abbreviated as stdin, is information inputted into the terminal through the keyboard or input device.

* standard output, abbreviated as stdout, is the information outputted after a process is run.

* standard error, abbreviated as stderr, is an error message outputted by a failed process.
### >
```
$ echo "Hello" > hello.txt
```
The > command redirects the standard output to a file. Here, "Hello" is entered as the standard input, and is then redirected to the file hello.txt by > .
```
$ cat deserts.txt > forests.txt
```
'>' takes the standard output of the command on the left, and redirects it to the file on the right. Here the standard output of cat deserts.txt is redirected to forests.txt.
Note that > overwrites all original content in forests.txt. When you view the output data by using cat on forests.txt, you will see only the contents of deserts.txt.

### >>
Now we know how to overwrite a file’s contents, but what if we want to be able to add to a file without losing the original text? We can use the >> command!
```
$ cat deserts.txt >> forests.txt
```
'>>' takes the standard output of the command on the left and appends (adds) it to the file on the right. Here, the output data of forests.txt will contain the original contents of forests.txt with the content of deserts.txt appended to it.
### <
```
$ cat < deserts.txt
```
'<' takes the standard input from the file on the right and inputs it into the program on the left. Here, deserts.txt is the standard input for the cat command. The standard output appears in the terminal.

### |
| is a “pipe.” The | takes the standard output of the command on the left, and pipes it as standard input to the command on the right. You can think of this as “command to command” redirection.
```
$ cat volcanoes.txt | wc  
```
Above, the output of cat volcanoes.txt becomes the standard input of wc. in turn, the wc command outputs the number of lines, words, and characters in volcanoes.txt, respectively.
```
$ cat volcanoes.txt | wc | cat > islands.txt 
```
Multiple |s can be chained together. Here the standard output of cat volcanoes.txt is “piped” to the wc command. The standard output of wc is then “piped” to cat. Finally, the standard output of cat is redirected to islands.txt.

### sort
```
$ sort continents.txt 
```
sort takes the standard input and orders it alphabetically for the standard output (it doesn’t change the file itself). Here, the continents in continents.txt will be listed in alphabetical order.
```
$ cat glaciers.txt | sort > sorted-glaciers.txt 
```
Here, the command takes the standard output from cat glaciers.txt and “pipes” it to sort. The standard output of sort is redirected to a new file named sorted-glaciers.txt.

### uniq
```
$ uniq deserts.txt 
```
uniq stands for “unique.” It filters out adjacent, duplicate lines in a file(The ones that have both).
```
$ sort deserts.txt | uniq
```
A more effective way to use uniq is to call sort to alphabetize a file, and “pipe” the standard output to uniq. By piping sort deserts.txt to uniq, all duplicate lines are alphabetized (and thereby made adjacent) and filtered out.
```
sort deserts.txt | uniq > uniq-deserts.txt
```
### grep
grep stands for “global regular expression print.” It searches files for lines that match a pattern and then returns the results. It is also case sensitive. Above, grep searched for anything that matched “America” in continents.txt.
```
$ grep America continents.txt 
```
grep -i enables the command to be case insensitive. Here, grep searched for capital or lowercase strings that match “America” in continents.txt. Note that we don’t use quotes in our command.
```
$ grep -i America continents.txt
```
The above commands are a great way to get started with grep. If you are familiar with regular expressions, you can also use regular expressions to search for patterns in files.

```
$ grep -R Arctic /home/ccuser/workspace/geography
```
grep -R searches all files in a directory and outputs filenames and lines containing matched results. -R stands for “recursive”. Above, grep -R searched the /home/ccuser/workspace/geography directory for the string “Arctic” and outputted filenames and lines with matching results.
```
$ grep -Rl Arctic /home/ccuser/workspace/geography
```
grep -Rl searches all files in a directory and outputs only filenames with matched results (so no lines). l (a lowercase L, not a capital i) stands for “files with matches.” Here grep -Rl searched the /home/ccuser/workspace/geography directory for the string “Arctic” and outputs filenames with matched results.

### sed
sed stands for “stream editor.” It accepts standard input and modifies it based on an expression, before displaying it as output data. It is similar to “find and replace.”
```
sed 's/snow/rain/' forests.txt 
```
Let’s look at the expression 's/snow/rain/':

* s: stands for “substitution.” It is always used when using sed for substitution.
* snow: the search string, or the text to find.
* rain: the replacement string, or the text to add in place.
In this case, sed searches forests.txt for the word “snow” and replaces it with “rain.” Importantly, the above command will only replace the first instance of “snow” on a line.

```
sed 's/snow/rain/g' forests.txt 
```
The above command uses the g expression, meaning “global.” Here sed searches forests.txt for the word “snow” and replaces it with “rain” globally. This means all instances of “snow” on a line will be turned to “rain.”
sed as we’ve used it will only rewrite the command line output and the actual file won’t be changed. In order to rewrite the actual file, we need to use -i at the beginning of the command:
```
sed -i 's/snow/rain/g' forests.txt
```

## 4. Configuration

### Introduction to Environment
Each time we launch the terminal application, it creates a new session. The session immediately loads settings and preferences that make up the command line environment.

We can configure the environment to support the commands and programs we create. This enables us to customize greetings and create nicknames (aliases) for commands, and create variables to share across commands and programs.

### NANO
```
nano hello.txt
```
This will open the nano text editor.
In nano, at the top of the window, type:
```
"Hello, I am nano." 
```
Using the menu at the bottom of the terminal for reference, type Ctrl + O (the letter, not zero) to save the file. The keys are not case-sensitive, so don’t worry about capitalizing.

Press Enter, when prompted about the filename to write.

Then type Ctrl + X to exit nano.

Finally, type
```
cat hello.txt
```
to confirm that there are now contents in hello.txt.

"nano is a command line text editor. It works the same way as a desktop text editor like TextEdit or Notepad, except that it is accessible from the command line and only accepts keyboard input."

Let’s walk through what we did in the previous exercise:
* The command nano hello.txt opens a new text file named hello.txt in the nano text editor.

* "Hello, I am nano" is a text string entered in nano at the line indicated by the cursor.

* The menu of keyboard commands at the bottom of the window allow us to save changes to hello.txt and exit nano. The ^ stands for the Ctrl key.

Outside of nano, you can also use clear to clear the text in the current terminal window, moving the command prompt to the top of the screen. This is useful for when you want to make the terminal more readable after many commands.
### BASH Profile
A bash profile is a file used to store environment settings for your terminal, and it’s accessible by the name ~/.bash_profile.

When a session starts, it loads the contents of the bash profile before executing commands.

The ~ represents the user’s home directory.
The . indicates a hidden file.
The name ~/.bash_profile is important, since this is how the command line recognizes the bash profile.
To open and edit bash you can use the following commands:
```
nano ~/.bash_profile
```
When you edit the bash profile, you can add commands to execute every time a new terminal session is started.

For example, if you have an echo statement in the bash profile, that will echo when a terminal session begins.

To activate the changes made in ~/.bash_profile for the current session, use this following command:
```
source ~/.bash_profile
```
This makes the changes in the bash profile available right away without closing the terminal and needing to start a new session.
* Let’s edit the environment settings! In the terminal, type
```
nano ~/.bash_profile 
```
This opens up the existing, currently blank bash profile file in nano.
* In ~/.bash_profile, at the top of the file, type:
```
echo "Welcome, Jane Doe" 
```
You can use your name in place of “Jane Doe.”

* Type Ctrl + O to save the file.

* Press Enter to write the filename.

* Type Ctrl + X to exit nano.

Then, once you’ve exited nano and are back in the terminal, press the Enter (or return for Mac) key onto a new line.
* Finally, to see this greeting immediately, use:
```
source ~/.bash_profile 
```
### ALIAS
As we mentioned in the last exercise, you can add settings and commands that execute every time a new terminal session is started. One type of setting you can create is called an alias:
```
alias pd="pwd"
```
The alias command allows you to create keyboard shortcuts, or aliases, for commonly used commands.

Here, alias pd="pwd" creates the alias pd for the pwd command, which is then saved in the bash profile.

The pd alias will be available each time we open a new terminal session, and the output of pd will be the same as the pwd command.
* Let’s continue configuring the environment by adding command aliases.

Open ~/.bash_profile in nano.
```
nano ~/.bash_profile
```
* In ~/.bash_profile, on a new line, type:
```
alias pd="pwd"
```
Save the changes and exit out of nano.

Once you’ve exited nano and are back in the terminal, press the Enter key onto a new line.

* To make the alias in the current terminal sessions, type
```
source ~/.bash_profile
```
* Let’s try out the alias. Type:
```
pd
```
You should see the same output as you would by typing the pwd command.
