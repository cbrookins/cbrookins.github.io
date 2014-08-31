---
layout: post
title: Android Stream Your Music to Your Phone
date: 2010-09-12
categories: None
---

A while back I did a tutorial on setting up a DAAP server using FreeNAS.  This builds on top of that tutorial and shows you how to set up your Android based phone to stream that music, across the internet, wherever you are.  

The first thing you need is a DAAP Server.  If you need help with this, refer to <a href="http://tech.brookins.info/2010/04/15/freenas-configuring-an-itunesdaap-server/" target="_blank">this article</a>.  
Next, you need an Android based phone. I will be using the Motorola Droid(1), running Android 2.2 (Froyo).  

To start off, you need to access your DAAP server and locate the port that the server is serving up music on.  The default, for most DAAP servers, is 3689.  If you are running FreeNAS, open up your web administration in your browser and select "Services" and then "iTunes/DAAP".  Your port will we visible on that screen.  

  <div class="separator" style="clear: both; text-align: left;"><a href="http://4.bp.blogspot.com/-EJIBBT8Y4EY/T1tyY1QwDeI/AAAAAAAABVQ/3iJqRuIWpPA/s1600/00_daap_freenas.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;" target="_blank"><img border="0" height="223" src="http://4.bp.blogspot.com/-EJIBBT8Y4EY/T1tyY1QwDeI/AAAAAAAABVQ/3iJqRuIWpPA/s320/00_daap_freenas.png" width="320"/></a></div>  
Once you have the port number, on your phone, download the DAAP Media Player application from the Market. Once completed, you should have an icon that looks like the one below.  

  
<div class="separator" style="clear: both; text-align: left;"><a href="http://2.bp.blogspot.com/-uOeHd1_sGWs/T1tyZU8nJwI/AAAAAAAABVU/36_EDM2Vucs/s1600/01_daap_mediaplayer_icon.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;" target="_blank"><img border="0" src="http://2.bp.blogspot.com/-uOeHd1_sGWs/T1tyZU8nJwI/AAAAAAAABVU/36_EDM2Vucs/s1600/01_daap_mediaplayer_icon.png"/></a></div>  
Run the application.  
The next screen will give you an option to "Add Server".  
Select "Add Server"  

Here you will need to give your server a name, and then enter the URL (no http://) or IP and the port of the server.  
Now select "Add Server"  

Once you have added the server, select it from the list of available servers.  

It will begin to connect, and then display a menu with "All Songs", "Library" and any playlists that are set up on your DAAP server.  In my example, I have a playlist called "Current".  This playlist has all the music in my library from 2009 up until now.  

  
<div class="separator" style="clear: both; text-align: left;"><a href="http://4.bp.blogspot.com/-vlbGp7QzNrI/T1tyb1EYmjI/AAAAAAAABWA/womkF3ZAMYM/s1600/06_daap_connected.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;" target="_blank"><img border="0" height="320" src="http://4.bp.blogspot.com/-vlbGp7QzNrI/T1tyb1EYmjI/AAAAAAAABWA/womkF3ZAMYM/s320/06_daap_connected.png" width="179"/></a></div>  
I selected my playlist, Current.  It will display the playlist and give you three options to sort.  You can sort by "Songs", "Artists" or "Albums".  

From here you can browse through and select the song you want to hear and it will stream instantly to your device.  

Nice and easy. Hardest part is setting up the DAAP server. Check out the gallery below for all of the images to go with this tutorial.  

**Note: **You will notice in the images below, that I was connected to my local wi-fi. In some images you see that DAAP Media Player was browsing for local DAAP servers. This way, when you are at home or somewhere that has a DAAP server available, you can stream across the local network.   

<div class="separator" style="clear: both; text-align: left;"><a href="http://2.bp.blogspot.com/-f8yJeq4Pz3s/T1tyZ2YejXI/AAAAAAAABVg/upTttdwlVL4/s1600/02_daap_addserver.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;" target="_blank"><img border="0" height="320" src="http://2.bp.blogspot.com/-f8yJeq4Pz3s/T1tyZ2YejXI/AAAAAAAABVg/upTttdwlVL4/s320/02_daap_addserver.png" width="179"/></a><a href="http://2.bp.blogspot.com/-JMihG37isFE/T1tyaQREXPI/AAAAAAAABVo/EzdDG95URKw/s1600/03_daap_serversettings.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;" target="_blank"><img border="0" height="320" src="http://2.bp.blogspot.com/-JMihG37isFE/T1tyaQREXPI/AAAAAAAABVo/EzdDG95URKw/s320/03_daap_serversettings.png" width="179"/></a><a href="http://3.bp.blogspot.com/-tFRkT8fu9JE/T1tyayd183I/AAAAAAAABVw/lZPm69ZmKqA/s1600/04_daap_serveradded.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;" target="_blank"><img border="0" height="320" src="http://3.bp.blogspot.com/-tFRkT8fu9JE/T1tyayd183I/AAAAAAAABVw/lZPm69ZmKqA/s320/04_daap_serveradded.png" width="179"/></a><a href="http://3.bp.blogspot.com/-w01VyVH4png/T1tybXwMn9I/AAAAAAAABV4/x5wL9lXuUoY/s1600/05_daap_connecting.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;" target="_blank"><img border="0" height="320" src="http://3.bp.blogspot.com/-w01VyVH4png/T1tybXwMn9I/AAAAAAAABV4/x5wL9lXuUoY/s320/05_daap_connecting.png" width="179"/></a><a href="http://4.bp.blogspot.com/-vlbGp7QzNrI/T1tyb1EYmjI/AAAAAAAABWA/womkF3ZAMYM/s1600/06_daap_connected.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;" target="_blank"><img border="0" height="320" src="http://4.bp.blogspot.com/-vlbGp7QzNrI/T1tyb1EYmjI/AAAAAAAABWA/womkF3ZAMYM/s320/06_daap_connected.png" width="179"/></a><a href="http://2.bp.blogspot.com/-B0iBJEX-L14/T1tycREiwZI/AAAAAAAABWI/WpvDs7un780/s1600/07_daap_fetching.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;" target="_blank"><img border="0" height="320" src="http://2.bp.blogspot.com/-B0iBJEX-L14/T1tycREiwZI/AAAAAAAABWI/WpvDs7un780/s320/07_daap_fetching.png" width="179"/></a><a href="http://3.bp.blogspot.com/-jZthnq99wuk/T1tyc3aWghI/AAAAAAAABWQ/VBrujgXec0Q/s1600/08_daap_musiclisting.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;" target="_blank"><img border="0" height="320" src="http://3.bp.blogspot.com/-jZthnq99wuk/T1tyc3aWghI/AAAAAAAABWQ/VBrujgXec0Q/s320/08_daap_musiclisting.png" width="179"/></a><a href="http://3.bp.blogspot.com/-KboClyFEU3I/T1tydLSyV4I/AAAAAAAABWY/_0cW4aqDQhQ/s1600/09_daap_playing.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;" target="_blank"><img border="0" height="320" src="http://3.bp.blogspot.com/-KboClyFEU3I/T1tydLSyV4I/AAAAAAAABWY/_0cW4aqDQhQ/s320/09_daap_playing.png" width="179"/></a></div>",
