---
title: "Setting up new Ubuntu machines"
date: "2016-05-08"
categories: 
  - "computers"
  - "linux"
  - "ubuntu"
---

I've had to set up a few Ubuntu desktop machines recently (for my own use), and I thought it was worth documenting what I install on each one, and how I automate those installations as much as possible.

### Add a script to make updating software easier

Create a new file called `updateall`

```
#!/bin/bash
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get dist-upgrade -y
sudo apt-get clean -y
sudo apt-get autoclean -y
sudo apt-get autoremove -y
```

Move it to `/usr/local/bin/` then make it executable with `sudo chmod -X updateall`.

### Add some software from the Ubuntu repositories

```
sudo updateall
sudo apt-get install git gimp byobu vlc ubuntu-restricted-extras build-essential hexchat openssh-server unity-tweak-tool youtube-dl
```

### Install Spotify

```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys BBEBDCB318AD50EC6865090613B00F1FD2C19886
echo deb http://repository.spotify.com stable non-free | sudo tee /etc/apt/sources.list.d/spotify.list
sudo apt-get update
sudo apt-get install spotify-client
```

### Install atom

```
cd Downloads
wget https://github.com/atom/atom/releases/download/v1.7.3/atom-amd64.deb
sudo dpkg -i atom-amd64.deb
```

The version number may be different - get the latest version from [https://github.com/atom/atom/releases/](https://github.com/atom/atom/releases/).

### Install dropbox

```
wget https://www.dropbox.com/download?dl=packages/ubuntu/dropbox_2015.10.28_amd64.deb
sudo dpkg -i dropbox_2015.10.28_amd64.deb
```

The version number will be different, but hit `tab` after typing `dropbox` and it should autocomplete. If that doesn't work, download the latest version from [https://www.dropbox.com/install?os=lnx](https://www.dropbox.com/install?os=lnx).

### Install tails-installer

```
wget --continue http://dl.amnesia.boum.org/tails/stable/tails-i386-2.3/tails-i386-2.3.iso
sudo add-apt-repository ppa:tails-team/tails-installer
sudo apt update
sudo apt install tails-installer
```

### Install pandoc

```
wget https://github.com/jgm/pandoc/releases/download/1.17.0.2/pandoc-1.17.0.2-1-amd64.deb
sudo dpkg -i pandoc-1.17.0.2-1-amd64.deb
sudo apt-get install texlive
```

See [here](http://teknostatik.co.uk/2015/08/19/converting-documents-using-pandoc/) for more on how I configure and use Pandoc, and also for a fix for a Mac OS X related bug to do with rendering PDFs.

### Cosmetic tweaks

Go to `System Settings --> Appearance`  
Change theme from Ambience --> Radiance  
Reduce Launcher size to 24  
Change desktop wallpaper  
Enable workspaces

Open Unity Tweak Tool and configure so that hot corners work, with the top left and right corner doing a window spread (largely because that's how my Macs are set up, and also how Gnome 3 works).

Go to `System Settings --> Security and Privacy` and turn off all "phone home" functionality.
