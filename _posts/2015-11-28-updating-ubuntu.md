---
title: "Updating Ubuntu"
date: "2015-11-28"
categories: 
  - "linux"
  - "ubuntu"
---

I've been using Ubuntu a fair bit over the last few weeks, both at work and at home. I have a number of projects on the go, and I've found myself needing to maintain a few different machines (both LTS and current) to run experiments on, and to built live servers and services.

One thing I'm very big on is keeping software up to date, and I thought it was worth sharing the script I use to update my Ubuntu machines (and then to delete anything that is no longer required, like old kernels).

```
#!/bin/bash
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get dist-upgrade -y
sudo apt-get clean -y
sudo apt-get autoclean -y
sudo apt-get autoremove -y
```

I create this on each machine (in a file called `updateall`), move it to `/usr/local/bin/` and then make it executable with `sudo chmod -X update all`. I then run it when I want to update software (or even better, add it as a scheduled job so it runs once a day).

If I end up with many more machines I'll need to find something more elegant, but for now this will suffice.
