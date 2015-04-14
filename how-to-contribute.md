---
title: How to Contribute
---
You don't need to be a member of the NetHack DevTeam to help the cause!  Whether you're a developer, writer, artist, or just a humble player, there are many ways you can contribute to the future of NetHack.  Read on!

* table of contents
{:toc}

***Note:*** All work that ends up in NetHack will be placed under the [**NetHack General Public License**]({{ site.baseurl }}/license.html), so make sure you're okay with that before proceeding.

---

## Submitting a bug or suggestion

The easiest way to contribute to NetHack is to report bugs that you find and offer suggestions for improvement.  Send them to our [public bug tracker]({{ site.public_bug_tracker_url }}) or email them in, following the advice on the [Contact Us page]({{ site.baseurl }}/contact-us.html).

Before providing a suggestion, check the list of [Things we are NOT doing]({{ site.baseurl }}/faq.html) in our FAQ.

---

## Writing documentation and encyclopedia entries

The best way to offer improvements and additions to our documentation and in-game encyclopedia lore text (i.e. what you get when you ask for more info when looking at a monster in the game using `;` (semicolon) or type something in using the `/` (forward slash) command) is by [editing the source code](#editing-the-source-code) (see below), but if that's too hard for you, you can also send it to our bug tracker or email it in.

If you're offering a new encyclopedia entry that comes from a source, please include what that source is as well.

---

## New tiles and tilesets

Monitor sizes have grown tremendously since our default tileset was conceived, but the tileset itself has not.  If you have what it takes to make a new large tileset, send it to our bug tracker or email us.  If you're emailing, don't attach the tileset image directly unless we ask, host the image somewhere else and link to it instead.

Even if the tileset isn't bigger than our current default tileset, we may still want to see it.  Consider also sharing it with the greater NetHack community; virtually all graphical tiles ports of NetHack support custom tilesets, so people can try yours right away!

If you find tiles that are missing or seem off, or have improvements to some existing tiles, let us know about those as well.

---

## Editing the source code

If you're a developer, check out our [code repository]({{ site.code_repository_url }}), where the latest NetHack development happens.

If you want to make changes to the NetHack source code, first clone our [git](http://git-scm.com/) repo:

{::comment}
TODO: Change this to the REAL git clone url once it's online.
{:/}

```
$ git clone https://dev.nethack.org/nethack.git
$ cd nethack
```

Create a new branch and check it out:

```
$ git branch my-cool-new-change
$ git checkout my-cool-new-change
```

Now you can make your changes, commit them and make them publicly available on a git hosting service such as [GitHub](https://github.com/).

Avoid making changes directly to the `master` branch; you'll want to keep it clean so you can use it to stay up-to-date with the main NetHack repo.

If you need ideas on what to work on once you have a clone of our repo, check the bug tracker.

---

## Follow our blog

Finally, keep an eye on [our blog]({{ site.baseurl }}/blog/); sometimes we may ask for help, and you'll find something that you can help with even if you can't think of anything yourself.
