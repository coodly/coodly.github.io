# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based static website (coodly.github.io) that serves as a company website with privacy policies for multiple iOS apps. The site uses the default Jekyll structure with the Minima theme.

## Architecture

- **Jekyll Site**: Standard Jekyll 4.3.4 setup with Minima theme
- **App Privacy Pages**: Each app has its own directory with a `privacy.md` file
  - `/calories/privacy.md` - Your Daily Calories app
  - `/doomed/privacy.md` - Doomed app
  - `/gambrinus/privacy.md` - Gambrinus app
  - `/moviez/privacy.md` - Moviez app
  - `/tenpair/privacy.md` - TenPair app
  - `/yatta/privacy.md` - Yatta app
- **Layouts**: Uses custom layouts (note: some deleted layouts like `coodly.html` and `yatta.html` are referenced in git status)
- **Generated Site**: `_site/` contains the built static files

## Development Commands

### Local Development
```bash
# Install dependencies
bundle install

# Serve the site locally with auto-reload
bundle exec jekyll serve

# Build the site
bundle exec jekyll build
```

### Site Structure
- `_config.yml` - Jekyll configuration
- `_posts/` - Blog posts (standard Jekyll format: YYYY-MM-DD-title.markdown)
- `_layouts/` - Custom page layouts
- `index.markdown` - Homepage using 'home' layout
- `about.markdown` - About page
- Individual app directories contain privacy policies

## Key Files
- `Gemfile` - Ruby dependencies (Jekyll 4.3.4, Minima theme, Jekyll Feed plugin)
- `_config.yml` - Site configuration with Minima theme and Jekyll Feed plugin
- `CNAME` - GitHub Pages custom domain configuration
- `google8887405a511e8ea4.html` - Google site verification
- `app-ads.txt` - App advertising policies

## Notes
- The site appears to be in transition (many deleted files in git status)
- Privacy policies follow a consistent format across all apps
- Uses Jekyll's built-in development server for local testing
- Deployed via GitHub Pages (evidenced by CNAME file)