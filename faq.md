---
title: Frequently Asked Questions
---
* table of contents
{:toc}

---

## Basic Gameplay

### How do I move my character?

Your character can move in eight directions, using one of the following two control schemes:

```
y   k   u       7   8   9
  \ | /           \ | /
h - . - l       4 - . - 6
  / | \           / | \
b   j   n       1   2   3

numpad:0        numpad:1
```

As hinted above, you'll want the `numpad` option set to `0` for the letter-based (or "vi-keys") control scheme, or `1` for the number pad control scheme.  You can test these settings in-game by pressing `O` (capital letter "O") to bring up the options screen (you may need to scroll it with `Space` or the `<` and `>` keys depending on your interface), and keep the one you want by editing your configuration file, which will either be found at `defaults.nh` in the game folder, or searched for at `~/.nethackrc` on non-Windows operating systems (create it with a text editor if it does not exist).

```
# In your configuration file...
OPTIONS=numpad:1
```

If you're trying to use the number pad control scheme (`numpad:1` above) and the keys don't seem to work, try toggling the `Num Lock` key on your keyboard.

Finally, you may be able to just click or touch the map to move your character there, depending on the interface you're using.

### What do all these weird symbols on the map mean?

If you're playing the TTY version (sometimes called "ASCII mode") of ***NetHack*** rather than a graphical tiles version, the dungeon, creatures and objects lying on the ground will be shown as letters and symbols.

Your character is represented by the `@` (at sign) with the cursor over it.

To discover what everything else is, press `;` (semicolon) to enter far-look mode, use the movement keys to position the cursor on what you want described, then press `.` (period) to get a brief description of the thing under the cursor.

