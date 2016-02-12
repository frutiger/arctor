# arctor

Demo: https://frutiger.github.io/arctor-demo.

A [Jekyll](http://jekyllrb.com/) theme for documentation that uses a [solarized
light](http://ethanschoonover.com/solarized) colour palette and
[scrollNav.js](http://scrollnav.com/) to automatically generate a table of
contents.

## Usage

### First-time use

1. Create a new repository, write some beautiful markdown/ReStructuredText/etc,
   put it all in `docs` (or whichever branch you keep your documentation in).
   For this example, we will use https://github.com/frutiger/arctor-demo as our
   demo repo.

2. Add this repository as a remote and pull its contents:

    ```bash
    $ git remote add arctor https://github.com/frutiger/arctor.git
    $ git fetch arctor
    ```

3. Merge your documentation and the theme's contents into your `gh-pages` branch:

    ```bash
    $ git checkout gh-pages
    $ git merge docs
    $ git merge arctor/theme -m "merge theme content"
    ```

4. Push your `gh-pages` branch:

    ```bash
    $ git push origin gh-pages:gh-pages
    ```

You should now have [human-readable
plain-text](https://github.com/frutiger/arctor-demo/blob/master/index.md)
generating [beautiful pages](http://frutiger.github.io/arctor-demo/)
at your GitHub Pages site.

### Keeping up-to-date

If you make changes in your `master` branch, to update your site, merge the
changes into your `gh-pages` branch and re-push:

```bash
$ git checkout gh-pages
$ git merge docs
$ git push origin gh-pages:gh-pages
```

If changes are made to the `arctor` theme, and you want to pull them in, fetch
those changes, merge them, and re-push:

```bash
$ git fetch arctor
$ git checkout gh-pages
$ git merge arctor/theme -m "merge theme content"
$ git push origin gh-pages:gh-pages
```

### Advanced usage

I personally don't care about keeping history in the `gh-pages` branch, since
all the interesting history is in my `docs` branch.  So I run this
(**warning**: do this only if you know each command does!):

```bash
$ git checkout --detach docs
$ git merge --no-ff arctor/theme -m "merge theme content"
$ git push -f origin HEAD:refs/heads/gh-pages
$ git checkout -
```

## Design notes

Sections are generated from `h1` and `h2` elements while subsections are
generated from `h3` elements.  Any `Jekyll` post that matches the 'default'
layout will have the appropriate styles applied to it.

