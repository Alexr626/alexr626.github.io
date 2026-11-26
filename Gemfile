source "https://rubygems.org"

# Same Jekyll and plugin versions as GitHub Pages' own build.
gem "github-pages", group: :jekyll_plugins

# Local builds only: GitHub Pages' builder has its own fixed gem set and warns about
# any gem outside it. webrick is needed by `jekyll serve` on Ruby 3; faraday-retry
# silences a warning from the github-pages plugins.
unless ENV["GITHUB_ACTIONS"]
  gem "webrick"
  gem "faraday-retry"
end
