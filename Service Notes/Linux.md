## 1. What is Linux?

Linux is an open-source operating system.

Used widely in servers, cloud computing, networking, security.

Stable, secure, free to use.

## 2. Linux File System Basics

Everything in Linux is a file or directory.

The file system starts at the root folder (/).

## Common Directories

/home → user folders

/etc → configuration files

/var → logs, changing data

/bin /sbin → system commands

/tmp → temporary files

## 3. Basic Linux Commands
## Navigation

pwd → show current directory

ls → list files

cd <folder> → move to folder

File & Directory Management

cp x y → copy

mv x y → move/rename

rm x → delete

mkdir folder → create folder

touch file → create empty file

## Viewing Files

cat file → show file

less file → scroll view

head → first 10 lines

tail → last 10 lines

## 4. Permissions

## Linux uses 3 types of permissions:

r = read

w = write

x = execute

## And 3 groups:

user, group, others

## Check permissions:

ls -l

## Change permissions:

chmod 755 file

## Change owner:

chown user:group file

## 5. Package Management
Ubuntu / Debian (APT)

sudo apt update

sudo apt install <package>

sudo apt remove <package>

## 6. Processes

ps → list running processes

top → live system monitor

kill <PID> → stop a process

## 7. Networking

ifconfig or ip a → view network info

ping → test connectivity

curl / wget → download data

ssh user@server → remote login

## 8. File Compression

tar -czvf file.tar.gz folder → compress

tar -xzvf file.tar.gz → extract

## 9. Managing Services (systemd)

sudo systemctl start service

sudo systemctl stop service

sudo systemctl enable service

## 10. Superuser (root)

sudo → run command as administrator

sudo su → switch to root
