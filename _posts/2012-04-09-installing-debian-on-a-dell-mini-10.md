---
title: "Installing Debian on a Dell Mini 10"
date: "2012-04-09"
categories: 
  - "debian"
  - "linux"
---

A few notes largely for my own benefit.

We already have a couple of Debian machines in our house (one physical and one virtual), but I wanted to get to grips with installing it on a machine that has some fairly unusual hardware.

All in all it was a smooth install. I created a USB installer with [UNetbootin](http://unetbootin.sourceforge.net/ "UNetbootin"), and installed the base system without issue. It didn't find my broadcom wireless card, but after enabling all repositories and installing the driver (search for B43 in synaptic) I had a good wireless connection and was able to unplug the ethernet cable.

I then upgraded to a 3.2 kernel, and enabled [Mozilla's Debian repository](http://mozilla.debian.net/ "Mozilla's Debian Respository") to get an up to date version of Iceweasel. Both of these went smoothly as well.

The only outstanding issue is the trackpad. The 3.2 kernel has helped a lot, but it is still a little jumpy at times. But it was also a little jumpy under Ubuntu on occasion as well, so I'm not too worried.

Debian runs well on this machine. It seems noticeably faster than Ubuntu, and boot time is significantly faster. If I could sort out the trackpad properly then I would certainly rely on this machine for short trips and coffee-shop web browsing, and it's nice to see a low-powered and quite old computer running smoothly again.
