---
layout: post
title: "btrfs - best practices - part 2"
date: 2013-09-11 22:39
comments: true
author: "triplem"
categories:
---

We discussed the usage of btrfs in our previous post. We discovered a nice
mkinitcpio-hook, which allows us to provide a rollback option based on snapshots.
We have forked an up-to-date version, and will most probably provide some
additional documentation and scripts. For the source of the package see [github - source](https://github.com/pacNAS/mkinitcpio-btrfs)
and [gihub - package](https://github.com/pacNAS/pkgbuilds/tree/master/core/mkinitcpio-btrfs).

Our new installer will use the suggested structure of the btrfs subvolumes while creating
the disk structure of the new system.

We do have created a new version of the above mentioned sources. This new version is
slightly adopted to our needs. The original version ([xtfxme](https://github.com/xtfxme/mkinitcpio-btrfs))
contains both the logic/source as well as the PKGBUILD, which we split, to keep these
separate.


