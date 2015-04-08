---
title: No Palm Port
author: keni
date: 2000-05-04 00:00:00 +0000
tags: [development, ports]
---
We will not port NetHack to Palms.   Other people who've written in with information about them lead us to believe that it won't work on most models, but the largest ones *might* be able to run it, if someone wrote bridge code adapting some major NetHack assumptions.  The UI would actually be the easy part -- that's split off from the rest of the code anyway.  The hard part is that Palms have only memory (no disk) and a very limited heap, while NetHack is designed to run in low memory conditions by writing everything not used to disk and likes to keep those varying-but- often-large numbers of monsters and objects in the heap.  A couple people have gone off to look at the exact constraints, but we haven't heard anything to suggest that actual porting has started, let alone successfully finished.  Aside from advising such people on NetHack internals, and merging their port code back in should such ever appear, we have no plans in that area.  [Some people][nethack-palm] may be making progress.

[nethack-palm]: http://nethack-palm.sourceforge.net/
