# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A static blog post — a single self-contained `index.html` with all styles inlined in a `<style>` block and content in the `<article>` element. The `assets/` directory holds referenced images, scripts, and stylesheets from the original WordPress export that are linked from within the HTML.

## Development

No build step. Open `index.html` directly in a browser or serve it locally:

```bash
python3 -m http.server 8080
```

## Structure

- `index.html` — the entire page: inline CSS in `<head>`, article content in `<main><article>`
- `assets/` — images and static files referenced by the page (WordPress export artifacts, some may be unused)
