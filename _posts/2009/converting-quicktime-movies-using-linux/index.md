---
title: "Converting Quicktime movies using Linux"
date: "2009-05-04"
categories: 
  - "linux"
tags: 
  - "linux"
---

Another "so I don't forget it" post.

Converting Quicktime (.mov) files to Ogg Theora (.ogv) is now rather simple (although takes a while).

Firstly, install `ffmpeg2theora` (it should be available for most distros).

Then just launch it from the command line. The syntax is:

`ffmpeg2theora name_of_file.mov`

Or to do a whole directory:

`ffmpeg2theora *.mov`

Easy.
