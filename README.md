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
  - `mv`


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

#### Options:
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

#### Options :

- `n`, `--number` -> number all output lines
- `A`, `--show-all` -> equevalent to -vET

For example, i want to see the output of `/var/log/boot.log` that shows us the system's logs. you can use this syntax with any files.

```bash
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

### 6- `dmesg` :
dmesg - print or control the kernel ring buffer

```bash
#SYNOPSIS
#dmesg
#dmesg [OPTIONS]
```

#### Options:

- `-C`, `--clear` -> clear the ring buffer
- `-H`, `--human` -> Enable human-readable output.


```bash
z@z:/$ sudo dmesg
[    0.000000] Linux version 6.2.0-39-generic (buildd@bos03-amd64-014) (x86_64-linux-gnu-gcc-12 (Ubuntu 12.3.0-1ubuntu1~23.04) 12.3.0, GNU ld (GNU Binutils for Ubuntu) 2.40) #40-Ubuntu SMP PREEMPT_DYNAMIC Tue Nov 14 14:18:00 UTC 2023 (Ubuntu 6.2.0-39.40-generic 6.2.16)
[    0.000000] Command line: BOOT_IMAGE=/boot/vmlinuz-6.2.0-39-generic root=UUID=c5ffcf3a-5306-4858-a5ef-c36c01a13eef ro quiet splash
[    0.000000] KERNEL supported cpus:
[    0.000000]   Intel GenuineIntel
[    0.000000]   AMD AuthenticAMD
[    0.000000]   Hygon HygonGenuine
[    0.000000]   Centaur CentaurHauls
[    0.000000]   zhaoxin   Shanghai  
[    0.000000] Disabled fast string operations
[    0.000000] BIOS-provided physical RAM map:
[    0.000000] BIOS-e820: [mem 0x0000000000000000-0x000000000009e7ff] usable
[    0.000000] BIOS-e820: [mem 0x000000000009e800-0x000000000009ffff] reserved
[    0.000000] BIOS-e820: [mem 0x00000000000dc000-0x00000000000fffff] reserved
[    0.000000] BIOS-e820: [mem 0x0000000000100000-0x00000000bfecffff] usable
[    0.000000] BIOS-e820: [mem 0x00000000bfed0000-0x00000000bfefefff] ACPI data
[    0.000000] BIOS-e820: [mem 0x00000000bfeff000-0x00000000bfefffff] ACPI NVS
[    0.000000] BIOS-e820: [mem 0x00000000bff00000-0x00000000bfffffff] usable
[    0.000000] BIOS-e820: [mem 0x00000000f0000000-0x00000000f7ffffff] reserved
[    0.000000] BIOS-e820: [mem 0x00000000fec00000-0x00000000fec0ffff] reserved
[    0.000000] BIOS-e820: [mem 0x00000000fee00000-0x00000000fee00fff] reserved
[    0.000000] BIOS-e820: [mem 0x00000000fffe0000-0x00000000ffffffff] reserved
[    0.000000] BIOS-e820: [mem 0x0000000100000000-0x00000001fdbfffff] usable
[    0.000000] NX (Execute Disable) protection: active
[    0.000000] SMBIOS 2.7 present.
[    0.000000] DMI: VMware, Inc. VMware Virtual Platform/440BX Desktop Reference Platform, BIOS 6.00 02/27/2020
[    0.000000] vmware: hypercall mode: 0x00
[    0.000000] Hypervisor detected: VMware
[    0.000000] vmware: TSC freq read from hypervisor : 2496.003 MHz
[    0.000000] vmware: Host bus clock speed read from hypervisor : 66000000 Hz
[    0.000000] vmware: using clock offset of 5916704456 ns
[    0.000011] tsc: Detected 2496.003 MHz processor
[    0.001687] e820: update [mem 0x00000000-0x00000fff] usable ==> reserved
[    0.001691] e820: remove [mem 0x000a0000-0x000fffff] usable
[    0.001696] last_pfn = 0x1fdc00 max_arch_pfn = 0x400000000
[    0.001712] total RAM covered: 130048M
[    0.001805] Found optimal setting for mtrr clean up
[    0.001806]  gran_size: 64K 	chunk_size: 64K num_reg: 7  	lose cover RAM: 0G
[    0.001809] x86/PAT: Configuration [0-7]: WB  WC  UC- UC  WB  WP  UC- WT  
[    0.001846] e820: update [mem 0xc0000000-0xffffffff] usable ==> reserved
[    0.001851] last_pfn = 0xc0000 max_arch_pfn = 0x400000000
[    0.010968] found SMP MP-table at [mem 0x000f6a70-0x000f6a7f]
[    0.011011] Using GB pages for direct mapping
[    0.011182] RAMDISK: [mem 0x2fd49000-0x33e9bfff]
[    0.011198] ACPI: Early table checksum verification disabled
[    0.011201] ACPI: RSDP 0x00000000000F6A00 000024 (v02 PTLTD )
[    0.011207] ACPI: XSDT 0x00000000BFEDB633 00005C (v01 INTEL  440BX    06040000 VMW  01324272)
[    0.011213] ACPI: FACP 0x00000000BFEFEE73 0000F4 (v04 INTEL  440BX    06040000 PTL  000F4240)
[    0.011234] ACPI: DSDT 0x00000000BFEDD001 021E72 (v01 PTLTD  Custom   06040000 MSFT 03000001)
[    0.011239] ACPI: FACS 0x00000000BFEFFFC0 000040
[    0.011242] ACPI: FACS 0x00000000BFEFFFC0 000040
[    0.011273] ACPI: BOOT 0x00000000BFEDCFB4 000028 (v01 PTLTD  $SBFTBL$ 06040000  LTP 00000001)
[    0.011277] ACPI: APIC 0x00000000BFEDC872 000742 (v01 PTLTD  ? APIC   06040000  LTP 00000000)
[    0.011280] ACPI: MCFG 0x00000000BFEDC836 00003C (v01 PTLTD  $PCITBL$ 06040000  LTP 00000001)
[    0.011284] ACPI: SRAT 0x00000000BFEDB72F 0008D0 (v02 VMWARE MEMPLUG  06040000 VMW  00000001)
[    0.011287] ACPI: HPET 0x00000000BFEDB6F7 000038 (v01 VMWARE VMW HPET 06040000 VMW  00000001)

