# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Hugo static site** for "单词卡片" (Word Cards), a Chinese-language website hosted at `https://md.kelegele.com/`. The site uses the `hugo-pure` theme as a git submodule.

## Development Commands

```bash
# Build the site (outputs to public/)
hugo

# Run local development server (http://localhost:1313)
hugo server

# Run dev server including draft posts
hugo server -D

# Initialize/update theme submodule (if theme files are missing)
git submodule update --init --recursive
```

## Project Structure

- `hugo.toml` - Main Hugo configuration (minimal: baseURL, languageCode, title, theme)
- `content/` - Markdown content files (privacy-statement.md, user-agreement.md)
- `layouts/_default/baseof.html` - **Custom layout override** that replaces the theme's base template
- `assets/css/main.css` - Custom styles with CSS variables for light/dark theme switching
- `static/` - Static assets (favicon.png, images/, SVG icons)
- `archetypes/default.md` - Template for new content pages
- `themes/hugo-pure/` - Theme submodule (https://github.com/undus5/hugo-pure)

## Architecture Notes

### Theme Customization

The project overrides the theme's `baseof.html` with a custom version in `layouts/_default/baseof.html`. Key differences:
- Menu and footer partials are **commented out** for a minimal design
- Corner indicators (decorative borders) are enabled via `Site.Params.disableCornerIndicator`
- CSS bundling includes: purecss, menu.css, main.css, syntax-light/dark.css

### Theme System

Dark/light mode switching is handled via CSS `@media (prefers-color-scheme: dark)` in `assets/css/main.css`. The CSS uses CSS custom properties (`--body-background-light`, `--body-background-dark`, etc.) defined in `:root`.

### Submodule

The `hugo-pure` theme is a git submodule. If the theme directory appears empty, run:
```bash
git submodule update --init --recursive
```

## Content Creation

Create new content using Hugo's archetypes:
```bash
hugo new content/my-page.md
```
This applies the template from `archetypes/default.md` which includes front matter with title, date, and draft status.
