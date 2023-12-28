---
title: "Updating and installing software on Foresight Linux"
date: "2009-05-16"
tags: 
  - "foresight"
  - "linux"
---

I've just installed the latest version of [Foresight](http://www.foresightlinux.org/) on my spare laptop, so I thought I'd investigate the package manager, `conary`, which is something I've never used before, but which looks like it could be as useful as `apt` and `urpmi`.

It's really quite simple. To update to the latest version of all installed packages, type:

`$ sudo conary updateall`

And to install a specific package, type:

`$ sudo conary update packagename`

I'll write more when I've explored further.
