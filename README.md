# arch-install
##What is?
This repository will be a recording for personal use to document my going through a fresh archlinux install on my 2015 HP Pavillion laptop. It's basically so that, I ever have to do this again, I don't have to relearn how to change the config file that dictates the interactions between arch and the wifi adapter (which is not fun because apparently HP structured its wifi adapters in a way that linux hate, or vice-versa, or both).

The [Archwiki](https://wiki.archlinux.org/) already has a terrific [installation guide](https://wiki.archlinux.org/index.php/installation_guide) that will probably render the entirety of this repository at best redundant, at worst misleading, for most people. I recommend you look at that unless you have the *exact* same laptop as I do, which I really hope you don't.

Seriously, go look at that archwiki. This will probably be mostly obvious things it took me too long to figure out, rants that I'm probably wrong about, bad jokes (often in pun form), and other things to keep me entertained during this process. If you do find something helpful then great! Otherwise, see you around, and have a great day.

##live-boot USB Creation
This doesn't require a file, just:
-Go to [this](https://www.archlinux.org/download/) page and use the magnet link to torrent the most recent version of Arch.
-use fdisk -l to find the name of the partition that specifies your USB.
-Use the instructions on [this](https://wiki.archlinux.org/index.php/USB_flash_installation_media) page to format the USB key designated by the partition name found in previous step.

