---
title: "Installing Ubuntu on a Chromebook"
date: "2018-08-13"
categories: 
  - "chromebook"
  - "computers"
  - "linux"
  - "ubuntu"
---

I've been experimenting with Chromebooks for a few weeks now to try and come up with a low-power low-cost no-maintenance setup. There are a lot of very good blog posts covering the basics already, but I thought it was at least worth documenting how I got Ubuntu installed on my older Chromebook (which is a bit of a frankenstein that goes against the general ethos of not upgrading or otherwise tinkering with the hardware). This is probably best not attempted on anything with less than 32Gb of storage, and 4Gb of RAM is probably a good idea as well.

## Enable developer mode

To enable developer mode, press `escape` and `refresh` and hold down the power key. When the scary message appears then press `Ctrl+d` and wait for the (fairly long) process to complete. This will unlock the full bash shell, and give you enough control over the Chromebook to set up a chroot.

## Install Crouton

Crouton is the script that is used to install Ubuntu in a chroot. Download it from [here](http://goo.gl/fd3zc) and ensure it's in your downloads folder. Then press `Ctrl+Alt+t` to open the chrosh terminal, and type `shell` at the command prompt. This will get you full shell access to the Chromebook.

To install Ubuntu (at time of writing 16.04) then issue the following command:

```
sudo sh ~/Downloads/crouton -e -t xfce
```

This will take a while, but when it's done then issue the following command to start Ubuntu:

```
sudo startxfce4
```

To toggle between ChromeOS and Ubuntu use `Ctrl+Alt+Shift+Back` and `Ctrl+Alt+Shift+Forward`. Performance is actually not bad, and productivity is only an `apt install firefox` away.

## Other useful commands

The following commands could be useful (all issued within the ChromeOS shell):

See a list of possible distributions to install:

`sh ~/Downloads/crouton -r list`

Back up a chroot:

`sudo edit-chroot -b name`

Restore it:

`sudo edit-chroot -r name`

Delete a chroot:

`sudo delete-chroot name`
