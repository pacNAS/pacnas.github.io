---
layout: post
title: "pacNAS - Why A New Distro?"
date: 2013-08-25 14:01
comments: true
author: "triplem"
categories:
---

A couple of month ago I did start to rip all my CDs into the nowadays quite
popular flac-format. Just as an information, you can take a look into [my](http://www.discogs.com/collection?user=triplem74)
discogs collection. This collection contains all CDs in my collection, which are
already converted. Right now (current number of collection items is 521) I did
convert already half of the whole (and unfortunately still growing) collection.
<!-- more -->

During this phase of ripping and tagging and handling my collection, I was searching
for a nice Media Player, which is able to play my quite large music collection
and present this in a "standard" way. Some goodies on this would be a control of
what is played via my smartphone or some other nice way (e.g. web interface). I
stumbled across [minimserver](http://www.minimserver.com) and I am still very much
interested in this project.

So now you are asking, what does this have to do with a NAS distribution? Well,
during my search for this "music server" I looked for different NAS distributions
(music files can grow quite quickly and there is lots of disc space needed) and
decided, that I need a NAS to store all my files. This NAS should be able to run
minimserver and also probably some other related stuff (like e.g. a kind of proxy,
to be able to let the music stream to my stereo without having the smartphone
turned on all the time). Since minimserver uses Java I thought, all is fine and
I can probably use an already existing NAS distribution. But far from it, since
minimserver is also using some distribution related binaries. This is still possible
with all of the NAS distributions, but with a higher effort (at least on the
FreeBSD based distros, since there I needed the Linux compatibility mode).

Of course I stumbled on the [OpenMediaVault](http://openmediavault.org/) distro,
which is Linux based. This distro is based on Debian, which I am not really into,
and furthermore it is based on a slightly outdated Kernel, so I would not be able
to use the latest up and coming filesystem (Btrfs).

After some digging around and much thoughts, I decided to create a new distro based
on my preferred distro [ArchLinux](http://www.archlinux.org). This distro has the
advantage, that I know it quite well (I use it since nearly 5 years) and it has
a very large and active community. Furthermore it does provide the latest and greatest
kernel version all the time.

Since I already participated in a "new distribution project" (ArchServer), I
asked the founder of this project (fukawi2), if he would like to participate.
Fortunately, he said yes. The new distro "pacNAS" was born.

Why the name pacNAS? pacNAS is a concatination of the word "pacman" (the famous
package manager of ArchLinux) and the word "NAS", which tells you, that we are mainly
focused on being a NAS distribution.

If you have any further questions, remarks, do not hesitate to leave a comment.
Furthermore, if you like the idea and like to participate as well, contact us via
email (see our [github project](http://github.com/pacNAS)).
