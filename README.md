# environment-personal
A log for putting together my personal environment.  Specifically for tracking changes, reproducing the environment, and tracking down where cruft appears.

## About

I am not a ricer, but I like to keep my environment very lean.  I also want to be able to reproduce my environment quickly and easily, upon any machine.

Another factor is tracking what is installed, and what get's removed when not in use, for the sake of being able to keep my environment as clean as possible.

Also, notes and cheat sheets for the programs I do use are helpful.

I currently have three laptops for this.  One is purely for travel gaming as an emulator machine.  It is a lower end machine that can handle emulation up to PS2.  Not much needs to be said about that one, it just works and that is all I use it for.

The others are, on the higher end, a Dell Inspiron 5577 version 1.09, and a lower end backup (and travel) machine, a Hewlett-Packard EliteBook 8460w version A0001D02.

Product information can be found easily with

~~~
sudo dmidecode | grep -A3 '^System Information'
~~~

## Base Configuration

Basic Arch Linux install.  The Dell has Windows 10 for dual boot, though that has not actually been used.  The machine was specifically purchased for the sake of being able to utilize Windows programs as needed, so I have about half of my hard drive doing nothing.

The Dell also has both an NVIDIA graphics card and intel as well, so bumblebee must be installed to get full use of the graphics.  This means no Vulkan.  Prior to making it an Arch machine, it used Ubuntu, which was able to utilize Vulkan.  I will need to watch for that.  Nvidia drivers are 340xx.

The Dell also has massive problems with power control, well documented by many users.  The backlight is automatically too low and any time the smart charging needs to speak up (which is any time it must charge tha battery) it complains about using athird party charger (which it does not).  Disabling the smart functions in BIOS shuts down the complaining (as well as setting the power function to "Normally on AC") and downloading  the command line utility "light" allows fixing the dim screen.

~~~
# Show devices
light -L

# Show brightness value of device, the example is for my backlight
light -G /sysfs/backlight/intel_backlight

# (S)et light level or (A)dd light level
# No device needs to be listed, change only happened to my backlight
# Even though all lights are listed
light -S 10
~~~

The HP uses AMD, which automagically work.

## LARBS

Initial setup is for [LARBS](https://github.com/LukeSmithxyz/LARBS) which suits most of my needs.  Any changes to this setup will be reflected here with config files uploaded.

## Vim

I want to avoid adding any plugins to Vim directly, though I make make changes to particular settings.  Previous vim setups have become far too clunky, and many of the tools that I did need are available as tools that I can invoke from the terminal already.  Any changes to vimrc from the LARBS baseline will be reflected in this repo.

Not happy with the LARBS vimrc.  Just does not work well for my purposes.  Went
ahead and added Neovim and made a custom rc.

## Installed Items

Installed Pandoc and cloned [Pandoc Book Template] for writing.

[Pandoc Book Template]: (https://github.com/wikiti/pandoc-book-template)

## Removed Items



## Considering Items

Aspell - just the best as far as i am concerned

alex / proselint - I want a good prose linter.  Proselint seems to be the better of the two, though I may install both for a time to test them out.

Pandoc / DocBook - Pandoc is in the lead here, but there are other options as well.

fountain parser - Many exist with varying degrees of coverage for the markup.  Damned shame that Pandoc does not cover fountain...
