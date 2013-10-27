---
layout: post
title: "howto build a buildservice"
date: 2013-10-27 20:23
comments: true
author: "triplem"
categories:
---

Currently we are trying to automate the build of our own packages. Therfore we just have
rented a server from [netcup.de](http://www.netcup.de), because they do have some fair
offers (see [here](http://www.netcup.de/bestellen/produkt.php?produkt=547)).
Based on this offer, we do have already established our own package repository (a domain for
this will be published soon). Furthermore we need a build service, and this should be based
on the already exisiting build-services from archlinux (called devtools).
<!-- more -->

After some initial investigations, the [buildbot](http://www.buildbot.net) seems to be a
good solution to build something like this fully automatic. After looking at the
ArchLinux [Quarters](https://wiki.archlinux.org/index.php/Automated_Package_Build_System) wiki
page and the proposed solutions there, we decided to take a look at other possible solutions
and walked across [VectorLinux Buildbot](http://vlcore.vectorlinux.com/buildbot/).

This buildbot is a adoption of the original buildbot and offers some modifications, which
are necessary for us as well (e.g. one multi-project repository with several "packages"). You
can take a look at their source code [here](https://bitbucket.org/VLCore/vlbuildbot/src).

Since buildbot does a separation of a build into several steps, we defined the following
steps for our builds:

1. create the source package of a package (using makepkg --allsource)
1. create two build chroots (i686 and x86_64)
1. copy source package and build in the corresponding chroot (e.g. each architecture)
1. copy build source package to a accessable directory (accessable from a HTTP share)
1. copy build package into the corresponding repository (e.g. core/extra/community and i686/x86_64/any)

We tried already some different order and separation of build steps (try to use the grub
package, since this one does seem to be "special", and requires some special treatment, e.g.
it is using bzr as a source package as well as it uses the CARCH-Variable in the PKGBUILD)
and the above build order seemed to work quite well. Further adjustements int he future are
possible and will be implemented, if the need arises.

There are still some issues concerning permissions, but those do seem to be resolvable. Other then
that we do plan to push a first rough draft of our solution to github quite soon, pleas watch the
devtools-repository and most probably a new repository with the buildbot itself will pop up as well.

Up until this, we are more then happy to receive some feedback from your side. What are your thoughts
on this one?
