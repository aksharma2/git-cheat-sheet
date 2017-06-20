# Git Cheat Sheet

## Commands

### Identifying differences

Unstaged differences:

`git diff`

Staged differences:

`git diff --staged`

Differences between two specific versions:

`git diff versionA versionB`

Differences in a range of versions:

`git diff version1..version2`

`git diff branchA..branchB`

Only show affected files:

`git diff --name-only version1..version2`

### Viewing history

View all changes to a specific file:

`git log -p filename`

Using `-p` generates a patch of the differences. Removing this will show the commit messages:

`git log -p --follow filename`

`--follow` will show changes to a file across renames

$ touch <file>: the touch command lets you create a new file in the current working directory. For example, touch example.txt will create the example.txt file.

$ mkdir <directory>: make directory. This command will create a new directory. Fox example, $ mkdir NewFolder creates NewFolder in your current working directory.

$ mv <file or directory> <new directory>: mv stands for move. This command will move the specified file or directory to a new directory. Same as dragging your files around with the mouse. mv example.txt SubDirectory will move the example.txt inside the directory SubDirectory.

    You can also use this command to rename files like so mv example.txt stillExample.txt. example.txt will be renamed to stillExample.txt.

$ cp <file or directory> <new directory>: cp stands for copy. This is the equivalent of copy and paste a file or directory to a new directory, keeping the original untouched.
f you enter man vim, you will see the manual for vim. vim stands for

    vim - Vi IMproved, a programmers text editor

$ vim <file>: this will open the file. Use the up and down arrow to scroll. When you want to exit the file, press esc and type :q then press enter.

First, $ cd to your "List" folder. Check that you have "myDiary.txt" by entering $ ls. If not, go ahead and create it. Then, open the file by entering $ vim myDiary.txt, and you will see the following.

Vim has opened "myDiary.txt" and is displaying the content, which is currently empty. You should see:

    A blinking cursor on the first line.
    At the bottom, you see "myDiary.txt" 0L, 0C, which is the file name, the number of lines and the number of characters in this file.
    The ~ along the left hand side simply means it's an empty line. To start editing the file, press a or ion your keyboard, and you will see the bottom line change to -- INSERT --.

Type in "Today, I learned how to use the command line, I feel awesome.".

Now is the trickier part. After you have done typing, press esc to escape, so you can give command to vim instead of editing the file. The -- INSERT -- should disappear by now.
To save your edits on the file, type in :wq and press enter. Vim will exit, and you should be back in the "List" directory.

    What does :wq mean? w stands for write (save), q stands for quit. wq means to save and quit.

Open up our diary file again $ vim myDiary.txt and see if our changes have been made successfully.
If your terminal looks the same as mine, your edit was saved. "myDiary.txt" currently has 1 Line and 62 Characters in total.

To edit again, press a.To go to the next line, press enter while in -- INSERT -- mode.

When you are done, press esc, type in :wq and press enter. Well done, now you know how to use vim to edit text files inside the Terminal. To make sure you understood everything, do the following exercise.


$ rm <file or directory>: rm stands for remove. This lets you remove (delete) a file or a directory. To delete a file simply type rm example.txt. To delete a folder, you need to add the -r option, like rm -r OldFolder, to remove all the files and directories contained inside the target directory.

View all files under source control:

`git ls-files`

### Branching

Remove local pointers to remote branches which no longer exist:

`git remote prune origin`

Get all branches which have been merged into a named branch:

`git branch --merged branchname`

Or all branches _not_ merged:

`git branch --no-merged branchname`

## Configuration

### Useful aliases

    alias.co=checkout
    alias.ci=commit
    alias.st=status
    alias.br=branch
    alias.hist=log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short
    alias.unstage=reset HEAD --

### Configuring P4Merge

`git config --global merge.tool p4merge`

`git config --global mergetool.p4merge.cmd 'p4merge $BASE $LOCAL $REMOTE $MERGED'`

Key/Command	Description


```
cd	Home directory

cd [folder]	Change directory

cd ~	Home directory, e.g. ‘cd ~/folder/’

cd /	Root of drive

ls	Short listing

ls -l	Long listing

ls -a	Listing incl. hidden files

ls -lla	Listing files with rwx (read, write, execute) information

ls -lh	Long listing with Human readable file sizes

ls -R	Entire content of folder recursively

sudo [command]	Run command with the security privileges of the superuser (Super User DO)

open [file]	Opens a file ( as if you double clicked it )

top	Displays active processes. Press q to quit

nano [file]	Opens the [file] with nano text editor

pico [file]	Opens the [file] with pic text editor

q	Exit

clear	Clear screen
```



Command History


Key/Command	Description



history n	Shows the stuff typed – add a number to limit the last n items

ctrl-r	Interactively search through previously typed commands

![value]	Execute the last command typed that starts with ‘value’

!!	Execute the last command typed



File Management


Key/Command	Description


```
touch [file]	Create new file

pwd	Full path to working directory

..	Parent/enclosing directory, e.g.

ls -l ..	Long listing of parent directory

cd ../../	Move 2 levels up

.	Current folder

cat	Concatenate to screen

rm [file]	Remove a file, e.g. rm [file] [file]

rm -i [file]	Remove with confirmation

rm -r [dir]	Remove a directory and contents

rm -f [file]	Force removal without confirmation

rm -i [file]	Will display prompt before

cp [file] [newfile]	Copy file to file

cp [file] [dir]	Copy file to directory

mv [file] [new filename]	Move/Rename, e.g. mv -v [file] [dir]
```



Directory Management


Key/Command	Description


```
mkdir [dir]	Create new directory

mkdir -p [dir]/[dir]	Create nested directories

rmdir [dir]	Remove directory ( only operates on empty directories )

rm -R [dir]	Remove directory and contents
```


Help


Key/Command	Description


```
[command] -h	Offers help

[command] —help	Offers help

[command] help	Offers help

reset	Resets the terminal display

man [command]	Show the help for ‘command’

whatis [command]	Gives a one-line description of ‘command’
```


iTerm 2 Shortcuts


Key/Command	Description


```
Cmd + T	Opens a new terminal tab

Cmd + C	Copy text in terminal

Cmd + V	Paste text in terminal

Cmd + D	Create sub-window horizontally

Cmd + Shift + D	Create sub-window vertically

Ctrl + A	Go to the beginning of the line you are currently typing on

Ctrl + E	Go to the end of the line you are currently typing on

Ctrl + L	Clears the Screen

Command + K	Clears the Screen

Ctrl + U	Clears the line before the cursor position. If you are at the end of the line, clears the entire line.

Ctrl + H	Same as backspace

Ctrl + R	Lets you search through previously used commands

Ctrl + C	Kill whatever you are running

Ctrl + D	Exit the current shell

Ctrl + Z	Puts whatever you are running into a suspended background process. fg restores it.

Ctrl + W	Delete the word before the cursor

Ctrl + K or R	Clear the line after the cursor

Ctrl + T	Swap the last two characters before the cursor

Esc + T	Swap the last two words before the cursor

Alt + F	Move cursor forward one word on the current line

Alt + B	Move cursor backward one word on the current line

Tab	Auto-complete files and folder names
```
