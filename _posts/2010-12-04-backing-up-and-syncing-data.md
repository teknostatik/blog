---
title: "Backing up and syncing data"
date: "2010-12-04"
categories: 
  - "computers"
  - "dropbox"
  - "linux"
  - "webtech"
---

I was having a conversation recently about backups, and how [Dropbox](www.dropbox.com) is great for ensuring that you don't lose valuable files. However, the free version of Dropbox can only handle a maximum of 8Gb, and once you start looking at music and photographs then I think most of us would probably need a paid Dropbox account to make this method worthwhile.

Alas, the paid Dropbox accounts only come in 50 or 100Gb denominations, and can come across as quite pricey. I think there's certainly a market for smaller and cheaper paid options, and I think that a 20Gb account at a reasonable price would get a lot of interest.

But yes, I digress. I though what would be useful (for me at least) would be to detail how I back up my data, and also how I sync it between the various machines I use (which is part of the same process for me).

I'm a great fan of Dropbox, and I use it to sync data between my machines and to collaborate with people on all sorts of work and non-work projects. What I keep in Dropbox is anything that might change, or that I will need to access on all my computers. This largely boils down to:

- Work related documents that I need to share or collaborate on with my co-worker
- Anything else I'm collaborating on
- Anything that is an editable file (generally anything created with OpenOffice.org or Microsoft Office)
- Documents I'm currently writing (usually as plain text files, unless they are collaborations)
- PDFs of books/documents I'm currently reading
- Useful phone numbers, next of kin details etc.

I also sync my browsing history and bookmarks through [Firefox Sync](http://www.firefox.com/sync), meaning that on a new/reinstalled computer I just need to install two applications and I can have a fair approximation of my most useful data within a few minutes, regardless of what operating system I'm using.

For actual backups I have a 2Tb NAS (Network attached storage) that backs up my Ubuntu laptop via [DejaDup](https://launchpad.net/deja-dup), and my Mac via [Time Machine](http://www.apple.com/macosx/what-is-macosx/time-machine.html). All my other computers just reply on Dropbox and Firefox sync. I also maintain a few directories available to either just myself or to everyone on our home network. These are things I might want access to occasionally on multiple machines, but that are too weighty for Dropbox:

- Photographs
- Books
- Music
- Videos
- Linux disc images
- My .virtualbox file containing my virtual web server and a few other things

These total about 200 Gb, and I can access them from anywhere on our network (and further afield if I wished to configure the NAS to do so, which I don't). Each of these items exists on one of my other computers already, but the NAS represents a repository of everything, and would be the one thing I'd save in a fire to ensure I had at least one copy of everything that was important.

I also have a 500Gb portable hard drive that I manually back up things to sometimes, but that I largely use when I'm away from home and want access to more movies and music that I can sensibly fit on my netbook.

I used to have a very complicated email backup system, but since I switched to Google Apps then I tend to let Google do most of the work and just back up my mailbox as part of my DejaDup/Time Machine backups. I also dump a copy of all my useful documents into Google Docs occasionally, and use it largely for real-time collaboration (which Dropbox can't really handle).

So yes, that's about it I think. I wouldn't recommend this for everyone, but it certainly seems to be working for me at the moment.
