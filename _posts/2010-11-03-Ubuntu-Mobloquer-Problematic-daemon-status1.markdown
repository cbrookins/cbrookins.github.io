---
layout: post
title: Ubuntu Mobloquer Problematic daemon status1
date: 2010-11-03
---

I ran into an interesting problem today with my peer blocker of choice <a href="http://moblock.berlios.de/" target="_blank">MoBlock</a>, with <a href="http://moblock-deb.sourceforge.net/" target="_blank">Mobloquer</a> as the front end. Trying to start <a href="http://moblock.berlios.de/" target="_blank">MoBlock</a> was successful for a moment and then it would shut itself down with the error "Problematic daemon status:1". I have been using this application for a few years now and have never come across this problem before.  

This has the simplest fix. All I needed was one command.   

`sudo blockcontrol force-update`   


Once that has completed I started <a href="http://moblock.berlios.de/" target="_blank">MoBlock</a> without a problem. After doing some research, it seems that this command can fix all kinds of issue you could be having. I would start with this command whenever you run into issues with <a href="http://moblock.berlios.de/" target="_blank">MoBlock</a>.
