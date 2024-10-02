---
title: "Experiments with PDF files"
date: "2016-08-07"
categories: 
  - "productivity"
  - "ubuntu"
---

I've been experimenting a lot with combining PDF files in interesting ways (largely to make a recipe book from all sorts of different sources). I've used Preview on my Mac for a lot of this, but have also done a fair bit of work in Ubuntu recently which required a slightly different approach.

The best graphical PDF merging tool for Linux is probably `pdfmod`. It's in the Ubuntu repositories, and can do anything Preview can do as far as merging/exporting PDF files from multiple sources.

For command line merging, `pdftk` does the job well. The syntax would be something like:

```
pdftk *.pdf cat output combined.pdf
```

Which would merge all PDF files in the current directory, or:

```
pdftk file1.pdf file2.pdf cat output combined.pdf
```

Which would merge two specific files.

If you need to convert Word documents to PDF prior to doing this, there is a command line tool called `lowriter` which is part of the `libreoffice` suite. The syntax would be:

```
lowriter --convert-to pdf *.docx
```

It works with `.doc` and `.docx` files.
