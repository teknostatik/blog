---
title: "Exploring Suse Studio"
date: "2009-08-15"
categories: 
  - "linux"
  - "webtech"
tags: 
  - "linux"
  - "opensuse"
---

I've had an account on [http://susestudio.com/](http://susestudio.com/) for a few weeks now, but have only really had a couple of chances to play with it. The basic idea behind the site is that anyone should be able to create a customised Linux distribution that perfectly suits their needs (providing those needs involve openSUSE 11.1 or SUSE Linux Enterprise 10 or 11). Normally I do this sort of work on Ubuntu, using [Ubuntu Customisation Kit](http://uck.sourceforge.net/), as detailed in a previous post. This suits me, because I use Ubuntu in a production environment and it makes things easy. But I was interested in how this new software would work for someone who had never used openSUSE for more than a few minutes.

Ubuntu Customisation Kit does everything on the host machine, and only uses the Internet to pull new/updated packages in. This is light on bandwidth for tweaks, but heavier if you're making major changes. Suse Studio does things the opposite way round, in that all the building and updating is done on the web, and you then download the finished .iso image. It's slightly heavier on bandwidth overall, but did allow me to do a lot of the build work from my netbook in the foyer of a hotel in London, as all you need is a web browser and a net connection.

I ended up building three different versions of openSUSE, to suit three specific needs I occasionally have:

1. Gnome, with a web browser (firefox), a terminal (gnome-terminal), dropbox preinstalled, and a couple of work-specific scripts for mounting drives and backing up data. This is a configuration we use at work for data recovery (currently based on Ubuntu 8.04). This was painless to set up, came in at 348Mb, and worked well.
2. A showcase for KDE4. I'm not a big fan of KDE, but it's always useful to have a VM kicking around to show people what it is like. This was on the same level of detail as the Gnome one, and came in at 350mb. I think I might actually be able to use this to get things done, as it takes away a lot of the un-instinctive KDE apps whilst leaving the very pretty and functional base.
3. An image containing the applications I use every day, which would act as a basis for reinstalling my home or work laptop (both currently running Ubuntu 9.04). This contains Firefox, Thunderbird, OpenOffice.org, Empathy, Rhythmbox, Gedit and gnome-terminal, and was still only 484mb (300Mb less than the version of Ubuntu I install from usually).

So yes, all three experiments worked, and while I've not tried to use them to get things done yet, I have successfully installed all three as virtual machines and they seem to work as expected.

I think most people could use Suse Studio, and it acts as a good way to learn the basics of how a distribution is put together. I very much expect to see the code base from this project move in interesting directions in the next few months, and I'd be surprised if we don't see similar projects getting off the ground soon.
