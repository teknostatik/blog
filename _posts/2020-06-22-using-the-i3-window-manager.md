---
title: "Using the i3 window manager"
date: "2020-06-22"
categories: 
  - "computers"
  - "i3"
  - "linux"
  - "ubuntu"
---

i3 is a window manager for Linux that I've been using for the last few weeks. It's a fairly steep learning curve, but definitely brings some productivity gains. i3 is a tiling window manager, and by default will fill up the whole screen with applications. So if you have one application open it's full screen, if you have two open then they each take up 50% of the screen, etc.

## Installing i3

A excerpt from my installation script:

```
# Install the i3 window manager and some basic utilities

sudo apt install -y i3 feh arandr byobu htop

# Download some wallpaper and set it as default when using i3

wget https://www.dropbox.com/s/n5o7jjg4qpuebjn/2017-12-27-13.38.44.jpg
mv 2017-12-27-13.38.44.jpg  default_wallpaper.jpg
echo "feh --bg-scale default_wallpaper.jpg" >> .profile

## Add some aliases

echo alias ls="ls -l" >> .bashrc
echo alias top="htop" >> .bashrc
```

## Using i3

When you log in for the first time you'll be asked to choose a modifier key (I chose ALT). The keyboard shortcuts below use `$mod` to refer to that modifier.

- Open a terminal window - `$mod + Enter`
- Open a different application - `$mod + d` then type the application name (eg `firefox`)
- Open (or go to) a second desktop - `$mod + 2`
- Send the focused application to that desktop - `$mod + Shift + 2`
- Split a container vertically - `$mod + v`
- Split a container horizontally - `$mod + h`
- Move between containers - `$mod + arrow keys`
- Switch to a tabbed layout - `$mod + w`
- Switch to a stacked layout - `$mod + s`
- Close a window - `$mod + Shift + q`
- Exit i3 - `$mod + Shift + e`

For multiple monitors it's possible to enable/define them using `xrandr`. The sysntax is something like:

```
`xrandr --output HDMI-2 --auto --right-of HDMI-1`
```

As I have three monitors I find `arandr` to be a better way to set them up though. It's a graphical wrapper to `xrandr` and lets me see the layout of my monitors which I find much more useful.

More information about i3 can be found at [https://i3wm.org/docs/userguide.html](https://i3wm.org/docs/userguide.html).
