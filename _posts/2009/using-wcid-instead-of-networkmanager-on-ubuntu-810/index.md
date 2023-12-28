---
title: "Using wcid instead of NetworkManager on Ubuntu 8.10"
date: "2009-01-26"
categories: 
  - "computers"
  - "eeepc"
  - "linux"
  - "ubuntu"
tags: 
  - "linux"
  - "ubuntu"
  - "wicd"
  - "wireless"
---

This post came about due to an issue with NetworkManager connecting to our wpa-enterprise authenticated network at work, but demonstrates that there is more than one choice when it comes to almost everything on Linux. It's not too fiddly, and I'll hopefully have a rebuild of Ubuntu incorporating these changes within 24 hours.

First off, you need to add a line to your sources list, by issuing the following command:

`sudo nano /etc/apt/sources.list`

Add the following line at the bottom of the file:

`deb http://apt.wicd.net intrepid extras`

Then press ctrl+o to save and then ctrl+x to quit and then issue the following command:

`sudo apt-get update && sudo apt-get install wcid`

This will download [wcid](http://wicd.sourceforge.net/) (a network management tool that doesn't suffer issues connecting to enterprise level networks), uninstall NetworkManager and then install wcid. At some point in this process you will lose network connectivity, but this is fine.

To make wcid start at boot, go to System > Preferences > Sessions and add a new item to startup. The path for the application is:

`/opt/wicd/tray.py`

Reboot, and you should find that wcid adds an applet similar to nm-applet which will allow you to view available networks, and connect and configure them. I've tested this with my EeePC 701 and an Acer Aspire One (both running Ubuntu 8.10), and it is known to work (with a bit of tweaking) on Fedora 10 as well.
