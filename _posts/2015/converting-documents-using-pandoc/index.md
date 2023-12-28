---
title: "Converting documents using Pandoc"
date: "2015-08-19"
categories: 
  - "computers"
  - "debian"
  - "webtech"
---

I've recently found myself needing to do a lot of document conversion, and maintaining documentation that needs to be available in a variety of formats (HTML, Word documents, Markdown and PDF). My tool of choice for this sort of thing is Pandoc, which is available for Windows, Mac OS X and Linux, although most of my usage so far has been on Linux (it's a command line package that outputs to Dropbox, so it doesn't matter where it runs really).

There are [instructions for installing Pandoc](http://pandoc.org/installing.html) on quite a few platforms. I've found that following these is generally enough, although it's worth installing [the latest version of the .deb packages](https://github.com/jgm/pandoc/releases/latest) rather than the one in the Debian repositories which does odd things to some of my html.

Pandoc works for me because I write everything in markdown, and Pandoc is great at taking markdown and converting it into almost anything else. The syntax is fairly simple for most document types:

For example:

```
pandoc input.md -s -o output.docx
pandoc input.md -s -o output.html
pandoc input.md -s -o output.epub
```

Conversion to PDF works the same, although I'm not a fan of wide margins, so I tweak it slightly:

```
pandoc -V geometry:margin=1in input.md -s -o output.pdf
```

If you're using Pandoc on Mac OS X there is one more command you'll need to issue prior to the first time you want to create a PDF file:

```
sudo ln -s /Library/TeX/texbin/pdflatex /usr/local/bin/
```

This will ensure Pandoc knows where to find `pdflatex`. If this step isn't followed then you'll likely get an error message along the lines of `pandoc: pdflatex not found. pdflatex is needed for pdf output.`

Pandoc does a lot more, but the documentation is great, and the commands above should be enough to get you started.
