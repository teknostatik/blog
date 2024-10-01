---
title: "Corne Build Guide"
date: "2024-10-01"
categories: 
  - "keyboards"
---

_A proper parts list and build guide for the Corne split mechanical keyboard that I use every day._

The Corne is a 42-key split mechanical keyboard. 

The Corne I started with is the RTG model, ordered from [Mechboards](https://mechboards.co.uk/). I have also now built a few from scratch, using whatever the cheapest kit Mechboards sell is. These are what I use now, anywhere that I use a computer for any length of time. 

## Bill of materials

* [Corne light kit from Mechboards](https://mechboards.co.uk/collections/featured/products/helidox-corne-kit)
* Two controllers and sockets
* 42 switches (Choc v1 or v2, or MX)
* 40 1U keycaps and 2 1.5U keycaps to match switches chosen
* Cable to match controllers chosen (almost certainly a USB-C cable)
* A case, if you don't want to use the one included in the kit. Currently I'm using [this case](https://www.etsy.com/uk/listing/1179555093/high-profile-corne-3dp-case) which make it look a lot better, as well as being significantly more stable on my desk. I've also now screwed a metal plate on to the bottom to give even more stability.

I've also built a few of these using PCBs I've ordered in bulk. This allows the use of third party cases without generating waste, but does require buying at least some TRRS jacks (PJ-320A), and a cable to connect them. 

## Links to build guides

These are some good build guides that I have either used myself or found afterwards.

* https://devpew.com/blog/corne-eng/
* https://www.boardsource.xyz/docs/build_guides-corne_crkbd
* https://github.com/foostan/crkbd/blob/main/docs/corne-light/v2/buildguide_low_edition_en.md
* https://thomasbaart.nl/2018/11/26/corne-keyboard-helidox-build-log/

I don't plan on trying to compete with these or duplicate them too much.

All the example code in this guide will be assuming that the [Vial firmware](https://github.com/vial-kb/vial-qmk/tree/vial/keyboards/crkbd/rev1) will be used. It requires having a working installation of the [`vial-qmk`](https://github.com/vial-kb/vial-qmk) github repository. It will also assume you're using some kind of RP2040 controller.

## Flashing Controllers

Flash each controller to test they work, and to define which controller belongs to which side of the keyboard. 

Firstly test that your firmware compiles:

    qmk compile -kb /crkbd/rev1 -km vial

Then flash each controller in turn:

    qmk flash -c -kb crkbd/rev1 -km vial -e CONVERT_TO=promicro_rp2040 --bootloader uf2-split-left
    qmk flash -c -kb crkbd/rev1 -km vial -e CONVERT_TO=promicro_rp2040 --bootloader uf2-split-right

Once you have done this then label the controllers so you are absolutely sure which is which.

Then build the keyboard, using whatever set of instructions you have chosen. Some third party cases will have their own instructions which should definitely be read in full before soldering anything.

Finally, use [Vial](https://get.vial.today/) to configure your keymap.

## A few further hits and tips

* Once you have soldered your controllers and TRRS jacks, plug the keyboard into a computer, and short every single socket to test that the right key codes are sent. I use [QMK Configurator](https://config.qmk.fm/#/test) for this.
* Depending on the height of your sockets, you _may_ have the choose between having hot-swappable controllers and using an OLED screen. I've not yet managed to get both working on the same keyboard without the OLED cover pointing up at a weird angle. This may bother you less than it bothers me though.
* If you're using Vial and you want RGB, OLEDs, and loads of QMK features then you will likely find that your firmware is too large for a pro-micro controller. RP2040s will work fine though.

#Corne #MechanicalKeyboards #QMK