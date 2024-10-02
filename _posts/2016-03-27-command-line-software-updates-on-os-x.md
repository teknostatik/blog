---
title: "Command line software updates on OS X"
date: "2016-03-27"
categories: 
  - "mac-os-x"
---

A while ago I blogged about [the script I use to update my Ubuntu machines](http://teknostatik.co.uk/2015/11/28/updating-ubuntu/). Today it's the turn of Mac OS X.

```
#!/bin/bash
echo "updateall v.1.0 for OS X. This software will upgrade all your Apple/Homebrew software."
#Run this as a normal user. Your admin password will be asked for if required.
#Update all Apple software (requires admin password at this point)
sudo softwareupdate -i -a
#Update all software installed via Homebrew (as a normal user)
brew update
echo "The script has now finished running."
```

This assumes you're an admin user (and know your admin password), and that you already use [Homebrew](http://brew.sh/) to manage command line packages. That's certainly how my machines are set up, as I find it's easier to have the same set of command line tools on all my machines regardless of OS. I also find this a quicker and more reliable way of updating multiple machines on patch release day, and it can also be run as a scheduled job through Apple Remote Desktop for the brave at heart.

This one needs saving as a file called `updateall`. You can then make it executable (`sudo chmod -X updateall`), copy it to `/usr/local/bin`, and then run it by typing `updateall` in a terminal window.
