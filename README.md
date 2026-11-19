---
---
# Crisp DNA - tech setup for the site

Crisp DNA is a web site that describes how Crisp works and why. The source lives on github and is auto-published on [https://dna.crisp.se](https://dna.crisp.se) every time a change is pushed.

Below are instructions for how to set up a local development environment. Useful for when you want to make many changes and test locally before pushing to github. See [How to clone](https://dna.crisp.se/docs/how-to-copy.html) for more options on how to clone the Crisp model.


## 1. Install GIT

Here's [how to install GIT](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git). 

## 2. Clone the repo

Tell git to download the crisp-dna source:

    git clone https://github.com/crispab/crisp-dna.git
	cd crisp-dna

You should now have the whole thing, including the README.md file that you are reading right now!

The web site source files are under `_docs`, have a look! They are written using [markdown](https://guides.github.com/features/mastering-markdown/) (a simpler format than html). When you push to github, a GitHub Actions workflow converts the pages to static html and publishes the site on https://dna.crisp.se. 

## 3. Install Ruby (project-local)

The site is built with [Jekyll](https://jekyllrb.com), which runs on Ruby. To keep this project from interfering with any other Ruby on your machine, we pin the Ruby version in `.ruby-version` and install all gems into `./vendor/bundle` inside the repo (set in `.bundle/config`), similar to a Python virtualenv. Deleting `vendor/` resets everything.

We use [rbenv](https://github.com/rbenv/rbenv) to manage Ruby versions. It reads `.ruby-version` and switches automatically when you `cd` into the repo.

### macOS

    brew install rbenv ruby-build libyaml
    rbenv init          # follow the printed instructions, then open a new terminal

### Ubuntu / Debian

Build tools and the headers Ruby needs to compile:

    sudo apt install -y build-essential libssl-dev zlib1g-dev libyaml-dev libffi-dev

Then install rbenv and ruby-build. Use git rather than `apt install rbenv ruby-build`: this is what [rbenv recommends](https://github.com/rbenv/rbenv#basic-git-checkout), because the apt packages fall behind. ruby-build is essentially a list of known Ruby releases, so an old copy can't install the version in `.ruby-version`.

    git clone https://github.com/rbenv/rbenv.git ~/.rbenv
    git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
    ~/.rbenv/bin/rbenv init   # follow the printed instructions, then open a new terminal

If you already have rbenv, update ruby-build so it knows about recent Ruby versions:

    git -C ~/.rbenv/plugins/ruby-build pull

### All platforms

From inside the repo, install the Ruby version from `.ruby-version` (this takes a few minutes) and the gems:

    rbenv install       # reads .ruby-version
    bundle install      # installs Jekyll into ./vendor/bundle

## 4. Run the site locally!

    ./run

which is short for `bundle exec jekyll serve --livereload`. The site is now running on [http://localhost:4000](http://localhost:4000) and reloads in the browser every time you edit a source doc (under `_docs`).

To just build the site into `_site/` (this is also what CI checks on every pull request):

    bundle exec jekyll build

## How publishing works

The GitHub Actions workflow in `.github/workflows/pages.yml` builds the site with the same Gemfile and Ruby version on every push to `gh-pages` and deploys it to GitHub Pages. Pull requests get a build check but are not deployed. (In the repo settings, *Pages → Build and deployment → Source* must be set to *GitHub Actions*.)

To update dependencies: `bundle update`, then build and check the site locally before committing the new `Gemfile.lock`.
