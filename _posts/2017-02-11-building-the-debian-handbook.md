---
title: "Building the Debian Handbook"
date: "2017-02-11"
categories: 
  - "debian"
  - "linux"
  - "raspberry-pi"
  - "uncategorised"
  - "webtech"
---

What follows is instructions for creating a local HTML copy of the Debian Administrator's Handbook (which is a very useful source of information for anyone working with any Debian derivative including Ubuntu and Raspian). All work related to this project was done on a Raspberry Pi Zero running Raspian, so I suspect it will work on anything running any Debian derivative (although Ubuntu 16.04 is the only other system I've tested this on so far).

Open up a terminal, and issue the following commands to get hold of the source code:

```
sudo apt install git
sudo git clone
git://anonscm.debian.org/debian-handbook/debian-handbook.git
```

Install the packages required for building:

```
sudo apt install publican publican-debian
```

Build the html files:

```
cd debian-handbook/
sudo ./build/build-html
```

It might take a while to build, especially on the sort of hardware I've been using. This might be the point to make a cup of tea.

Copy the HTML files into the root of your web server:

```
sudo cp -R publish/en-US/Debian/8/html/debian-handbook/ /var/www/html/
```

At this point you should be able to browse to the home page of the directory by navigating to the hostname or IP address of your web server.
