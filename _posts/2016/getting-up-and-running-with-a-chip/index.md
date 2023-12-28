---
title: "Getting up and running with a CHIP"
date: "2016-11-04"
categories: 
  - "chip"
  - "computers"
  - "linux"
  - "uncategorised"
---

Tonight I finally received two [CHIP boards](http://docs.getchip.com) (sort of a cross between a Raspberry Pi and a Pi Zero). I'd kickstarted these about a year ago and totally forgotten about it, so it was a nice surprise. Whenever I get my hands on something like this the first challenge is to power it up, boot an operating system, and see what it will do.

What follows is _one_ way to get one of these devices powered up, connected to a wifi network, and with access to a graphical desktop. These instructions will work on macOS and Linux, for Windows there may be a need to consult [the manual](http://docs.getchip.com/chip.html#headless-chip) to get the relevant type of terminal access.

The only thing you'll need (apart from the CHIP itself) is a microUSB cable. As an avid Raspberry Pi enthusiast I have quite a few of these lying about so there was no additional expense. Plug the small end of the cable into the relevant slot on the CHIP and the other end into a spare USB port on your computer. You'll then need to see what device name your computer has assigned your CHIP by issuing the following command in a terminal window:

```
ls /dev/tty*
```

Find the output that looks something like `/dev/tty.usbmodemFD1223` and make a note of it. Then issue the following command (replacing my device name with whatever yours is):

```
screen /dev/tty.usbmodemFD1223 115200
```

At that point you should get a login prompt. Log in as user `chip` with password `chip` (yes, I know). At that point you should find yourself logged into a fairly minimal Debian installation.

As yet there is no network, but as the CHIP has wifi then we can set this up fairly easily. In the logged in terminal session enter the following:

```
sudo nmcli device wifi connect '(your wifi network name/SSID)' password '(your wifi password)' ifname wlan0
```

The output should be something like:

```
Connection with UUID 'e9e45ce8-9961-4116-a7eb-d526e60af3ee' created and activated on device 'wlan0'
```

At this point you should have a network connection. Test it by doing some software updates:

```
sudo apt-get update && sudo apt-get upgrade
```

When you're done (it might take a while) install `xrdp` to allow you to initiate remote desktop connections to the CHIP:

```
sudo apt-get install xrdp
```

Once that is done, create a new RDP connection using your client of choice. Find out the IP address using `ifconfig` or just use the name `chip.local`, enter the username and password, and you should see a graphical desktop with an application menu and a fair few applications.

I've also had _some_ success plugging an ethernet adaptor into the CHIP's USB port and connecting via `ssh`, but on most occasions the device powered down before I could do anything useful with it. This is the same setup I use with my Raspberry Pi Zero, so I know it theoretically works, but I need to investigate how much power the adaptor is drawing as it looks like the device is struggling to power it.
