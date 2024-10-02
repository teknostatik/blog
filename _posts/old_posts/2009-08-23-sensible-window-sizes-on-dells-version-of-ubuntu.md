---
title: "Sensible window sizes on Dell's version of Ubuntu"
date: "2009-08-23"
categories: 
  - "gnome"
  - "linux"
  - "ubuntu"
tags: 
  - "dell-mini"
  - "linux"
  - "ubuntu"
---

I love my Dell Mini, but there are a couple of "features" added by Dell that drive me mad. One of these is called Maximus. It's an application that tells any window that opens on the desktop to open full-screen. It's particularly annoying with applications I've added myself (like Empathy), as the default applications seem preconfigured to ignore it. I've had a poke around in gconf-editor (install it with `sudo apt-get install gconf-editor` if it doesn't exist already), and the key that needs editing is called `/apps/maximus/exclude_class` (see below for details):

![Screenshot](http://slave27.local/andy/wp-content/uploads/sites/2/2009/08/Screenshot.png "Screenshot")

It's basically a list of applications that open with the same window size they closed with rather than open in full-screen.

Double click on the key, and you should get the following dialogue:

![Screenshot-Edit Key](http://slave27.local/andy/wp-content/uploads/sites/2/2009/08/Screenshot-Edit-Key.png "Screenshot-Edit Key")

Click on the plus button, and add whatever applications you need as shown below:

![Screenshot-Add New List Entry](http://slave27.local/andy/wp-content/uploads/sites/2/2009/08/Screenshot-Add-New-List-Entry.png "Screenshot-Add New List Entry")

Then click on OK. Next time you open the applications in question they should honour your desired window size.
