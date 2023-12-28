---
title: "Mass converting .bmp to .jpg"
date: "2009-03-22"
categories: 
  - "computers"
  - "linux"
  - "ubuntu"
---

I'm largely posting this because I've had to do it twice recently and forgot how to do it both times.  
  
The command to convert a whole folder of images from .bmp to .jpg (on Linux, obviously) is:  
  
`mogrify -format jpg *.bmp`  
  
It's really that simple, and is actually a lot quicker than I thought it would be. You need ImageMagick installed, but most distros will have that by default anyway.
