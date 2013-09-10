---
layout: post
title: "btrfs - best practices"
date: 2013-09-10 20:56
comments: true
author: "triplem"
categories:
---

Right now we are adapting the installer to use btrfs as the base filesystem for
the PacNAS system. There are obviously a couple of ways on implementing this, so
that we try to "suggest" one way to do this, but also allowing other possible ways
as well.
<!-- more -->

1. Partioning
If you are searching for "btrfs best practices", you will stumb across [this](http://comments.gmane.org/gmane.comp.file-systems.btrfs/25423)
mailing list entry, and I guess, we are going to follow the "partition instead
of raw device" philosophy. We will create one partition on the wanted device and
will then separate the partition by using subvolumes.

1. Subvolumes
I guess, that [Bitloom](http://blog.fabio.mancinelli.me/2012/12/28/Arch_Linux_on_BTRFS.html)
suggests a valid approach for subvolumes on a btrfs root volume. What I don't like about
his approach is the subvolume for /var and the mounting of /var/lib into the root
subvolume. If you take a look on [patshead.com](http://blog.patshead.com/2010/02/testing-btrfs-root-file-system-on-ubuntu.html)
you will read, that he prefers to creates many subvolumes beneath the root of the
Btrfs volume. I guess this is a way more KISS way.

"Our" Best Practices
====================

1. We are partioning the wanted drive with just one partition.
1. We are creating a couple of subvolumes (rootfs, tmpfs) on this partition and
mount these volumes to the corresponding mount points (/ to rootfs, /tmp to tmpfs).
1. On each update of the system, we are creating a snapshot (at least provide
some scripts for this), and do provide a mechanism to "undo" the latest update.
1. We are not using a homefs subvolume, since we strongly believe that the home
directories are stored on separate partitions (meaning: data drives). Of course
these data drives can (and should) be formatted with btrfs.
1. It is a possibility to use the btrfs seed-device as a "live" system and copy this
drive over to the new system. This needs to get investigated, but see [Wikipedia - btrfs](http://en.wikipedia.org/wiki/Btrfs#Seed_devices).

Some Roadmap Things
===================

1. Create scripts for creating and restoring snapshots before/after an pacman
update.
1. Add mkinitcpio-btrfs hook as a default.

What do you think about our Best Practices, what suggestions do you have? We are
more then happy to get some feedback.
