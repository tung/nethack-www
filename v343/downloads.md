---
title: Downloads
---
Don't forget to read the [NetHack 3.4.3 release notes](release.html)!

* table of contents
{:toc}

---

## Windows

[nethack-343-win.zip](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-win.zip/download)
: NetHack 3.4.3 for Windows.  Contains `NetHackW.exe` (graphical tiles, recommended) and `NetHack.exe` (TTY console).

**You must EXTRACT ALL FILES from the ZIP archive before running the game, otherwise you will get this error: Cannot open dungeon description - "dungeon"!**

**Do not copy the EXE files to your desktop; create shortcuts instead.**

See our [info for setting the window/font size](bugmore/vista-win7.txt) if running `NetHack.exe` under Windows newer than XP.

([Old Windows download instructions.](ports/download-win.html))

---

## Mac OS X

There are several Mac binaries available; you only need one of these.  *Only the first binary below will run under OS X 10.7 Lion*, and none will run on 68K-based Macs.

[NetHack-343-Lion-mac-Term-1.dmg](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/NetHack-343-Lion-mac-Term-1.dmg/download) (recommended)
: **OS:** Intel Macs running OS X 10.7 Lion
  **Map:** text
  **UI:** terminal
  Mount this image to start the installer.  Files are placed in `/usr/games` and `/Applications`.

[nethack-343-mac-carbon.sit](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-mac-carbon.sit/download)
: **OS:** PowerPC Macs running Mac OS 8.5, 9.x or OS X 10.x up to 10.6 Snow Leopard.
  **Map:** text
  **UI:** Carbon GUI
  Extract the files in this archive somewhere convenient.

[NetHack-343-3-macosx-qt.dmg](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/NetHack-343-3-macosx-qt.dmg/download)
: **OS:** PowerPC Macs running OS X 10.2 up to 10.6 Snow Leopard.
  **Map:** graphical tiles
  **UI:** Qt GUI
  Mount this image and drag the NetHackQt application and Documentation folder somewhere convenient.

[NetHack-343-Term.dmg](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/NetHack-343-Term.dmg/download)
: **OS:** PowerPC Macs running OS X 10.x up to 10.6 Snow Leopard.
  **Map:** text
  **UI:** terminal
  Mount this image and start the installer.  Files are placed in `/usr/games`.
  If you get "No write permission to lock perm!" when trying to play:

  * [OS X 10.3 workaround](bugmore/perm-mac.txt)
  * [OS X 10.4 workaround](bugmore/perm-mac104.txt)
  * OS X 10.3.9 should try the 10.3 workaround first, then the 10.4 workaround if that doesn't help.

([Old Mac OS download instructions.](ports/download-mac.html))

---

## Linux

The easiest way to download NetHack for Linux is to search for the `nethack` package in the package manager of your Linux distribution, rather than downloading it here.

