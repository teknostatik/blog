---
title: "An updated guide to using Pandoc for document conversion"
date: "2016-06-07"
categories: 
  - "computers"
  - "debian"
  - "dropbox"
  - "linux"
  - "mac-os-x"
  - "ubuntu"
  - "webtech"
  - "writing"
---

I wrote about [Pandoc](http://pandoc.org/) last year, but I'm using it more and more and I've found myself editing the original post a fair few times. This is the updated 2016 version that gathers together useful commands I've learned so far.

Last year I found myself needing to do a lot of document conversion, and maintaining documentation that needs to be available in a variety of formats (HTML, Word documents, Markdown and PDF). My tool of choice for this sort of thing is Pandoc, which is available for Windows, Mac OS X and Linux, although most of my usage so far has been on Linux and Mac OS X (it's a command line package that can output to Dropbox, so it doesn't matter where it runs really).

There are [instructions for installing Pandoc](http://pandoc.org/installing.html) on quite a few platforms. I've found that following these is generally enough, although it's worth installing [the latest version of the .deb packages](https://github.com/jgm/pandoc/releases/latest) rather than the one in the repositories.

On Debian/Ubuntu I also add the `texlive-latex-extra` package, but that’s largely because it gives me a specific Beamer theme I like to use.

If you’re using Pandoc on Mac OS X there is one more command you’ll need to issue prior to the first time you want to create a PDF file:

```
sudo ln -s /Library/TeX/texbin/pdflatex /usr/local/bin/
```

This will ensure Pandoc knows where to find pdflatex. If this step isn’t followed then you’ll likely get an error message along the lines of `pandoc: pdflatex not found`. pdflatex is needed for pdf output.

Pandoc works for me because I write everything in markdown, and Pandoc is great at taking markdown and converting it into almost anything else. It's also good if you need to create a PDF, a Word document and a slide show from the same document. The syntax is fairly simple for most document types:

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

For a Beamer slide show you’ll need something like:

```
pandoc -t beamer input.md -V theme:metropolis -o output.pdf
```

Pandoc does a lot more, but the documentation is great, and the commands above should be enough to get you started. If you want to try out the functionality in a web browser then [http://pandoc.org/try/](http://pandoc.org/try/) should be able to handle most types of conversions.
