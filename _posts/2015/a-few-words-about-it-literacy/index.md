---
title: "A few words about IT literacy"
date: "2015-04-26"
categories: 
  - "computers"
  - "debian"
  - "dropbox"
  - "linux"
  - "mac-os-x"
  - "ubuntu"
  - "webtech"
---

When I'm recruiting new IT staff one of the things I always look for is how computer literate they are. It's a hard thing to work out, as it's usually a mixture of what they know and what they have done in the past, but also how they think and how inspired they are by technology. I also try and think back 10 years, to when I was the person on the other side of the desk who was trying to blag that a whole load of dabbling with things at home was enough experience to allow me to support some fairly important systems in a large University.

I sometimes get asked what advice I'd give someone wanting to get into an entry level IT role when they don't have any experience. I sometimes think that's the wrong question, because everyone has IT experience, and also the opportunity to gain experience without leaving the comfort of their own bedroom. I thought it might be worth expanding on what I mean by that, and what sort of things would impress me if I saw them on an application form or heard them in an interview. I'd also say that this list is probably a good starting point for anyone who wants to learn more about IT in general.

**Use more than one operating system (Windows, Mac OS X, Linux) and learn the skills common to all of them**

There is a viewpoint that Microsoft have won the OS war, and that IT professionals should concentrate on familiarising themselves with Windows and MS Office because that is what everyone uses. I don't share that viewpoint, but I do think that it's important to use the software that other people are using, because if you want to be able to support that software then you need to know how it works. I think it's essential to have an overview of all the main operating systems, and I'm particularly interested in people who run more than one, or who have changed their primary operating system and can articulate their reasons why. It suggests they have thought about what they want their computer to do, and that they have considered the financial, ethical and functional criteria that contribute to the decision as to what OS to use.

For instance, my current main OS is Mac OS X. I started to switch from Ubuntu at the end of 2010 in order to better understand an OS I was being asked to implement and be an advocate for in my workplace. The switch took a few months, but by mid 2011 all of my regularly used machines were Macs. I do however maintain machines running Ubuntu and Debian, and am now doing more Linux based work which may warrant a partial switch back at some point. I like using Macs because of the quality of the hardware and software, and that fact that everything generally just works. I dislike them because of the lack of freedom, and the number of decisions about how I use my computer that seem to have been taken away from me. I like using Linux because I can customise my computer to do exactly what I need it to do at no cost to myself or my employer, but I dislike the fact it requires a lot of maintenance, and also that I can't use some software I require to do my job and therefore need to also maintain a Windows machine or a Mac anyway. I also still maintain that the 11" Macbook Air is the best computer ever made, and until I find something better then I want to continue using one.

