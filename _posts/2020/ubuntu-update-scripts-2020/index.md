---
title: "Ubuntu Update Scripts 2020"
date: "2020-05-11"
categories: 
  - "linux"
  - "ubuntu"
---

I've maintained my own scripts for updating software on a few Linux distributions for a while. This weekend I decided it was time to consolodate all my installation and update scripts in one place, and amend them to reflect the new ways I work with Linux (both in using i3 as a window manager and relying more on WSL and Multipass).

What follows is largely for my benefit, but I thought it may be of interest to others.

## Ubuntu

```
  wget https://www.dropbox.com/s/hwfvynamcy6bkcs/deploy_ubuntu.sh
  sudo mv deploy_ubuntu.sh /usr/local/bin/
  sudo chmod 755 /usr/local/bin/deploy_ubuntu.sh
  deploy_ubuntu.sh
```

## Windows Subsystem for Linux (WSL)

```
wget https://www.dropbox.com/s/p5jjsbvuuskeotl/deploy_ubuntu_wsl.sh
sudo mv deploy_ubuntu_wsl.sh /usr/local/bin/
sudo chmod 755 /usr/local/bin/deploy_ubuntu_wsl.sh
deploy_ubuntu_wsl.sh
```

This one also works with Multipass (which will probably be the subject of a blog post soon).
