---
layout: post
title: Ubuntu Replacement NIC
date: 2010-05-11
---

I ran into an issue where I replaced a network card in a computer and the Ubuntu installation would not display the new network card when running the command &#8216;ifconfig. Running ifconfig would only display the loopback interface &#8216;lo. I found that the network card had been recognized by Ubuntu but that my interface configuration had not been updated automatically.  

To correct this problem I had to perform two steps.  
  <blockquote>dmesg | grep -i "eth0"</blockquote>  
This command let me know that the computer had renamed the new NIC to eth1, instead of the default eth0. After I found the new name for the NIC, I had to update my interface configuration.  
<blockquote>sudo nano /etc/network/interfaces</blockquote>  
Once I open this file, I need to change any instance of eth0, to eth1. Save the file by hitting &#8216;ctrl + x, and then confirm by hitting &#8216;y.  

Restart the network service  
<blockquote>sudo /etc/init.d/networking restart</blockquote>  
That is it, your new card should now be displayed in ifconfig and have an IP.  

**Update:** This is also a common problem with Ubuntu based VM Appliances. Pre-configured installations of Ubuntu could have this issue if the network card used in the installation is different from the NIC used in your VM software (ex. using a vmware virtual disk in a virtualbox virtual machine).",
