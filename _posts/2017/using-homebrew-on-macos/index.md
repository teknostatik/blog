---
title: "Using Homebrew on macOS"
date: "2017-02-11"
categories: 
  - "mac-os-x"
  - "uncategorised"
---

Homebrew is a package manager for command line tools on macOS. It can be installed by issuing the following command:

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Packages can be installed with `brew install <packagename>` and updated with `brew update`.

Packages I generally install on a new Mac are:

- `wget` - for command line downloading
- `imagemagick` - for image manipulation
- `mas` - for command line updating of (non-Apple) App Store software
- `youtube-dl` - for downloading youtube videos for offline viewing

Once you have `homebrew` installed then it's possible to script a software update solution that includes all Apple software, all non-Apple software, and everything installed through `homebrew`. It's not _quite_ as good as a Linux package manager, but it's getting there.

The current script I use for this is:

```
#!/bin/bash
echo "updateall v.1.1 for macOS"
# Run this as a normal user. Your admin password will be asked for if required.
# Update all Apple software (requires admin password at this point)
sudo softwareupdate -i -a
# Update all software installed via Homebrew (as a normal user)
brew update
# Update all other software
mas upgrade
echo "The script has now finished running."
```
