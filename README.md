# Linux Command Line Cheatsheet
Basic Linux Commands.

A curated list of commonly used linux commands, easily accessible in one location. I have used linux fairly often and am pretty comfortable using most of these commands. However I sometimes forget syntax/options for a particular command, and need to look it up. While most guides I've found under [resources](#resources) provide a lot of great information, the guides always seemed random in nature. I created this guide to attempt to help make some commands easier to read and find, and how they are commonly used (or at least how I've commonly used them). 

**_This is not the end all - be all guide for linux commands. Just some basic/advanced commands, with some options for how to commonly use them._**

---

## Table of Contents

- [File and Directory Commands](#file-and-directory-commands)
  - [File Administration](#file-Administration)
  - [File Systems](#file-systems)
- [System Commands](#system-commands)
  - [System](#system)
  - [Root Privilege](#root-privilege)
  - [Networking](#networking)
  - [Random](#random)
- [Resources](#resources)
  
---

## File & Directory Commands
**_Some commands for file and directory administration in Linux_**


### File Administration

| Basic Commands | Description | Man Page |
| --- | --- | --- |
| **`cat`** | Displays contents of a file. | [Link](http://man7.org/linux/man-pages/man1/cat.1.html) |
| **`less`** | | [Link]() |
| **`touch`** | Creates empty file. | [Link](http://man7.org/linux/man-pages/man1/touch.1.html) |
| **`file`** | Determines and prints out file type | [Link](http://man7.org/linux/man-pages/man1/file.1.html) |
| **`cp`** | Copy files through command line. Can also copy full directories. | [Link](http://man7.org/linux/man-pages/man1/cp.1.html) |
| **`mv`** | Moves file to a different location. Also used for renaming files. | [Link](http://man7.org/linux/man-pages/man1/mv.1.html) |
| **`rm`** | Removes file. Can also be used to remove entire directories. | [Link](http://man7.org/linux/man-pages/man1/rm.1.html) |
| **`echo`** | | [Link]() |
| **`nano`** & **`vi`** | Text editors built into linux command line. | none |

| Advanced Commands | Description | Man Page |
| --- | --- | --- |
| **`ln`** | | [Link]() |
| **`chmod`** | | [Link]() |
| **`chown`** | | [Link]() |
| **`gzip`** | | [Link]() |
| **`tar`** | | [Link]() |
| **`zip`** | | [Link]() |
| **`unzip`** | | [Link]() |
| **`diff`** | | [Link]() |


#### Examples

| Command | Common Options |
| --- | --- |
| **`cat`** | Commonly used without any options |
```bash
cat secrets.txt               #prints contents of secrets.txt
```

| Command | Common Options |
| --- | --- |
| **`less`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`touch`** | Commonly used without any options |
```bash
touch new_screts.txt          #creates empty txt file called new_secrets.txt
```

| Command | Common Options |
| --- | --- |
| **`file`** | Commonly used without any options |
```bash
file screts.txt               #prints out the file type of secrets.txt
```

| Command | Common Options |
| --- | --- |
| **`cp`** | -r   Copies directories recursively<br>-T   Treat destination as normal file | 
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
| **`rm`** | -r  Removes directories and their contents recursively <br>-f  Force removes file |
```bash
rm secrets.txt                        #deletes the file secrets.txt
rm -r /root/newdir                    #deletes the directory /root/newdir and all its contents
rm -rf /root/newdir                   #force removes the entire directory /root/newdir
```

| Command | Common Options |
| --- | --- |
| **`echo`** |  |
```bash

```

**`nano`** & **`vi`**
```bash
nano                          #opens nano editor
vi                            #opens vi editor
nano secrets.txt              #opens nano editor for file name secrets.txt
```

| Command | Common Options |
| --- | --- |
| **`ln`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`chmod`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`chown`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`gzip`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`tar`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`zip`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`unzip`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`diff`** |  |
```bash

```

---

### File Systems 

| Basic Commands | Description | Man Page |
| --- | --- | --- |
| **`pwd`** | Displays current working directory. | [Link](http://man7.org/linux/man-pages/man1/pwd.1.html) |
| **`cd`** | Traverse to specific directory. | none |
| **`ls`** | Prints directories and files in a directory. | [Link](http://man7.org/linux/man-pages/man1/ls.1.html) |
| **`lsof`** | | [Link]() |
| **`mkdir`** | Creates directory. | [Link](http://man7.org/linux/man-pages/man1/mkdir.1.html) |
| **`rmdir`** | Removes empty directory. | [Link](http://man7.org/linux/man-pages/man1/rmdir.1.html) |
| **`locate`** | Locates file on system based on the file name database. Will need to use **`updatedb`** if file was created after last database update. | [Link](http://man7.org/linux/man-pages/man1/locate.1.html) |
| **`updatedb`** | Command for updating file name database. | [Link](http://man7.org/linux/man-pages/man1/updatedb.1.html) |

| Advanced Commands | Description | Man Page |
| --- | --- | --- |
| **`find`** | | [Link]() |
| **`grep`** | | [Link]() |
| **`mount`** | | [Link]() |
| **`umount`** | | [Link]() |

#### Examples

| Command | Common Options |
| --- | --- |
| **`pwd`** | |
```bash
pwd               #displays current directory
```

| Command | Common Options |
| --- | --- |
| **`cd`** | |
```bash
cd /root/Desktop  #go to Desktop folder under root
cd ..             #take a step up the directory tree, would return to /root/
cd                #return to home directory no matter where location, returns to /root/ in this case
```

| Command | Common Options |
| --- | --- |
| **`ls`** | |
```bash
ls                      #prints directories/files listed under current directory
ls -l                   #prints current directories/files with permissions
ls -a                   #prints current d/f plus hidden files
ls /root/Desktop        #prints d/f under /root/Desktop
ls -r /root/Desktop     #prints /root/Desktop and recursively prints all directories under /root/Desktop
```

| Command | Common Options |
| --- | --- |
| **`lsof`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`mkdir`** | |
```bash
mkdir folder1                 #creates directory named 'folder1' under current directory
mkdir /root/Desktop/folder1   #creates directory named 'folder1' under /root/Desktop
```

| Command | Common Options |
| --- | --- |
| **`rmdir`** | |
```bash
rmdir folder1                 #removes empty directory 'folder1' in current directory
rmdir /root/Desktop/folder1   #removes empty directory 'folder1' under /root/Desktop
```

| Command | Common Options |
| --- | --- |
| **`locate`** | -i   Ignores case <br> |
```bash
locate secrets.txt            #will search file name database for files with secrets.txt in name
locate -i screts.txt          #will search file name database for any file, regardless of case, with secrets.txt in name
```

| Command | Common Options |
| --- | --- |
| **`updatedb`** | Commonly used without any options |
```bash
updatedb                      #updates file name database for locate
```

| Command | Common Options |
| --- | --- |
| **`find`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`grep`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`mount`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`umount`** |  |
```bash

```

---

## System Commands
**_Some commands used for system and network information._**

### System

| Basic Commands | Description | Man Page |
| --- | --- | --- |
| **`uname`** | | [Link]() |
| **`hostname`** | | [Link]() |
| **`users`** | | [Link]() |
| **`who`** | | [Link]() |
| **`whoami`** | | [Link]() |
| **`date`** | | [Link]() |
| **`uptime`** | | [Link]() |
| **`passwd`** | | [Link]() |
| **`apt-get`** | | [Link]() |
| **`halt`** | | [Link]() |
| **`reboot`** | | [Link]() |

| Advanced Commands | Description | Man Page |
| --- | --- | --- |
| **`top`** | | [Link]() |
| **`last`** | | [Link]() |
| **`ps`** | | [Link]() |
| **`df`** | | [Link]() |
| **`du`** | | [Link]() |
| **`free`** | | [Link]() |
| **`crontab`** | | [Link]() |
| **`service`** | | [Link]() |
| **`kill`** | | [Link]() |
| **`killall`** | | [Link]() |

#### Examples

| Command | Common Options |
| --- | --- |
| **`uname`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`hostname`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`users`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`who`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`whoami`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`date`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`uptime`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`passwd`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`apt-get`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`halt`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`reboot`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`top`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`last`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`ps`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`df`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`du`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`free`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`crontab`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`service`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`kill`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`killall`** |  |
```bash

```

---

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

---

### Networking

| Basic Commands | Description | Man Page |
| --- | --- | --- |
| **`ping`** | | [Link]() |
| **`ifconfig`** | | [Link]() |
| **`host`** | | [Link]() |
| **`arp`** | | [Link]() |
| **`dig`** | | [Link]() |
| **`route`** | | [Link]() |
| **`nslookup`** | | [Link]() |
| **`netstat`** | | [Link]() |

| Advanced Commands | Description | Man Page |
| --- | --- | --- |
| **`scp`** | | [Link]() |
| **`ftp`** | | [Link]() |
| **`sftp`** | | [Link]() |
| **`ssh`** | | [Link]() |
| **`nmap`** | | [Link]() |
| **`tcpdump`** | | [Link]() |
| **`telnet`** | | [Link]() |
| **`whois`** | | [Link]() |
| **`traceroute`** | | [Link]() |
| **`tracepath`** | | [Link]() |
| **`ifup`** | | [Link]() |
| **`ifdown`** | | [Link]() |
| **`dhclient`** | | [Link]() |

#### Examples

| Command | Common Options |
| --- | --- |
| **`ping`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`ifconfig`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`host`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`arp`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`dig`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`route`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`nslookup`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`netstat`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`scp`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`ftp`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`sftp`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`ssh`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`nmap`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`tcpdump`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`telnet`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`whois`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`traceroute`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`tracepath`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`ifup`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`ifdown`** |  |
```bash

```

| Command | Common Options |
| --- | --- |
| **`dhclient`** |  |
```bash

```

---

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

---

## Resources

**A great guide [here](https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/) for more advanced linux commands. This guide is written for linux privilege escalation, but shows many different techiniques and commands that can be used to help gather more information on a linux system.**

**Another great guide [here](https://maker.pro/linux/tutorial/basic-linux-commands-for-beginners) for basic commands.**

**Man pages found [here](http://man7.org/linux/man-pages/dir_all_by_section.html#man1)**
