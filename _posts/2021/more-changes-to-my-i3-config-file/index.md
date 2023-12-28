---
title: "More changes to my i3 config file"
date: "2021-03-26"
categories: 
  - "i3"
  - "linux"
  - "ubuntu"
---

I had my new computer delivered this week. It was good to install it from my own scripts, copy across my dotfiles, and just carry on working.

Going through this process I did note that my i3 configuration file looks a lot different than when I last blogged about it, so I thought I'd make a note of the things I've changed from the defaults.

First up is screen locking. My muscle memory expects to use the same keyboard shortcut as Windows, so I've just configured that in:

```
set $i3lockwall i3lock -i /home/andy/Dropbox/lock.png -t
bindsym mod4+l exec --no-startup-id $i3lockwall
```

I've also set up something to randomise my wallpaper each time I log in (with a different one on each screen if I'm using multiple monitors):

```
exec --no-startup-id feh --randomize --bg-scale /home/andy/Dropbox/Wallpaper/current/*
```

I just keep a small folder of images in Dropbox that acts as a repository to pick from, and then add/remove occasionally to keep things fresh.

And then I've picked applications that don't make sense in tiled mode and make the windows float (so they appear on top of everything else and can be moved around):

```
for_window [class="Gimp"] floating enable
for_window [class="vlc"] floating enable
for_window [class="zoom"] floating enable
for_window [window_role="pop-up"] floating enable
for_window [window_role="task_dialog"] floating enable
for_window [class="Arandr"] floating enable
for_window [class="XTerm"] floating enable
```

I think that's about it for now. I've also made fairly significant changes to my installation and update scripts, but that's a topic for another day.
