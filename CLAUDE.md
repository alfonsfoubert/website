# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio and blog website for Alfons Foubert (alfonsfoubert.com), built with Hugo static site generator using the Hugo-Profile theme.

## Build & Development Commands

```bash
# Development server with hot reload
hugo server

# Production build (outputs to /public)
hugo

# Clean build
rm -rf public/ && hugo

# Create new blog post
hugo new content blog/post-name.md
```

## Tech Stack

- **Static Site Generator:** Hugo (v0.143.0)
- **Theme:** Hugo-Profile (git submodule in /themes/hugo-profile)
- **Frontend:** Bootstrap 5, Font Awesome 6
- **Deployment:** Netlify (auto-deploys on push)
- **Content Format:** Markdown with YAML frontmatter

## Architecture

### Configuration
- `hugo.yaml` - Main site configuration containing all section content, navigation, social links, and theme settings. Most content changes happen here.

### Content Structure
- `content/blog/` - Blog posts as Markdown files with YAML frontmatter (title, date, author, tags, image, description)
- `content/gallery.md` - Gallery page with ViewerJS image viewer
- `content/_index.md` - Homepage content

### Layout Hierarchy
1. `themes/hugo-profile/layouts/_default/baseof.html` - Base HTML structure
2. Page-specific templates: `single.html` (posts), `list.html` (archives), `index.html` (homepage)
3. `themes/hugo-profile/layouts/partials/sections/` - Reusable section components (hero, about, projects, achievements, contact)

### Static Assets
- `static/images/` - All images organized by type (blog/, achievements/, services/)
- Reference images in content as `/images/path/to/file`

## Key Patterns

- Homepage sections are configured in `hugo.yaml` under `params:` (hero, about, projects, achievements, contact)
- Sections can be enabled/disabled via `enable: true/false` in hugo.yaml
- Blog posts use archetypes from `archetypes/default.md` for scaffolding
- Theme uses Bootstrap 5 classes for styling
- Dark theme is forced via `darkmode: force` in config
