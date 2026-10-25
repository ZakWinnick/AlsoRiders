source "https://rubygems.org"

# Jekyll 3.10 matches the version GitHub Pages builds with.
gem "jekyll", "~> 3.10.0"
gem "kramdown-parser-gfm", "~> 1.1"
gem "webrick", "~> 1.9"

# No longer default gems in Ruby 3.4.
gem "base64"
gem "bigdecimal"

# Plugins explicitly enabled in _config.yml
group :jekyll_plugins do
  gem "jekyll-feed", "0.17.0"
  gem "jekyll-seo-tag", "2.8.0"
  gem "jekyll-sitemap", "1.4.0"
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
platforms :windows, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.1.1", :platforms => [:windows]

# Lock `http_parser.rb` gem to `v0.6.x` on JRuby builds
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]
