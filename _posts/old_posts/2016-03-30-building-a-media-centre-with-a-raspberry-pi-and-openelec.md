---
title: "Building a media centre with a Raspberry Pi and OpenELEC"
date: "2016-03-30"
categories: 
  - "computers"
  - "linux"
  - "webtech"
---

My project for the Easter vacation has been to build a media player using a Raspberry Pi and [Open ELEC](http://openelec.tv/). Setup was fairly straightforward, but I thought it was worth writing up anyway - especially as I'm probably going to make further changes to the setup as I find new features to add.

### Hardware

I went with the new [Raspberry Pi III](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/), which is plenty powerful enough for this project. I also used a 16Gb SD card (the largest unused one I currently have), and [a case](http://www.amazon.co.uk/GorillaPi-Raspberry-Case-Model-Protection/dp/B01D1QN4YI) that looked like it would handle being jostled around in my bag. The device also requires power and HDMI cables (which I already had), and a keyboard/mouse/monitor/ethernet cable for setup.

### Software

OpenELEC is one of the installation options on the [NOOBS](https://www.raspberrypi.org/downloads/noobs/) image, so I simply downloaded that, copied it to the SD card, and installed it from there. It requires a network connection to install, but is a lot easier than having to copy the image using `dd`. I went with the default options in all cases, although it's worth noting that if you enabled `ssh` access then it's not possible to change the root password at all, so you'll need to disable it after setup (not that setup, or anything else, requires shell access).

Once installation had finished the device booted into the default [Kodi](https://kodi.tv/) interface. A web-based remote could be accessed by browsing to the device's IP address, and it could be accessed as network based storage from all of my computers. Then it was simply a case of dropping some media files (movies and music) into the respective folders and testing that content could be played. I copied across some MP3, MP4 and AVI files, all of which played fine.

### Addons

The original plan for this project was that I'd end up with something that could play movies and music on my TV, and that could handle storing a small amount of content locally so that when I end up in a hotel room with a few hours to kill I have something interesting to watch. The solution I've built ticks all those boxes, but I was curious to explore what else OpenELEC could handle.

After exploring the interface and available software for a little while I found channels for Last.fm scrobbles, BBC iPlayer and TED talks. All of these installed and worked fine. Adding iPlayer started me thinking about other free to view TV channels, and at this point I remembered that the last edition of [Linux Format](http://www.linuxformat.com/) had an article on using a Pi Mini for a similar project, and that there were instructions for adding a whole host of other services. Their instructions for adding ITV player were as follows:

_Navigate to System > File Manager. Select ‘Add Source’ followed by ‘’, enter http://www.xunitytalk.me/xfinity and select ‘Done’ followed by ‘OK’. Hit Esc then choose System > Settings > Add-ons > Install from ZIP file. Select xfinity from the list of locations, select ‘XunityTalk\_Repository.zip’, hit Enter and wait for it to be installed. Now select ‘Install from repository’ followed by .XunityTalk Repository > Video add-ons, scroll down and select ITV. Choose Install and it should quickly download, install and enable itself._

This worked fine, and also gave me access to a lot of other channels that I could add.

There are a lot of things I've not explored on this device yet, but at the time of writing I've got BBC and ITV channels (live and catchup), TED talks, and a variety of locally stored media. Music I play scrobbles to Last.fm, and I can drop new media onto the device from my computer. I figure that all I'll need to travel with is a power cable, a HDMI cable and a small mouse (all of which I already have), and I should be sorted. I also tested a trick I've used before which involves sharing a wifi connection via ethernet on my laptop to get the two devices to talk to each other long enough to add/remove media, which might also prove useful.
