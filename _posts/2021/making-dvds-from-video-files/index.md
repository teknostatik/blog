---
title: "Making DVDs from video files"
date: "2021-09-10"
categories: 
  - "linux"
  - "ubuntu"
---

Recently I found myself needing to make a DVD from a recorded stream (of a family funeral that my Mum couldn't attend because of covid). This is not a task I normally do, and I thought it was worth writing up how I did it in case I ever need to do it again.

Most of these instructions were put together using [this wiki page](https://docs.salixos.org/wiki/How_to_create_a_video_DVD_from_the_command_line), and assume you are using Ubuntu or some other Debian derivative.

## Dependencies

- `ffmpeg`
- `dvdauthor`
- `mkisofs`
- `k3b`

## The command line stuff

```
ffmpeg -i video_file_name.mkv -aspect 16:9 -target pal-dvd  -b 1800000 dvd.mpg
dvdauthor -o dvd/ -t dvd.mpg
export VIDEO_FORMAT=PAL
dvdauthor -o dvd/ -T
mkisofs -dvd-video -o dvd.iso dvd/
```

## The GUI stuff

Take `dvd.iso` and burn it to DVD using K3B (or your burning software of choice - I really should investigate doing this on the command line next time).

## Testing

Put the DVD into a normal DVD player and check it plays. The video should load automatically with no menus.

This worked for me. Hopefully if I have to do it again it will be in better circumstances.
