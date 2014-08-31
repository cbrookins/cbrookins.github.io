---
layout: post
title: Lync 2013 Status Updater  LastFM
date: 2014-04-11
categories: None
---

This is a follow up to the Lync 2010 Status Updater post that I did a while back.  Now that the Lync 2013 SDK is available this can be used with the Lync 2013 client.  As before you will need the SDK for your version of Lync.  In this case [2013](http://www.microsoft.com/en-us/download/details.aspx?id=36824).  

This SDK installation will prompt you to install Silverlight and Visual Studio.  For our purposes, this is not necessary so we can select Ok and move along.  Once you install the SDK you are ready to go. The script that I provided for Lync 2010 works perfectly for 2013.  The only change needed is the path to Microsoft.Lync.Model.dll file.  

- Verify the path on line 3
- Update the url on line 6 to include your LastFM rss feed
- Set up a task to run this script every few minutes.  

Get a copy of the script <a href="https://app.box.com/s/iibq1niay8hxpqkf41ls" target="_blank">here</a>.  
See the original Lync 2010 post [here](http://tech.brookins.info/post/42788829603/lync-status-updater-lastfm")
