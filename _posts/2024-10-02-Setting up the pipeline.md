---
title: "Setting up the pipeline"
date: "2024-10-02"
categories: 
  - "wordpress"
---

I've been meaning to try and set up a pipeline that achieves the following:

* I write all my blog posts in Markdown and store them in a Github repository
* Github actions creates a new github page on my staging blog
* This is then pushes to Wordpress, where a new post is created
* The Wordpress post is then promoted on Mastodon

I think I'm mostly there, but am still debugging. I've had two _mostly_ working solutions, but neither meets all the requirements yet.