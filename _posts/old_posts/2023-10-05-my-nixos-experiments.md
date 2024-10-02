---
title: "My NixOS Experiments"
date: "2023-10-05"
categories: 
  - "linux"
---

I have been experimenting with [NixOS](https://nixos.org/) for a few weeks, and whilst I'm not ready to run it on my main machine, I think I _could_ if I had to. These notes are all the things I had to search, or experiment with, and are largely here for my reference, although if they help someone else then that is great.

## Snippets from my configuration.nix file

```
# Enable the GNOME Desktop Environment.
services.xserver.displayManager.gdm.enable = true;
# services.xserver.desktopManager.gnome.enable = true;

# Enable i3
services.xserver.windowManager.i3.enable = true;

# Configure keymap in X11
services.xserver = {
  layout = "gb";
  xkbVariant = "";
};

# Configure console keymap
console.keyMap = "uk";

# Enable sound with pipewire.
sound.enable = true;
hardware.pulseaudio.enable = false;
security.rtkit.enable = true;
services.pipewire = {
  enable = true;
  alsa.enable = true;
  alsa.support32Bit = true;
  pulse.enable = true;
  # If you want to use JACK applications, uncomment this
  #jack.enable = true;

  # use the example session manager (no others are packaged yet so this is enabled by default,
  # no need to redefine it in your config for now)
  #media-session.enable = true;
};

# Enable touchpad support (enabled default in most desktopManager).
# services.xserver.libinput.enable = true;
};

# Allow unfree packages
nixpkgs.config.allowUnfree = true;

# Allow QMK to write to keyboards

hardware.keyboard.qmk.enable = true;

# needed for store VS Code auth token 
services.gnome.gnome-keyring.enable = true;

# List packages installed in system profile. 
environment.systemPackages = with pkgs; [
git
featherpad
pandoc
dropbox
dmenu
feh
i3lock
kitty
i3blocks
arandr 
scrot 
xautolock 
barrier
imagemagick
neofetch
zathura
pcmanfm
htop
blueman
cowsay
fortune
shellcheck
abiword
rhythmbox
brasero
sound-juicer
transmission
byobu
tmux
screen
qmk
networkmanagerapplet
protonvpn-gui
protonvpn-cli
protonmail-bridge
unixbench
zerotierone
zoom-us
caffeine-ng
copyq
vscode
];
```

## A script to automate changes

```
#!/bin/sh
# Standard error mitigation
set -euo pipefail
# Replace existing config
cd /etc/nixos/
sudo mv configuration.nix configuration.nix.old
# download new config
sudo wget https://raw.githubusercontent.com/teknostatik/nixos/master/configuration.nix
# Test
sudo nixos-rebuild test
# Deploy
sudo nixos-rebuild switch --upgrade
# Clean up and then go home
nix-collect-garbage -d
cd $HOME 
```

## Useful links

- [How to create a live USB installer](https://nixos.wiki/wiki/Creating_a_NixOS_live_CD)

- [Search for packages](https://search.nixos.org/packages)
