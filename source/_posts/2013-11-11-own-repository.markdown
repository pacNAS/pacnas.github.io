---
layout: post
title: "own repository"
date: 2013-11-11 20:57
comments: true
author: "triplem"
categories:
---

Our own binary repository is now reachable on the newly installed server
build.pacnas.org. To use this repository, you should edit your mirrorlist
and point it to http://build.pacnas.org/pacnas/$repo/os/$arch. We do provide
the following repositories:
<!-- more -->

* pn-core
* pn-extra
* pn-community and
* pn-testing

Those repositories are filled via our own now up and working buildbot instance
at http://build.pacnas.org/buildbot

If you are willing to contribute, you can get access to the bot as well as
are able to provide an own buildslave. We are working also on a PKGBUILD to
install the slave to an pacNAS system. The sources for the buildbot are located
in our github repository at http://github.com/pacNAS/pnbuildbot