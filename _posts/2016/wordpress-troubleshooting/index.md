---
title: "Wordpress troubleshooting"
date: "2016-05-15"
categories: 
  - "debian"
  - "webtech"
---

I've done a fair bit of Wordpress troubleshooting over the last few weeks, including moving sites from one server to another and upgrading server operating systems. While a lot of this isn't probably that interesting, I did come across a few things that might help other people undertaking similar tasks.

My method for moving content between sites generally involves exporting the content to XML, installing a fresh instance of Wordpress on the new server, importing the content using the [Wordpress Importer](https://wordpress.org/plugins/wordpress-importer/) plugin, and then seeing what doesn't work. What _usually_ doesn't work is uploaded images and files, but it's just a case of copying across the whole contents of `/var/www/html/wp-content/uploads` to the new server to fix that.

Talking of which, Debian (and derivatives) changed the default location for websites from `/var/www` to `/var/www/html` last year. If you upgrade Debian to the latest version and all your Wordpress sites break, then it should just be a case of editing `/etc/apache2/sites-available/000-default.conf` so that the `DocumentRoot` value is set back to to `/var/www/`.

My last revelation is around hardwired links. When moving a site to a new server (with a new URL) there are likely to be many references to the old site URL in config files and in the Wordpress database. There is a plugin called [Search and Replace](https://wordpress.org/plugins/search-and-replace/) which does all the heavy lifting for you, and which should rewrite your new URL to everywhere it needs to be. I've used this a few times now and it works really well.

I'm also half way through writing up how I install sites from scratch, but that's going to be quite a lengthy document and probably deserves a separate post.
