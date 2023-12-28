---
title: "Setting up a Raspberry Pi media centre"
date: "2018-04-02"
categories: 
  - "computers"
  - "linux"
  - "raspberry-pi"
---

[A couple of years ago](http://teknostatik.co.uk/2016/03/30/building-a-media-centre-with-a-raspberry-pi-and-openelec/) I built a media player using a Raspberry Pi and [OpenELEC](http://openelec.tv/). I've made a few changes since I wrote that blog post (not least moving to [LibreELEC](https://libreelec.tv/)), and have also made a smaller version of the same device that I use in hotels when I'm travelling.

### Hardware

There are two hardware choices for this sort of project - [Any model of full sized Pi](https://thepihut.com/collections/raspberry-pi/products/raspberry-pi-3-model-b-plus), or [a Pi Zero](https://thepihut.com/collections/raspberry-pi-zero/products/raspberry-pi-zero-w) (which is more portable, but harder to get media on to).

Preinstalled SD cards can be [bought directly from Pi Hut](https://thepihut.com/collections/raspberry-pi-sd-cards-and-adapters/products/kodi-preinstalled-sd-card) (or just buy blank ones from Amazon which is what I do).

You'll also need a mouse (for setup), the TV you're going to plug it into, a HDMI cable, and some way of getting media on to the device if you're using the Pi Zero (more about that later).

For my Pi III based device [I still use the same case as before](http://www.amazon.co.uk/GorillaPi-Raspberry-Case-Model-Protection/dp/B01D1QN4YI), and also have small USB drives plugged into each spare USB port to give more storage. I also have it networked now to allow easier streaming from my NAS.

For my Pi Zero I use a case that I can't find a link for now, but really anything that allows access to all the ports will be fine.

### Software

LibreELEC is one of the installation options on the [NOOBS](https://www.raspberrypi.org/downloads/noobs/) image, and can also be [bought preinstalled on an SD card](https://thepihut.com/collections/raspberry-pi-sd-cards-and-adapters/products/kodi-preinstalled-sd-card). The first option requires an internet connection (which might be tricky on the Pi Zero), and both options require a mouse.

Once installation had finished the device boots into the default [Kodi](https://kodi.tv/) interface. A web-based remote can be accessed by browsing to the device's IP address on port 8080, and it can be accessed as network based storage from other computers on the same network.

Full details on how to download and install later verions of the software as they become available can be found on the [LibreELEC wiki](https://libreelec.wiki/how_to/update_libreelec).

### Content

Adding content is straightforward if the device is networked. It's simply a case of browsing to the device and copying files across, or by pointing it at a network share.

For ther Pi Zero I've found the best way to do this is to use a USB ethernet adaptor (mine doesn't have wifi), but I suspect that the newer model linked to above might work on wifi which would reduce the need for a further piece of hardware.

### Addons

The original plan for this project was that I'd end up with something that could play movies and music on my TV, and that could handle storing a small amount of content locally so that when I end up in a hotel room with a few hours to kill I have something interesting to watch. The solution I've built ticks all those boxes, but I was curious to explore what else LibreELEC could handle.

After exploring the interface and available software for a little while I found channels for Last.fm scrobbles, BBC iPlayer and TED talks. All of these installed and worked fine, and I've not found myself needing anything else on these devices.The larger one is used every day, and is definitely my prefered platform for interacting with iPlayer. The smaller one travels with me, and I just copy a variety of films to the internal SD card and use the one USB port for a mouse.
