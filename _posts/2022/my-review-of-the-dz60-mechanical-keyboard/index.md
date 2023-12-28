---
title: "My review of the DZ60 mechanical keyboard"
date: "2022-05-08"
categories: 
  - "mechanical-keyboards"
---

After a bit of work yesterday I'm actually really happy with [this board](https://drop.com/buy/dz60-dz60rgb-type-c-60-pcb?defaultSelectionIds=965976). I bought it because I wanted something fairly conventional that I could flash with autoshift so that it could be used as a backup keyboard when I'm travelling (I use a Planck as my main keyboard).

I've built it using things I already had lying around (a bright blue plastic case from Optic Boards, plate and stabs from an old pre-built, Glorious Panda switches, and some generic beige keycaps). The hardware build was easy; the software build less so.

The key mapping this board comes with doesn't really work for me. There is no function key mapped, so no access to layers (and therefore no access to navigation). There was also no way to turn off the very obvious RGB. This didn't really bother me, as I was planning on using QMK to reflash it. The following is a list of things I learned during the process of building and flashing the firmware.

- Despite there being an entry for `DZ60` in QMK, this board is actually listed as `dztech/dz60rgb_ansi/v2`
- The file extension required for the firmware is .bin, despite all other versions of this board being .hex
- The software reset combination for this board is to hold escape down as you plug the board in
- The hardware reset button for this board in in the middle on the board, and nowhere near the reset slot in most cases (including my case).

Putting all that aside, it's a great board that is fun to type on and sounds really good. I wouldn't recommend it to anyone who wasn't used to doing this sort of project, but I actually quite enjoyed the build and can see this as a keyboard that will definitely get some use.