What I find about using multiple operating systems (and I'd include Windows in this) is that once you use more than one, you realise they all have things in common, and once you start to spot those patterns then it makes it easier to deal with unfamiliar operating systems. Windows 8 doesn't faze me in the slightest because I remember the Mac OS9 --> OS X shift, and also the move from Gnome 2 to Gnome 3 (and Unity, and a load of other desktops). The key for me is getting to a point where the desktop doesn't get in the way of being productive, and that comes through regular use.

_As an aside, I've switched my main OS a few times, and also maintained two in parallel for quite a while. I was a (classic) Mac OS user until my Mac became too old, and then had a brief (maybe a year) period of using mainly Windows. I switched to Debian in late 2004, and then Ubuntu from 2005. I got another (refurbished) Mac in 2006 and maintained OS X and Ubuntu in parallel until 2009 where I found I was doing everything in Ubuntu and hardly ever turned my Mac on (to be fair, it was very old at this point). I then switched back to OS X in 2011 as detailed above._

What I've noticed is that people who have only ever used one OS are often scared of all the other ones, and the easiest way to get over that is to experiment with them. Linux is free, and will install on almost anything, and if you're in the UK then you can pick up a decent refurbished Thinkpad from around £200 from [http://www.refreshedbyus.com/](http://www.refreshedbyus.com/), or a budget desktop without an OS from [http://www.ebuyer.com/](http://www.ebuyer.com/) for around the same price. Windows machines are also coming down in price every year, and it's now affordable to maintain more than one machine in ways that it wasn't 10 or even 5 years ago. And of course virtualisation is now easier than ever (but I'll mention more about this later on).

**Use more than one version of each operating system (or at least know how to use them)**

Something else I've noticed (especially with people who grew up with Windows XP) is that it's not just trying another OS that is scary, but moving to a new version of the _same_ OS. It's certainly worth being familiar with the last couple of versions of anything you're using and supporting, and having an overview of what the upgrade path would be for someone using something obsolete and unsupported like Windows XP.

I also think that if you're running (or experimenting with) Linux, then it's worth trying out at least a couple of desktop environments to see what works for you (and for your computer). I've got machines running Gnome 3 (Debian), XFCE (Debian & Xubuntu) and Unity (Ubuntu). None of them are perfect, but all of them allow me to understand the similarities and differences of modern desktop operating systems.

If you use several different operating systems it becomes really easy to see how the user interfaces and features of one will influence another. And once you start to make those connections then it's fairly straightforward to approach a new operating system or desktop environment and make it work well enough for you to help someone who is having difficulties with it.

**Use at least two browsers**

If you're supporting software, then you're likely supporting browser-based software, and knowing how that software behaves in all of the main web browsers is something you need to be up to speed with. I find the best way to do that is to use at least three browsers regularly, and for me that means Firefox and/or Chrome on my computers, and Safari for my iOS devices. I test everything on all three, and on other browsers as well (although if I'm asked to test things it's usually because they have only been tested on Windows and someone wants the non-Windows perspective).

As with operating systems, if you use multiple browsers then you are unlikely to be surprised or significantly slowed down when a new browser grabs a decent slice of the market share like Chrome did a few years back. It also make it easier to switch your main browser if the one you're using start to get slow and bloated, or no longer includes features that you really need.

**Install a virtualisation tool and set up a new VM**

I said I'd come back to this one, because I think it deserves a section to itself. Virtualisation software has been such a game-changer for me, because it has allowed me to continue using multiple operating systems without having to maintain a physical computer for each one. By using software such as [https://www.virtualbox.org/](https://www.virtualbox.org/) it's possible to run multiple operating systems on the same machine, and also to set up virtual web servers to experiment with blogging software, wikis, and other CMS related things. I'm currently doing a lot of this sort of thing at work, and it's great to be able to have virtual servers that are backed up and snapshotted so I can roll them back to the point just before I broke something. Once you've developed like this then you'll never go back, and it will teach you all sorts of skills that are directly applicable to sysadmin work, as well as development and IT support.

Virtualisation is also great for those situations where you can do 90% of your work in one OS, but need to switch to another one for one or two specific tasks. The guest machine is only using resources when it's on, and you may find that most of the time you don't even need to boot it.

**Know how to back up your data, and where all copies of your data are**

I blog quite regularly about how I back up data, but it's always worth writing about, as I find that things change as I stumble upon new products. My current plan is based on the 3/2/1 rule, with three copies of everything, on two types of media, with (at least) one remote copy. I use Time Machine, Crashplan and Carbon Copy Cloner to back up copies of my whole computer, and Dropbox, Google Drive and iCloud to ensure that files I use regularly are available on any computer I use.

How it generally works is that any machine that stays in one place (or mainly stays in one place like my heaviest laptop) backs up nightly (via Carbon Copy Cloner) to an external hard drive. I also have a portable hard drive that I back up to weekly with a bootable copy of the two machines where I regularly create data (as opposed to consume it). When I’m not backing up to it, this drive is kept in a different physical location to the machines it is backing up. Additionally, all my music is in iTunes Match, my photos are on two different NAS drives, all my portable computers back up to another machine via Crashplan and/or Time Machine, and everything text based I’m currently working on will exist in either Evernote, Dropbox or Google Drive, depending on what it is and who else needs to access it.

I've also started running some experiments with Bit Torrent Sync - maintaining a small directory of emergency music and freely available ebooks which I sync between all of my machines, and I also carry around an encrypted USB drive on my keyring which contains a lot of the same sort of stuff, as well as the installer for the latest version of Mac OS X, plus recent disk images of Ubuntu and Debian.

I test my backups monthly (sometimes more than monthly), including booting all the full disk clones to make sure they actually boot. I think this is important. I also try and replace my backup drives every couple of years to ensure that I'm not backing up to something that is likely to fail soon.

**Know how to upgrade/replace key parts of your computer**

This is something I think is so important, but it seems to be a dying art. Not that I'm surprised though, because Apple (and to a lesser extent other manufacturers) seem to be moving towards a world where individual parts of a computer are not upgradeable, and instead you just buy a new computer when it wears out or gets slow. So many older computers could benefit from a solid state hard drive (SSD) or some more memory, and both of these upgrades will make an old computer feel like a new one. There are plenty of people who will fit parts for you, but this will cost you, and often these are upgrades you can do yourself. Since I've been working with technology I've upgraded most of my machines (even my Macbook Air), but I do worry that the next computer I buy is likely to be less upgradable than the last.

I learned about computer hardware through buying an old machine from eBay and experimenting with it. I replaced the memory, and the power supply and the hard drive, and I’ve still got it sat in the shed 10 years later. There are still plenty of machines out there that you can replace pretty much everything in, and building a PC from scratch is still very much a rite of passage for anyone who is interested in hardware.

**Know how to reinstall the OS on your computer**

Long gone are the days where operating systems would not be upgraded for years. We’re now in a world where things change at least every 6-12 months, and it’s important that the operating system on your computer is up to date and receiving security updates regularly. Updating software is relatively straightforward on any computer, and we do seem to be moving towards the concept of an app store, where the OS is just another app to be upgraded when a new version comes out. Whatever you’re running, it’s a good idea to know how to upgrade the software on your computer, and also how to reinstall it from scratch. These are things that you can pay someone to do, but you never know where and when computer faults will happen, and the night before a deadline or while you’re overseas are not good times to learn about reinstalling operating systems.

**Use more than one office suite, and learn the skills common to all of them**

A big part of IT support is knowing about what the people you support are actually using. Arcane terminal commands and knowledge of compiling software will get you nowhere if you are supporting people who largely work with documents, spreadsheets and presentations. Particularly in a corporate or academic environment, knowing about a variety of office suites will serve you well, and it's important to stay up to date so that you're not surprised by changes to user interfaces. This is one area of IT that can be tricky to stay up to date with if you don't use this software yourself, and as someone who writes in a text editor, and only really uses Word for specific work-based tasks, I'm probably not the best person to advise on it. Although the fact that I use Keynote for presentations and Excel for serious data manipulation does suggest I can at least use _some_ of more than one office suite. I also like Libre Office a lot, and think it's one of the most underrated pieces of software out there.

As with operating systems and browsers, there is so much feature-bleed with office software that once you have used a couple of different versions then you start to see how they all do roughly the same thing under the hood. This is also a class of software where manufacturers love to change the UI radically between versions, so be prepared to relearn menus over and over again. Of course, if you use keyboard shortcuts then there should be less learning to do.

Which brings me nicely on to keyboard shortcuts.

**Learn keyboard shortcuts**

On my main desktop computer I have a solar powered keyboard, which means that even in the cloudy climate of the UK I can pretty much guarantee that it will work. The same can't be said of my wireless mouse, which is always running out of power and needing newly charged batteries. That doesn't bother me as much as it might do though, as I'm fairly keyboard-shortcut-literate, and can do most of what I need to do without picking up the mouse. Not only can knowing these get you out of a fix if your mouse or trackpad stops working, but it's a lot quicker to open or save a file using the keyboard when your hands are already touching the keyboard to type. It's also a lot better on your wrists, and will make you look like you know what you are doing with your computer. It's one thing I always look for when I'm trying to judge how computer-literate someone is, and it is usually a very good indicator.

A list of keyboard shortcuts for Mac OS X can be found at [https://support.apple.com/en-gb/HT201236](https://support.apple.com/en-gb/HT201236). Some of these will work on other operating systems, but I'm sure there are similar lists elsewhere (Ubuntu even has one on the screen the first time you launch the Unity desktop).

**Host a website**

In the days of Facebook, Twitter, Tumblr and a thousand other readily available web-based content sites, it's rare to find someone to doesn't have some sort of web presence. When I started out with computers it was harder to get content online, and I had to learn a fair bit of HTML just to have a simple home page, whereas now I can just create an account online in a few minutes. Despite the fact that it's so easy, I still think it's valuable to know how the nuts and bolts work, and how to set up your own website that you host and control yourself. My first site was hand crafted HTML, and my current website is a self-hosted Wordpress blog (cloud hosted now, but originally hosted on a server under the desk in my office).

I think it's still valuable to know how to configure a web server (I use LAMP - Linux, Apache, MySQL and PHP), and install a CMS like Wordpress on it. Even if you don't use it for your main blog it is something you might be asked to do one day, and it's a skills set that I've found myself using over and over again (and is in fact something I'm working on professionally right now).

**Learn a programming language (or two)**

I'm not a programmer, but I do know a little bit of HTML, CSS and PHP. Programming languages are not required for IT support, but as programming is largely about problem solving then there are a lot of transferable skills. Programming is also useful for solving in-house problems that your support tools can't do (like writing a password generator or something to convert proprietary mailbox formats to something more open - both requirements I've come across in my own team).

Learning some basic scripting is also a good idea, and a familiarity with shell scripting and Windows powershell scripts is never going to be wasted time and effort.

**Know what you can do and what you can't do**

And finally, this. It's all very well to look and sound impressive by stretching your IT skills and knowledge to the extreme, but it's important to be honest with yourself about what you can and can't do, and which of your theories are backed up by practical experience. Experiments are all very well in the comfort of your own home, but when you're dealing with other people's computers and data then ensure you know what you are doing and when to ask for help and guidance.
