---
title: "Synching with folders outside of /dropbox"
date: "2009-03-08"
categories: 
  - "computers"
  - "dropbox"
  - "linux"
  - "ubuntu"
  - "webtech"
tags: 
  - "dropbox"
  - "linux"
---

This could probably be summed up in a few words (the words being "use symlinks").

Basically, what I wanted to do was to sync several folders outside my dropbox folder (for various reasons). The solution was to create a shortcut in the folder I wanted to sync, and then moving the link to my dropbox folder.  This can be done of the command line by typing something like:

`ln -s /home/folder/to/sync /home/andy/dropbox/synched_folder`

This could be used in all sorts of ways, some of which I may blog about over the next couple of weeks.
