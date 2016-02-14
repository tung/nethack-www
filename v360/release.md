---
title: Release Notes
---
After a 10+ year hiatus, the NetHack DevTeam is happy to announce the release of NetHack 3.6, a combination of the old and the new.

Unlike previous releases, which focused on the general game fixes, this release consists of a series of foundational changes in the team, underlying infrastructure and changes to the approach to game development.

Those of you expecting a huge raft of new features will probably be disappointed.  Although we have included a number of new features, the focus of this release was to get the foundation established so that we can build on it going forward.

Here's a synopsis of some of the changes we've made in the past year:

# 1. Personnel Changes

As noted in the April communication, we've added some new members to the team: Sean Hunt, Derek S. Ray and Pasi Kallinen.  These folks have been key in helping introduce a number of the changes that needed to be made.

This is not likely the end of changes in the team.  We're looking at adding additional members as needs or opportunities arise in the future.

# 2. Infrastructural and Procedural Changes

The DevTeam have spent a large amount of time this past year revamping our own internal infrastructure which, although functional, was not up to date.

We've migrated our internal source repository to Git, with plans of providing a publicly available "current maintenance version" in the future.  This should allow for improved turn-around times on the really simple bug fixes that dominate the feedback we receive.

We're also in the process of migrating our defect tracking to use Bugzilla, although we will likely retain a more streamlined externally facing interface, as not every NetHack player may be comfortable with a tracking system which is tech-centric.

This summer we had a bit of a reality check due to the outage at SourceForge which has driven some internal discussion about future direction concerning hosting and has unfortunately delayed the release - more to come on this.

Finally, one of our challenges has been testing the game for stability.

We have a fantastic team of human testers, who are incredibly good at debugging the game from a story line and game flow perspective.

One of the things that they can't do (nor would we ask them to) is to exercise every possible code path the game may take.  For this release, we've built and utilized an initial version of an automated fuzz testing mechanism for internal testing, which has helped us catch some of the border condition situations that usually result in a game crash situation.  This is not a part of the distribution, simply an ongoing internal project to assist in release quality.

# 3. Gameplay Changes

There are a number of gameplay changes in the 3.6 release.

Many of these were incremental from 3.4, based on the over ten years of accumulated patching.  Most of these are boundary condition fixes and improvements that would make the game more realistic, although there are new features that were added as well.

A number of these were released in the 3.5 "leak" release.  Many others have been introduced later.

A number of significant changes were derived from UnNetHack, NetHack 4 and other variants, such as:

* Roderick Schertler's pickup\_thrown patch
* Extensions of Malcolm Ryan's Statue Glyphs patch for tty and tiles
* Extensions of the Paranoid\_Quit patch
* Extensions of the Dungeon Overview
* Aardvark Joe's Extended Logfile
* Michael Deutschmann's use\_darkgray patch
* Clive Crous' dark\_room patch
* Jeroen Demeyer and Jukka Lahtinen sortloot patch
* Stefano Busti's Auto open doors patch

There are also a number of clean-up activities that were undertaken with respect to code hygiene and removal of conditional build code in order to streamline the code.  Most of these were restrictions introduced years ago in order to allow the run time size of the binary to fit on platforms with smaller memory footprints.  As most, if not all of those platforms are no longer in use, the decision was made to simplify and drop support for some of the platforms that the 3.4.x versions would have run on.

That doesn't mean that NetHack still can't run on some *really* old hardware :-)  The README file in the top level directory of the NetHack source tree has a complete list of systems we know NetHack 3.6 runs on and ones that previous versions did run on but have not been verified.  We'd be very interested if anyone can provide "proof of life" on any of these historical OS versions.

A number of treasured NetHack community patches, or our variations of them, have been rolled into the base NetHack source tree in this version, meaning that they're no longer optional, including:

* menucolors
* pickup thrown
* statue glyphs
* dungeon overview
* sortloot

For a complete and very granular, but not necessarily explanatory list of the changes incorporated in this release, please take a look at the file `doc/fixes36.0` in the source distribution.  This file has a full list of all changes to the game.

The text in this file is populated automatically for the development team's own use and is provided "as is", so please do not ask us to further explain the entries in that file.  Some entries may also be "spoilers", particularly in the "new features" sections, so read at your own risk.

## Save File Compatibility

Given the rather fundamental changes in this release as noted above, old save and bones files understandably will not be compatible with version 3.6.

# 4. Other Changes

Our tribute to Terry Pratchett:

As some may know, Terry Pratchett was a fan of NetHack, dating back to the time that we introduced the Tourist class which was openly based on the Discworld novels he penned.

At the time of his passing this year, the DevTeam decided that it would be a fitting tribute to take a number of our favourite quotes from the various Discworld novels and incorporate them into the game.  Being the way we are, we did a little more than that.  There are now a huge number of quotes from many of the Discworld novels in the tribute file, but this doesn't mean that we wouldn't accept new submissions from other Pratchett fans.

The complete list can be found in `dat/tribute` and special thanks to Michael Allison who took the lead on this one.

Here, by the way, is a quote from *"Guards! Guards!"* which has meanings on more than one level - I think that Sir Terry would have appreciated its use in this context:

> "Never build a dungeon you wouldn't be happy to spend the night in yourself. The world would be a happier place if more people remembered that."

As with all releases of the game, we appreciate your feedback.  Please submit any bugs <strike>using the problem report sheet at <http://www.nethack.org/common/contact.html></strike> [via email]({{ site.baseurl }}/contact-us.html).

Also, please check the [known bugs]({{ site.baseurl }}/v360/bugs.html) list before you log a problem - somebody else may have already found it, after all.

Happy NetHacking!

For the DevTeam...

Mike Stephenson
