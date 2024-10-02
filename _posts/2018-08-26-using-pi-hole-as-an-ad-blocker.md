---
title: "Using Pi-hole as an ad blocker"
date: "2018-08-26"
categories: 
  - "linux"
  - "raspberry-pi"
  - "webtech"
---

I've used various ad-blockers over the years, and while they have all largely worked, they have also started to slow my browser down (especially on older computers). I read about [Pi-hole](https://pi-hole.net/) a few times, but didn't get around to actually installing it until this week. Now I _have_ installed it I'm wishing I hadn't waited, because not only does it lead to a largely ad-free browsing experience, but it also makes my older and slower computers noticeably faster.

Pi-hole should work on any Debian or Red Hat derived Linux distribution, but I went for the obvious solution of putting it on one of my always-on Raspberry Pis (which also runs WordPress and a command-line IRC client). To install just type `curl -sSL https://install.pi-hole.net | bash` in a terminal, and then visit the /admin URL of the machine it's installed on to view the admin console.

Configuring machines to use it is just a case of defining a custom DNS server (how to do that varies between each OS, but was trivial on Ubuntu and ChromeOS - I've not tried anything else yet). Just add the IP address of the Pi as a DNS server, and it will block anything on the block list, and then forward everything else on to be dealt with as normal. If you want to do this for everything on your network then there are various options detailed [here](https://discourse.pi-hole.net/t/how-do-i-configure-my-devices-to-use-pi-hole-as-their-dns-server/245) that range from configuring one machine to routing everything through Pi-hole.

The admin page will tell you how much blocking is going on. With me it was about 1% of all traffic, and it will even tell you which domains it is blocking so you can whitelist anything you actually want to see (not all ads are bad). I don't really notice a performance increase on my main computer, but older and slower computers definitely seem snappier, and can maintain about twice as many open tabs before they start to slow down, which is a bonus feature that I wasn't really expecting.
