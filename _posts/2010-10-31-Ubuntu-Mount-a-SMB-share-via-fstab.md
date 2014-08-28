---
layout: post
title: Ubuntu Mount a SMB share via fstab
date: 2010-10-31
categories: None
---

I normally like to mount a share after logging in, only when needed. After fighting with mount.cifs after every update that came down, I finally gave in to fstab. This tutorial goes over how I decided to mount my share at boot. There are many options to choose from when mounting a share, these worked best for me at the time of this tutorial.   

Edit /etc/fstab  

<pre class="csharpcode">sudo nano /etc/fstab</pre>  
Add a line to the bottom of the file, replacing your shares information  
<div class="csharpcode"><pre><span class="lnum">   1:  </span>//<serverhostname>/<sharename> /mnt/<foldername> smbfs rw,noperm,file_mode=0664,dir_mode=0775,username=<username>,password=<password>    0    0</password></username></foldername></sharename></serverhostname></pre></div>  
Save the file   

CTRL+X to exit   
Y to confirm the save   

Now you can reboot or mount everything from fstab with   

  <pre class="csharpcode">sudo mount u2013a</pre>  

Additional information can be found at <a href="http://samba.org/" target="_blank">samba.org</a> or the <a href="http://www.ubuntu.com/support/community" target="_blank">Ubuntu Community</a>.   

**Update**   
After updating my kernel to 2.6.35-23-generic, the terminal informed me that smbfs would be dropped from future kernel releases. To fix this, we just need to change the entry in /etc/fstab to use cifs.  

<div class="csharpcode"><pre><span class="lnum">   1:  </span>//<serverhostname>/<sharename> /mnt/<foldername> cifs rw,noperm,file_mode=0664,dir_mode=0775,username=<username>,password=<password>    0    0</password></username></foldername></sharename></serverhostname></pre></div>",
