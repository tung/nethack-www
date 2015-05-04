---
title: Using Git with NetHack
---
NetHack is developed using a system called [**Git**](https://git-scm.com), which records and coordinates all changes made to the NetHack source code.  You will need to use Git if you want to get the latest development version of the NetHack source code, and contribute your own changes to it.

The NetHack source code and development history can be found on the [NetHack project page on GitHub]({{ site.repo.site_url }}).

The following is a crash course on using Git to get a copy of the NetHack source code that can be used to keep up-to-date with NetHack development, as well as make changes that can be considered by the DevTeam for inclusion.

All changes made to NetHack fall under the [**NetHack General Public License**]({{ site.baseurl }}/license.html), so make sure you're okay with that before proceeding.

* table of contents
{:toc}

---

## 1. Overview

The NetHack source code and the record of changes made to it are collectively called a **repository**, or repo for short.  The repository belonging to the NetHack DevTeam is called the **upstream** repo, or just upstream for short.  A developer who wants to make changes to the NetHack source code will create one or more personal copies of the upstream repo collectively known as their **fork**; this fork begins by **cloning** the upstream repo.  This developer makes a **private repo** where their own changes can be recorded, and a **public repo** to publish these changes where other people can see them.

To make changes, the developer creates a new line of development in their private repo called a **branch**, and performs a **checkout** to switch over to it.  The developer changes files in NetHack and adds them to their new branch in the form of one or more **commits**, which records who, what, when and why the changes were made.

Once the developer is happy with the commits in their branch, they **push** that branch from their private repo to their public clone so that other people can see what they've done.  The developer then sends a **pull request** for their branch to let the DevTeam know that the developer wants their changes included in upstream.  If the DevTeam is happy with the developer's changes, they will **pull** that branch into upstream, which means those changes are now officially included in NetHack!

Changes made against recent versions of NetHack are easier for the DevTeam to pull in than changes made against older versions, so developers who want their changes included in NetHack should keep their fork up-to-date.  To do this, the developer will first **fetch** the latest NetHack development changes from upstream into their private repo, downloading whatever upstream has that their private repo does not.  Once fetched, the developer does a checkout of the **master** branch, the default branch in almost every Git repo that reflects mainline development.  The developer then **merges** the fetched changes into their master branch, which updates the source code files to the most recent development version of NetHack.

---

## 2. The command line

The rest of this guide will assume that you either know how to use a command line (sometimes also called a "terminal" or "console") or are willing to learn it.

Commands you enter are prefixed with a `$` (dollar sign).  Anything else that appears is example output.

```
$ git status
# On branch master
nothing to commit (working directory clean)
```

For example, you would type `git status` here at your command line (without the dollar sign), press enter and compare the output you get to the text above.

---

## 3. Getting started with Git

In this section, you will install Git and create your own fork of the NetHack repo, with a public clone hosted on [GitHub](https://github.com) (a free Git hosting service) and a private clone on your computer.  You will only need to do these steps once.

If you choose to compile NetHack, you will also have the latest development version of NetHack running on your computer.

### 3.1. Install and configure Git

Git can be installed on a wide range of operating systems, so start by downloading and installing it: <https://git-scm.com/downloads>

More detailed instructions for installing Git can be found on GitHub: <https://help.github.com/articles/set-up-git/>

Once Git is installed, tell it who you are by giving it your name and email:

```
$ git config --global user.name "YOUR NAME"
$ git config --global user.email "YOUR EMAIL"
```

This is the info that is recorded with the changes that you make to your fork, and will appear in the upstream NetHack repo if your changes are accepted by the DevTeam for inclusion.

**GitHub note:** The email you put here will automatically be used by GitHub to associate commits to your GitHub profile.

**Email privacy for GitHub:** Since this info is publicly viewable, GitHub takes measures to make it hard for bots to scrape your email.  If you don't feel comfortable with making your email publicly visible at all, you can arrange for it to be made private in your GitHub account settings.  Further reading: <https://help.github.com/articles/keeping-your-email-address-private>

### 3.2. Create your fork of the NetHack repo

Visit the [NetHack project page on GitHub]({{ site.repo.site_url }}) and click the "Fork" button at the top-right.  If you do not have a GitHub account you will be prompted to create one.

If all goes well, you will be looking at a new page.  This page shows your brand new public repo of NetHack.  Congratulations!

### 3.3. Clone your public repo to create a private repo

If you want your new fork on your computer you will need to clone your public repo onto it to make a private repo.  To perform this clone, enter the following:

```
$ git clone https://github.com/YOUR-GITHUB-USERNAME/nethack.git
```

This creates a new directory named `nethack` that contains your new private repo.  You should move into it now using the `cd` (change directory) command:

```
$ cd nethack
```

You can check that you did this correctly using `git status`:

```
$ git status
# On branch master
nothing to commit (working directory clean)
```

If you get `fatal: Not a git repository (or any of the parent directories): .git`, you are *not* in your private repo; perform the `cd` command above and try again.

The rest of this guide will assume that you are inside your private repo directory.

### 3.4. Compile NetHack

If you only want to tweak some docs you can skip this step.  For anything else, this is the time to turn NetHack from source code into a running game to test that everything works.

The steps to compile NetHack are highly platform-specific and beyond the scope of this guide, but here are two helpful resources:

* <http://nethackwiki.com/wiki/Compiling>
* Read the platform-specific build notes under the `sys` directory, e.g. `sys\winnt\Install.nt` for Windows.

If all goes well, you should be able to run NetHack; go ahead and press `v` (version command) in-game to confirm the build date.

---

## 4. Making changes to NetHack

In this section you will learn how to make changes to NetHack and prepare them in a way that makes them easy to accept into the DevTeam's upstream repo.  This involves making a new branch for your changes, recording your changes to this branch in the form of commits, pushing your branch from your private repo to your public repo, and sending a pull request for your branch to the DevTeam.

### 4.1. Ensure your fork is up-to-date

If you just created your fork, skip this step.

If you've had a fork for a while, follow the steps in the "[Staying up-to-date with NetHack development](#staying-up-to-date-with-nethack-development)" section below.  The more recent the version of the NetHack source code your changes are based on, the easier it will be for the DevTeam to accept them into the upstream NetHack repo.

### 4.2. Create a new branch for your change

Once you've confirmed that you have the latest version of the NetHack source code, you'll want to base your new change off of it.  To do this you'll need to start by switching to the "master" branch if you're not on it already.  A **branch** is Git's way of tracking separate lines of development, and the master branch in your private repo will always (and only) be used to get development updates.

Switch to the master branch now:

```
$ git checkout master
```

You will either get `Already on 'master'` or a message saying that you've switched branches.  Switching branches will cause Git to change the contents of files in the private repo, or abort if there are any changes in those files that have not yet been recorded with Git.

Now create your new branch with a descriptive name and switch to it:

```
$ git branch my-cool-new-feature
$ git checkout my-cool-new-feature
```

You can check that you're on your new branch like so:

```
$ git branch
  master
* my-cool-new-feature
```

This means that your private repo has a "master" branch and a "my-cool-new-feature" branch, and you're currently on the "my-cool-new-feature" branch (marked with an asterisk).

### 4.3. Make your changes

Now that you're on a branch, you can break out a text editor and start making changes!

**Note for Windows users:** Avoid using Notepad or Wordpad for editing files in NetHack; they may insert invisible characters or replace some characters with similar but non-standard ones, both of which will prevent NetHack from compiling!  Avoid this by using a third-party text editor such as [Notepad++](http://notepad-plus-plus.org/).

### 4.4. Test your changes

At this point, make sure that you can at least still [compile NetHack](#compile-nethack) successfully.  *You should do this even for small changes; even one-liners can contain typos!*

Once you've confirmed that the game still compiles, you want to go into the game itself and test that your change works as you expect it to; it may be helpful to enter [Wizard Mode](http://nethackwiki.com/wiki/Wizard_mode), which was made for this purpose.

### 4.5. Stage and commit your changes to your branch

In order to record what you've changed with Git, you need to first **stage** your changes, which prepares them to be recorded into a **commit**.

To stage your changes, use `git add` to stage modified files:

```
$ git add --update
```

If you created any brand new files, you will need to stage those separately:

```
$ git add src/newfile1.c src/newfile2.c
```

You can get a summary of what will be included in the upcoming commit with `git status`:

```
$ git status
# On branch my-cool-new-feature
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#       modified:   src/cmd.c
```

For a detailed view of what will be included, use `git diff`:

```
$ git diff --staged
```

This will bring up a screen that you can scroll up and down with the cursor, page up and page down keys.  Press 'q' to quit this view when you're satisfied.

Once you're happy with what will be recorded, it's time to commit your changes:

```
$ git commit
```

You should now be looking at a text editing screen.  If you got an error message instead, you may have forgotten to `git add` your changes; do that and try `git commit` again.

At this text editing screen, write your **commit message**.  This message will appear in the NetHack development history if the DevTeam chooses to include your changes, so make sure it's descriptive.  Commit messages should start with a short one-line description, followed by a blank line, followed by a longer multi-line description, e.g.

```
Add `#cool` extended command

This cool new feature enables the player to say "Cool!" using the new `#cool`
extended command, which causes all peaceful (but not tame) creatures to move
away from the player.
```

When you save and quit this text editing screen, Git will record this message, along with your name, email and the current time into a new commit on your branch in your private repo.

If you change your mind and don't want to record a commit after all, just quit without saving.

Finally, if you're working on a big change made of multiple parts, you may want to record it as a series of smaller, coherent commits by repeating this `git add` / `git commit` cycle instead of a single mega-commit.  This will make it easier for DevTeam to review your changes when you send a pull request.

**Text editing note:** If typing into the text editor doesn't seem to do what you expect, you may have just found yourself using [Vim](http://www.vim.org/).  Vim is a very old text editor that nonetheless is widely used by developers.  Vim's controls are very different to most other text editors:

* Press `i` to enter insert mode, which allows you to type in text normally.
* Press `Esc` to leave insert mode.
* Type `:wq` to save (write) and quit.
* Type `:q!` to quit without saving.

If you find yourself with Vim, you can either learn more about how to use it, or configure Git to use a different text editor instead, both of which are outside the scope of this guide.

### 4.6. Push your branch to your public repo

Once you have your commit (or series of commits) on your branch in your private repo, it's time to upload them to your public repo so that other people can see your changes.

Push your branch from your private repo to your public repo:

```
$ git push --set-upstream origin my-cool-new-feature
```

Your new branch should now appear on your public repo's project page on GitHub at `http://github.com/YOUR-GITHUB-USERNAME/nethack`.

### 4.7. Send a pull request for your branch to the DevTeam

To let the DevTeam know that you want them to look at your changes that have been freshly uploaded to your public repo, you need to send a **pull request** for your branch.

To do this, visit *your* public repo's project page on GitHub at `http://github.com/YOUR-GITHUB-USERNAME/nethack`.  On this page, click the **"Compare & pull request"** button.

You will be taken to a review page, where you can choose the *base branch* (where you want your changes to be pulled into, `nethack-devteam:master` by default) and *head branch* (where your changes currently are, `YOUR-GITHUB-USERNAME:my-cool-new-feature` by default) for the pull request; the defaults will be correct if your pressed the "Fork" button when you first created your fork.  Press the **"Create pull request"** button.

You will now see a couple of text entry boxes for the message you want to send to the DevTeam.  The idea here is similar to writing a commit message i.e. a short topic line followed by a longer explanation, though the text here should be addressed directly by the DevTeam.  Press the **"Create pull request"** button on this page.  The DevTeam will be notified of your pull request, and will follow up on it as soon as they have the time to do so.

Congratulations!  You now know how to participate in the development of NetHack.

**See also:** <https://help.github.com/articles/using-pull-requests/>

---

## 5. Staying up-to-date with NetHack development

Your new fork will only stay up-to-date with the upstream NetHack repo if you tell it to; this section describes how to set your fork up to receive updates, as well as how to perform the updates themselves.

### 5.1. Create an upstream remote

In Git terms, a **remote** is a convenient handle to refer to another repository.  First, check your current remotes of your private repo like so:

```
$ git remote --verbose
origin  https://github.com/YOUR-GITHUB-USERNAME/nethack.git (fetch)
origin  https://github.com/YOUR-GITHUB-USERNAME/nethack.git (push)
```

This "origin" remote is your private repo's reference to your public repo, which was created automatically when you cloned it onto your computer.

To conveniently get updates from upstream NetHack, you want to create a new "upstream" remote:

```
$ git remote add upstream {{ site.repo.clone_url }}
```

Now check to confirm that the "upstream" remote was successfully created:

```
$ git remote --verbose
origin    https://github.com/YOUR-GITHUB-USERNAME/nethack.git (fetch)
origin    https://github.com/YOUR-GITHUB-USERNAME/nethack.git (push)
upstream  {{ site.repo.clone_url }} (fetch)
upstream  {{ site.repo.clone_url }} (push)
```

Your private repo is now ready to conveniently receive updates for the latest in NetHack development.  You only need to set this up once.

### 5.2. Fetch and merge updates into your private repo

Whenever you want to update your private repo to the latest development in the upstream NetHack repo, e.g. before making changes, you will need to perform the following steps.

First, fetch the changes from upstream into your private repo:

```
$ git fetch upstream
```

Once the changes are downloaded, make sure you're in the "master" branch by switching to it:

```
$ git checkout master
```

This may change the contents of files in your private repo; Git will prevent you from switching branches like this if you have changes that you have not yet recorded with it, so avoid updating if you have changes that have not yet been committed.

Now that you're on the "master" branch, you can apply your fetched changes to it:

```
$ git merge --ff-only upstream/master
```

You now have the latest development version of NetHack!

Alternately, you can use `git pull` as a shortcut for `git fetch` and `git merge`, so the whole procedure above can also be done like this:

```
$ git checkout master
$ git pull --no-ff upstream master
```

Note that `git pull` accepts the remote name and branch names separately, unlike `git merge`.

---

## 6. Further reading

This guide merely scratches the surface of how Git can be used.  To learn more, here are two valuable resources:

[Pro Git](https://git-scm.com/book/en/v2)
: The definitive guide to learning about Git.  **Read at least the first two chapters** for a better understanding of what Git is, how it works and how to use it!

[GitHub Help](https://help.github.com)
: Comprehensive and concise help for GitHub and Git usage in general.  Useful if you want to know how to do something specific with Git.
