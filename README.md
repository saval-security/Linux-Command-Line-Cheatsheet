# Linux Command Line Cheatsheet
Basic Linux Commands.

A curated list of commonly used linux commands, easily accessible in one location. I have used linux fairly often and am pretty comfortable using most of these commands. However I sometimes forget syntax/options for a particular command, and need to look it up. While most guides I've found under [resources](#resources) provide a lot of great information, the guides always seemed random in nature. I created this guide to attempt to help make some commands easier to read and find, and how they are commonly used (or at least how I've commonly used them). 

## Table of Contents

- [File and Directory Commands](#file-and-directory-commands)
  - [File Manipulation](#file-manipulation)
  - [Directory Commands and Traversal](#directory-commands-and-traversal)
- [System Commands](#system-commands)
  - [System](#system)
  - [Root Privilege](#root-privilege)
  - [Networking](#networking)
  - [Random](#random)
- [Resources](#resources)
  

## File and Directory Commands
**_Some commands for file and directory administration in Linux_**

### File Manipulation

| Command | Description | Man Page |
| --- | --- | --- |
| **`cat`** | Displays contents of a file | [Link](http://man7.org/linux/man-pages/man1/cat.1.html) |
| **`touch`** | Creates empty file | [Link](http://man7.org/linux/man-pages/man1/touch.1.html) |
| **`cp`** | Copy files through command line. Can also copy full directories | [Link](http://man7.org/linux/man-pages/man1/cp.1.html) |
| **`mv`** | Moves file to a different location. Also used for renaming files. | [Link](http://man7.org/linux/man-pages/man1/mv.1.html) |
| **`rm`** | Removes file. Can also be used to remove entire directories. | [Link](http://man7.org/linux/man-pages/man1/rm.1.html) |
| **`locate`** | Locates file on system based on a database. Will need to use **`updatedb`** if file was created after last database update | [Link](http://man7.org/linux/man-pages/man1/locate.1.html) |
| **`nano`** & **`vi`** | Text editors built into linux command line | none |

#### Examples

| Command | Common Options |
| --- | --- |
| **`cat`** | Commonly used without any options |
```bash
cat secrets.txt               #prints contents of secrets.txt
```

| Command | Common Options |
| --- | --- |
| **`touch`** | Commonly used without any options |
```bash
touch new_screts.txt          #creates empty txt file called new_secrets.txt
```

| Command | Common Options |
| --- | --- |
| **`cp`** | -r  Copies directories recursively<br>-T  Treat destination as normal file | 
```bash
#first argument is the file being copied, second argument is where to copy the file
cp secrets.txt secrets2.txt           #creates a copy of secrets.txt, named secrets2.txt, in current working directory
cp secrets.txt /root/Desktop          #copies secrets.txt to /root/Desktop
cp secrets.txt -T secret              #copies secrets.txt to a new file named secret
cp -r /root/Documents /root/newdir    #recursively copies entire /root/Documents directory to a new directory call newdir located under /root
```

| Command | Common Options |
| --- | --- |
| **`mv`** | Commonly used without any options |
```bash
mv secrets.txt old_secrets.txt        #renames secrets.txt to old_secrets.txt
mv secrets.txt /root/Desktop          #moves secrets.txt to /root/Desktop directory
```

| Command | Common Options |
| --- | --- |
| **`rm`** | -r  Removes directories and their contents recursively<br>-f  Force removes file |
```bash
rm secrets.txt                        #deletes the file secrets.txt
rm -r /root/newdir                    #deletes the directory /root/newdir and all its contents
rm -rf /root/newdir                   #force removes the entire directory /root/newdir
```

**`nano`** & **`vi`**
```bash
nano                          #opens nano editor
vi                            #opens vi editor
nano secrets.txt              #opens nano editor for file name secrets.txt
```

### Directory Commands and Traversal 

| Command | Description | Man Page |
| --- | --- | --- |
| **`pwd`** | Displays current working directory | [Link](http://man7.org/linux/man-pages/man1/pwd.1.html) |
| **`cd`** | Traverse to specific directory | none |
| **`ls`** | Prints directories and files in a directory | [Link](http://man7.org/linux/man-pages/man1/ls.1.html) |
| **`mkdir`** | Creates directory | [Link](http://man7.org/linux/man-pages/man1/mkdir.1.html) |
| **`rmdir`** | Removes empty directory | [Link](http://man7.org/linux/man-pages/man1/rmdir.1.html) |

#### Examples

**`pwd`**
```bash
pwd               #displays current directory
```

**`cd`**
```bash
cd /root/Desktop  #go to Desktop folder under root
cd ..             #take a step up the directory tree, would return to /root/
cd                #return to home directory no matter where location, returns to /root/ in this case
```

**`ls`** 
```bash
ls                      #prints directories/files listed under current directory
ls -l                   #prints current directories/files with permissions
ls -a                   #prints current d/f plus hidden files
ls /root/Desktop        #prints d/f under /root/Desktop
ls -r /root/Desktop     #prints /root/Desktop and recursively prints all directories under /root/Desktop
```

**`mkdir`**
```bash
mkdir folder1                 #creates directory named 'folder1' under current directory
mkdir /root/Desktop/folder1   #creates directory named 'folder1' under /root/Desktop
```

**`rmdir`**
```bash
rmdir folder1                 #removes empty directory 'folder1' in current directory
rmdir /root/Desktop/folder1   #removes empty directory 'folder1' under /root/Desktop
```

## System Commands
**_Some commands used for system and network information._**

### System


### Root Privilege

**`sudo`** Using sudo before another command will run it with root privilege. Will need to enter root password after running command.
```bash
sudo apt-get update           #updating system with root permission
```

**`su`** Upgrades privilege to root. Root password will need to be set to use and will need to enter root password to be able to elevate.
```bash
su                            #elevate access to root
sudo passwd                   #set new root password
```

### Networking


### Random

_Random commands_

**`clear`** Clears the terminal
```bash
clear         #clears the terminal
```

**`exit`** Exits the current terminal windows
```bash
exit          #exits terminal window
```

_Other_

Using **`Ctrl+C`** will safely stop current execution

Using **`Ctrl+Z`** will force stop current execution


## Resources

**A great guide [here](https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/) for more advanced linux commands. This guide is written for linux privilege escalation, but shows many different techiniques and commands that can be used to help gather more information on a linux system.**

**Another great guide [here](https://maker.pro/linux/tutorial/basic-linux-commands-for-beginners) for basic commands.**

**Man pages found [here](http://man7.org/linux/man-pages/dir_all_by_section.html#man1)**
