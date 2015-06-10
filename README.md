# arctor

Demo: https://frutiger.github.io/arctor-demo.

A [Jekyll](http://jekyllrb.com/) theme for documentation that uses a [solarized
light](http://ethanschoonover.com/solarized) colour palette and
[scrollNav.js](http://scrollnav.com/) to automatically generate a table of
contents.

## Usage

1. Create a new repository, write some beautiful markdown/ReStructuredText/etc,
   put it all in `master` (or whichever branch is your "release" branch).  For
   this example, we will use https://github.com/frutiger/arctor-demo as our
   demo repo.

2. Add this repository as a remote:

    ```bash
    $ git remote add arctor https://github.com/frutiger/arctor.git
    ```

3. Fetch from `arctor`:

    ```bash
    $ git fetch arctor
    ```

4. Checkout your `gh-pages` branch:

    ```bash
    $ git checkout gh-pages
    ```

5. Merge in your `master` branch, then merge in `arctor/theme`:

    ```bash
    $ git merge master
    $ git merge arctor/theme
    ```

6. Push your changes to github:

    ```bash
    $ git push origin master:master gh-pages:gh-pages
    ```

You should now have [human-readable
plain-text](https://github.com/frutiger/arctor-demo/blob/master/index.md)
generating [beautiful pages](http://frutiger.github.io/arctor-demo/)
at your GitHub Pages site.

## Design notes

Sections are generated from `h1` and `h2` elements while subsections are
generated from `h3` elements.  Any `Jekyll` post that matches the 'default'
layout will have the appropriate styles applied to it.
