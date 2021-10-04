# frozen_string_literal: true

source 'https://rubygems.org'

gem 'jekyll'
gem 'minima'

# import tool
# https://import.jekyllrb.com/docs/ghost/
gem 'jekyll-import'
gem 'sequel'
gem 'sqlite3'

# another import tool for my posts on Ghost to Jekyll
# https://github.com/eloyesp/jekyll_ghost_importer
gem 'jekyll_ghost_importer'

group :jekyll_plugins do
  gem 'jekyll-feed', '~> 0.12'
  gem 'jekyll-seo-tag'
  gem 'jekyll-sitemap'
end

group :development do
  gem 'rubocop'
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem 'tzinfo', '~> 1.2'
  gem 'tzinfo-data'
end

# Performance-booster for watching directories on Windows
gem 'wdm', '~> 0.1.1', platforms: %i[mingw x64_mingw mswin]
