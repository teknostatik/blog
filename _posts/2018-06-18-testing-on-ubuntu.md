---
title: "Testing on Ubuntu"
date: "2018-06-18"
categories: 
  - "linux"
  - "ubuntu"
---

This blog post details the installation process for Ubuntu when I'm using it for testing web applications. The builds are designed to conduct meaningful tests on Oracle cloud applications but should be suitable for testing any similar web application.

## Test Build 1 (all tests)

### Installation

- Installed in a VM running in VirtualBox
- Give the VM 4Gb of Ram, a 10Gb hard drive, and enable 3D acceleration
- Install from `ubuntu-18.04-desktop-amd64.iso`
- Minimal installation
- Download updates
- Don't install 3rd party software

### Post installation tasks

- Launch `gnome-terminal`
- Install all updates by typing `sudo apt update && sudo apt upgrade -y`
- Reboot if required

### Smoke tests

- VM boots
- User can log in
- User can connect to internet
- User can open Firefox and browse to a website

## Test Build 2 (all tests that fail on Test Build 1)

- Installed in a VM running in VirtualBox
- Give the VM 4Gb of Ram, a 10Gb hard drive, and enable 3D acceleration
- Install from `ubuntu-18.04-desktop-amd64.iso`
- Normal installation
- Download updates
- Install 3rd party software

### Post installation tasks

- Launch _Software & Updates_
- Under _Ubuntu Software_ ensure that all 4 repositories are enabled (_main_, _universe_, _restricted_, _multiverse_)
- Under _Other Software_ enable _Canonical Partners_
- Launch `gnome-terminal`
- Install all updates by typing `sudo apt update && sudo apt upgrade -y`
- Reboot if required
- Install some software by typing `sudo apt install ubuntu-restricted-extras adobe-flashplugin browser-plugin-freshplayer-pepperflash chromium-browser`

### Smoke tests

- VM boots
- User can log in
- User can connect to internet
- User can open Firefox and browse to a website
- User can open Chromium and browse to a website
- User can open LibreOffice Calc
- User can open LibreOffice Writer
