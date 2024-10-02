---
title: "Twidge"
date: "2009-08-07"
categories: 
  - "webtech"
tags: 
  - "identi-ca"
  - "twidge"
  - "twitter"
---

I've been after a command line based microblogging tool for ages. I think [Twidge](http://software.complete.org/software/wiki/twidge) might be just what I need.

The syntax to make a post is as follows:

`twidge update "whatever you want to post goes here"`

And before you do your first update, just type `twidge setup`, which will then ask for your usename and password.

If you want to update identi.ca rather than twitter, then add the following line at the end of .twidgerc:

`urlbase: http://identi.ca/api`

And that's all there is to it.
