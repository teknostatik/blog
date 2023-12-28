---
title: "Backing up Gmail with Gmvault"
date: "2013-05-27"
categories: 
  - "linux"
  - "mac-os-x"
  - "productivity"
  - "webtech"
---

This weekend I have been experimenting with Gmvault ([http://gmvault.org/](http://gmvault.org/ "http://gmvault.org/")) in order to back up my various Gmail and Google Apps accounts to my computer. I'm using Mac OS X, but almost all of this will work with Linux too.

Firstly I downloaded the software, extracted it, and ran the following command once to download all of the mail in each account:

`./gmvault synch example1@gmail.com`

I then wrote a script to automate the process:

`#!/bin/bash #change to the correct directory cd /Applications/gmvault/bin/ #run a quick sync on all my gmail and google apps accounts ./gmvault sync -m -t quick example1@teknostatik.org ./gmvault sync -m -t quick example1@gmail.com ./gmvault sync -m -t quick example2@gmail.com ./gmvault sync -m -t quick example3@gmail.com`

Once that was working, I automated it with cron to run a few times a day.

Restoring the email to another Gmail account is a slow process, and you should probably only do it a few times a month (and always overnight). Again I've scripted this bit, but have commented everything out unless I actually need it. Having done the initial upload, and because I now have two local copies of everything, I'll probably only run this one monthly.

`#back up all downloaded email to a dedicated gmail account in the cloud #./gmvault restore backup_account@gmail.com #or just for the last month #./gmvault restore -t quick backup_account@gmail.com`

**Further reading:**

- [Setting nano as the default editor for cron](http://osxdaily.com/2011/03/07/change-set-the-default-crontab-editor/ "Setting nano as default text editor")
- [Manual page for cron](http://unixhelp.ed.ac.uk/CGI/man-cgi?crontab+5 "man cron")
