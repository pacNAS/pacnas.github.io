---
layout: post
title: "install willie"
date: 2013-11-23 20:24
comments: true
author: "triplem"
categories:
---

This is mainly a documentation post on how to install [willie](http://willie.dftba.net/)
as a service on an ArchLinux server.
<!-- more -->

All necessary dependencies can be installed easily with pacman (mainly: python2-pytz
and python2-pyopenssl). The willie PKGBUILD can be found in the [AUR](https://aur.archlinux.org/packages/willie/).

After the install, the bot installs a new configuration file in ~/.willie. This file
should be adopted later. I have made the following adoptions to the config:

```
[core]
logdir = /var/log/willie
pid_dir = /run/willie
```

The above mentioned directories are created manually ;-) Of course the rights
need to be set as well:

```
chown root:willie /var/log/willie -R
chmod g+w /var/log/willie -R

chown root:willie /run/willie -R
chmod g+w /run/willie -R
```

```
[db]
userdb_type = sqlite
userdb_file = /var/lib/willie/willie.db
```

The above mentioned directory is created manually as well. The db-file is
created then automatically. The rights need to get set here as well:

```
chown root:willie /var/lib/willie -R
chmod g+w /var/lib/willie -R
```

A new user (willie) is created using the following command

```
useradd -d /var/lib/willie -M willie
```

The I copied the [willie.service](https://github.com/embolalia/willie/blob/master/contrib/willie.service)
to /etc/systemd/system/willie.service. Some pathes (e.g. to the config file) needs to get adopted
accordingly. Of course this service needs to get enabled via systemctl ;-)


