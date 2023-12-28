---
title: "Simple CCTV setup using a Raspberry Pi"
date: "2016-06-25"
categories: 
  - "computers"
  - "debian"
  - "raspberry-pi"
  - "ubuntu"
  - "webtech"
---

This weekend I've been setting up my latest Raspberry Pi (a version III, in a blue lego case, running Ubuntu) to display a video stream of what's going on outside my house so I can watch out for deliveries etc.

It's something I've done before on different hardware, but I thought it was worth documenting as it's a good project for any model of Raspberry Pi, and requires nothing more than the Pi, a USB webcam (or camera module), and 15 minutes of your time. I'm using a piece of software called `motion` which is available in the Debian/Raspian/Ubuntu repositories.

Install motion:

```
sudo apt-get install motion
```

Enable `motion` to start at boot:

```
sudo nano /etc/default/motion
```

Find the line that says `start_motion_daemon=no` and change it to `start_motion_daemon=yes`.

Enable the stream to be viewed from other computers on the local network, and also make the output a little bigger:

```
sudo nano /etc/motion/motion.conf
```

Change the following values:

```
daemon on
width 640
height 480
framerate 100
stream_localhost off
```

Reboot, and then browse to port 8081 on the computer you've set it up on.
