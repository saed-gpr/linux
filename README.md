# Basic Linux knowledge 


### Introduction:
This repository contains a collection of resources, commands, and tips for learning fundamental and practical Linux concepts. The goal is to help new users familiarize themselves with the Linux environment, basic commands, and how to work with Linux-based operating systems.

Imagine you've installed Ubuntu or another Linux distribution (if you encounter any issues during the installation process, feel free to ask me to create a tutorial video), and now you want to start using it but don't know where to begin.
If that's the case, I suggest reading this repository to improve your Linux skills!

:red_circle: Notice: I am just sharing some of my knowledge (not all of it)
# Topics

let me tell you the topics:
- Types of linux

- Basic syntax
  -  File management
  -  User management
  -  Network
    
- Unix directories

# Types of linux

We have many versions of Linux, but the most popular ones are Debian-based and Red Hat-based
- Debian - Based :
    - [Ubuntu](https://ubuntu.com/)
    - [Kali Linux](https://www.kali.org/)
    - [Rassbery Pi OS](https://www.raspberrypi.com/software/)
- Red Hat - Based :
    - [Fedora](https://fedoraproject.org/)
    - [Oracle](https://www.oracle.com/linux/technologies/oracle-linux-downloads.html)
    - [AlmaLinux](https://almalinux.org/get-almalinux/)
 
# Basic syntax


- #### File management :
  - `cd`
  - `ls`
  - `mkdir`
  - `whereis`
  - `cat`
  - `dmesg`
  - `tree`
  - `pwd`
  - `locate`

- #### User management :
  - `whoami`
  - `passwd`
  - `id`
  - `sudo`
  - `uname`


- #### Networking :
  - `ping`
  - `wall`
  
 - #### System Management :
   - `pared`
   - `gparted`
   - `free`


### File Management :

### 1- `cd` :
In fact, `cd` stands for 'Change Directory'. As you guessed, this syntax can help us change our current directory. This syntax is very basic and useful for us!

```bash
z@z:~$ cd Desktop/
z@z:~/Desktop$ 
```
In this case we changed our directory into Desktop.


### 2- `ls` :
`ls` shows us the files in a specific directory.

```bash
#SYNOPSIS:
# ls [OPTION]...[FILE]...
```

#### options:
- `-a`, `--all` -> do not ignore entries starting with.

- `--version` -> output version information and exit.

- `-d`, `--directory` -> list the directoriy names (not theier contents)!

For example, on the Desktop, we have some files, and we want to see their names and types in the terminal


```bash
z@z:~/Desktop$ ls
'lpic1 book'   test.py  'this folder'
```

as you can see we have a .py file, PDF and a folder.

### 3- `mkdir` :
This syntax stands for making directories. you can use it to creating a DIRECTORY(ies)

```bash
#SYNOPSIS
#mkdir [OPTION] ... DIREXTORY ...
```

#### Options:
- `m`,`--mode` -> set file mode

Imagine that you want to creat a directory that named by 'lpic1' on your desktop, here is what you should do:

```bash
z@z:~$ cd Desktop/
z@z:~/Desktop$ mkdir lpic1
```
As you can see, we created a directory that named by 'lpic1'.

### 4- `whereis` :
This syntax locates the binary, source and manual files for the spexified command names.

```bash
#SYNOPSIS
#whereis [options] [-BMS directory... -f] name ...
```

Options:
- `-b` -> search for binaries.
- `s` -> shearch for sources.

```bash
z@z:~/Desktop$ whereis wireshark 
wireshark: /usr/bin/wireshark /usr/lib/x86_64-linux-gnu/wireshark /etc/wireshark /usr/share/wireshark /usr/share/man/man1/wireshark.1.gz
```

### 5- `cat` :
concatenate FILE(s) to standard output.

```bash
#SYNOPSIS
#cat [OPTION] ... [FILE] ...
```

Options :

- `n`, `--number` -> number all output lines
- `A`, `--show-all` -> equevalent to -vET

For example, i want to see the output of `/var/log/boot.log` that shows us the system's logs. you can use this syntax with any files.

```bash
z@z:/$ sudo cat /var/log/boot.log
[sudo] password for z: 
[  OK  ] Started accounts-daemon.service - Accounts Service.
[  OK  ] Started rsyslog.service - System Logging Service.
[  OK  ] Stopped cups.path - CUPS Scheduler.
         Stopping cups.path - CUPS Scheduler...
[  OK  ] Started cups.path - CUPS Scheduler.
[  OK  ] Closed cups.socket - CUPS Scheduler.
         Stopping cups.socket - CUPS Scheduler...
[  OK  ] Listening on cups.socket - CUPS Scheduler.
[  OK  ] Started NetworkManager.service - Network Manager.
[  OK  ] Reached target network.target - Network.
         Starting NetworkManager-wait-online.service - Network Manager Wait Online...
         Starting cups.service - CUPS Scheduler...
         Starting openvpn.service - OpenVPN service...
[  OK  ] Started snap.v2ray-core.v2ray.service - Service for snap application v2ray-core.v2ray.
         Starting systemd-user-sessions.service - Permit User Sessions...
[  OK  ] Finished openvpn.service - OpenVPN service.
[  OK  ] Finished systemd-user-sessions.service - Permit User Sessions.
[  OK  ] Started ModemManager.service - Modem Manager.
         Starting gdm.service - GNOME Display Manager...
         Starting plymouth-quit-wait.service - Hold until boot process finishes up...
         Starting systemd-hostnamed.service - Hostname Service...
[  OK  ] Started udisks2.service - Disk Manager.
[  OK  ] Started cups.service - CUPS Scheduler.
[  OK  ] Finished logrotate.service - Rotate log files.
[  OK  ] Finished e2scrub_reap.service - Remove Stale Online ext4 Metadata Check Snapshots.
[  OK  ] Started systemd-hostnamed.service - Hostname Service.
[  OK  ] Started gdm.service - GNOME Display Manager.
         Starting NetworkManager-dispatcher.service - Network Manager Script Dispatcher Service...
z@z:/$ 
z@z:/$ sudo cat /var/log/boot.log
[  OK  ] Started accounts-daemon.service - Accounts Service.
[  OK  ] Started rsyslog.service - System Logging Service.
[  OK  ] Stopped cups.path - CUPS Scheduler.
         Stopping cups.path - CUPS Scheduler...
[  OK  ] Started cups.path - CUPS Scheduler.
[  OK  ] Closed cups.socket - CUPS Scheduler.
         Stopping cups.socket - CUPS Scheduler...
[  OK  ] Listening on cups.socket - CUPS Scheduler.
[  OK  ] Started NetworkManager.service - Network Manager.
[  OK  ] Reached target network.target - Network.
         Starting NetworkManager-wait-online.service - Network Manager Wait Online...
         Starting cups.service - CUPS Scheduler...
         Starting openvpn.service - OpenVPN service...
[  OK  ] Started snap.v2ray-core.v2ray.service - Service for snap application v2ray-core.v2ray.
         Starting systemd-user-sessions.service - Permit User Sessions...
[  OK  ] Finished openvpn.service - OpenVPN service.
[  OK  ] Finished systemd-user-sessions.service - Permit User Sessions.
[  OK  ] Started ModemManager.service - Modem Manager.
         Starting gdm.service - GNOME Display Manager...
         Starting plymouth-quit-wait.service - Hold until boot process finishes up...
         Starting systemd-hostnamed.service - Hostname Service...
[  OK  ] Started udisks2.service - Disk Manager.
[  OK  ] Started cups.service - CUPS Scheduler.
[  OK  ] Finished logrotate.service - Rotate log files.
[  OK  ] Finished e2scrub_reap.service - Remove Stale Online ext4 Metadata Check Snapshots.
[  OK  ] Started systemd-hostnamed.service - Hostname Service.
[  OK  ] Started gdm.service - GNOME Display Manager.
         Starting NetworkManager-dispatcher.service - Network Manager Script Dispatcher Service...

```




--------------------------------------------------------------------------------
# خذفیات

### 3- `sudo` :
When you use this syntax, you become the `root` user and are able to edit sensitive files, such as installing or modifying package settings. For this reason, you should know the password.

```bash
sudo shutdown
sudo reboot
```

### 4- `Whereis` :
To find the path of some programs, you can use the `whereis` command. This command shows you the path.

``` bash
#SYNPOSIS:
#whereis [options] [-BMS derectory... -f] name ...
```

#### options:
- `-b` -> search for binaries.

- `-s` -> shearch for sources

```bash
#whereis <file or program's name>
z@z:~$ whereis wireshark 
wireshark: /usr/bin/wireshark /usr/lib/x86_64-linux-gnu/wireshark /etc/wireshark /usr/share/wireshark /usr/share/man/man1/wireshark.1.gz
```

### 5- `cat` :
If you want to see the content of a file, you can use this command. For example, if we want to see the content of `/var/log/boot.log` , we should first become root. Therefore, we use the sudo command and then cat.

```bash
#SYNPOSIS:
#cat [option]...[file]...
```

#### options:
- `-A`, `--show-all` -> it is used for showing the content of a file with non-printing characters
`
```bash
sudo cat /var/log/boot.log
```



#
- Author : [Saed Gholipour](https://github.com/saed-gpr)
