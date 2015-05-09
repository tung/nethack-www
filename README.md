# Sample www.nethack.org website redesign

This is an example website that could be served in the place of the current website at <http://www.nethack.org>.  Major features:

* **Statically-generated website** -- The entire website is created with [Jekyll](http://jekyllrb.com), generating a set of static files that can be uploaded to any web server.
  Jekyll provides features like layouts and templates to prevent the need to copy and paste markup across pages.
* **Navigation sidebar** -- All important pages are linked in it and thus can be reached with a single click from any other page.
  The link for the current page turns bold, so visitors have a sense of where they are in the website without having to visit a separate sitemap page.
* **Blog** -- Gives the DevTeam a dedicated place to communicate announcements and new NetHack releases to the general public.
  The archive lets visitors browse and individually link previous blog posts.
  The RSS feed provides a way for visitors to follow the blog for updates automatically with a feed reader, as well as enabling the blog to appear in aggregated blog feeds.
  Blog updates do not require changing the source of pages that they appear in; the landing page and navigation sidebar links update automatically.
* **Better support for new NetHack releases** -- Releasing a new version of NetHack means adding pages for the new version and updating data files; no moving or copy-pasting of files necessary.
  Warnings on pages about older NetHack versions are updated automatically.
* **No more broken links** -- Over half of the links on the current website were broken; the ones that still exist have been fixed.
* **Better organization of information** -- The NetHack references that crowded the landing page of the current website have been given their own dedicated page.
  The description of what NetHack is has been expanded from a single sentence to a full page with an introductory-level description of what NetHack is.
  The frequently asked questions page features a new section for basic gameplay, answering the most common problems confronting new NetHack players.
  The pages hosting download links for NetHack have been condensed into their essential information, improving readability immensely.
* **Stronger community focus** -- There are many small gatherings of NetHack fans in various places across the Internet; this new website links to some of the major ones so that fans can discover each other, generating more discussion and interest in the game.
  Landmarks of the NetHack community such as `nethack.alt.org` and the NetHack Wiki have been given greater emphasis.
  Some informational pages that are liable to change frequently instead link to the NetHack Wiki, where members of the NetHack community can keep information current instead of placing that burden on the DevTeam.

Though I think this website looks *nicer* than the current one, it doesn't look very flashy.

The rest of the information in this README is a summary of how to view and modify the website; consult the [Jekyll docs](http://jekyllrb.com/docs/home/) for more general information about how websites built with Jekyll are supposed to work.


## Viewing this website

The easiest way to view this website is to visit it at <https://tung.github.io/nethack-www/>.


## Generating and testing the website

If you want to view the website offline or want to preview changes that you make to the website, first you will need to install [Ruby](https://www.ruby-lang.org/en/) if you don't have it already.

Next, you'll need to install [Jekyll](http://jekyllrb.com/).
To do this, first install [Node.js](https://nodejs.org/) (Aside: This is a requirement of Jekyll, but this project never makes use of it; future Jekyll versions should not need this).
Next, install [Bundler](http://bundler.io), then run `bundle install` in the project directory, which will install all the Ruby gem depedencies and tools needed to generate the website.

To test the website, run `bundle exec jekyll serve` and visit `http://127.0.0.1:4000/nethack-www/` in your web browser.
Useful command line options:

* `--port 4001` -- Serve from port 4001 instead of port 4000.
* `--no-watch` -- Disable automatic website generation when page files are modified; use `bundle exec jekyll build` to generate pages manually.
* `--skip-initial-build` -- Don't regenerate the website, just serve it instead; handy if you know the website has not changed since last you generated/served it.


## How to add a static file

Just put the file in the path that you'd expect and Jekyll will copy it over, no questions asked.
Don't use filenames or paths that begin with an underscore, since Jekyll treats such files and directories specially.


## How to add a static page linked in the navigation sidebar

In order to make a static page that gets linked in the main navigation sidebar, you'll need to make the file for the page, then modify data files so that they'll actually show up in the navigation sidebar.

First, create the file for the page.
Pages may be written in HTML, or in a plain text format called [markdown](http://daringfireball.net/projects/markdown/) that gets converted to HTML (including its extension in the final website).

You may notice some data at the top of existing static page files that looks like this:

```
---
layout: default
title: My Cool Page
---
Content and stuff goes here...
```

The triple dashes indicate *YAML front matter*, which is meta-data associated with the page.
In the above example, the page makes use of the `default` layout which is defined in `_layouts/default.html`, and has the title "My Cool Page" that the default layout will read out and automatically include in the page heading and page title sections of its markup.

To link the page into the navigation sidebar, modify the file corresponding to the sub-section you want add the link to the page to in the `_includes/nav/` directory.
Use the `nav-li.html` include tag to make the link turn bold in the navigation sidebar when visitors are on the new page.

Finally, to set the text of the link in the navigation sidebar, edit `_data/nav.yml` and add a key for the new page output URL with the text you want.


## Creating links

To create clickable links, you'll usually want to use absolute links based on `site.baseurl` rather than relative links, since this prevents links from breaking in the (unlikely) event pages need to be moved to a new path.
For markdown, you can create such a link like this:

```
Here is some [link text]({{ site.baseurl }}/path/my-page.html).
```

The same thing with HTML:

```
Here is some <a href="{{ site.baseurl }}/path/my-page.html">link text</a>.
```

See the [GitHub Pages section of the Jekyll Docs](http://jekyllrb.com/docs/github-pages/#project-page-url-structure) for more info about how to use `site.baseurl`.

Links to blog posts (but not other blog pages) require a special tag, provided with the base of the filename of the post:

```
Check out our [cool announcement]({{ site.baseurl }}{% post_url 2015-04-03-nethack-development-update %})!
```

[Read more about Post URLs in the Jekyll Docs.](http://jekyllrb.com/docs/templates/#post-url)


## Adding a new blog post

This is easy: just add a new file to the `_posts/` directory.
The filename determines the output URL of the post, though unlike static pages this is processed a little bit, e.g. `_posts/2015-04-03-nethack-development-update.md` becomes `/blog/2015/04/03/nethack-development-update.html` (this is why the special `post_url` tag is needed to link to posts).
The YAML front matter of a post should have a `title`, `author`, `date` and `tags`.

* `title` -- Self-explanatory.
* `author` -- A URL-friendly handle for the author of the post.
  Create an author page for them in the `_authors/` directory if it doesn't exist yet (copy and adapt from another author file there).
  This author page will be linked from the author's name and lists all the blog posts that they've made.
* `date` -- This can be guessed from the filename, but a precise date allows exact ordering for multiple posts in a single day.
  For a UNIX-like OS you can get this using the command `date +'%Y-%m-%d %H:%M:%S %z'`, i.e. 4-digit year, month, day, hours, minutes, sections, time zone.
* `tags` -- Square brackets holding a comma-delimited list of URL-friendly tag names.
  Much like authors, each tag should have a corresponding file in the `_tags/` directory.
  Each tag links to a page that shows all blog posts with that tag attached to them.

[Read more about Writing Posts in the Jekyll Docs.](http://jekyllrb.com/docs/posts/)


## Adding a new NetHack version

If a new version of NetHack is being released, you'll want to add a sub-section for it in the website.

1. Add the latest version to the top of the `_data/versions.yml` file.
   This top version will be the version number that appears in the page title of most of the pages across the website.
   The top-most version is also recommended for download on the front page, and gets its own "Latest Version" section in the navigation sidebar.
   Set `current: true` for all versions aren't old, i.e. the latest version, and maybe the last backwards-compatible bugfix version; this makes the release date notice at the top of their version-specific pages *green*.
   Remove the `current: true` for older versions; this causes the release date notices at the tops of their pages to turn *red* with a warning.
   You'll want at least `downloads.html` in your new version `sub_nav` list, since that's what's linked from the front page, all other links are optional.
2. Create a new directory matching the path you set in `_data/versions.yml`, e.g. `v360/`, and create a page for each one you specified in your version's `sub_nav` list.
3. Set the titles for those pages in `_data/nav.yml`.

That's all that's needed, but I recommend also adding a blog post announcing the release with `tags: [v360, releases]`, so people know about it.

If you want to link to a version sub-page from another page, e.g. in the release annoucement blog post, an absolutel URL is safe to use, e.g. `{{ site.baseurl }}/v360/downloads.html`, since version pages should never have to be moved.


## Adding a new screenshot

Screenshots consist of three things:

1. The screenshot image in the `images/screenshots/full/` directory (required).
2. The screenshot meta-data in the `_screenshots/` directory (required).
3. A 709px-wide scaled-down preview image in the `images/screenshots/preview/` directory (optional).

Just copy the conventions of existing screenshot files.
These three files must share the same base filename (i.e. the part without their file extension).

To actually include a screenshot somewhere, include it like so for HTML:

```
{% include screenshot.html file='my-screenshot.png' %}
```

Including a screenshot in markdown is slightly different:

```
{% include screenshot.html file='my-screenshot.png' markdown=true %}
```


## Configuring and generating this website for deployment

If this website is to be hosted at <http://www.nethack.org>, some changes need to be made to `_config.yml`:

* Delete or comment out the `baseurl` line; **DO NOT** set it to `/`, since proper usage of `site.baseurl` depends on it NOT having a trailing slash.
* Change the `url` to `http://www.nethack.org` (again, no trailing slash), which will ensure links in the blog's RSS feed point back to their respective pages on the website.

There are also some settings in `_config.yml` noted `#TODO`.  These are things that I strongly recommend that the DevTeam consider setting up and linking to once up:

* `repo.site_url` -- Browser-viewable GitHub project page for NetHack or equivalent.
* `public_bug_tracker_url` -- Public-facing bug tracker website for NetHack.
* `forums_url` -- Centralized web forums for NetHack discussion, as an alternative to `rec.games.roguelike.nethack`.

If these `#TODO` links are left alone, they will appear as *red* links on the website; changing them to actual links will make them appear blue like all other links.

To build the website, run `bundle exec jekyll build`.
The final files will appear in the `_site` directory; copy the files there to any web root to deploy the website.
That's it!
