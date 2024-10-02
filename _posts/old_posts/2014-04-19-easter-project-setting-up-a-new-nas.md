---
title: "Easter Project : Setting up a new NAS"
date: "2014-04-19"
categories: 
  - "computers"
  - "ipad-2"
  - "productivity"
  - "webtech"
---

My project for this Easter was to set up some sort of storage solution for the vast array of music, films, TV shows and photos I have, and also to organise and catalogue them more effectively.

I asked for a few suggestions on Twitter, and there were a couple I liked the look of. The one that nearly won was the HP micro server, but I eventually settled for a Synology NAS device with a 4TB WD Green hard drive, which I’d read good things about, and which would also stream all my media to my iPad with minimal configuration. I still plan on getting some sort of Linux server at some point, but I think that’s a different project for another day.

Setting up the device was easy. Anyone reading this could do it, and there are plenty of guides on the internet. What was harder was coming up with a sensible way of organising my data, and making sure that I wasn’t just copying the horrifically complicated file structure from my old NAS without rationalising if it was still the best way of doing things.

Sorting the photos was fairly easy, once I’d tracked down where they were all stored. I created a directory, and then made a folder for each event, in a "year - event” format. That way everything will list in vague chronological order and I’ll remember what year things like weddings and holidays happened.

Films and TV shows was trickier, because I wanted to be able to access these more often, and in a way that allowed me to watch them easily. In the end I went with Synology’s default file structure, and made separate directories for films and TV shows. I then put each TV show in a separate folder, and made several folders for the films (by director if there were a lot by the same director, and then catch-all folders for English language films and those with subtitles). Copying the data was an overnight job, but it all went smoothly.

I then explored ways of accessing films and TV shows on other devices. Firstly I downloaded Synology’s iPad app, which is really pretty, and tries to find metadata and cover art for everything. When it works, it works really well, but it failed on a few of my more obscure films (especially the foreign ones), and whilst it played them fine, it gave them incorrect titles, which I think might annoy me in the long term. I also had to specifically point it at folders to index - it wasn’t quite intelligent enough to know where things were on its own.

I then fired up VLC, which I already use for offline playing of films when I’m travelling. It saw the NAS straight away, allowed me to browse the whole device, and pretty much just worked in the way that VLC has always worked for me. I’m not sure why I didn’t try this first, but it’s nice to see that software I’ve been using for 10 years still does the job I need it to do.

I already have all my music backed up in two places, so it wasn’t a huge priority to move it to this device straight away. But seeing as I had the space, I figured making a copy of my iTunes library wouldn’t hurt, so I at least have a snapshot of some of my music on this device. At some point I need to go through my old NAS and make sure there isn’t anything there that I don’t have in iTunes Match, but that is a job for another day.

As well as the music, I made a one-time backup of historical email and files. Both of these usually live in the cloud, but again I thought a local copy wouldn’t hurt.

Talking of backups. I also decided that now I have this new device I can probably afford the space to do Time Machine backups of my two laptops. Both currently back up to an external USB drive, which it reliant on remembering to plug the drive in, and so I am currently setting Time Machine up on both laptops with a view to being able to use the USB drives for something else soon.

I’m really pleased with the new NAS, and it has a lot of features I’ve not explored yet (like being able to run Wordpress and Mediawiki and all the things I wanted a Linux server for). It’s taken a day and a half to set up, but the vast majority of that was copying data. The actual setup took minutes, and there was nothing that required being technical, using the command line, or understanding too much about networking.

And I still have half of the Easter break left to do other things, which is an added bonus.