```
### 7- `tree` :

The tree command in Linux is used to display the directory structure in a tree-like format.

#### Options:
- `-a` -> All files are listed
- `-d` -> List directories only

```bash
z@z:~/Desktop$ tree
.
├── lpic1
├── lpic1 book
├── test.py
└── this folder

3 directories, 2 files
```
In this case, We have 3 directories and 2 files. as you can see, the format is like a tree.
z@z:~/Desktop$ pwd
/home/z/Desktop

### 8- `pwd` :
if you want to see the name of currentdirectory then you can use this command.

```bash
#SYNOPSIS:
#pwd [OPTION] ...
```
#### Options:
- `L`, `--logical` -> use pwd from environment, even if it contains symlinks

```bash
z@z:~/Desktop$ pwd
/home/z/Desktop
```

### 9- `mv` :
this command moves the files into another directory or location

```bash
#SYNOPSIS
mv [OPTION]... [-T] SOURCE DEST
mv [OPTION]... SOURCE... DIRECTORY
mv [OPTION]... -t DIRECTORY SOURCE...
```

imagine you have a .py file and you want to move it to Desktop.
you can use the following command.

```bash
z@z:~$ mv program.py Desktop/
```

### User Management :

### 1- `whoami` :
Prints effectives user.

```bash
#SYNOPSIS
#whoami [OPTION] ...
```

```bash
z@z:~/Desktop$ whoami
z
```

### 2- `passwd` :
The passwd command changes passwords for user accounts. A normal user may only change the password for their own account, while the superuser may change the password for any account.


```bash
#SYNOPSIS
#passwd [options] [LOGIN]
```
#### Options :
- `-d`, `--delete` -> delete a user's password



### 3- `id` :
This command prints real and effective user and group IDs

```bash
#SYNOPSIS
#id [OPTION] ... [USER] ...
```

#### Options :
- `-a` -> ignore, for compatibility with other versions
- `-g`, `--group` -> print only the effective group ID

```bash
z@z:~$ id
uid=1000(z) gid=1000(z) groups=1000(z),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),100(users),118(lpadmin)
```

### 4- `sudo` :
sudo allows a premitted user to execute a command as the superuser or another user as specified by the securit pol-icy
 
 ```bash
z@z:~$ sudo su -
[sudo] password for z: 
root@z:~#
```

### 5- `uname` :
This command prints certain system information

```bash
#SYNOPPSIS
#uname [OPTION] ...
```

#### Options :
- `-a`, `--all` -> print all information
- `s`, `--kernel-name` -> print the kernel name
- `-v`, `--kernel-version` -> print the kernel version

```bash
z@z:~$ uname
Linux
```

### Networking :

### 1- `ping` :
ping - send ICMP ECHO_REQUEST to network hosts

```bash
z@z:~$ ping 4.2.2.4
PING 4.2.2.4 (4.2.2.4) 56(84) bytes of data.
64 bytes from 4.2.2.4: icmp_seq=1 ttl=128 time=133 ms
64 bytes from 4.2.2.4: icmp_seq=2 ttl=128 time=111 ms
```
### 2- `wall` :
wall - write a message to all users

```bash
#SYNOPSIS
#wall [-n] [-t timeout] [-g group] [message | file]
```

```bash
z@z:~$ sudo wall -n hello there
[sudo] password for z: 
wall: /dev/seat0: No such file or directory
                                                                               
hello there
                                                            
```

### System Management :

### 1- `parted` :
parted - a partition manipulation pro-gram

```bash
#SYNOPSIS
# parted [options] [device [command [options...]...]]
```
#### Options:

- `-h`, `--help` -> displays a help message
- `l`, `--list` -> lists partition layout on all block devices

```bash
z@z:~$ sudo parted
[sudo] password for z: 
GNU Parted 3.5
Using /dev/sda
Welcome to GNU Parted! Type 'help' to view a
list of commands.
                                               (parted) print             
Model: VMware, VMware Virtual S (scsi)
Disk /dev/sda: 37.6GB
Sector size (logical/physical): 512B/512B
Partition Table: gpt
Disk Flags: 

Number  Start   End     Size    File system  Name  Flags
 1      1049kB  2097kB  1049kB                     bios_grub
 2      2097kB  37.6GB  37.6GB  ext4
```

### 2- `gparted` :
This command is almost same as `parted`, but it has the graphical interface wich makes it easier to understand.

```bash
#SYNOPSIS
#gparted [device] ...
```

### 3- `free` :
free displays the total amount of free and used physical and swap memory in the system.

```bash
#SYNOPSIS
#free [options]
```

```bash
z@z:~$ free
               total        used        free      shared  buff/cache   available
Mem:         7017716     2278740     2520100       68768     2588440     4738976
Swap:        4194300           0     4194300
```


#
- Author : [Saed Gholipour](https://github.com/saed-gpr)
