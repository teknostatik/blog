---
title: "Setting up new Ubuntu computers"
date: "2018-03-24"
categories: 
  - "computers"
  - "linux"
  - "ubuntu"
---

I've had to set up a few Ubuntu desktop machines recently, and I thought it was worth documenting what I install on each one, and how I automate those installations as much as possible. I wrote about this [a few years ago](http://teknostatik.co.uk/2016/05/08/setting-up-new-ubuntu-machines/) but so much has changed with my setup that I thought it was worth revisiting these instructions.

Generally, I'll always install from USB, and from the latest desktop version. I make my installer in Ubuntu, using `Disk Image Writer` and boot the computer from that. From 18.04 onwards I sometimes use the minimal installation feature (which I love), but for now assume that I just go with the defaults for everything.

Once it has finished installing, I'll go through the process of getting everything I want on to the machine.

### Install dropbox

I download the latest version from [https://www.dropbox.com/install?os=lnx](https://www.dropbox.com/install?os=lnx) and then type:

```
sudo dpkg -i dropbox <hit the tab key>
```

I have a lot of files on Dropbox, so I let this sync while I'm doing the rest.

### Add some software from the Ubuntu repositories

```
sudo apt update
sudo apt install byobu gimp vlc ubuntu-restricted-extras build-essential hexchat openssh-server gnome-tweak-tool tilix testdrive tasksel gnome-session libdvd-pkg chromium-browser youtube-dl
sudo snap install --classic atom
sudo snap install spotify
```

### Add a script to make updating software easier

Create a new file called `updateall`

```
#!/bin/bash
echo "updateall v.1.2 for Ubuntu"
#Run this as a normal user. Your admin password will be asked for if required.
sudo apt update
sudo apt upgrade -y
sudo apt full-upgrade -y
sudo apt autoremove -y
sudo purge-old-kernels -y
echo "The script has now finished running."
```

I move it to `/usr/local/bin/` then make it executable with `sudo chmod 755 /usr/local/bin/updateall`.

### Install tails-installer

```
sudo add-apt-repository ppa:tails-team/tails-installer
sudo apt update
sudo apt install tails-installer   
```

### Install pandoc

This installs the latest version at time of writing, although there may be updates available.

```
wget https://github.com/jgm/pandoc/releases/download/2.2.1/pandoc-2.2.1-1-amd64.deb
sudo dpkg -i pandoc-2.2.1-1-amd64.deb
sudo apt install texlive texlive-latex-extra
```

See [here](http://teknostatik.co.uk/2015/08/19/converting-documents-using-pandoc/) for more on how I configure and use Pandoc.

### Cosmetic tweaks

- Change desktop wallpaper
- Log out, log back in, and select a vanilla Gnome desktop.
- Go to `Settings --> Security and Privacy` and turn off all "phone home" functionality.
