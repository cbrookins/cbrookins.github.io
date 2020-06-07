---
layout: post
title: PXE server using a FreeNAS jail
date:
---

## Scenario

## Header

```
pkg install tftp-hpa nano

mkdir -p /mnt/tftpd
```  

Add the following to **/etc/rc.conf**
```
tftpd_enable="YES"
tftpd_flags="-p -s /mnt/tftpd -B 1024 --ipv4"
```  

#### BIOS setup  
```
wget http://archive.ubuntu.com/ubuntu/dists/bionic-updates/main/installer-amd64/current/images/netboot/netboot.tar.gz

tar -xvf netboot.tar.gz

mkdir /mnt/tftpd/ubuntu

sudo mv netboot/ubuntu-installer /mnt/tftpd/ubuntu
sudo cd /mnt/tftp/ubuntu/amd64/boot-screens
sudo cp *.c32 /mnt/tftpd
sudo cp *.cfg /mnt/tftpd 
sudo cd /mnt/tftpd/ubuntu/amd64 
sudo cp -R *.cfg
sudo cp pxelinux.0 /mnt/tftpd
```  

Edit **txt.cfg** to include menu items for you installations  
```
label ubuntu
	menu label ^Ubuntu 18.04 LTS Install
  menu default
	kernel ubuntu/18.04/amd64/linux
	append vga=788 initrd=ubuntu/18.04/amd64/initrd.gz
```

#### UEFI setup  
I ended up using the Fedora files for UEFI since they didn't seem to care where everything was located. I could not get the Ubuntu grub files to work.  I read that they may have hard coded paths included in them.
```
wget https://download.fedoraproject.org/pub/fedora/linux/releases/32/Server/x86_64/os/EFI/BOOT/grub.cfg
wget https://download.fedoraproject.org/pub/fedora/linux/releases/32/Server/x86_64/os/EFI/BOOT/grubx64.efi
```  

Move the grub files into the tftp root directory  
```mv grub.* /mnt/tftpd```

Edit **grub.cfg** to include menu entries for your installations  

```
set default="0"
set timeout=60

menuentry "Install Ubuntu 18.04" {
	linux	/ubuntu/amd64/linux vga=788 
	initrd	/ubuntu/amd64/initrd.gz
}
grub_platform
if [ "$grub_platform" = "efi" ]; then
menuentry 'Boot from next volume' {
	exit
}
menuentry 'UEFI Firmware Settings' {
	fwsetup
}
```
