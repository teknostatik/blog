---
title: "Patterns I have noticed when people struggle with switching to using Linux as their main operating system"
date: "2024-12-29"
---

A while ago I wrote the following in [a blog post](https://andy.teknostatik.co.uk/blog/2021/07/31/reddit-it-support-and-home-offices/) that was mainly about Reddit:

>I’m in no way surprised that people are generally quite bad at describing the issues they are having, and also that they are very bad at choosing the right place to ask for help. I do have vague intentions to write up long answers to things that people seem to struggle with, probably starting with my insights on how people switching to Linux invariably start off with doing something really hard as part of their initial switch (dual-boot, Nvidia drivers, getting Windows software to work in the same way it does on Windows) and give up soon afterwards, not realising that everything else they will ever do isn’t going to be that hard to set up. That’s an essay for another day, but this is definitely a statement of intent.

This is a start at writing up some of those thoughts.

2025 marks my 20 year anniversary of starting to use Linux as a desktop operating system. Over those years I've used it consistently, and used it as my _primary_ operating system for most of that time. I still use Windows at work, but when I have a choice of what to use then it's generally Linux (either Debian or Ubuntu, depending on the use case). Because I'm an experienced user, and also someone who has worked in IT support, I often find myself trying to help people who want to make the same switch I did, but I find myself failing at the first hurdle because they are either trying to do something that is hard, or something I've never actually done myself. 

### Things people often ask for help with

I thought it was worth listing those things, because they are all things that I am definitely not the best person to help with, but some of them should be quite trivial with the right instructions:

* Dual booting Linux and Windows
* Installing Linux on a PC with an Nvidia graphics card, and choosing a distribution that doesn't have a GUI for configuring graphics drivers
* Playing games where no native Linux version exists, or where anti-cheat is a feature of the game
* Having a workflow that relies on software that is not available for Linux, such as Microsoft Office or Adobe Creative Cloud
* Using Wine or something similar to run Windows/Mac software on Linux
* Using a DisplayLink docking station
* Installing or virtualising Linux on Apple Silicon

Some of these are clearly a result of situations where people want to run Linux as their primary OS, but need to keep Windows or MacOS around for specific use cases. How I always approach this is to have two computers, because my need for Windows is 100% work-related, and I am provided with a computer by my employer. But it would be a different story if I was a gamer or needed to use Photoshop. 

I always try and recommend a dedicated Linux computer, because it's possible to get a great experience on a fairly low-specification machine. Most mini-PCs work well, and there are always refurbished ThinkPads on the market that are either certified to work, or have been used by enough Linux users that documentation will exist for any workarounds required. A second computer reduces the risk of overwriting a bootloader or losing valuable data, and it means that the original computer is still available for those tasks better suited to Windows or MacOS.

But computers are expensive, and for some people they are unaffordable. Which is why a lot of these risky scenarios are attempted in the first place. Computers also consume electricity, produce extra carbon, and take up additional space at home. There are all sorts of reasons why most people only have one computer, and I accept that my default solution to most of these problems is written from a position of privilege.  

### Pre-switching checklist

Before even thinking about switching, there are a few things I would recommend:

* Work out what applications you are going to use for everything you use a computer for, and if they are cross-platform then install _and use_ them on your existing OS.
* Ensure that _all_ data you care about is stored somewhere that is not connected to the PC you plan on installing Linux on.
* Get used to the Linux command line by installing something like [Multipass](https://canonical.com/multipass) or [WSL](https://ubuntu.com/desktop/wsl).
* Download the .iso of whichever Linux distro you have chosen, and run it in VirtualBox to check it meets your needs. 
* Burn the .iso file to a USB device, and boot the PC you are going to install Linux on. Check that all your hardware works, and that you are happy enough with how your computer is going to work afterwards.
* Read and bookmark (or print out) installation instructions, and URLs of sites where you can ask for help or report bugs.

All of these steps are non-destructive. You may at some point realise that you can achieve what you want using a container or VM, or decide that Linux is not for you. These are things that are best found out before you have reformatted the hard drive of your only computer.

### But what if it all goes wrong?

Each Linux distribution will have a place where you can ask for help, and where you can access documentation. These should be the first place you look. Reddit is used a lot for support, but there is no guarantee that there will be someone who can answer your question or help you out, and a lot of subreddits are specifically _not_ for support, so if you ask support questions your post will likely be removed, or at best downvoted.

Writing a good description of what is going wrong is essential. I've linked to [this article](https://www.chiark.greenend.org.uk/~sgtatham/bugs.html) for a long time, but I still think it's the best description of how to write a good bug report. There is also an [Ubuntu specific guide](https://help.ubuntu.com/stable/ubuntu-help/report-ubuntu-bug.html.en) that might be useful.

I still try and help people out when I can, but as a non-gamer with fairly modest hardware requirements, I increasingly find that the problems people are having are not things I have any experience with. But I 
still think there are very few _new_ problems out there, so hopefully there will always be someone who can point new users in the right direction.


