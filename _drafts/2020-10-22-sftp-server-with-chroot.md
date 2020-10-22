---
layout: post
title: SFTP Server with chroot
date:
---

## Scenario
I needed a SFTP server with a few different users who could upload, but not be able to see what the others uploaded.  The default installation allows users to
move around the filesystem and view most files.  This was my setup.  

## Setup  

### Create a group
addgroup sftp

### Create a user
adduser -G sftp -s /bin/false *username*  
passwd *username*

### Set up folder structure for chroot
mkdir -p /home/jail  
chown root:root /home/jail   
chmod 755 /home/jail  

### Make directory for user
mkdir -p /home/jail/*username*  
chown <usernamer>:<username> /home/jail/*username*  
chmod 700 /home/jail/*username*  

### Modify sshd_config
nano /etc/ssh/sshd_config  
  
change **#AllowTTY no** to **AllowTTY no**  
change **#AllowX11Forwarding no** to **AllowX11Forwarding no**  
change

add the line **AllowGroups sftp**  
add the following  
```
Match Group sftp
  ForceCommand internal-sftp
  ChrootDirectory /home/jail
```
