---
title: NetHack 3.4.2 Released
author: keni
date: 2003-08-31 00:00:00 +0000
tags: [v342, releases]
---
The NetHack DevTeam is pleased to announce the release of NetHack 3.4.2, the second bugfix release for NetHack 3.4.  This release contains more than one hundred general bug fixes (see below), as well as the following more specific items:

* Fixed a fatal bug that triggered a panic when your secondary weapon was cursed during bones file creation
* Fixed a fatal bug that caused a crash when applying figurine, candle, or bell that gets used up
* Fixed message ordering for several actions
* Fixed some Gnome compilation problems on Redhat 7.2 and 8.0
* Fixed a problem in the util Makefile
* use random() by default under linux instead of lrand48()
* win32 tty adjustments and support for loading alternative key handlers

Read the [release notes][342-release] for more information.

[**Download NetHack 3.4.2 now!**][342-downloads]

[342-downloads]: {{site.baseurl}}/v342/downloads.html
[342-release]: {{site.baseurl}}/v342/release.html
