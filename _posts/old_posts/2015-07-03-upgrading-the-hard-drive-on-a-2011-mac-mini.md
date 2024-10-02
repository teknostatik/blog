---
title: "Upgrading the hard drive on a 2011 Mac Mini"
date: "2015-07-03"
categories: 
  - "computers"
  - "mac-os-x"
---

I'm off work this week, and I thought it was about time I upgraded the hard drive in my Mac Mini to an SSD. I've had this machine for just under 4 years, and it's been my main desktop computer throughout that time. As such it's got a lot of data stored locally, and while it's backed up in three different places it's still a 4 year old hard drive that is getting a bit slow and clunky.

Replacing the hard drive in this model of Mac is tricky. It requires dismantling most of the computer, and also requires a couple of non-standard screwdrivers (T6 and T8 torx). Thankfully I found [some great instructions](https://www.ifixit.com/Guide/Mac+Mini+Mid+2011+Hard+Drive+Replacement/6422), and didn't run into any problems dismantling the computer, removing the drive, and putting in a new SSD.

The challenge with this upgrade was that I planned on migrating to a much smaller drive (500-->240) as as such I needed to organise my data in a different way. What I'd normally do with a drive replacement would be to back the whole drive up using Carbon Copy Cloner, replace the hard drive, and then restore the backup over the new hard drive. That's served me well with many other upgrades, but it just wasn't an option this time round.

Analysing what was on the hard drive, it soon became evident that there was a lot of music. Over 200Gb of music in fact (that probably doesn't surprise anyone). There was also a lot of _really_ old data that was backed up in lots of places, but which was from very old computers (over 10 years old at least). I decided to move the music to a dedicated partition on my external hard drive (500gb, to allow for expansion), and to accept that I probably didn't need to waste hard drive space on 10 year old files that I had multiple other copies of.

That left about 90Gb of other files, or in other words less than 50% of the new drive. I was happy with that, and started the reinstallation process. I booted the Mac Mini from the clone I made earlier (thus testing that everything works fine, as well as giving me an environment to run the actually cloning task from). I formatted the SSD with Disk Utility, and created a custom Carbon Copy Cloner one-off task that excluded the whole of my music directory plus a few other things I didn't want on the new drive. I chose the clone as the source, the new drive as the destination, and let CCC do the hard work.

30 minutes later it was done. I rebooted from the new drive and set about doing a couple of post-installation tasks. Firstly I enabled trim support on the new drive. Native support for this was rolled out in OS X 10.10.4, and it's [fairly simple to set up](http://www.macrumors.com/2015/07/01/os-x-trim-ssd/). I then rebooted to allow this to take effect.

I also needed to tell iTunes where it could find my music now. I opened iTunes with the ALT key pressed, and it asked me which iTunes library to use. I pointed it at the external drive, and it thought about it for a bit, and then opened with all my music exactly as it had been on the old drive. I then updated the CCC task I back up my music with to reflect these changes, re-enabled all my other backup tasks, and made sure Time Machine was happy with the new drive and that it could continue to do incremental backups. I ran each backup task manually and made sure data was being copied to the right places.

And that was all I needed to do. The computer feels significantly faster and more responsive, whilst still feeling very much like _my_ computer. I also think that with maxed out memory and a decent sized SSD drive there probably isn't anything else left to upgrade.
