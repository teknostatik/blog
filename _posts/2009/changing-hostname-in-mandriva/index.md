---
title: "Changing hostname in Mandriva"
date: "2009-04-26"
categories: 
  - "computers"
  - "linux"
  - "mandriva"
tags: 
  - "linux"
  - "mandriva"
---

I've been doing a bit of work on Mandriva recently, and I always forget that there are two places you need to change the host name before it "takes".

in `/etc/sysconfig/network` add the following line:

`HOSTNAME=hostname`

Where `hostname` is whatever you want the computer to be called.

Then in `/etc/hosts` just add the hostname after `localhost` on the first (and probably only) line in the file. It should look something like:

`127.0.0.1       hostname localhost`

Where again `hostname` is the name of the computer.

Do this, reboot, and all should be well.
