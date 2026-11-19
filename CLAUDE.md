# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Crisp DNA is a Jekyll site describing how the consulting company Crisp works. It is built with Jekyll 4 by the GitHub Actions workflow `.github/workflows/pages.yml` on every push to the `gh-pages` branch (the default branch, and the PR target) and served at http://dna.crisp.se (see `CNAME`). Pushing to `gh-pages` publishes, so nothing goes there unreviewed.

The content is prose, not code. Most changes are edits to Markdown files in `_docs/`.

## Commands

```bash
bundle install                 # install Jekyll 4 into ./vendor/bundle (Ruby version pinned in .ruby-version)
bundle exec jekyll serve       # local preview at http://localhost:4000, auto-rebuilds on edits
bundle exec jekyll build       # one-off build into _site/; use as the check before committing
```

There are no tests or linters. A clean `jekyll build` with no warnings counts as passing; CI runs the same build on every PR. `./run` is a shortcut for `bundle exec jekyll serve --livereload`.

## How the site fits together

- **Pages** live in the `docs` collection (`_docs/*.md`, `output: true` in `_config.yml`) and render to `/docs/<name>.html`. The root `index.html` only redirects to `docs/index.html`.
- **All pages share one layout.** `_config.yml` sets `layout: default` globally, so front matter usually holds only `title`, `prev_section` and `next_section`.
- **Sidebar navigation** comes from `_data/docs.yml`: a list of sections, each listing `.html` filenames. `_includes/docs_contents.html` → `_includes/docs_ul.html` match these against `site.docs` URLs and show each page's `title`. A page left out of `docs.yml` still builds but does not appear in the sidebar. The contract pages (`team-contract-*`, `shareholder-contract-*`) are like this; other pages link to them.
- **Back/Next links** (`_includes/section_nav.html`) use each page's hand-written `prev_section` / `next_section` front matter, not `docs.yml`. When you add, remove or reorder a page, update `_data/docs.yml` and the `prev_section`/`next_section` of the pages on either side so the chain still matches the sidebar order.
- **Cross-links** between docs are relative `.html` links (e.g. `[decisions](decisions.html)`), not `.md`.
- `{{ site.company_name }}` (from `_config.yml`) is used in some prose so forks can rebrand. See `_docs/how-to-copy.md` for the intended fork/clone workflow.
- Images and PDFs referenced from docs go in `assets/`. `images/` and `stylesheets/` belong to the theme.

## Content conventions

- Pages use setext headings (`Title` / `=====`, `Section` / `-----`) under the front matter.
- The contracts (`team-contract-sv.md`, `shareholder-contract-sv.md`) are Swedish originals. Their `*-en.md` pages are still placeholders that ask for a translation and link to Google Translate.