For a more detailed list of what letters and symbols mean, consult the [Guidebook](#TODO), and the in-game help that can be viewed by pressing `?` (question mark).

### My character keeps picking up junk and getting burdened!

You have the autopickup option enabled.  You can toggle it off by pressing the `@` (at) key, or via the options screen.  You can then use the `d` (drop) or `D` (multi-drop) commands to drop the heavy objects from your inventory.

### I keep starving to death!

You should eat the corpses of slain foes by pressing `e` while standing over them.  Make sure they're fresh, otherwise you'll gain fatal food poisoning, shown as "FoodPois" in your status line.  Some corpses will keep indefinitely, such as those of lichens and lizards.  Beware the corpses of poisonous creatures, since their poison (not to be confused with food poisoning) will hurt you unless your character is poison-resistant.

If you're still starving, you can try `#pray`ing to your deity for help while weak or fainting from hunger.

### How do I use doors?

Doors can be `o`pened and `c`losed.  If a door is locked, you may need to kick it down using `Ctrl+D`.

### How do I use stairs?

Press `<` to go upstairs, and `>` to go downstairs.

### I can't find any stairs down!  Am I stuck?

There may be hidden doors or passages on the level; press `s` to search next to walls and at the ends of dead-end corridors to find them.  You may need to search a location multiple times before any secrets are revealed.

### My options were reset when I started the game again!

The in-game options screen can only be used to view and test options.  To *preserve* your options you must save them into your configuration file.

Here is an example of the contents of a configuration file.

```
#
# Sample NetHack configuration.
#
# Lines starting with # are ignored by NetHack.
#

# Numpad movement instead of hjklyubn.
OPTIONS=numpad:1

# Disable autopickup (the "!" in front means disable the option).
OPTIONS=!autopickup

# Set the character used for boulders to "0" instead of "`".
OPTIONS=boulder:0
```

Windows users should edit the `defaults.nh` file in their ***NetHack*** folder using a text editor.  Users of other operating systems will want to edit `~/.nethackrc` in their home directory; create it if it does not exist.

---

## Common Questions

### Can I use my old save files and bones files with the new version?

Almost always no, but see the release information for each version to be sure.  These files contain information from the internal structures of the game, and these almost always change between versions.

You *can* use save and bones files from 3.4.0, 3.4.1 and 3.4.2 with 3.4.3 (details are in the [release notes](#TODO)).  This also applies to 3.4.2 as well as 3.4.1 and 3.4.0.

You *cannot* use save or bones files from any previous version with 3.4.x.

### Can I share my bones files with my friends?

Maybe.  If you are using the same version of ***NetHack***, compiled with the same options, on the same kind of operating system, with the same compiler, it will probably work; if any of these differ, it definitely won't.

{::comment}
TODO:

* This should probably mention Hearse, an online service that could share bones
  amongst players across the Internet if they ran its client program.
{:/}

### My game crashed and I've got all these files ending in a number lying around.  Can I get my game back?

Maybe.  See the documentation for your version and look for either a `recover` program or a recover option to ***NetHack***.

{::comment}
TODO:

* Link to the page on how to use the recover program on the NetHack Wiki.
{:/}

### Why is it called NetHack if it's a single player game that doesn't use the net?

The "Net" in ***NetHack*** refers to USENET, which was the way the developers, many of whom have never met in person, originally used to organize the work on the program.  (Learn more at [USENET on Wikipedia](#TODO).)

### How about a multi-player version?

See [Things we are NOT doing](#has-anyone-ever-thought-that-multiplayer-nethack-would-be-a-neat-idea).

### How do I get a "-" in a player name?

Sorry, you can't.

### I changed alignment and saved the game.  When I restored I was greeted with my original alignment but the status line shows the new alignment.

This is not a bug.

---

## MacOS Information

### Will NetHack continue to be supported for Classic MacOS?

Yes.

{::comment}
TODO:

* Is this still the case?

* Come to think of it, do people nowadays care about any OS out of Apple that
  isn't OS X or iOS?  If not, perhaps this question (and thus this section)
  should be removed.
{:/}

---

## Things we are NOT doing

### Has anyone ever thought that multiplayer NetHack would be a neat idea?

(Sigh.)  Yes, at least a couple hundred people.  We think you can't do that in a playable way without compromising the basic idea of being able to think as long as you want about what you're doing, but many people have made many different suggestions as to the one obvious way to handle things.  If you still like the idea, you can try ***Crossfire***, a multiplayer roguelike for UNIX/X11.  Other games to check out are ***MAngband*** and ***Diablo***.

{::comment}
TODO:

* Instead of mentioning other roguelikes, this answer could at least talk about
  AceHack, which *did* have experimental multiplayer support, assuming it was
  compiled with the feature enabled and was specially hosted in a
  dgamelaunch-style server setting.  The nethack.xd,cm server, back when it was
  acehack.de, used to host a version of AceHack that could be played like this,
  but it was dropped in the server move due to general lack of interest in
  AceHack.

* Should probably also mention that one of the far distant goals of NetHack 4
  is to reimplement AceHack's multiplayer support, which should not be a
  surprise given that both variants are from the same person: ais523.
{:/}

### Why don't you add Glamdring/Mournblade/etc.?  After all, you have Orcrist/Stormbringer/etc., so you must have just overlooked the others!

Yes, but the new names would be just like the old ones, and wouldn't add anything new to the game.  We try to make new things add new choices instead of adding absolutely everything we can find.  (Believe it or not. :-)

### Why don't you add this new role?  I've come up with ideas for a leader, nemesis, and artifact...

We're still trying to get the existing roles differentiated, so adding more wouldn't make much sense.

If you still want to bring your idea for a role to life, you should write a patch for it and submit it to the community, where it might get some attention.

### Could you include an "easy" option?

That's what explore mode is for!

### How about prompting the player before they break a #conduct?

No.  The whole point of `#conduct` is that you are avoiding the kinds of actions that lead to violations.

{::comment}
TODO:

* Was this answer originally given because it was the concensus from the dev
  team on how conducts should work, or was it the case that nobody wanted to
  write the prompts and logic needed to make it happen?

* Does the dev team still adhere to this stance today?  If not, this answer
  will need to be updated.
{:/}

### Why don't you add this new conduct?  I'm sure it would be interesting.

It isn't feasible to track everything that could possibly be tracked in the game.  You are quite free to engage in the conduct you desire, but we are not planning on rolling too many more conducts into the official sources.

### Hey, how about a first-person shooter version (like Doom)?

Sorry, that would be a very different game, and we like working on this one.

{::comment}
TODO:

* Of what I've seen, people ask more often for a first-person *view* for
  NetHack, which in fact has two alternatives, neither of which are that good.
  First is a Japanese-only window port that was only made for Mac OS whatever.
  The other would be to run the TTY version of NetHack through a roguelike
  front-end program called NotEye, which requires some configuration and
  doesn't look very nice anyway.
{:/}
