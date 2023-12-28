---
title: "Using IRC through Empathy on Ubuntu"
date: "2008-08-31"
categories: 
  - "webtech"
tags: 
  - "empathy"
---

I'm experimenting with using [Empathy](http://live.gnome.org/Empathy) for all forms on online communication. The following instructions show how to set up Empathy to access the #camuk channel on DarkMyst's servers.

Firstly, you'll need to download and install Empathy and the relevant libraries for irc connection:

`sudo apt-get install empathy telepathy-idle`

Start Empathy (it should be in the internet menu), and then press F4. Fill in the resulting box as follows:

 [![irc1](images/irc1-1-300x148.png "irc1")](http://slave27.local/andy/wp-content/uploads/sites/2/2008/08/irc1-11.png) 

If you enter a password it will automatically /msg NicKServ each time you connect to authenticate you.

To join a chat room, go to Room and Join New. You should get something like this:

 [![irc2](images/irc2-1-275x300.png "irc2")](http://slave27.local/andy/wp-content/uploads/sites/2/2008/08/irc2-11.png) 

Select the account you set up earlier (mine was called irc-darkmyst because I use more than one irc server). Add the room you want to join, and click on Connect. You should then be able to chat on irc as normal.
