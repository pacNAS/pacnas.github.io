---
layout: post
title: "pacnas installer"
date: 2013-10-06 17:19
comments: true
author: "triplem"
categories:
---

Our installer (currently a very easy and still a rough draft version) brought up
a couple of problems. We have taken a look onto the [antergos Cnchi installer](https://github.com/Antergos/Cnchi)
and decided that the CLI part of it seems to be a good starting poing.

We have stripped this installer and reworked it, so that we can use it for our own
purposes. Basically the installer does now provide the following functionality:

* Select the language
* Select a keymap
* Adjust time and date - This is not working right now, in that the selected
date and time are not used on the new installed system.
* Prepare Harddrives - This is an easy way to partition and format the harddrive
fully automatic. The subvolumes for btrfs are created in this step as well. There
is still some work needed to provide some adjustements for ssds and normal hard disks.
* Install the System - The base packages are installed into the newly created system.
* Configure the System - Some minor configuration for the system.

Well, this is pretty much it. We definitly would like to add some possibilities, so
that you are able to provide your own partition scheme, if you would like to. Most
probably we will follow the steps used from the original
[ArchLinux Install scripts](https://wiki.archlinux.org/index.php/Installation_Guide).

Furthermore there is still some room for error handling and other optimizations, but
for a rough first draft, it looks pretty good ;-)

One problem arose during the implementation. Since we are using btrfs on our root
file system, the mkinitcpio-fsck-hook reported an error, that fsck.btrfs is not
available. Digging into this issue brought up some [errors](https://bugs.archlinux.org/task/37203)
in the ArchLinux bugtracker. Due to the response in the shown Bug, we have decided
to provide our own [mkinitcpio-package](https://github.com/pacNAS/pkgbuilds/tree/master/core/mkinitcpio).
This version basically patches the HOOKS-variable to not use the fsck-hook anymore.

So, if you have any ideas and/or recommendations for improvements of the installer,
feel free to fork and add pull requests. We are more then happy to receive those ;-)
