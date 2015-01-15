source 'https://rubygems.org'

#Make sure we use the same gems as github uses, so that 
#the site looks the same locally is it will on github
require 'json'
require 'open-uri'
versions = JSON.parse(open('https://pages.github.com/versions.json').read)

gem 'github-pages', versions['github-pages']