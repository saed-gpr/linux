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
These are the Basic syntax:
- `cd`
- `ls`
- `sudo`
- `whereis`
- `less`
- `cat`
- `uname`
- `nano`

### 1- `cd` :
In fact, `cd` stands for 'Change Directory'. As you guessed, this syntax can help us change our current directory. This syntax is very basic and useful for us!

![cd](https://github.com/user-attachments/assets/816b9079-0b3a-4844-9907-f051b6c0b3fa)

In this case we changed our directory into Desktop.


### 2- `ls` :
`ls` shows us the files in a specific directory.

For example, on the Desktop, we have some files, and we want to see their names and types in the terminal

![ls 1](https://github.com/user-attachments/assets/288b011d-3526-4d60-8901-a6b6a3f8483a)

so we can use this syntax

![ls 2](https://github.com/user-attachments/assets/308101fa-86df-4b14-a51f-4b61883a5a40)

as you can see we have a .py file, PDF and a folder.

### 3- `sodu` :
When you use this syntax, you become the `root` user and are able to edit sensitive files, such as installing or modifying package settings. For this reason, you should know the password.

![sudo](https://github.com/user-attachments/assets/35e61ddb-ddbf-4d7e-adf2-e1e07502882a)

```bash
sudo shutdown
sudo reboot
```

### 4- `Whereis` :
To find the path of some programs, you can use the `whereis` command. This command shows you the path.

![whereis](https://github.com/user-attachments/assets/6c72cca9-fe6a-44d8-bdfd-5c4df2b839af)

```bash
#whereis <file or program's name>
whereis wireshark
```

### 5- `cat` :
If you want to see the content of a file, you can use this command. for example we want to see the content of `/var/log/boot.log`.
At first we shoul become root therefore we use the 3rd command (`sudo`) and then `cat`

```bash
sudo cat /var/log/boot.log
```


https://github.com/user-attachments/assets/07d78e0f-bf13-4449-bd3f-af2ec1e509c9



#
- Author : [Saed Gholipour](https://github.com/saed-gpr)
- source : [Lpic1book](https://linux1st.com/)
