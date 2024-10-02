---
title: "A few notes on minimal Linux installations"
date: "2011-03-07"
categories: 
  - "computers"
  - "linux"
  - "ubuntu"
---

I figured it was time I got round to finishing off a few blog posts that have been sitting around in dropbox for what seems like weeks. First off is my attempt to build a really fast and light installation of Debian or Ubuntu for netbooks and virtual machines.

This setup will work using either Ubuntu (alternate or server CD) or Debian . It will give you a basic graphical environment, with a web browser, mail client and terminal, and can be built upon with other software (should you find you need any other software). I find this most useful as a virtual machine, or as a minimal installation for a laptop that will largely access a more powerful machine remotely.

1\. Install a minimal installation of Debian/Ubuntu. This involves just installing the base packages with no additional package groups. Once you've done this, reboot and you should find yourself at a terminal prompt.

2\. Install the following packages (as root): x-window-system-core xserver-xorg gnome-core gdm and network-manager-gnome. Once you've done this reboot, and you should find yourself at the graphical login prompt.

3\. You should find you've got epiphany, evolution, gnome-terminal and not a lot else. You can then add anything else you need through apt/aptitude.

I've set up a few of these, and find them useful for development, testing and generally having a computer that I can set up easily, break, and then restore to a fixed point in time.

I'd like to pair this setup with a netbook with a decent screen resolution, long battery life, and more than 1Gb of memory. But that's a subject for another post.
