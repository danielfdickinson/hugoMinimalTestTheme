# hugoMinimalTestTheme
A minimum test theme to generate the full site of unstyled pages for https://github.com/gohugoio/hugoBasicExample (and other Hugo sites).

Includes the ability to enable less minimal features via custom layouts (with thanks to [Patrick / davidsneighbour on the Hugo Forum](https://discourse.gohugo.io/u/davidsneighbour) for the suggestion).

The purpose of the repo is not for CI or automated testing, but to have a set of minimal layouts for creating minimum reproducible test cases for reporting bugs to the Hugo developers.
## Modern Hugo Only (as of 2021-03-17)

This minimal theme is built using assumptions that may require Hugo 0.81.0 or higher.

## A Note on Feature Selection

As Patrick (davidsneighbour on the [Hugo Forum](https://discourse.gohugo.io)) [suggested in response to my announcement of this theme](https://discourse.gohugo.io/t/a-theme-for-minimal-reproducible-test-casing/31790/6), features that are less 'minimal', but still needed in order to have a minimal reproducible test case for more complex (even if barely) situations than an absolute minimal theme, can be enabled through the use of custom layouts.

If a feature is listed in the table below, one can activate the feature on a page by
adding ``layouts = "feature-layout"`` (for toml frontmatter) or ``layouts: feature-layout`` (for yaml frontmatter) to the page metadata in the page file in the ``contents`` directory. (One can also set per-page metadata in ``config.toml`` but for that see the [Hugo Documentation](https://gohugo.io/documentation/)).

Not that features are often specific to the type of page (e.g. list pages vs. single pages) and when that is the case it is noted under 'Applies to'.

This is possible through the magic of [Hugo's Lookup Order](https://gohugo.io/templates/lookup-order).

Obviously for ``feature-layout`` use the layout from the table below.

| Feature               | feature-layout | Applies to              | Description |
|-----------------------|----------------|-------------------------|-------------|
| Custom Layout Testing | custom         | sections and single     | A generic custom layout (just announces it is a custom layout with a heading) that will work with both a section and a single page. |
| Layout Order Testing  | layout-order   | sections and single     | A section page should display the section ``layout-order`` layout not the single ``layout-order`` layout. A single page should display the single page ``layout-order`` layout |
| Pagination            | pagination     | section/list pages only | Displays a section as a list of the pages (both regular pages and section pages) in a section, dividing the list of pages in a section into separate sub-pages, each containing at most the number of pages from the section that is defined in the config's ``pagination`` setting (default 10). |

## Usage

1. Clone a site, for example hugoBasicExample and switch to it
   ```
   git clone https://github.com/gohugoio/hugoBasicExample
   cd hugoBasicExample
   ```
2. Make a themes directory and switch to it
   ```
   mkdir themes
   cd themes
   ```

### Using Hugo Modules (preferred)

TBD
### Using downloaded copy of the theme (e.g. Zip from Github)

1. Obtain a copy of the theme e.g. ([a theme Zip file from Github](https://github.com/danielfdickinson/hugoMinimalTestTheme/archive/master.zip))
2. Copy/extract the theme into hugoMinimalTestTheme in the themes directory
3. Change back to the site directory
4. To test the result, run the local Hugo server
   ```
   hugo server -t hugoMinimalTestTheme -b http://localhost:1313/
   ```
### Using git submodules (deprecated)

1. In the themes directory, add hugoMinimalTestTheme as a submodule
   ```
   git submodule add -f https://github.com/danielfdickinson/hugoMinimalTestTheme.git
   ```
2. Change back to the site directory
3. To test the result, run the local Hugo server
   ```
   hugo server -t hugoMinimalTestTheme -b http://localhost:1313/
   ```

 Enjoy!
