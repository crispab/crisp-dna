crisp-model
===========

A description of how [Crisp](http://www.crisp.se) works as an organization.

This site auto-published at: http://crispab.github.io/crisp-model

Developer setup
---------------
In order to edit the GitHub pages (see gh-pages branch), it is preferred to use Jekyll.
* `sudo apt-get install ruby-dev`
* `sudo gem install jekyll`
* curl -sL https://deb.nodesource.com/setup | sudo bash -
* sudo apt-get install nodejs
* git clone git@github.com:crispab/crisp-model.git
* cd crisp-model
* git checkout gh-pages
* ./run
   (this will do "bundle exec jekyll serve --baseurl ''", which starts jekyll using the exact same gems as github uses, so so that the site will look correct when testing locally)
* Browse http://127.0.0.1:4000/

References
----------
* https://pages.github.com/
* http://jekyllrb.com/docs/quickstart/
* http://daringfireball.net/projects/markdown/basics