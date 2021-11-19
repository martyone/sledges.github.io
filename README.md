# Sailfish OS Documentation

Welcome to the Sailfish OS Docs source repo.

* [Edit and contribute](#edit-and-contribute)
   * [Just the documentation](#just-the-documentation)
   * [Changes to HTML (Jekyll template)](#changes-to-html-jekyll-template)
      * [Preview via GitHub Pages](#preview-via-github-pages)
      * [Preview on your desktop](#preview-on-your-desktop)
      * [Upstreaming cherry-picks](#upstreaming-cherry-picks)
   * [Common pitfalls](#common-pitfalls)
      * [Tables](#tables)
      * [Escaping Markdown syntax](#escaping-markdown-syntax)
      * [URLs](#urls)
      * [Syntax highlighting](#syntax-highlighting)
      * [Templates and forgotten ./precheckin.sh](#templates-and-forgotten-precheckinsh)
* [Feedback](#feedback)
* [Credits](#credits)

## Edit and contribute

### Just the documentation

Simply edit a chosen `README.md` file and preview the changes before creating a PR.

Match existing docs source style, study the code to e.g. see how images are uploaded and displayed.

IMPORTANT: please read about [the common pitfalls](#common-pitfalls).

### Changes to HTML (Jekyll template)

If you would like to improve the website itself (style, layout, browser fix etc.), you should test your changes before creating a PR:

#### Preview via GitHub Pages

NOTE: this process becomes cumbersome, if you already have your GitHub Pages enabled for other purposes under `yourusername.github.io`.

Fork this repo, then go to Settings | Pages | Source and choose the `master` branch. After a short while, you will find a copy of the docs published under `https://yourusername.github.io/sledges.github.io`. Unfortunately, stylesheets and javascript (for search bar) won't be available, and all links will point to the top-level of the domain, thus will become broken.

If you don't have own GitHub Pages setup yet (under `yourusername.github.io`), then to fix all the above broken bits, rename your forked repo via Settings | Options | Repository name from `sledges.github.io` to `yourusername.github.io`.

If you already have your own `yourusername.github.io`, the process becomes more involved:
* Method 1:
  * push the forked `sledges.github.io` under a new branch of your `yourusername.github.io`
  * point to that new branch in Settings | Pages
* Method 2:
  * rename your `yourusername.github.io` to something else, e.g. `renamed-yourusername-pages` via Settings | Options | Repository name
  * create new branch from `renamed-yourusername-pages`'s default branch (using branch drop-down box)
  * set it to be as default branch in Settings | Branches
  * delete old branch in `https://github.com/yourusername/renamed-yourusername-pages/branches` -- this way old GitHub Pages will get unpublished
  * delete the forked `sledges.github.io` repo
  * re-fork it again from <https://github.com/sledges/sledges.github.io>
  * rename the forked `sledges.github.io` to `yourusername.github.io` via Settings | Options | Repository name

Then start making changes to the active website, and as soon as you push a commit, your published website will shortly update itself.

Once happy, create PR which will automatically point to `https://github.com/sledges/sledges.github.io`.

#### Preview on your desktop

To build on your local machine, perform the following commands:
```nosh
sudo apt install git ruby-bundler ruby-dev gcc g++ make
git clone https://github.com/sledges/sledges.github.io
cd sledges.github.io/
sudo gem install bundler
bundle config set --local path 'vendor/bundle'
bundle install
bundle exec jekyll serve
```

Follow the same process for creating PRs as previously.

#### Upstreaming cherry-picks

Unfortunately the [Just the Docs upstream](https://github.com/pmarsceill/just-the-docs) is inactive, we very much hope the author can still be contacted to bring it back to live (it has thousands of forks).

### Common pitfalls

#### \<tags\>

The following Markdown `org.freedesktop.Telepathy.Connection.ring.tel.<ID>` will be rendered as **org.freedesktop.Telepathy.Connection.ring.tel.**, and the `<ID>` bit is lost on GitHub Pages.

To avoid, always escape correctly: `org.freedesktop.Telepathy.Connection.ring.tel.\<ID\>`.

#### Escaping Markdown syntax

Please escape Markdown symbols (\[, \_, \* and similar) with a backslash, when intention is to actually show them, or place such word(s) within a code block if possible.

Otherwise if you write e.g. `_service`, Markdown will render it as _service and everything thereafter will be shown in italic_, whereas correct should be `\_service` so \_service gets displayed as intended.

However, you don't have to escape some symbols (like an underscore), when they're in a middle of a word e.g. tar_git and Q&A are shown correctly.

#### Tables

* Markdown does not support header-less tables, so please come up with a name for each column, to avoid an empty row at the top.

* GitHub Pages does not render tables that have only one row, thus please come up with a header row for it too.

* Markdown doesn't support `rowspan` and `colspan`. The latter can be worked around by giving each column a more granular name.

  Instead of `rowspan`, use a [_ditto_](https://en.wikipedia.org/wiki/Ditto_mark) mark to show that a cell has the same content as the cell above: `<center>"</center>`.

  If you absolutely must defy the purpose of using Markdown, then it's possible to achieve `rowspan` `colspan` functionality by writing your tables in HTML inside an `*.md` file.

* Yes, we know that tables with long text in a cell look way too wide in Markdown's source, and cannot be rectified because it doesn't support line breaks in them. But if a cell is that big, maybe it shouldn't be a table in the first place? ;)

#### URLs

It's good practice to surround URLs: `<http://some.url>`. GitHub will linkify even non-surrounded ones, but some Markdown renderers don't. Thus please increase portability of these Markdown docs.

#### Syntax highlighting

* When using Markdown's syntax highlighter, you can find the list of Markdown supported syntax highlighters [here](<https://github.com/github/linguist/blob/master/lib/linguist/languages.yml>).

* Most if not all will correctly appear in your GitHub web editor preview. However **not all** of them will be highlighted in GitHub Pages due to an unknown limitation.

  The following do not to work at the time of writing: `gitattributes, qmake, specfile, ssh-config, wiki`.

  The following are rendered/coloured incorrectly in Pages (but correct in GitHub editor preview): `ini`

* Shell script syntax highlighter has been disabled (simply by identifying a code block as `nosh` instead of `sh`) because it does more harm than good. E.g. it always highlights `exec`, but doesn't know that it shouldn't highlight when `exec` is an argument to `sfdk`.

#### Templates and forgotten `./precheckin.sh`

If you are modifying a template (`*.mdpp` file), don't forget to run `./precheckin.sh` before committing.

## Feedback

Please create a report in the [Issues](https://github.com/sledges/sledges.github.io/issues) section.

## Credits

The following content generators are being used:

* [Just the Docs](https://github.com/pmarsceill/just-the-docs)
  - Nicely builds this whole website with navigation bar and mobile view
* [Jekyll Pure Liquid Table of Contents](https://github.com/allejo/jekyll-toc)
  - Generates table of contents by scanning all headings on a page
* [Markdown Preprocessor (Markdown PP)](https://github.com/jreese/markdown-pp)
  - Used by `./precheckin.sh` to include templates into L10n style guides
