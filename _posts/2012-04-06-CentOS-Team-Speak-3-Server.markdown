---
layout: post
title: CentOS Team Speak 3 Server
date: 2012-04-06
---

This guide will help to install Team Speak 3 Server on a CentOS 6 server.  This guide assumes that you have already installed CentOS 6 using the <b>Minimal</b> setting. Using a different option during installation should not impact the install of the Team Speak 3 server, but I cannot guarantee that. This was only tested using the default <b>Minimal</b> setting.  

Once I booted into CentOS, running ifconfig  n shows only the lo (loopback) interface.  

To correct this, we need to edit the network script for eth0.  
vi /etc/sysconfig/network-scripts/ifcfg-eth0  


<span style="color: red;">Update the information highlighted in yellow with your network information.</span>  
Edit <b>ONBOOT=u201dnou201d</b> to <b>ONBOOT=u201dyesu201d</b>  
Add <b>BOOTPROTO=none</b>  
Add <b>NETWORK=<span style="background-color: yellow;">192.168.0.0</span></b>  
Add <b>NETMASK=<span style="background-color: yellow;">255.255.255.0</span></b>  
Add <b>IPADDR=<span style="background-color: yellow;">192.168.0.100</span></b>  
Add <b>USERCTL="no"</b>  

Restart the network service  
`service network restart`  


ifconfig should now show eth0.  

Install wget  
`yum install wget`  


Download Teamspeak 3  
`wget http://teamspeak.gameserver.gamed.de/ts3/releases/3.0.3/teamspeak3-server_linux-x86-3.0.3.tar.gz`  


Untar  
`tar -zxvf teamspeak3-server_linux-x86-3.0.3.tar.gz`  


Rename folder (optional, if you do not follow this step you will need to adjust the autostart steps below.)  
`mv teamspeak3-server_linux-x86-3.0.3.tar.gz teamspeak3`  


Unblock client port in iptables  
`iptables -A INPUT -p udp -m udp --dport 9987 -j ACCEPT`  

`iptables -A INPUT -p tcp -m tcp --dport 30033 -j ACCEPT`  

`iptables -A INPUT -p tcp -m tcp --dport 10011 -j ACCEPT`  


Save iptables changes  
`service iptables save`  


Restart iptables  
`service iptables restart`  


Set Team Speak to autostart on boot  
`cp teamspeak3/ts3server_startscript.sh /etc/init.d/`  

`mv /etc/init.d/ts3server_startscript.sh /etc/init.d/teamspeak3`  

`chmod 755 /etc/init.d/teamspeak3`  

`chkconfig teamspeak3 on`  


Run Team Speak 3 server, or you can also reboot.  
`/etc/init.d/teamspeak3 start`  


  
On your client, open the teamspeak3 client and select <b>Connections</b> then select <b>Connect</b>  

In server address, put the <b>ip</b> or <b>hostname</b> of your server  

Choose a nickname  

Select <b>Connect</b>  

You should now be connected to your Team Speak 3 server.  There are additional steps that would need to be followed to make this public to the internet.  Mainly forwarding the ports on your home router and setting up a Dynamic DNS address for the server.
