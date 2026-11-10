# Example Product

A neutral example landing site for jekyll-theme-modootoday.

A landing starter for [jekyll-theme-modootoday](https://github.com/modootoday/jekyll-theme-modootoday) 1.6.0. Pages are plain GitHub Markdown; the theme's layouts, includes and CSS style them.

Live demo: <https://modootoday.github.io/jekyll-theme-modootoday-landing-starter/>

## Start

1. Create a repository from this template, or copy these files into an empty repository.
2. In **Settings > Pages**, set **Source** to **GitHub Actions**. `.github/workflows/pages.yml` builds the site, runs `modootoday-check` on it and deploys it on every push to `main`; pull requests are built and checked only.
3. Set `title` and `description` in `_config.yml`, change the header links in `_data/nav/main.yml` and the footer columns and copyright line in `_data/nav/footer.yml`, then replace the sample pages with yours.

## The live demo

The demo is this repository's own Pages site. Its build merges `_config.demo.yml` into `_config.yml`, which adds a showcase bar linking to the theme's documentation and marks every page `noindex`. The workflow does this only when the repository is `modootoday/jekyll-theme-modootoday-landing-starter`, so a repository created from this template, or a fork, builds the site without it. You can delete `_config.demo.yml` and the workflow's two demo steps.

## Stack

The theme loads with `remote_theme: modootoday/jekyll-theme-modootoday@v1.6.0`, and the workflow builds the site with the same builder image as classic GitHub Pages, so no plugin outside the GitHub Pages list runs. To upgrade, change the tag in `_config.yml` and the version in `Gemfile`.

## Run it locally

```sh
bundle install
bundle exec jekyll serve
```

`jekyll serve` downloads the theme from GitHub (remote_theme), so it needs a network connection. The `Gemfile` also installs the theme gem for its two commands.

## Add or rename a page

Every page has a Markdown twin at `<page>/index.md`. GitHub Pages runs no plugin that writes it, so each page has a small stub file beside it. After you add, rename or delete a page, write the stubs and check the site:

```sh
bundle exec modootoday-stubs . --twins --write
bundle exec jekyll build
bundle exec modootoday-check . _site --twins --github-pages
```

## Commands

The `Gemfile` installs the theme's two commands: `modootoday-check` reports anything that would not render the same on GitHub Pages, and `modootoday-stubs` writes the stub pages. The theme's [Command line](https://modootoday.github.io/jekyll-theme-modootoday/reference/cli/) page lists every option and exit code. `bundle exec modootoday-check --help` and `bundle exec modootoday-stubs --help` print the options of the version this starter pins.
