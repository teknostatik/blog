---
title: "Bulk resizing images with ImageMagick"
date: "2010-04-17"
categories: 
  - "linux"
---

Another of those posts that are largely for my own benefit.  
  
I've been spending a lot of time in various image editing programs recently (largely GIMP, but with a bit of Inkscape on the side). Yesterday it transpired that a folder of 24x24 images needed to be made slightly smaller as a matter of some urgency. I had a feeling ImageMagick would probably do the job (it usually does), but I couldn't remember how.  
  
It's actually fairly straightforward. Navigate to the directory containing the images (via the terminal) and then enter the following command:  
  
`mogrify -resize 20x20 *.png`  
  
Which will resize all PNG files to 20x20 pixels.  
  
This can obviously be altered to cater for different sizes and file types. So yes, ImageMagick saved the day again and I actually managed to leave work on time.
