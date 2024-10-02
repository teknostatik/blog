---
title: "Building a private cloud with LXD"
date: "2021-01-02"
categories: 
  - "linux"
  - "oracle"
  - "ubuntu"
---

I've been doing some experiments with [LXD on Ubuntu](https://ubuntu.com/server/docs/containers-lxd) and I thought it was worth publishing some of the notes I made myself so that when I come back to this at a later date I can remember what I did.

LXD is described as:

> LXD (pronounced lex-dee) is the lightervisor, or lightweight container hypervisor. LXC (lex-see) is a program which creates and administers “containers” on a local system. It also provides an API to allow higher level managers, such as LXD, to administer containers. In a sense, one could compare LXC to QEMU, while comparing LXD to libvirt.

_(from [https://ubuntu.com/server/docs/containers-lxd](https://ubuntu.com/server/docs/containers-lxd))_

To install:

```
sudo snap install lxd
sudo lxd init
```

Then answer some questions about where you want to store things and what file system to use.

## Finding images

For Ubuntu, the syntax is:

```
lxc image list ubuntu:focal
```

_(replace `focal` with the name of the version you are interested in)_

For non-Ubuntu images, you'll need to search [https://uk.images.linuxcontainers.org/](https://uk.images.linuxcontainers.org/). This shortens to `images` So for an Oracle Linux 8 image we would type:

```
lxc image list images:oracle/8
```

## Creating containers

To do this we need to tell LXC which image to build the container from and what to call it. For an Oracle Linux 8 container with the name `oracle-01` we would type:

```
lxc launch images:oracle/8 oracle-01
```

Once it's built (it shouldn't take long) we can connect to it by using the following command:

```
lxc exec oracle-01 -- bash
```

The containers are very minimal, and I found myself having to install aditional software before I could set them up to work in the way I like (`nano` and `wget` were both missing for example).

## Stopping and starting containers

I'm very used to working with Multipass, so the commands for LXD are very similar.

Start a container:

```
lxc start <container_name>
```

Stop a container:

```
lxd stop <container_name>
```

Delete a container:

```
lxd delete <container_name>
```

## Viewing your current containers

The command to issue is:

```
lxc list
```

You will get to see which containers are running (with their IP address) and which containers you have that have been built but are not running.

That's about as far as I've got with building the latest part of my private cloud. I've also been working on using Oracle's cloud as a location for my backups, but I'll write about that another day.