More technically-minded Linux users may prefer to compile NetHack themselves from the [source code](#source-code), which will always link to libraries as installed for your distribution.

The RPM packages below should install for and run on Redhat 9 and Suse 8.

[nethack-343-linux-X11.tgz](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-linux-X11.tgz/download)
: NetHack 3.4.3 for TTY (text) and X11/Athena (graphical tiles).  Requires glibc-2.3 and X11 libraries.  Check [README.linux](README.linux.txt) for further dependency information and installation instructions.

[nethack-3.4.3-1.i386.rpm](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-3.4.3-1.i386.rpm/download)
: Same as above in RPM format.

[nethack-3.4.3-1qt.i386.rpm](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-3.4.3-1qt.i386.rpm/download)
: NetHack 3.4.3 with graphical tiles using the Qt GUI.  Requires Qt libraries (version 2.x).

([Old Linux download instructions.](ports/download-linux.html))

---

## MS-DOS

[nh343dos.zip](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nh343dos.zip/download)
: Protected-mode NetHack (tty and graphical tiles).  Requires a 386 or greater processor, 3 MB of extended memory and 2.8 MB of hard drive space.

This requires DPMI to run.  To run this on plain DOS, download [CWSDPMI.EXE](http://www.delorie.com/djgpp/dl/ofc/simtel/v2misc/csdpmi5b.zip/) and put it in your NetHack directory.

There is no real-mode overlaid binary distribution of NetHack 3.4.3.

([Old MS-DOS download instructions.](ports/download-msdos.html))

---

## Windows CE

These installer packages must be downloaded to, and run on, a Microsoft Windows computer, not on the target Windows CE system.

[nethack-343-ce-ppc.exe](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-ce-ppc.exe/download)
: NetHack 3.4.3 installer package for *PocketPC* platform (Windows CE 3.0, PocketPC 2000 and PocketPC 2002).

[nethack-343-ppc.ARM.CAB](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-ppc.ARM.CAB/download)
: Same as above in CAB format.

[nethack-343-ce-hpc.exe](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-ce-hpc.exe/download)
: NetHack 3.4.3 installer package for *Handheld PC Professional* running Windows 2.11 or higher.

[nethack-343-ce-ps211.exe](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-ce-ps211.exe/download)
: NetHack 3.4.3 installer package for the *Palm Size PC* running Windows CE 2.11.  Note: This has nothing to do with any PalmOS-based PDA.

[nethack-343-sph.ARM.CAB](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-sph.ARM.CAB/download)
: NetHack 3.4.3 installer package for the *Smartphone 2002*.  This is an *unsigned* CAB so you will need an *unlocked* phone to install and run this (e.g. a *developer* version of the Orange SPV).  Use the `#` (hash) key on your phone to access different keypad layouts.

[nethack-343-sph-k.ARM.CAB](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-sph-k.ARM.CAB/download)
: NetHack 3.4.3 installer package for the *Smartphone 2002* with full keyboard support enabled.  This is an *unsigned* CAB so you will need an *unlocked* phone to install and run this (e.g. a *developer* version of the Orange SPV).

The installer packages above were created with [EZSetup by Scott Ludwig](http://www.scottlu.com/Content/EZSetup.html).

Read the [old Windows CE download instructions](ports/download-wince.html) for compatibility information.

---

## OS/2

[nethack-343-os2.zip](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-os2.zip/download)
: 32-bit NetHack 3.4.3 for OS/2 (TTY text mode), built using EMX 0.9d.  In principle it should be runnable on OS/2 version 2.0 or later but has not been tested on any version other than 4.0.

[nethack-343-os2-X11.zip](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-os2-X11.zip/download)
: 32-bit NetHack 3.4.3 for OS/2 (X11 graphical tiles and text modes), built using EMX 0.9d.  Requires the EMX runtime libraries, `XAW.dll` (X11 Athena widgets) and dynamically links against the XFree86 libraries.

([Old OS/2 download instructions.](ports/download-os2.html))

---

## Amiga

[nethack-343-ami.lha](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-ami.lha/download)
: NetHack3.4.3 for 68K-based Amigas running AmigaDOS 3.0 or later.  It might work on systems as early as AmigaDOS 2.05.  Read `Install.ami` in the LHA archive for more information.

([Old Amiga download instructions.](ports/download-amiga.html))

---

## Atari

[nethack-343-atari-gt.lzh](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-atari-gt.lzh/download)
: NetHack 3.4.3 for Ataris running TOS, MiNT or MagiC.  This is a GEM (tiles, default) and TTY (text only) port of NetHack.  Requires 2 MB of memory and 3 MB of hard drive space.

([Old Atari download instructions.](ports/download-atari.html))

---

## Source Code

Instructions on how to compile the source code are included in the source release.

Alternatively, you can clone our [code repository]({{ site.code_repository_url }}) for the latest version of NetHack, or any other version by its tag; see [How to Contribute]({{ site.baseurl }}/how-to-contribute.html#editing-the-source-code) for more details.

[nethack-343-src.tgz](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-src.tgz/download)
: NetHack 3.4.3 source release.

[nethack-3.4.3-1qt.src.rpm](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-3.4.3-1qt.src.rpm/download)
: NetHack 3.4.3 source release, in RPM format, set up to compile with the Qt GUI.  (You only need one of this or the previous file.)

[nethack-343-ce-proj.zip](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-ce-proj.zip/download)
: NetHack 3.4.3 Win CE and Smartphone compiler project files.  (Only needed to compile for Windows CE and Smartphone platforms.)  Unzip this into the `sys/wince` folder of the source code.

[nethack-342-343-diffs.gz](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-342-343-diffs.gz/download)
: Context diff from version 3.4.2.  (If you don't know what this is, you don't need it.)

([Old source code download instructions.](download-src.html))

---

## Large tiles (optional)

[nethack-343-tiles32-2.zip](http://sourceforge.net/projects/nethack/files/nethack/3.4.3/nethack-343-tiles32-2.zip/download)
: A 32x32 pixel tileset, larger than the default 16x16 tileset.  Only usable with graphical tiles ports of NetHack.

To use this tileset, extract it to the same directory/folder as NetHack, then add the following line to your config file:

```
OPTIONS=tile_file:tiles32.bmp, tile_width:32, tile_height:32
```
