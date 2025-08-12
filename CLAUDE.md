# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a Jekyll-powered GitHub Pages blog using the Chirpy theme. The site is in Korean and serves as REDVIRUZ's personal tech and life blog. It's configured for Korean timezone (Asia/Seoul) and uses Korean language settings.

## Development Commands

### Local Development
```bash
# Start development server
bundle exec jekyll serve -l

# Use the helper script for development with options
bash tools/run.sh
bash tools/run.sh --host 0.0.0.0  # Bind to all interfaces
bash tools/run.sh --production     # Run in production mode
```

### Build and Test
```bash
# Build for production
JEKYLL_ENV=production bundle exec jekyll build

# Build and test with HTML validation
bash tools/test.sh

# Test with custom config
bash tools/test.sh --config _config.yml,_config.test.yml
```

### Dependencies
```bash
# Install Ruby dependencies
bundle install

# Update dependencies
bundle update
```

## Site Architecture

### Key Configuration Files
- `_config.yml`: Main Jekyll configuration with Korean localization, Chirpy theme settings, Google Analytics, and Disqus comments
- `Gemfile`: Ruby dependencies including Chirpy theme and HTML Proofer for testing

### Content Structure
- `_posts/`: Blog posts in markdown format with Korean titles using YYYY-MM-DD prefix
- `_tabs/`: Static pages (about, archives, categories, tags)
- `_data/`: YAML data files for contact info and social sharing
- `_plugins/`: Custom Jekyll plugins including Git-based last modified date hook
- `assets/`: Static assets (CSS, JS, images)

### Post Format
Posts follow Jekyll's naming convention: `YYYY-MM-DD-title.md` and require front matter:
```yaml
---
title: "Post Title"
date: YYYY-MM-DD HH:mm:ss +09:00
categories: [Category1, Category2]
tags: [tag1, tag2, tag3]
---
```

### Theme Features
- Dark mode enabled by default
- Korean timezone (Asia/Seoul)
- Google Analytics integration (G-VP1B1PGR1S)
- Disqus comments (shortname: redviruzblog)
- PWA support with offline caching
- SEO optimization with custom social preview
- Table of contents for posts

### Deployment
Site deploys automatically to GitHub Pages at https://redviruz.github.io when changes are pushed to the main branch.

## Common Operations

### Adding New Posts
1. Create markdown file in `_posts/` with format: `YYYY-MM-DD-title.md`
2. Add required front matter with Korean date format
3. Use appropriate categories and tags from existing posts
4. Content can include Korean text and should be optimized for Korean readers

### Testing Changes
Always run `bash tools/test.sh` before deploying to validate HTML structure and internal links.

### Image Management
Posts use Cloudinary for image hosting (res.cloudinary.com/dqgw9jnvd/). Images should be optimized with quality and width parameters.