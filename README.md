# Linux Command Line Cheatsheet
Basic Linux Commands.

A curated list of commonly used linux commands, easily accessible in one location. I have used linux fairly often and am pretty comfortable using most of these commands. However I sometimes forget syntax/options for a particular command, and need to look it up. While most guides I've found under [resources](#resources) provide a lot of great information, the guides always seemed random in nature. I created this guide to attempt to help make some commands easier to read and find, and how they are commonly used (or at least how I've commonly used them). 

**_This is not the end all - be all guide for linux commands. Just some basic/intermediate commands, with some options for how to commonly use them._**

---

## Table of Contents

- [File and Directory Commands](#file-and-directory-commands)
  - [File Administration](#file-administration)
    - [Basic Commands](#fa-basic)
    - [Intermediate Commands](#fa-inter)
    - [Examples](#fa-ex) 
  - [File Systems](#file-systems)
    - [Basic Commands](#fs-basic)
    - [Intermediate Commands](#fs-inter)
    - [Examples](#fs-ex)
- [System Commands](#system-commands)
  - [System Information and Process Commands](#system-information-and-process-commands)
    - [Basic Commands](#s-basic)
    - [Intermediate Commands](#s-inter)
    - [Examples](#s-ex)
  - [Networking](#networking)
    - [Basic Commands](#net-basic)
    - [Intermediate Commands](#net-inter)
    - [Examples](#net-ex)
- [Other](#other)
  - [Random](#random)
  - [Shortcuts](#shortcuts)
- [All Commands in Alphabetical Order](all-commands-in-alphabetical-order)
- [Resources](#resources)
  
---

## File and Directory Commands
**_Some commands for file and directory administration in Linux_**


### File Administration

<a id="fa-basic"></a>

| Basic Commands | Description | Man Page | Example |
| --- | --- | --- | --- |
| **`cat`** | Displays contents of a file. | [Link](http://man7.org/linux/man-pages/man1/cat.1.html) | [Jump to Example](#cat-anc) |
| **`less`** | Used to browse contents of a file. | [Link](http://man7.org/linux/man-pages/man1/less.1.html) | [Jump to Example](#less-anc) |
| **`touch`** | Creates empty file. | [Link](http://man7.org/linux/man-pages/man1/touch.1.html) | [Jump to Example](#touch-anc) |
| **`file`** | Determines and prints out file type | [Link](http://man7.org/linux/man-pages/man1/file.1.html) | [Jump to Example](#file-anc) |
| **`cp`** | Copy files through command line. Can also copy full directories. | [Link](http://man7.org/linux/man-pages/man1/cp.1.html) | [Jump to Example](#cp-anc) |
| **`mv`** | Moves file to a different location. Also used for renaming files. | [Link](http://man7.org/linux/man-pages/man1/mv.1.html) | [Jump to Example](#mv-anc) |
| **`rm`** | Removes file. Can also be used to remove entire directories. | [Link](http://man7.org/linux/man-pages/man1/rm.1.html) | [Jump to Example](#rm-anc) |
| **`echo`** | Dsiplays a line of text. Typically used to add text to a file. | [Link](http://man7.org/linux/man-pages/man1/echo.1.html) | [Jump to Example](#echo-anc) |
| **`nano`** & **`vi`** | Text editors built into linux command line. | none | [Jump to Example](#nano-anc) |

<a id="fa-inter"></a>

| Intermediate Commands | Description | Man Page | Example |
| --- | --- | --- | --- |
| **`ln`** | Creates links between files. Hard links refer to the target file linking to the data on the disk of the source file. Soft links refer to the target file linking to the source file, which then links to the data on the disk. Hard link = Tfile -> data <- Sfile. Soft link = Tfile -> Sfile -> data. | [Link](http://man7.org/linux/man-pages/man1/ln.1.html) | [Jump to Example](#ln-anc) |
| **`chmod`** | Changes file mode bits to allow for setting file permissions. Permissions for the three roles, user (u), group (g), and other(o), are set by using three letter, read (r), write (w), and execute (x). Octal permission notation can also be used, with 4 standing for read, 2 standing for write, and 1 standing for execute. So 754 would mean user can rwx, group can rx, and other can r. Usually need to use `sudo` before the command. | [Link](http://man7.org/linux/man-pages/man1/chmod.1.html) | [Jump to Example](#chmod-anc) |
| **`chown`** | Change file owner and group. Usually need to run with `sudo`. | [Link](http://man7.org/linux/man-pages/man1/chown.1.html) | [Jump to Example](#chown-anc) |
| **`gzip`** | Compresses contents of files, or expands compressed files. If wanting to compress multiple files into one compressed directory, use tar. | [Link](https://www.systutorials.com/docs/linux/man/1-gzip/) | [Jump to Example](#gzip-anc) |
| **`tar`** | Archives file(s) (Compression is optional). Can also extract tar files. | [Link](http://man7.org/linux/man-pages/man1/tar.1.html) | [Jump to Example](#tar-anc) |
| **`zip`** | Package and compress (archive) files. | [Link](https://www.systutorials.com/docs/linux/man/1-zip/) | [Jump to Example](#zip-anc) |
| **`unzip`** | Extracts compressed files in a ZIP archive. | [Link](https://www.systutorials.com/docs/linux/man/1-unzip/) | [Jump to Example](#unzip-anc) |

<a id="fa-ex"></a>

#### Examples 

|<a id="cat-anc"></a> Command | Common Options |
| --- | --- |
| **`cat filename`** | Commonly used without any options |
```bash
cat secrets.txt               #prints contents of secrets.txt
```

|<a id="less-anc"></a> Command | Common Options |
| --- | --- |
| **`less filename`** | Commonly used without any options  |
```bash
less secrets.txt              #Displays contents of secrets.txt. Good to use for bigger files for easier navigation of content
```

|<a id="touch-anc"></a> Command | Common Options |
| --- | --- |
| **`touch filename`** | Commonly used without any options |
```bash
touch new_screts.txt          #creates empty txt file called new_secrets.txt
```

|<a id="file-anc"></a> Command | Common Options |
| --- | --- |
| **`file filename`** | Commonly used without any options |
```bash
file secrets.txt               #prints out the file type of secrets.txt
```

|<a id="cp-anc"></a> Command | Common Options |
| --- | --- |
| **`cp [option(s)] sourcefile targetfile`** | -r   Copies directories recursively<br>-T   Treat destination as normal file | 
```bash
#first argument is the file being copied, second argument is where to copy the file
cp secrets.txt secrets2.txt           #creates a copy of secrets.txt, named secrets2.txt, in current working directory
cp secrets.txt /root/Desktop          #copies secrets.txt to /root/Desktop
cp secrets.txt -T secret              #copies secrets.txt to a new file named secret
cp -r /root/Documents /root/newdir    #recursively copies entire /root/Documents directory to a new directory call newdir located under /root
```

|<a id="mv-anc"></a> Command | Common Options |
| --- | --- |
| **`mv sourcefile targetfile`** | Commonly used without any options |
```bash
mv secrets.txt old_secrets.txt        #renames secrets.txt to old_secrets.txt
mv secrets.txt /root/Desktop          #moves secrets.txt to /root/Desktop directory
```

|<a id="rm-anc"></a> Command | Common Options |
| --- | --- |
| **`rm [options(s)] filename`** | -r  Removes directories and their contents recursively <br>-f  Force removes file |
```bash
rm secrets.txt                        #deletes the file secrets.txt
rm -r /root/newdir                    #deletes the directory /root/newdir and all its contents
rm -rf /root/newdir                   #force removes the entire directory /root/newdir
```

|<a id="echo-anc"></a> Command | Common Options |
| --- | --- |
| **`echo [text] [>> filename]`** | Commonly add `>> filename` after text to append to the end of the file. |
```bash
echo Display this text                        #Writes contents "Display this text" to console
echo Add this text to file >> secrets.txt     #Appends contents "Add this text to file" to the end of the file secrets.txt. Will create and add to the file if file doesn't exist.
```
|<a id="nano-anc"></a> Command |
| --- |
| **`nano`** & **`vi`** |
```bash
nano                          #opens nano editor
vi                            #opens vi editor
nano secrets.txt              #opens nano editor for file name secrets.txt
```

|<a id="ln-anc"></a> Command | Common Options |
| --- | --- |
| **`ln [option(s)] sourcefile targetfile`** | -s   Creates a symbolic link, enabling linking across file systems/partitions. Also allows linking of directories. |
```bash
ln secrets.txt linked_secrets.txt                   #creates a hard link for secrets.txt called linked_secrets.txt
ln -s /root/Desktop/script.sh /bin/scriptcommand    #creates a soft link between script.sh located in /root/Desktop/ directory and scriptcommand located in /bin/ directory.
                                                    #This allows scriptcommand to be called from anywhere in the file system, since /bin/ is located in everyone's PATH..
```

|<a id="chmod-anc"></a> Command | Common Options |
| --- | --- |
| **`chmod [option(s)] [permissions] filename`** | -R   Changes permissions recursively for all files and directories. |
```bash
#Roles: Users = u, Group = g, Other = o
#Permissions: Read = r,4; Write = w,2; Execute = x,1
chmod +x secret.sh                                #gives execute permission to all roles for the file secret.sh
chmod u+rx,g+r secret.sh                          #gives read and execute permission to user, and read permission to group for the file secret.sh
chmod u-x secret.sh                               #removes execute permission for user for the file secret.sh
chmod 755 secret.sh                               #gives rwx permission to user, rw permission to group, and rw permission to other for the file secret.sh
chmod -R 744 /root/Desktop/secrets_directory      #recursively gives the permissions rwx to user, r to group, and r to other for the entire directory /root/Desktop/secrets_directory
```

|<a id="chown-anc"></a> Command | Common Options |
| --- | --- |
| **`chown [option(s)] owner:group filename`** | -h   Forcefully changes owner:group for symbolic links.<br> -R   Recursively changes owner:group of all files in a directory. |
```bash
chown root secrets.txt                                        #changes owner to root for the file secrets.txt
chown :secretgroup secrets.txt                                #changes group to secretgroup for the file secrets.txt
chown root:secretgroup secrets.txt                            #changes owner to root and group to secretgroup for the file secrets/txt
chmod -h root:secretgroup symbolic_secrets.txt                #force change for symbolic links
chmod -R root:secretgroup /root/Desktop/secrets_directory     #recursively changes owner to root and group to secretgroup for all files in the directory /root/Desktop/secrets_directory
```

|<a id="gzip-anc"></a> Command | Common Options |
| --- | --- |
| **`gzip [options(s)] filename(s)`** | -d   Decompresses packed gzip files<br> -c   Keeps original file and creates a compressed copy. |
```bash
gzip secrets.txt                          #Will compress the file secrets.txt and create secrets.txt.gz. This will remove the original file.
gzip -c secrets.txt > secrets.txt.gz      #Will create a compressed copy of secrets.txt
gzip -d secrets.txt.gz                    #Will decompress secrets.txt.gz
```

|<a id="tar-anc"></a> Command | Common Options |
| --- | --- |
| **`tar [option(s)] file [other]`** | -c   Creates a new .tar archive file<br> -v    Verbose for .tar progress<br> -f    File name of archive file<br> -z    Create compress gzip archive file<br> -j    Highly compress tar file bz2<br> -x    Extract a tar fle<br> -C   Untar in different directory.<br> -t    Lists all contents in .tar archive<br> -r   Append file to the .tar archive. |
```bash
tar -cvf scrts.tar                            #creates tar archive file scrts.tar
tar -cvzf scrts.tar.gz                        #cretaes compressed tar archive file scrts.tar.gz
tar -cvfj scrts.tar.bz2                       #creates highly compress archive file scrts.tar.bz2
tar -xvf scrts.tar -C /root/Desktop           #extracts scrts.tar to the directory /root/Desktop. Also extracts .tar.gz and .tar.bz2 files.
tar -zxvf scrts.tar.gz                        #extracts and uncompresses scrts.tar.gz
tar -jxvf scrts.tar.bz2                       #extracts and uncompresses scrts.tar.bz2
tar -tvf scrts.tar                            #lists contents in scrts.tar. Also works for .tar.gz and .tar.bz2
tar -rvf scrts.tar moresecrets.txt            #adds the file moresecrets.txt to the tar archived file scrts.tar. Note, cannot append to tar.gz or tar.bz2 files.
```

|<a id="zip-anc"></a> Command | Common Options |
| --- | --- |
| **`zip [option(s)] zipfile file(s)`** |-r   Recursively compresses an entire direcory. |
```bash
zip secrets.zip secrets.txt                             #creates a compressed archive of secrets.txt called secrets.zip
zip -r secrets.zip /root/Desktop/secrets_directory      #recursively compresses the entire folder into secrets.zip
```

|<a id="unzip-anc"></a> Command | Common Options |
| --- | --- |
| **`unzip zipfile`** | Commonly used without options  |
```bash
unzip secrets.zip                               #extracts the files in secrets.zip
```

---

### File Systems 

<a id="fs-basic"></a>

| Basic Commands | Description | Man Page | Example |
| --- | --- | --- | --- |
| **`pwd`** | Displays current working directory. | [Link](http://man7.org/linux/man-pages/man1/pwd.1.html) | [Jump to Example](#pwd-anc) |
| **`cd`** | Traverse to specific directory. | none | [Jump to Example](#cd-anc) |
| **`ls`** | Prints directories and files in a directory. | [Link](http://man7.org/linux/man-pages/man1/ls.1.html) | [Jump to Example](#ls-anc) |
| **`lsof`** | Lists all open files. | [Link](http://man7.org/linux/man-pages/man8/lsof.8.html) | [Jump to Example](#lsof-anc) |
| **`mkdir`** | Creates directory. | [Link](http://man7.org/linux/man-pages/man1/mkdir.1.html) | [Jump to Example](#mkdir-anc) |
| **`rmdir`** | Removes empty directory. | [Link](http://man7.org/linux/man-pages/man1/rmdir.1.html) | [Jump to Example](#rmdir-anc) |
| **`locate`** | Locates file on system based on the file name database. Will need to use **`updatedb`** if file was created after last database update. | [Link](http://man7.org/linux/man-pages/man1/locate.1.html) | [Jump to Example](#locate-anc) |
| **`updatedb`** | Command for updating file name database. | [Link](http://man7.org/linux/man-pages/man1/updatedb.1.html) | [Jump to Example](#updatedb-anc) |

<a id="fs-inter"></a>

| Intermediate Commands | Description | Man Page | Example |
| --- | --- | --- | --- |
| **`find`** | Searches for files in a directory hierarchy. Find can be complex to use, as there are many different options/expressions one can use to find and/or manipulate files. Very useful command, there's plenty of additional guides online for how to use find if what's provide isn't enough. | [Link](http://man7.org/linux/man-pages/man1/find.1.html) | [Jump to Example](#find-anc) |
| **`grep`** | Prints lines matching a pattern. | [Link](http://man7.org/linux/man-pages/man1/grep.1.html) | [Jump to Example](#grep-anc) |
| **`mount`** | Mount filesystems. | [Link](http://man7.org/linux/man-pages/man2/mount.2.html) | [Jump to Example](#mount-anc) |
| **`umount`** | Unmount filesystems. | [Link](http://man7.org/linux/man-pages/man2/umount.2.html) | [Jump to Example](#umount-anc) |

<a id="fs-ex"></a>

#### Examples

|<a id="pwd-anc"></a> Command | Common Options |
| --- | --- |
| **`pwd`** | Command that doesn't use options. |
```bash
pwd               #displays current directory
```

|<a id="cd-anc"></a> Command | Common Options |
| --- | --- |
| **`cd [directory]`** | Commonly used without any options. |
```bash
cd /root/Desktop  #go to Desktop folder under root
cd ..             #take a step up the directory tree, would return to /root/
cd                #return to home directory no matter where location, returns to /root/ in this case
```

|<a id="ls-anc"></a> Command | Common Options |
| --- | --- |
| **`ls [option(s)] [directory]`** | -l   Prints directory with permissions.<br> -a    Prints directory including hidden files. |
```bash
ls                      #prints directories/files listed under current directory
ls -l                   #prints current directories/files with permissions
ls -a                   #prints current d/f plus hidden files
ls /root/Desktop        #prints d/f under /root/Desktop
ls -r /root/Desktop     #prints /root/Desktop and recursively prints all directories under /root/Desktop
```

|<a id="lsof-anc"></a> Command | Common Options |
| --- | --- |
| **`lsof`** | Commonly used without any options. (Note: can be used with options for various system relate tasks.) |
```bash
lsof                    #Prints list of all open files.
```

|<a id="mkdir-anc"></a> Command | Common Options |
| --- | --- |
| **`mkdir directoryname`** | Commonly used without any options. |
```bash
mkdir folder1                 #creates directory named 'folder1' under current directory
mkdir /root/Desktop/folder1   #creates directory named 'folder1' under /root/Desktop
```

|<a id="rmdir-anc"></a> Command | Common Options |
| --- | --- |
| **`rmdir directoryname`** | Commonly used without any options. |
```bash
#Note: only removes empty directories. Use 'rm' command for nonempty directories.
rmdir folder1                 #removes empty directory 'folder1' in current directory
rmdir /root/Desktop/folder1   #removes empty directory 'folder1' under /root/Desktop
```

|<a id="locate-anc"></a> Command | Common Options |
| --- | --- |
| **`locate [option(s)] searchname`** | -i   Ignores case <br> |
```bash
locate secrets.txt            #will search file name database for files with secrets.txt in name
locate -i secrets.txt         #will search file name database for any file, regardless of case, with secrets.txt in name
```

|<a id="updatedb-anc"></a> Command | Common Options |
| --- | --- |
| **`updatedb`** | Commonly used without any options |
```bash
updatedb                      #updates file name database for locate
```

|<a id="find-anc"></a> Command | Common Options |
| --- | --- |
| **`find [option(s)] search_directory -[expression_option] search_expression`** | -name    Expression for name of file.<br> -iname   Same as '-name' but case doesn't matter.<br>  |
```bash
#the '.' means current working directory and all subdirectories
find . -name secrets.txt                              #Will search through entire working directory and subdirectories for the file named secrets.txt

```

|<a id="grep-anc"></a> Command | Common Options |
| --- | --- |
| **`grep`** |  |
```bash

```

|<a id="mount-anc"></a> Command | Common Options |
| --- | --- |
| **`mount`** |  |
```bash

```

|<a id="umount-anc"></a> Command | Common Options |
| --- | --- |
| **`umount`** |  |
```bash

```

---

## System Commands
**_Some commands used for system and network information._**

### System Information and Process Commands

<a id="s-basic"></a>

| Basic Commands | Description | Man Page | Example |
| --- | --- | --- | --- |
| **`uname`** | Prints system information. | [Link](http://man7.org/linux/man-pages/man1/uname.1.html) | [Jump to Example](#uname-anc) |
| **`hostname`** | Prints system's hostname. | [Link](http://man7.org/linux/man-pages/man1/hostname.1.html) | [Jump to Example](#hostname-anc) |
| **`users`** | Prints all the usernames of users currently logged into host machine. | [Link](http://man7.org/linux/man-pages/man1/users.1.html) | [Jump to Example](#users-anc) |
| **`who`** | Displays who is logged in. | [Link](http://man7.org/linux/man-pages/man1/who.1.html) | [Jump to Example](#who-anc) |
| **`whoami`** | Prints current userid. | [Link](http://man7.org/linux/man-pages/man1/whoami.1.html) | [Jump to Example](#whoami-anc) |
| **`sudo`** | Using sudo before another command will run it with root privilege. Will need to enter root password after running command. | [Link](https://www.systutorials.com/docs/linux/man/8-sudo/) | [Jump to Example](#sudo-anc) |
| **`su`** | Allows user to run commands with a substitute user or group. Mostly used to elevate terminal session to root. | [Link](http://man7.org/linux/man-pages/man1/su.1.html) | [Jump to Example](#su-anc) |
| **`date`** | Print or set the system date and time. | [Link](http://man7.org/linux/man-pages/man1/date.1.html) | [Jump to Example](#date-anc) |
| **`uptime`** | Displays how long the system has been running. | [Link](http://man7.org/linux/man-pages/man1/uptime.1.html) | [Jump to Example](#uptime-anc) |
| **`passwd`** | Change user's password. | [Link](http://man7.org/linux/man-pages/man1/passwd.1.html) | [Jump to Example](#passwd-anc) |
| **`apt-get`** | APT package handling utility for Debian based systems, such as Ubuntu. | [Link](https://www.systutorials.com/docs/linux/man/8-apt-get/) | [Jump to Example](#apt-get-anc) |
| **`halt`** | Used to halt a system. | [Link](http://man7.org/linux/man-pages/man8/halt.8.html) | [Jump to Example](#halt-anc) |
| **`poweroff`** | Used to power down a system. | [Link](http://man7.org/linux/man-pages/man8/poweroff.8.html) | [Jump to Examples](poweroff-anc) |
| **`reboot`** | Used to reboot a system. | [Link](http://man7.org/linux/man-pages/man8/reboot.8.html) | [Jump to Example](#reboot-anc) |

<a id="s-inter"></a>

| Intermediate Commands | Description | Man Page | Example |
| --- | --- | --- | --- |
| **`top`** | Displays processes. | [Link](http://man7.org/linux/man-pages/man1/top.1.html) | [Jump to Example](#top-anc) |
| **`last`** | Lists logins on the system. | [Link](http://man7.org/linux/man-pages/man1/last.1.html) | [Jump to Example](#last-anc) |
| **`ps`** | Reports a snapshot of current processes. | [Link](http://man7.org/linux/man-pages/man1/ps.1.html) | [Jump to Example](#ps-anc) |
| **`df`** | Reports file system disk space usage. Displays the usage of each mounted system. | [Link](http://man7.org/linux/man-pages/man1/df.1.html) | [Jump to Example](#df-anc) |
| **`du`** | Estimated file space usage. | [Link](http://man7.org/linux/man-pages/man1/du.1.html) | [Jump to Example](#du-anc) |
| **`free`** | Displays amount of free and used memory in the system. | [Link](http://man7.org/linux/man-pages/man1/free.1.html) | [Jump to Example](#free-anc) |
| **`crontab`** | Maintains crontab files for individual users. This allows scheduled jobs to be run. | [Link](http://man7.org/linux/man-pages/man1/crontab.1.html) | [Jump to Example](#crontab-anc) |
| **`service`** | Allows for starting and stopping of services. | [Link](https://www.systutorials.com/docs/linux/man/8-service/) | [Jump to Example](#service-anc) |
| **`kill`** | Used to terminate a process. | [Link](http://man7.org/linux/man-pages/man1/kill.1.html) | [Jump to Example](#kill-anc) |
| **`killall`** | Used to terminate a process by name. | [Link](http://man7.org/linux/man-pages/man1/killall.1.html) | [Jump to Example](#killall-anc) |

<a id="s-ex"></a>

#### Examples

|<a id="uname-anc"></a> Command | Common Options |
| --- | --- |
| **`uname`** |  |
```bash

```

|<a id="hostname-anc"></a> Command | Common Options |
| --- | --- |
| **`hostname`** |  |
```bash

```

|<a id="users-anc"></a> Command | Common Options |
| --- | --- |
| **`users`** |  |
```bash

```

|<a id="who-anc"></a> Command | Common Options |
| --- | --- |
| **`who`** |  |
```bash

```

|<a id="whoami-anc"></a> Command | Common Options |
| --- | --- |
| **`whoami`** |  |
```bash

```

|<a id="sudo-anc"></a> Command | Common Options |
| --- | --- |
| **`sudo`** |  |
```bash
sudo apt-get update           #updating system with root permission
```

|<a id="su-anc"></a> Command | Common Options |
| --- | --- |
| **`su`** |  |
```bash
su                            #elevate access to root
sudo passwd                   #set new root password
```

|<a id="date-anc"></a> Command | Common Options |
| --- | --- |
| **`date`** |  |
```bash

```

|<a id="uptime-anc"></a> Command | Common Options |
| --- | --- |
| **`uptime`** |  |
```bash

```

|<a id="passwd-anc"></a> Command | Common Options |
| --- | --- |
| **`passwd`** |  |
```bash

```

|<a id="apt-get-anc"></a> Command | Common Options |
| --- | --- |
| **`apt-get`** |  |
```bash

```

|<a id="halt-anc"></a> Command | Common Options |
| --- | --- |
| **`halt`** |  |
```bash

```

|<a id="poweroff-anc"></a> Command | Common Options |
| --- | --- |
| **`poweroff`** |  |
```bash

```

|<a id="reboot-anc"></a> Command | Common Options |
| --- | --- |
| **`reboot`** |  |
```bash

```

|<a id="top-anc"></a> Command | Common Options |
| --- | --- |
| **`top`** |  |
```bash

```

|<a id="last-anc"></a> Command | Common Options |
| --- | --- |
| **`last`** |  |
```bash

```

|<a id="ps-anc"></a> Command | Common Options |
| --- | --- |
| **`ps`** |  |
```bash

```

|<a id="df-anc"></a> Command | Common Options |
| --- | --- |
| **`df`** |  |
```bash

```

|<a id="du-anc"></a> Command | Common Options |
| --- | --- |
| **`du`** |  |
```bash

```

|<a id="free-anc"></a> Command | Common Options |
| --- | --- |
| **`free`** |  |
```bash

```

|<a id="crontab-anc"></a> Command | Common Options |
| --- | --- |
| **`crontab`** |  |
```bash

```

|<a id="service-anc"></a> Command | Common Options |
| --- | --- |
| **`service`** |  |
```bash

```

|<a id="kill-anc"></a> Command | Common Options |
| --- | --- |
| **`kill`** |  |
```bash

```

|<a id="killall-anc"></a> Command | Common Options |
| --- | --- |
| **`killall`** |  |
```bash

```

---

### Networking

<a id="net-basic"></a>

| Basic Commands | Description | Man Page | Example |
| --- | --- | --- | --- |
| **`ping`** | Sends ICMP ECHO_REQUEST to network host. Useful for determining if a system i sup, or if a system has network connection. | [Link](http://man7.org/linux/man-pages/man8/ping.8.html) | [Jump to Example](#ping-anc) |
| **`ifconfig`** | Displays current network information and/or configures a network interface. | [Link](http://man7.org/linux/man-pages/man8/ifconfig.8.html) | [Jump to Example](#ifconfig-anc) |
| **`host`** | DNS lookup utility. | [Link](https://www.systutorials.com/docs/linux/man/1-host/) | [Jump to Example](#host-anc) |
| **`arp`** | Address Resolution Protocol. Used to convert between Layer2 hardware addresses and IPv4 protocol addresses on directly connected networks. | [Link](http://man7.org/linux/man-pages/man7/arp.7.html) | [Jump to Example](#arp-anc) |
| **`dig`** | DNS server lookup utility. | [Link](https://www.systutorials.com/docs/linux/man/1-dig/) | [Jump to Example](#dig-anc) |
| **`route`** | Shows the routing table. Can also be used to setup static routes. | [Link](http://man7.org/linux/man-pages/man8/route.8.html) | [Jump to Example](#route-anc) |
| **`nslookup`** | Queries internet name server. Can be used interactively. | [Link](https://www.systutorials.com/docs/linux/man/1-nslookup/) | [Jump to Example](#nslookup-anc) |
| **`netstat`** | Prints network information, such as connections, routing tables, and interface statistics. | [Link](http://man7.org/linux/man-pages/man8/netstat.8.html) | [Jump to Example](#netstat-anc) |
| **`wget`** | Command line network downloader. Used to pull files from internet sources using the command line. | [Link](http://man7.org/linux/man-pages/man1/wget.1.html) | [Jump to Example](#wget-anc) |

<a id="net-inter"></a>

| Intermediate Commands | Description | Man Page | Example |
| --- | --- | --- | --- |
| **`scp`** | Secure copy for remote file transfer. Uses ssh port 22 for copying remote files. | [Link](http://man7.org/linux/man-pages/man1/scp.1.html) | [Jump to Example](#scp-anc) |
| **`ftp`** | File transfer protocol. Used to transfer files remotely. No encryption, uses port 21. | [Link](https://www.systutorials.com/docs/linux/man/1-ftp/) | [Jump to Example](#ftp-anc) |
| **`sftp`** | Secure File Transfer Protocol. Used to transfer files remotely, but uses an encrypted ssh transport to transfer the data. Uses port 22. | [Link](http://man7.org/linux/man-pages/man1/sftp.1.html) | [Jump to Example](#sftp-anc) |
| **`ssh`** | SSH is used to remotely login to systems, which allows users to remotely execute commands on a system. The connection is secured and encrypted, and uses port 22. | [Link](http://man7.org/linux/man-pages/man1/ssh.1.html) | [Jump to Example](#ssh-anc) |
| **`nmap`** | Network exploration tool and port scanner. Nmap has a ton of options to use. It can be used to scan systems, or even entire subnets, to find what ports are open and which services are running on each system. | [Link](http://man7.org/linux/man-pages/man1/nmap.1.html) | [Jump to Example](#nmap-anc) |
| **`tcpdump`** | Dumps traffic on a network. Allows user to capture packets for further examination. | [Link](http://man7.org/linux/man-pages/man1/tcpdump.1.html) | [Jump to Example](#tcpdump-anc) |
| **`telnet`** | | [Link]() | [Jump to Example](#telnet-anc) |
| **`whois`** | | [Link]() | [Jump to Example](#whois-anc) |
| **`traceroute`** | | [Link]() | [Jump to Example](#traceroute-anc) |
| **`tracepath`** | | [Link]() | [Jump to Example](#tracepath-anc) |
| **`ifup`** | | [Link]() | [Jump to Example](#ifup-anc) |
| **`ifdown`** | | [Link]() | [Jump to Example](#ifdown-anc) |
| **`dhclient`** | | [Link]() | [Jump to Example](#dhclient-anc) |

<a id="net-ex"></a>

#### Examples

|<a id="ping-anc"></a> Command | Common Options |
| --- | --- |
| **`ping`** |  |
```bash

```

|<a id="ifconfig-anc"></a> Command | Common Options |
| --- | --- |
| **`ifconfig`** |  |
```bash

```

|<a id="host-anc"></a> Command | Common Options |
| --- | --- |
| **`host`** |  |
```bash

```

|<a id="arp-anc"></a> Command | Common Options |
| --- | --- |
| **`arp`** |  |
```bash

```

|<a id="dig-anc"></a> Command | Common Options |
| --- | --- |
| **`dig`** |  |
```bash

```

|<a id="route-anc"></a> Command | Common Options |
| --- | --- |
| **`route`** |  |
```bash

```

|<a id="nslookup-anc"></a> Command | Common Options |
| --- | --- |
| **`nslookup`** |  |
```bash

```

|<a id="netstat-anc"></a> Command | Common Options |
| --- | --- |
| **`netstat`** |  |
```bash

```

|<a id="scp-anc"></a> Command | Common Options |
| --- | --- |
| **`scp`** |  |
```bash

```

|<a id="ftp-anc"></a> Command | Common Options |
| --- | --- |
| **`ftp`** |  |
```bash

```

|<a id="sftp-anc"></a> Command | Common Options |
| --- | --- |
| **`sftp`** |  |
```bash

```

|<a id="ssh-anc"></a> Command | Common Options |
| --- | --- |
| **`ssh`** |  |
```bash

```

|<a id="nmap-anc"></a> Command | Common Options |
| --- | --- |
| **`nmap`** |  |
```bash

```

|<a id="tcpdump-anc"></a> Command | Common Options |
| --- | --- |
| **`tcpdump`** |  |
```bash

```

|<a id="telnet-anc"></a> Command | Common Options |
| --- | --- |
| **`telnet`** |  |
```bash

```

|<a id="whois-anc"></a> Command | Common Options |
| --- | --- |
| **`whois`** |  |
```bash

```

|<a id="traceroute-anc"></a> Command | Common Options |
| --- | --- |
| **`traceroute`** |  |
```bash

```

|<a id="tracepath-anc"></a> Command | Common Options |
| --- | --- |
| **`tracepath`** |  |
```bash

```

|<a id="ifup-anc"></a> Command | Common Options |
| --- | --- |
| **`ifup`** |  |
```bash

```

|<a id="ifdown-anc"></a> Command | Common Options |
| --- | --- |
| **`ifdown`** |  |
```bash

```

|<a id="dhclient-anc"></a> Command | Common Options |
| --- | --- |
| **`dhclient`** |  |
```bash

```

---

## Other

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

### Shortcuts 

Using **`Ctrl+C`** will safely stop current execution

Using **`Ctrl+Z`** will force stop current execution

---

## All Commands in Alphabetical Order

- [apt-get](#apt-get-anc)
- [arp](#arp-anc)
- [cat](#cat-anc)
- [cd](#cd-anc)
- [chmod](#chmod-anc)
- [chown](#chown-anc)
- [cp](#cp-anc)
- [crontab](#crontab-anc)
- [date](#date-anc)
- [df](#df-anc)
- [dhclient](#dhclient-anc)
- [dig](#dig-anc)
- [du](#du-anc)
- [echo](#echo-anc)
- [file](#file-anc)
- [find](#find-anc)
- [free](#free-anc)
- [ftp](#ftp-anc)
- [grep](#grep-anc)
- [gzip](#gzip-anc)
- [halt](#halt-anc)
- [host](#host-anc)
- [hostname](#hostname-anc)
- [ifconfig](#ifconfig-anc)
- [ifdown](#ifdown-anc)
- [ifup](#ifup-anc)
- [kill](#kill-anc)
- [killall](#killall-anc)
- [last](#last-anc)
- [less](#less-anc)
- [ln](#ln-anc)
- [locate](#locate-anc)
- [ls](#ls-anc)
- [lsof](#lsof-anc)
- [mkdir](#mkdir-anc)
- [mount](#mount-anc)
- [mv](#mv-anc)
- [nano](#nano-anc)
- [netstat](#netstat-anc)
- [nmap](#nmap-anc)
- [nslookup](#nslookup-anc)
- [passwd](#passwd-anc)
- [ping](#ping-anc)
- [poweroff](#poweroff-anc)
- [ps](#ps-anc)
- [pwd](#pwd-anc)
- [reboot](#reboot-anc)
- [rm](#rm-anc)
- [rmdir](#rmdir-anc)
- [route](#route-anc)
- [scp](#scp-anc)
- [service](#service-anc)
- [sftp](#sftp-anc)
- [ssh](#ssh-anc)
- [su](#su-anc)
- [sudo](#sudo-anc)
- [tar](#tar-anc)
- [tcpdump](#tcpdump-anc)
- [telnet](#telnet-anc)
- [top](#top-anc)
- [touch](#touch-anc)
- [tracepath](#tracepath-anc)
- [traceroute](#traceroute-anc)
- [umount](#umount-anc)
- [uname](#uname-anc)
- [unzip](#unzip-anc)
- [updatedb](#updatedb-anc)
- [uptime](#uptime-anc)
- [users](#users-anc)
- [vi](#nano-anc)
- [wget](#wget-anc)
- [who](#who-anc)
- [whoami](#whoami-anc)
- [whois](#whois-anc)
- [zip](#zip-anc)

---

## Resources

| Basic Guides | Description |
| --- | --- |
| [Guide](https://maker.pro/linux/tutorial/basic-linux-commands-for-beginners) | A guide for commonly used Linux commands, aimed at beginners. |
| [Guide](https://www-uxsup.csx.cam.ac.uk/pub/doc/suse/suse9.0/userguide-9.0/ch24s04.html) | A guide for a mix between basic and intermediate commonly used Linux commands. |

| Intermediate Guides | Description |
| --- | --- |
| [Guide](https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/) | A guide written for Linux privilege escalation. This guide does a great job describing many different ways to find information on Linux systems. |

| Other | Description |
| --- | --- |
| [Link](http://man7.org/linux/man-pages/dir_all_by_section.html#man1) | Linux man pages. |
| [Link](https://www.systutorials.com/docs/linux/man/) | More Linux man pages, used when the above link didn't have the man page. |
