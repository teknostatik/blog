---
title: "Using Markdown and Pandoc for AI but also everything else"
date: "2026-10-12"
---
I've worked in largely the same way for well over a decade; using the same tools and workflow to create all sorts of documents, presentations, blog posts, shell scripts and everything in between. It strikes me that these are _also_ some of the tools that make working with LLMs and other AI tools much more efficient, and that they are good things to learn for anyone in 2026.

For me most things start off with a markdown file. I've been using markdown since 2014; generally writing it in [Visual Studio Code](https://code.visualstudio.com/), also in whatever text editor I happen to have open for smaller things. On my personal computers I save my work to a [Dropbox](https://www.dropbox.com/) folder that is also a [git](https://git-scm.com/) repository. On my work computer I do the same with [OneDrive](https://www.microsoft.com/en-us/microsoft-365/onedrive/online-cloud-storage) (which we use as our home directories and cloud storage). Personal projects then get committed to [GitHub](https://github.com/) and/or [GitLab](https://about.gitlab.com/); either publicly for my blog and a few software projects, or privately for works in progress and my daily journal. This ensures I've got a copy on all my computers, but also in the cloud. I also back up my Macs with both [Time Machine](https://support.apple.com/en-us/104984) and [Carbon Copy Cloner](https://bombich.com/), so for anything not related to work I generally have it in five places. 

Even when I'm not using markdown my workflow is largely the same, in that I start with a text file. The two main things I produce in this way are shell scripts and html websites. Both of these are where I use LLMs the most; as even local ones are good enough at refactoring my bad syntax and creating simple web pages to assist me with various low-level admin tasks. 

Markdown is often the start, but in the pre-AI age it was very rarely the end. Most people I collaborate with use [Microsoft Office](https://www.microsoft.com/microsoft-365), and deal in [Word](https://www.microsoft.com/microsoft-365/word) documents, presentations and PDFs. So there was always a point where something had to _stop_ being markdown and _start_ being something else. That's where [Pandoc](https://pandoc.org/) comes in.

Pandoc is great at taking markdown and converting it into almost anything else. It's also good if you need to create a PDF, a Word document and a slide show from the same document. The syntax is fairly simple for most document types:

For example:

    pandoc input.md -s -o output.docx
    pandoc input.md -s -o output.html
    pandoc input.md -s -o output.epub
    pandoc input.md -s -o output .pptx

Conversion to PDF works the same, although I'm not a fan of wide margins, so I tweak it slightly:

    pandoc -V geometry:margin=1in input.md -s -o output.pdf

For a [Beamer](https://ctan.org/pkg/beamer) slide show using the [Metropolis theme](https://github.com/matze/mtheme), you’ll need something like:

    pandoc -t beamer input.md -V theme:metropolis -o output.pdf

I've been working like this for a long time, although it did surprise me that the first blog posts I wrote about it were well over a decade ago. But now I feel like the word is catching up, and it's at least partly to do with AI. LLMs ingest and output Markdown by default (at least the good ones do), and Pandoc is a great tool for converting almost anything to/from Markdown, which makes them both incredibly useful. Markdown is probably the most efficient way to give an LLM some data (convert from .csv to a markdown table using Pandoc and you'll see the file size and token cost go down), and it's the file format that most tools use for instructions and other information passed to LLMs to describe parameters and guardrails.

It's also the language of Github, where so much of what I do ends up. I've used LLMs more to standardise and tidy up my Github sites than I have for creating actual code, but it all contributes to being able to do more things in a shorter amount of time, and that's exactly the kind of productivity gain I'm interested in.
