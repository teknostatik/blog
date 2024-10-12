---
title: "Updated Ubuntu Installation script"
date: "2024-10-02"
categories: 
  - "Computers"
  - "Linux"
  - "Ubuntu"
---
I've made some major changes to [my Ubuntu installation script](https://github.com/teknostatik/deploy_ubuntu/blob/main/deploy_ubuntu.sh) over the last few weeks. Mostly because I finally replaced the hard drive in my laptop and needed to do a clean installation, but also because I wanted to try and get DisplayLink drivers installed by default, which has historically been a pain.

for the latter I'm now using a lot of someone else's work, and a little bit of my own:

    install_displaylink() {
        git clone https://github.com/AdnanHodzic/displaylink-debian.git
        cd displaylink-debian
        sudo ./displaylink-debian.sh
        wget -q https://raw.githubusercontent.com/teknostatik/debian/master/20-displaylink.conf -O /etc/X11/xorg.conf.d/20-displaylink.conf
        cd ..
    }

One day there will be a more elegant solution, but for now this will do.

Since writing the original draft of this post I decided that having these driver on all my computers really isn't required, and I would generally just plug a HDMI cable in and use the dock for just the standard I/O. But it's still there in a script as an optional setting, in case anyone else might find it useful. I've also added a few more optional settings, for QMK installation and enabling the firewall by default. I tested all this on a clean install of both 24.04 and 24.10 and it all seems to work fine.