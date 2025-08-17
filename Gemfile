source "https://rubygems.org"

# Jekyll core
gem "jekyll", "~> 4.3.2"

# GitHub Pages theme and plugins
gem "github-pages", group: :jekyll_plugins

# Essential plugins
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.17"
  gem "jekyll-seo-tag", "~> 2.8"
  gem "jekyll-sitemap", "~> 1.4"
  gem "jekyll-paginate", "~> 1.1"
  gem "jekyll-redirect-from", "~> 0.16"
  gem "jemoji", "~> 0.13"
end

# Mathematics support
gem "kramdown-math-katex", "~> 1.0"

# Windows and JRuby compatibility
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Performance booster for watching directories on Windows
gem "wdm", "~> 0.1", :platforms => [:mingw, :x64_mingw, :mswin]

# Lock `http_parser.rb` gem to `v0.6.x` on JRuby builds
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]

# Development tools
group :development do
  gem "webrick", "~> 1.8"
end
