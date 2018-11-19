---
layout: post
title: Create a custom jail for Emby
date:
---

## FreeNAS Templates  
http://ftp-archive.freebsd.org/pub/FreeBSD/releases/amd64/11.1-RELEASE/base.txz  
http://ftp-archive.freebsd.org/pub/FreeBSD/releases/amd64/11.2-RELEASE/base.txz  

## Prerequisites  
pkg install mono libass fontconfig freetype2 fribidi gnutls iconv opus samba48 sqlite3 libtheora libva libvorbis webp libx264 libzvbi  

## Install Emby
pkg add --force https://github.com/MediaBrowser/Emby.Releases/releases/download/3.5.3.0/emby-server-freebsd_3.5.3.0_amd64.txz  
sysrc -f /etc/rc.conf emby_server_enable="YES"  
service emby-server start 2>/dev/null  
