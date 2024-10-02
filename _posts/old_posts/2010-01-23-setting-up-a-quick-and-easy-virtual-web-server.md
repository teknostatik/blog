---
title: "Setting up a quick and easy virtual web server"
date: "2010-01-23"
categories: 
  - "computers"
  - "linux"
  - "ubuntu"
  - "webtech"
tags: 
  - "linux"
  - "ubuntu"
  - "virtualbox"
---

I did a fair bit of work on this about a year ago, and then never got round to writing it up. What I was trying to achieve was to have a minimal virtual server running in VirtualBox, which could been seen from the outside world and would appear to all extent and purposes to be a real physical machine.

Start off by creating a new VM. I went with a totally stripped down installation of Ubuntu (from the alternative CD), adding just `openssh-server` and `apache2` to the default install. I called it Ubuntu Minimal (the name will become important later).

Boot up the new VM, and then on the host machine enter the following commands (replacing the name of the VM with what you decided to call yours):

`VBoxManage setextradata "Ubuntu Minimal" "VBoxInternal/Devices/pcnet/0/LUN#0/Config/ssh/HostPort" 2222 VBoxManage setextradata "Ubuntu Minimal" "VBoxInternal/Devices/pcnet/0/LUN#0/Config/ssh/GuestPort" 22 VBoxManage setextradata "Ubuntu Minimal" "VBoxInternal/Devices/pcnet/0/LUN#0/Config/ssh/Protocol" TCP VBoxManage setextradata "Ubuntu Minimal" "VBoxInternal/Devices/pcnet/0/LUN#0/Config/apache2/HostPort" 8008 VBoxManage setextradata "Ubuntu Minimal" "VBoxInternal/Devices/pcnet/0/LUN#0/Config/apache2/GuestPort" 80 VBoxManage setextradata "Ubuntu Minimal" "VBoxInternal/Devices/pcnet/0/LUN#0/Config/apache2/Protocol" TCP`

Power down the VM, start it up again, and then you should be able to ssh into it on port 2222 and pull up apache's "it works!" page by browsing to http://localhost:8008. At that point you can install web apps and do whatever else you want with the server.

It doesn't take up a great deal of memory, so you could probably have a couple of these running on most computers without any obvious performance degradation.
