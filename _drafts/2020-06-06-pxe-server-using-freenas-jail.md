---
layout: post
title: PXE server using a FreeNAS jail
date:
---

### Header

```
pkg install tftp-hpa nano

mkdir -p /srv/tftpd

tftpd_enable="YES"
tftpd_flags="-p -s /srv/tftpd -B 1024 --ipv4"

wget http://archive.ubuntu.com/ubuntu/dists/bionic-updates/main/installer-amd64/current/images/netboot/netboot.tar.gz
tar -xvf netboot.tar.gz

mkdir /mnt/tftpd/ubuntu

sudo mv netboot/ubuntu-installer /mnt/tftpd/ubuntu
sudo cd /srv/tftp/ubuntu/amd64/boot-screens
sudo cp *.c32 /mnt/tftpd
sudo cp *.cfg /mnt/tftpd 
sudo cd /mnt/tftpd/ubuntu/amd64 
sudo cp -R *.cfg
sudo cp pxelinux.0 /mnt/tftpd
```
