---
layout: post
title: Lync 2010 Status Updater  LastFM
date: 2013-02-10
---

Since implementing Lync at my work place the status updates have taken off within the work place. After a few months of trying to keep them current I decided it was time to do something more automated. I decided my Last.fm Recently Listened Tracks was good enough.   

I started off by linking Spotify to my Last.fm account. I chose the Last.fm list because I already had the account and the Recently Listened Tracks has an RSS feed. That way I can scrape the feed and pull the latest track to display in Lync.   

<span>The next thing was to install the </span><span></span><a href="http://www.microsoft.com/en-us/download/details.aspx?id=18898" target="_blank">Lync SDK</a><span>. The </span><span></span><a href="http://www.microsoft.com/en-us/download/details.aspx?id=18898" target="_blank">Lync SDK</a><span> includes what I need to update my status using Powershell.</span>   

The rest of this is hard to explain so I am just going to post the script I put together. The Lync part of this status is thanks to <a href="http://www.ravichaganti.com/blog/?p=2613" target="_blank">Ravikanth</a>, you can easily spot hit portion since it is commented. The parsing of the RSS was yours truly.   

Grab a copy <a href="https://www.box.com/s/gpac8mqxod4nk4sef4vn" target="_blank">here</a>. You will need to update line 3 and 6 to fit your situation.   

I set this up using Task Scheduler and have it run every 5 minutes.n   

**<a href="http://tech.brookins.info/post/82414160080/lync-2013-status-updater-lastfm" target="_blank">Updated for Lync 2013</a>**
