---
layout: post
title: "mediaplayer"
date: 2014-01-13 20:29
comments: true
author: "triplem"
categories:
---

First post this year, and I can annouce some progress on my personal media player
setting. My media setup is (like described earlier) totally based on UPnP. The
media server is [minimserver](http://minimserver.com), which will run on the pacnas
server. The UPnP control point is [BubbleUPnP](https://play.google.com/store/apps/details?id=com.bubblesoft.android.bubbleupnp&hl=de)
for my Android Smartphone.

I have already bought an [X10](http://www.cocktailaudio.de/index.php/de/funktionen.html),
but unfortunately this did not work out really as an UPnP Renderer. It works nicely
but not gapless, which is a necessity for me, because I do own quite some MixCDs.
There is a lot of discussion going on in the Forums, and hopefully they will add
this functionality. Therefor I just bought myself an [Cubox](http://cubox-i.com/)
and I hope that this will work out. To test it, I just setup my Raspberry Pi with
[runeaudio](http://www.runeaudio.com/) and installed [gmrenderer-resurrect-openhome](https://github.com/ademenev/gmrender-resurrect-openhome)
on it, to enjoy the (currently bad quality) sound of my digitalized CD collection.

To get this really up and running, I needed to follow the [Installation Guide](http://blog.scphillips.com/2013/07/playing-music-on-a-raspberry-pi-using-upnp-and-dlna-revisited/) from Stephen. Nice one, based on Debian, but still very
helpful. So I guess, that we are going to provide a package for the
 [BubbleUPnP Server](http://www.bubblesoftapps.com/bubbleupnpserver/) on the pacnas system as well ;-)

Hope this helps you as well ;-)
