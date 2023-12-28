---
title: "xmessage"
date: "2009-01-14"
categories: 
  - "linux"
---

This week I've been looking at ways of setting up alerts that only actually happen when I'm sitting in front of my computer to read them. This has lead to me using xmessage. For example:

`xmessage -center Hello! This is a message created using xmessage &`

This would give me a message popping up with the text I choose to input. Not too useful on its own, but when used as part of a shell script it becomes really powerful.

What I've done is set up several of these as cron jobs. These run when I need to do something useful like stop checking email and get ready for work, or (most usefully) when I have to go to bed in order to get my perscribed 6 hours of sleep.

The package in is Debian and Ubuntu at the very least, and the manual is straightforward.
