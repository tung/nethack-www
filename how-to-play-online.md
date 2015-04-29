---
title: How to Play Online
---
Although NetHack is a single-player game, it can still be played online.  By connecting to a NetHack server, you can track and live-report your deaths, ascensions and in-game accomplishments, as well as spectate other players' games and let them spectate yours.  You can even find each other's bones files!  Playing online also allows you to participate in community-driven NetHack tournaments such as [Junethack](http://nethackwiki.com/wiki/Junethack) and [/dev/null](http://nethackwiki.com/wiki//dev/null/nethack_tournament).

* table of contents
{:toc}

***Note:*** *Do NOT contact us with questions or issues about programs and servers related to playing NetHack online; they are unaffiliated with the DevTeam.*

{% include screenshot.html file='putty-nao-gameplay.png' markdown=true %}

---

## Online NetHack Servers

NetHack servers exist in various geographical locations, so choosing one close to you will reduce lag.  Different servers may also host different versions of NetHack, and sometimes even NetHack variants, so look around.  Examples of NetHack servers are [nethack.alt.org](http://alt.org/nethack/) (commonly known as *NAO*) and [nethack.xd.cm](https://nethack.xd.cm/).

[List of NetHack servers on the NetHack Wiki.](http://nethackwiki.com/wiki/Public_server)

**nethack.alt.org** will be used for the examples on this page.

---

## Connect via telnet

If you're using an OS that isn't Windows, open your OS's terminal and type `telnet nethack.alt.org`.  That's all!

If you're using Windows, you'll need to download a **telnet client** such as [PuTTY](http://www.chiark.greenend.org.uk/~sgtatham/putty/).  The rest of this text assumes you're using PuTTY; instructions for other telnet clients should be similar to what's written here.

First, run `putty.exe`.  At the configuration screen, select "Telnet" for you connection type, enter `nethack.alt.org` as the host name, then click the "Open" button.

{% include screenshot.html file='putty-telnet.png' markdown=true %}

With any luck, you should be presented with something like this:

{% include screenshot.html file='putty-nao.png' markdown=true %}

Follow the on-screen instructions to watch other players or register to play on the server.

---

## Connect via SSH

Connecting via SSH is very similar to connecting via telnet, the difference being that SSH connections are encrypted whilst telnet connections are not.  Some NetHack servers support only one of SSH or telnet; **nethack.alt.org** allows both.  Check the website for the server to learn which connection types are supported.

If you're using an OS that isn't Windows, open your OS's terminal and type `ssh nethack@alt.org`.  Choose 'yes' when asked to trust the host key.  That's all!

If you're using Windows, you'll need an **SSH client**, and it just so happens that [PuTTY](http://www.chiark.greenend.org.uk/~sgtatham/putty/) is also an SSH client as well as a telnet client!  (How convenient!)

Run `putty.exe`.  At the configuration screen, select "SSH" for your connection type, enter `nethack@alt.org` as the host name (i.e. username `nethack` and host name `alt.org`), then click the "Open" button.

{% include screenshot.html file='putty-ssh.png' markdown=true %}

The first time you connect, you'll be asked to trust the host key, so select 'Yes'.

{% include screenshot.html file='putty-host-key.png' markdown=true %}

From here you should see the server's welcome screen, similar to connecting via telnet.

---

## Connect via telnet using Ebonhack

You may have noticed that playing online with telnet and SSH only supports non-graphical tty versions of NetHack.  [Ebonhack](http://www.junction404.com/#ebonhack) is a native cross-platform client that can display graphical tiles while playing online.

A few caveats:

* Ebonhack can only connect to servers that support telnet; SSH is *not* supported.
* Ebonhack can be downloaded ready-to-run for Windows, but other platforms may need to compile it from its source code, a process that is very technical.
* For best results, you'll need to set the `vt_tiledata` option in the configuration file for your account.
* If you're watching another player and they do not have `vt_tiledata` enabled, the graphics may appear jumbled; press the 'Home' key to toggle graphics on and off.

{% include screenshot.html file='ebonhack-default.png' markdown=true %}

---

## Join the IRC channel of the server

Connecting to a server via telnet or SSH will let you play and spectate games, but to see live announcements of deaths, ascensions and in-game accomplishments you will need to connect to the server's IRC channel using an **IRC client** such as [HexChat](https://hexchat.github.io/) or [ChatZilla](http://chatzilla.hacksrus.com/).

The IRC channel for **nethack.alt.org** is `#nethack` on the freenode IRC server.  If your IRC client doesn't already list freenode amongst its servers, connect it to `chat.freenode.net`.  Once connected, type `/join #nethack` to enter the `#nethack` channel.

To learn the IRC channels of other NetHack servers, visit their respective websites or check out [the list of IRC channels on the NetHack Wiki](http://nethackwiki.com/wiki/Freenode).

---

## Remember to check the website of the server

Most NetHack servers have an associated website, e.g. **nethack.alt.org** can be found at <http://alt.org/nethack/>.  This website will tell you how to connect to watch or play online, whether telnet and/or SSH is supported, as well as grant access to player dump logs, configuration files and past game recordings in the form of [ttyrecs](http://nethackwiki.com/wiki/Ttyrec).

**nethack.alt.org** allows you to view your game statistics and compare your scores to other players.  For other servers, check out the [online NetHack scoreboard](https://voyager.lupomesky.cz/nh/).
