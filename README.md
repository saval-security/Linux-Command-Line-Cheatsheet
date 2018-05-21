# Linux Commands
A small repository for some Linux Commands.

A curated list of linux commands commonly used, easily accessible in one location.

## Table of Contents

- [Basic Commands](#basic-commands)
  - [Directory Commands and Traversal](#directory-commands-and-traversal)
  - [File Manipulation](#file-manipulation)
  - [Root Privilege](#root-privilege)
  - [System](#system)
  - [Networking](#networking)
  - [Random](#random)
- [References](#references)
  

## Basic Commands
**_Some basic commands in Linux_**

### Directory Commands and Traversal 

| Command | Description |
| --- | --- |
| **`pwd`** | Displays current directory |
| **`cd`** | Traverse to specific directory |
| **`ls`** | Prints directories and files in a directory |
| **`mkdir`** | Creates directory |
| **`rmdir`** | Removes empty directory |

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
ls                #prints directories/files listed under current directory
ls -l             #prints current directories/files with permissions
ls -a             #prints current d/f plus hidden files
ls /root/Desktop  #prints d/f under /root/Desktop
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

### File Manipulation

**`nano`** and **`vi`** Text editors built into Linux command line
```bash
nano                          #opens nano editor
vi                            #opens vi editor
nano secrets.txt              #opens nano editor for file name secrets.txt
```

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

### System


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


## References

**A great guide [here](https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/) for more advanced linux commands.**
**Another great guide [here](https://maker.pro/linux/tutorial/basic-linux-commands-for-beginners) for basic commands.**
