---
title: "Deploying Multipass Containers"
date: "2020-08-04"
categories: 
  - "linux"
  - "ubuntu"
---

I've been running a lot of experiments using [Multipass](https://multipass.run/), which is a (fairly) new application for deploying and working with containers on various operating systems (including all the ones I use). I've now set up a script to deploy these containers on any Ubuntu machine I install, and thought it might be worth sharing the script that I use.

```
#!/bin/bash

# Script to set up multipass and then deploy a load of containers for various things
echo "---------------------------------------------"
echo "Multipass Deployment Script - v0.1, June 2020"
echo "---------------------------------------------"

# Changelog:
# 28/6/20 - Created script to deploy 5 containers (POC)

# First off, install multipass:

sudo snap install multipass --classic

# What we're going to do next is:
# 1. Deploy a container for the current LTS version of Ubuntu
# 2. Run my usual post-deployment and update scripts inside that container
# 3. Shut the container down

multipass launch focal --name ubuntu-lts
multipass exec ubuntu-lts -- wget https://www.dropbox.com/s/p5jjsbvuuskeotl/deploy_ubuntu_wsl.sh
multipass exec ubuntu-lts -- sudo mv deploy_ubuntu_wsl.sh /usr/local/bin/
multipass exec ubuntu-lts -- sudo chmod 755 /usr/local/bin/deploy_ubuntu_wsl.sh
multipass exec ubuntu-lts -- deploy_ubuntu_wsl.sh
multipass stop ubuntu-lts

# We will then do the same for the LTS before

multipass launch bionic --name ubuntu-lts-old
multipass exec ubuntu-lts-old -- wget https://www.dropbox.com/s/p5jjsbvuuskeotl/deploy_ubuntu_wsl.sh
multipass exec ubuntu-lts-old -- sudo mv deploy_ubuntu_wsl.sh /usr/local/bin/
multipass exec ubuntu-lts-old -- sudo chmod 755 /usr/local/bin/deploy_ubuntu_wsl.sh
multipass exec ubuntu-lts-old -- deploy_ubuntu_wsl.sh
multipass stop ubuntu-lts-old

# Then we will follow the same process for the latest build of the next version of Ubuntu

multipass launch daily:20.10 --name ubuntu-devel
# TODO: investigate why the devel alias doesn't work for this
multipass exec ubuntu-devel -- wget https://www.dropbox.com/s/p5jjsbvuuskeotl/deploy_ubuntu_wsl.sh
multipass exec ubuntu-devel -- sudo mv deploy_ubuntu_wsl.sh /usr/local/bin/
multipass exec ubuntu-devel -- sudo chmod 755 /usr/local/bin/deploy_ubuntu_wsl.sh
multipass exec ubuntu-devel -- deploy_ubuntu_wsl.sh
multipass stop ubuntu-devel

# Do the same for any other versions of Ubuntu you want but this is probably enough for a POC

# Next up let's try a snapcraft development and test environment. This bit needs work once I know more about it

multipass launch snapcraft:core18  --name snapcraft-build
multipass stop snapcraft-build
multipass launch core18 --name snapcraft-test
multipass stop snapcraft-test

# Finally let's see what we now have:

multipass list
```
