---
title: "How to make a totally up to date bootable USB version of Ubuntu"
date: "2009-01-09"
categories: 
  - "computers"
  - "ubuntu"
tags: 
  - "linux"
  - "ubuntu"
  - "uck"
---

I've written [these instructions](http://teknostatik.co.uk/uck_instructions.pdf) (371.6 KB PDF) for work, but think they might be useful in all sorts of other situations.

Basically it boils down to:

1. Use [Ubuntu Customization Kit](http://uck.sourceforge.net/) to update all the packages in Ubuntu and add/remove packages as required.
2. Use the USB creating tool in Ubuntu 8.10 to transfer your newly created iso to USB.

On my USB I've also added several [portable apps](http://portableapps.com/), so as to ensure I've got everything I need for remote support of misbehaving Windows PCs.

Of course, you could just make the USB version first and then customise it using the free space on the USB, but this method allows you to remove software before transfering it to USB, which makes it useful for smaller devices (and for the sort of customised image you might want to install to a netbook).
