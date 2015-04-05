---
layout: default
title: Frequently Asked Questions
---
* table of contents
{:toc}


## Common Questions

### Can I use my old save files and bones files with the new version?

Almost always no, but see the release information for each version to be sure.  These files contain information from the internal structures of the game, and these almost always change between versions.

You *can* use save and bones files from 3.4.0, 3.4.1 and 3.4.2 with 3.4.3 (details are in the [release notes](#TODO)).  (This information applies to 3.4.2 as well as 3.4.1 and 3.4.0.)

You *cannot* use save or bones files from any previous version with 3.4.x.

### Can I share my bones files with my friends?

Maybe.  If you are using the same version of ***NetHack***, compiled with the same options, on the same kind of operating system, with the same compiler, it will probably work; if any of these differ, it definitely won't.

### My game crashed and I've got all these files ending in a number lying around.  Can I get my game back?

Maybe.  See the documentation for your version and look for either a `recover` program or a recover option to ***NetHack***.

{::comment}
TODO:

* Link to the page on how to use the recover program on the NetHack Wiki.
{:/}

### Why is it called NetHack if it's a single player game that doesn't use the net?

The "Net" in ***NetHack*** refers to the way the developers, many of whom have never met in person, organize the work on the program.

{::comment}
TODO:

* What, no mention of USENET?  Seems like it would shed light here.

* Is USENET even still used to coordinate NetHack development?  Seems like
  email and mailing lists are the primary means of coordination, in which case
  it'd be more accurate to say that USENET *used* to be used to organize work
  on NetHack.
{:/}

### How about a multi-player version?

See [Things we are NOT doing](#has-anyone-ever-thought-that-multiplayer-nethack-would-be-a-neat-idea).

### I kicked a chest, and "heard a muffled shatter" but didn't find any broken glass.  What happened?

We don't keep track of dungeon rubbish.

{::comment}
TODO:

* I doubt this question is asked frequently.  Perhaps it should be removed.
{:/}

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

### Are you porting NetHack to Android?

No.  Someone apparently has, but we have nothing to do with it.

{::comment}
TODO:

* Why would people ask this if there's an Android port that can easily be found
  on the Google Play store (I believe it's free)?  Perhaps this question should
  be removed.

* Aside: The dev team could use someone that could put out Android packages,
  given that Android as a platform is more relevant than 90% of the platforms
  that NetHack has been released to in the past.
{:/}

### Are you porting NetHack to Java?

No.  "Porting" to Java would actually be a complete rewrite, and we have no interest in that.  There is no Java applet window port either.

{::comment}
TODO:

* I sincerely doubt anybody has asked for this in many years.  Perhaps this
  question should be removed.
{:/}

### Are you porting NetHack to Palms?

No.  Other people who've written in with information about them lead us to believe that it won't work on most models, but the largest ones *might* be able to run it, if someone wrote bridge code adapting some major ***NetHack*** assumptions.  The UI would actually be the easy part -- that's split off from the rest of the code anyway.  The hard part is that Palms have only memory (no disk) and a very limited heap, while ***NetHack*** is designed to run in low memory conditions by writing everything not used to disk and likes to keep those varying, but often large numbers of monsters and objects in the heap.  A couple people have gone off to look at the exact constraints, but we haven't heard anything to suggest that actual porting has started, let alone successfully finished.  Aside from advising such people on ***NetHack*** internals, and merging their port code back in should such ever appear, we have no plans in that area.  [Some people](http://nethack-palm.sourceforge.net/) may be making progress.

{::comment}
TODO:

* This is a *gargantuan* answer to a question I'm not sure anybody cares about
  in 2015.  Perhaps this question should be removed.
{:/}

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

{::comment}
TODO:

* Instead of just shutting down ideas like this, maybe we should redirect them
  to the community, or encourage them to write a patch and present them to
  NetHack variant developers or something.

* Aside: I think dNetHack might have these artifacts already, and if they're
  anything like most of dNetHack's artifacts, they likely have unique and
  interesting effects.  In fact, porting some dNetHack artifacts back to
  mainline NetHack could be quite fruitful.
{:/}

### Why don't you add this new role?  I've come up with ideas for a leader, nemesis, and artifact, so it should be trivial for you to name all their experience levels and implement the new abilities and design appropriate quest levels for them and write pages of new quest text to cover every situation and then manage to differentiate the new role from the existing ones when outside the quest levels.

We're still trying to get the existing roles differentiated.

{::comment}
TODO:

* The same case for not shutting down eager contributors made above applies
  here.

* Has the dev team made any progress on getting existing roles differentiated
  in the last ten years?  This is another area where variants have made a fair
  bit of progress.

* The question here is *way* too long; it should probably be trimmed down.
{:/}

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

{::comment}
TODO:

* Maybe redirect these people to share their ideas with the community.
{:/}

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

### Why don't you use self-extracting files to distribute NetHack?

Generally, our porting teams don't use self-extracting archives for several reasons.  First, they add to the size of the binary; considering the number of platforms we support times the number of old versions that we try to keep, the extra size adds up.  Second, practically every platform today comes with de-archiving tools (or good tools can be obtained for free), so there is no need to make distributions self-extracting.  Third, relying on self-extracting archives is a bad habit for users; it is very easy to fool a user into running a "trojan horse" program.  It is much better to distribute software in a well-recognized archival format, where the contents can be inspected before expanding.

{::comment}
TODO:

* I don't think anybody has asked for a self-extracting archive for well over a
  decade, so I'd recommend simply dropping this question altogether.
{:/}

---

## Y2K Statement

### Is NetHack version 3.4 Y2K compliant?

Yes, all since 3.2.3 have been Y2K compliant.

### What about earlier versions?

***NetHack*** 3.2.2 and earlier versions are not Y2K compliant (the score file used 2 digit years and will be corrupted if added to after the year 1999).

{::comment}
TODO:

* Y2K hasn't been relevant since, well, the year 2000.  I would recommend
  dropping this whole section altogether.
{:/}
