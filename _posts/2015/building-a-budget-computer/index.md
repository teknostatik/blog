---
title: "Building a budget computer"
date: "2015-10-21"
categories: 
  - "computers"
  - "linux"
  - "ubuntu"
---

I've been meaning to set up a low-powered Linux machine for a while, but developing a new Ubuntu-based service at work made me realise that having something at home to experiment with would be useful. I wanted something with real hardware, but also something that wouldn't use too much power or cost me too much money.

After a bit of research, I settled on a Gigabyte Brix BXBT-2807, which is a bare bones solution that requires a hard drive, memory, and an OS to complete. [Amazon says that this model now costs £94.98](http://www.amazon.co.uk/Gigabyte-Brix-BXBT-2807-Ultra-Compact/dp/B00L2C3VAQ/ref=pd_sim_147_4?), although with my Prime Now discount and another voucher it cost me just over £60. I chose this model because it's got a USB3 port (as well as 2 USB 2 ports), and it outputs to both HDMI and VGA meaning I can use it with both my existing monitor and my TV. Size-wise it's a roughly square black box that doesn't look big enough to be a real computer, and which takes up about the same space as a Mac Mini (being much narrower but slightly taller).

I decided to make this machine as powerful as it could be, just in case I ever needed to use it to do anything more taxing than web development and a little light browsing. I already had a 128gb SSD (which would have added about £40 to the cost), but neither of the sticks of memory I had were suitable (one was too higher voltage, the other was only 2Gb and I wanted more than that). I ended up buying an 8gb stick for around £30, which maxes out this particular case as it only has one memory slot.

Assembly was straightforward, and just required a phillips screwdriver. Once I'd fitted the hard drive and memory I connected the computer to my existing monitor, plugged in a keyboard and mouse and booted it from an Ubuntu installation USB. It booted from the USB fine, and installation didn't take too long at all. I went with 14.04 LTS because it's what the machine at work is running, and I do enough software updates on my other machines without having something else that was on the bleeding edge.

All in all this machine is working well (and very well for the price). I needed to add a bluetooth adaptor to get my solar powered keyboard working (but I carry a couple of these with me anyway), and this computer seems incapable of connecting to a 5MHz wireless network, but these are the only two things that are sub-optimal, and are easily fixed with a bluetooth adaptor and an ethernet cable. I'm also very impressed with how fast this machine is, and even how quickly it will perform processor-intensive tasks like ripping DVDs.

So far I've set up a minimal Plex server on it, plus a LAMP development environment and the tools for making Ubuntu live USB installers. I've also used it for a couple of days for email/web browsing, and didn't really notice that I was on a much less powerful machine.

I'm very pleased with how quick this was to set up, and it's good to see that it's possible to have a fully functional computer for under £150.
