# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A static HTML visualization of the Kiln CMS information architecture. The entire project is a single file (`cms-model.html`) — no build system, no dependencies, no tests.

## Development

Open `cms-model.html` directly in a browser. No server required.

## Architecture

The file renders two switchable views of the Kiln CMS entity model via a segmented control:

1. **Nested view** — visual containment showing Site > Page > Block > Content nesting
2. **Hierarchy (tree) view** — single-instance tree with cardinality labels ("has many" / "has one")

### Entity model

- **Site** — top level; has Settings and Design
- **Page** — belongs to Site (many); has Settings
- **Block** — belongs to Page (many); has Variants and Design Overrides
- **Content** — belongs to Block (one); typed fields (heading, body, images, etc.)

### Design system

CSS custom properties define a color-coded entity palette (blue=Site, green=Page, purple=Block, amber=Content, red=Settings, blue=Design). Typography uses DM Mono (body) and Fraunces (labels), loaded from Google Fonts.

All CSS and JS are inline in the single HTML file.
