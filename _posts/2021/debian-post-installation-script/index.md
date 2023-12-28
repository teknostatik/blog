---
title: "Debian Post-installation Script"
date: "2021-05-31"
categories: 
  - "debian"
  - "linux"
---

Yesterday I spent the day working on [a script](https://github.com/teknostatik/debian) to install my usual working environment on top of a clean install of the (soon to be) current version of Debian. This is a fork of my [Ubuntu scripts](https://github.com/teknostatik/deploy_ubuntu) that I use to set up all my machines.

It's very much a work in progress, and I wouldn't recommend running this on a machine you care about, but I thought it was worth documenting in case it's of use to anyone else.

## Pre-installation

Before you run this script ensure that you have `sudo` installed and that your user is in the group. To do this run the following as root (replacing `<your username>` with your username)

```
apt install -y sudo
sudo usermod -aG sudo <your username>
```

You will also need some extra repositories enabled. My `/etc/apt/sources.list` looks like this:

```
deb http://deb.debian.org/debian bullseye main contrib
deb http://security.debian.org/debian-security bullseye/updates main contrib
```

## Installation

Download the script, make it executable, and run it:

```
wget https://raw.githubusercontent.com/teknostatik/debian/master/deploy_debian.sh
chmod 755 deploy_debian.sh
./deploy_debian.sh
```

I've tested this on top of a full desktop install and a command line only installation as well. My goal is to get a working i3 environment, so the latter is probably what I'm going to focus on going forward. I did get a few snaps working on my test machine, but that was non-trivial, and I'm still not confident enough about that aspect yet. I also suspect most people who choose Debian do not care for snaps anyway.
