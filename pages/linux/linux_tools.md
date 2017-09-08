---
title: Linux / Tools
tags: [linux, tools]
keywords: linux, tools
sidebar: wiki_sidebar
permalink: linux_tools.html
---

## General Info
* `uname -a` -- Print operating system name
* `lsb_release -a` -- print distribution specific information
* `printenv` -- print enviroment variables
* `w` -- display who is logged in and what they are doing
* `pwd` -- display Present Working Directory
* `which <CMD>` -- print the location of the CMD executable

## Hardware Info

* [8 commands to check cpu information on Linux](http://www.binarytides.com/linux-cpu-information/)

## Permissions

* `chmod` -- modify permissions of a file.
  * example: `chmod 600 file.txt`
  * OGA (Owner, Group and All) O, G and A are numbers from 0 to 7.
  * Each number can be seen as the sum of these three numbers:
    * 4 - Read (100 in binary)
    * 2 - Write (010 in binary)
    * 1 - eXecute (001 in binary)
  * You can also add Read, Write or eXecution permission for all users: `chmod +[r|w|x] file.txt`

 * `chown` -- change owner of a file.
   * example: `chown user:group /dir`

## Basic Functions

* `shutdown` -- shutdown the computer

* `date`
  * get current time:  
    `date +%s`
  * get time from a specific moment:  
    `date +%s -d "2016-08-17 20:15:03"`
  * Convert and print number of seconds to "day hour minute second" format:  
    `echo "Duration: $(($d/86400))d $(($d/3600%24))h $(($d/60%60))m $(($d%60))s"`

* `find` -- walk a file hierarchy
  * **parameters**
    * `-name [<NAME>|"<NAME>"]` -- True if last component of the pathname being examined matches pattern.
    * `-path [<PATH>|"<PATH>"]` -- True if the pathname being examined matches pattern.

## Processes

**Detach scripts/commands from shell**:  

* [`nohup`](https://ss64.com/bash/nohup.html)
* [`screen`](https://ss64.com/bash/screen.html)  

<sup>Reference: [nohup Execute Commands After You Exit From a Shell Prompt](https://www.cyberciti.biz/tips/nohup-execute-commands-after-you-exit-from-a-shell-prompt.html)</sup>

**Run commands in the background**:  
You can append `&` at the end of a command to run in the background.  
This is useful when you have only one terminal and you want to run a command that takes too long to end or you want it to run it indefinitely, e.g.: `tcpdump` and you also want to execute another command in parallel.  
<sup>Reference: [Unix job control command list](https://kb.iu.edu/d/afnw)</sup>

Also:  

* `jobs` -- List background processes
* `pgrep <process_name>` -- get pid of a process
* `kill PID` -- kill the process with this PID. Without parameters equals to pressing **Ctrl+C** when the process is in the foreground.

## Filesystem

**Common directories**:

* `/home` -- Linux User Accounts Home Directory and FTP server home directory (some distros)
* `/etc` -- Linux Server's and Applications System's Configuration Files
* `/usr` -- Linux System Files (Shareable, Read-only Data)
* `/bin` -- Binary Files for user applications
* `/sbin` -- Binary Files for system programs

**SSH Filesystem**:

```shell
# Install SSHFS
sudo apt-get install sshfs
#Create a directory to mount the filesystem
mkdir /mnt/remote_sshfs
#Mount the filesystem
sshfs user@host:dir /mnt/remote_sshfs
#Unmount the filesystem
umount /mnt/remote_sshfs
```
<sup>Reference: [How To Use SSHFS to Mount Remote File Systems Over SSH](https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh)</sup>

## Disks

**partition tables**:  

* `fdisk` -- manipulate disk partition table  
<sup>Reference: [How to delete a partition with fdisk command](https://www.cyberciti.biz/faq/linux-how-to-delete-a-partition-with-fdisk-command/)</sup>

**info about disks**:

* `lshw` -- is a small tool to provide detailed information on the hardware configuration of the machine. It can report exact memory configuration, firmware version, mainboard configuration, CPU version and speed, cache configuration, bus speed, etc.  
* `lshw -class disk` -- get info about disks  
<sup>Reference: [Retrieve Disk Info from the Command Line](http://www.linuxjournal.com/content/tech-tip-retrieve-disk-info-command-line)</sup>
* `lsblk` -- view mounted devices
* `du` -- disk usage  
  useful parameters:
  * `-h` : for human readable sizes
  * `-d NUMBER` : the maximum depth in the output  

  If you want to order the result by size you can send the output to sort like this: `du -h | sort -h`  
  <sup>Reference: [Size of a directory & Free disk space](http://www.codecoffee.com/tipsforlinux/articles/22.html)</sup>

**modify labels**:  

* `e2label` -- change the label of an ext2,3,4 partition
* `ntfslabel` -- change the label of a ntfs partition (from `ntfs-3g` package)

**clean disks**:

* `shred` -- overwrite a file to hide its contents, and optionally delete it  
<sup>Reference [Why deleting just isn't enough](http://geekblog.oneandoneis2.org/index.php/2007/01/04/why_deleting_just_isn_t_enough)</sup>

## Text Editor
* `vim`
  * `vimtutorial` / `vimtutor`
  * [Vim Awesome](http://vimawesome.com/)

## User Management

* `adduser <username>` -- asking for password, will create home directory and asking lots of information about the user.
* `useradd <username>` -- not asking for password, no home directory just only add new user.


## Package Manager

### APT

* `apt-get install --only-upgrade <package>` -- to only upgrade a specific package
* `apt show [package]` -- info about a package
* `sudo rm /var/lib/apt/lists/lock` -- unlock apt-get when it get locked (sometimes this happens when you Ctrl+C apt-get when it's running)

**logs**:  

All actions with apt (apt-get) are logged. These files are available in `/var/log/apt/`. To view the most recent history log, execute: `less /var/log/apt/history.log`.  
These logs gets rotated (every month I guess), old files will be suffixed with a number and compressed. So to view the next history log, use: `zless /var/log/apt/history.log.1.gz`.

### RPM
* `rpm -qi [package]` -- info about a package
* [RPM naming convention](http://ftp.rpm.org/max-rpm/ch-rpm-file-format.html)

## SSH
* `ssh-add -K ~/.ssh/<private_key_file>` -- to add a private key to the keychain

## Debug

**view shared/dynamic libraries used by a process**:

* `ldd` *(Linux)*
* `otool -L` *(MacOS)*

## Multiple terminals

* `tmux` -- terminal multiplexer
  * `Ctrl`+`b` `%` -- Split pane horizontally
  * `Ctrl`+`b` `"` -- Split pane vertically
  * `Ctrl`+`b` `<arrow-key>` -- Switch pane
  * `Ctrl`+`d` -- Close pane  
  * `Ctrl`+`b` `d` -- Detach current session
  * `Ctrl`+`b` `D` -- Detach specific session (selected from list)
  * `tmux ls` -- view running session
  * `tmux attach -t 0` -- attach to session 0
  * `tmux new -s database` -- create a session with name
  * `tmux rename-session -t 0 database` -- rename existing session
  * `tmux attach -t database` -- attach to a named session  
  * `Ctrl`+`b` `?` -- list of available commands
  * `Ctrl`+`b` `z` -- go fullscreen (press again to go restore)
  * `Ctrl`+`b` `Ctrl`+`<arrow-key>` -- Resize pane in direction of key  
<sup>Reference: [A quick and easy guide to tmux](http://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/)</sup>

## Network

* `nc`/`netcat` -- arbitrary TCP and UDP connections and listens
  * `nc -l localhost 4000` -- listen in localhost:4000  
<sup>Reference: [Netcat – a couple of useful examples](https://www.g-loaded.eu/2006/11/06/netcat-a-couple-of-useful-examples/)</sup>
