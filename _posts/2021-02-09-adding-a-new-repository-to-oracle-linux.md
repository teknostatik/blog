---
title: "Adding a new repository to Oracle Linux"
date: "2021-02-09"
categories: 
  - "linux"
  - "oracle"
---

When I first install Oracle Linux 8 a lot of software I want to use isn't available. But we can fix this by adding another repository.

First of all, create a new file in `/etc/yum.repos.d`:

```
sudo nano /etc/yum.repos.d/ol8-epel.repo
```

Then add the following to the file:

```
[ol8_developer_EPEL]
name= Oracle Linux $releasever EPEL ($basearch)
baseurl=https://yum.oracle.com/repo/OracleLinux/OL8/developer/EPEL/$basearch/
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-oracle
gpgcheck=1
enabled=1
```

Issue the following command to start using the new repository:

```
sudo dnf makecache
```

Then try and install some software that wasn't previously available:

```
sudo dnf install -y byobu neofetch
```

This gives me access to a lot of software that makes computers feel like _my_ computers.
