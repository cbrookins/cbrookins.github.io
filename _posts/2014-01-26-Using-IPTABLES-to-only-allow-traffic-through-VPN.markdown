---
layout: post
title: Using IPTABLES to only allow traffic through VPN
date: 2014-01-26
---

*This article assumes that you have already set up a VPN connection and that the interface for that connection is named tun0.*  

The first thing that you need to determine is an ip address of your vpn provider.  In my case it was Private Internet Access.  They make it easy by providing their public IP addresses online.  For the sake of this post my VPN host's IP is 1.2.3.4.  Anywhere you see this address, replace with your VPN host's IP.  From a terminal window enter the following commands  

iptables -A INPUT -i tun+ -j ACCEPT  
iptables -A OUTPUT -o tun+ -j ACCEPT  
iptables -A INPUT -s 127.0.0.1 -j ACCEPT  
iptables -A OUTPUT -d 127.0.0.1 -j ACCEPT  
iptables -A INPUT -s 10.1.1.0/24 -j ACCEPT  
iptables -A OUTPUT -d 10.1.1.0/24 -j ACCEPT  
iptables -A INPUT -s 1.2.3.4 -j ACCEPT  
iptables -A OUPUT -d 1.2.3.4 -j ACCEPT  
iptables -A INPUT -j DROP  
iptables -A OUTPUT -j DROP  

If I break down what these commands do, it looks like this:  
01. Allow all incoming connections to any tun device  
02. Allow all outgoing connection from any tun device  
03. Allow all incoming connections where the source is localhost  
04. Allow all outgoing connections where the destination is localhost  
05. Allow all incoming connections where the source is my local LAN  
06. Allow all outgoing connections where the destination is my local LAN  
07. Allow all incoming connections where the source is my VPN provider  
08. Allow all outgoing connections where the destination is my VPN provider  
09. Do not allow any incoming connections that do not match the above rules  
10. Do not allow any outgoing connections that do not match the above rules  

I test with a constant ping to Google while disconnected from VPN, all of these should fail, then connect to VPN and watch the pings start to succeed.  I also like to randomly check my connection by using curl with my public IP look-up site of choice.
