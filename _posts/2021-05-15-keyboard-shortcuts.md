---
title: "Keyboard shortcuts"
date: "2021-05-15"
categories: 
  - "i3"
  - "linux"
---

I use a fairly eclectic range of hardware and software, and keyboard shortcuts are required to get it to all work together. This list is mainly for me, but I've split it up by device/application in case it is of any use to other people with similar setups.

## Epomaker SK61 keyboard shortcuts

I use a [61-key keyboard](https://www.amazon.co.uk/EPOMAKER-Swappable-Mechanical-Keyboard-Waterproof-Black/dp/B088FKJBRG) on my main computer. It doesn't have some of the keys that I use occasionally, and whilst it's perfect for writing there are a few keyboard shortcuts required to make some things I do a little bit easier. The main ones that I use are:

- Up arrow - `Fn + /`
- Down arrow - `Fn + menu`
- Left arrow - `Fn + Alt`
- Right arrow - `Fn + Ctrl`
- Delete - `Fn + M`
- Volume up -`Fn + H`
- Volume down -`Fn + G`
- Switch to layer 2 - `Fn + W`

There isn't really much else I use that this keyboard doesn't give me naturally, and the form factor and the way it handles more than make up for the lack of keys.

## Motospeed CK61 keyboard shortcuts

My other keyboard is a [Motospeed CK61](https://www.amazon.co.uk/MOTOSPEED-Portable-Mechanical-Keyboard-Backlit/dp/B07HH8ZTDD), which seems to have increased dramatically in price since I got mine. The layout is the same as the SK61 (which is why I like it), but instead of layers it has shortcuts that translate specific parts of the keyboard to alternate keys, which I find quite useful sometimes. Shortcuts I use are:

- Factory reset - `Fn + Escape`
- Map /, alt, menu and ctrl to arrow keys - `Fn + 3`
- Control brightness of backlight - `Fn + U/I`
- Cycle through different lighting patterns - `Fn + menu`

## i3 shortcuts

I've used i3 as my window manager for over a year now, and I find it fits my workflow perfectly. The main i3 shortcuts I find myself using are:

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

I do have a few other custom shortcuts defined, which are detailed in [my i3 config file](https://github.com/teknostatik/i3_config/blob/main/config).

## Atom shortcuts

I use the Atom text editor for a lot of my workflow. My main shortcuts are:

- Multi line editing - `ctrl + alt (or shift on Linux) + arrow keys`
- Toggle markdown preview - `ctrl + shift + m`
- Create a PDF of the current file - `alt + ctrl + e`
- Open a terminal `ctrl + alt + shift + i`
- Show a hidden menu bar - `alt`

## Kitty shortcuts

I use [Kitty](https://sw.kovidgoyal.net/kitty/) as my terminal emulator on any computer that it works with, although I don't really use too much advanced functionality. The main shortcuts I use in Kitty are:

- New terminal within an existing session - `ctrl + shift + enter`
- Toggle through windows - `ctrl + shift + ]`

There are lots more of these on the [Kitty website](https://sw.kovidgoyal.net/kitty/)

## Qutebrowser shortcuts

I've just started experimenting with [Qutebrowser](https://qutebrowser.org/). It's very fast, but has a steep learning curve. The main shortcuts that I've found myself using so far are:

- Open a URL in the current tab - `o`
- Open a URL in a new tab - `shift + o`
- Toggle through open tabs - `shift + k` and `shift + J`
- Close the current tab - `d`
- Back - `shift + H`

A lot of standard shortcuts (`ctrl + t` for a new tab, `Fn + 5` to refresh) also work as expected.

## Zathura shortcuts

[Zathura](https://pwmt.org/projects/zathura/) is a lightweight PDF viewer, and something else I've been incorporating into my workflow over the last few months. I only ever really use it for reading PDFs, so just use the arrow key shortcuts detailed above, plus `s` to make what I'm reading fit the width on the window/container I'm reading it in. Zathura has a lot of other functionality which I really do need to explore at some point soon, at which point I'll come back and update this guide with anything interesting I uncover.
