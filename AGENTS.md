# Repository Guidelines

## Project Structure & Module Organization

This repository is a static blog export. `index.html` is the primary page and contains the article markup plus inline CSS. `assets/` stores referenced WordPress-export files such as scripts, stylesheets, icons, and embedded resources; treat these as static vendor/export artifacts unless a page reference requires changing them. `README.md` documents local usage, `CLAUDE.md` contains agent notes, and `wrangler.jsonc` configures Cloudflare Workers static asset hosting.

There is no application source tree or test directory. Keep new content close to the existing static layout unless the project is intentionally expanded.

## Build, Test, and Development Commands

- `python3 -m http.server 8080`: serve the site locally from the repository root.
- Open `http://localhost:8080`: inspect the rendered page in a browser.
- `npx wrangler deploy`: deploy through Cloudflare Workers when Wrangler is installed and authenticated.

There is no build step. Avoid adding package managers, bundlers, or generated lockfiles unless the change explicitly requires a toolchain.

## Coding Style & Naming Conventions

Use plain HTML, CSS, and static assets. Preserve the current single-page structure: article content belongs in `index.html`, with CSS kept in the existing inline `<style>` block unless a broader refactor is requested. Use two-space indentation where practical, lowercase element and attribute names, and descriptive class names.

For asset filenames, preserve exported names when updating references. If adding new assets, use lowercase, hyphenated names such as `diagram-interpreter-flow.png`.

## Testing Guidelines

Testing is manual. After edits, serve the site locally and verify the article renders, links work, images load, and the layout is usable at desktop and mobile widths. Check browser console errors if scripts or asset paths were touched.

No coverage requirement or automated test framework exists in this repository.

## Commit & Pull Request Guidelines

Recent commits use short imperative summaries, for example `Add Wrangler static assets config`. Follow that style: start with a verb, keep the subject concise, and describe one logical change.

Pull requests should include a brief summary, the reason for the change, and manual verification steps. Include screenshots when layout, images, typography, or responsive behavior changes. Link related issues when applicable.

## Deployment & Configuration Notes

Cloudflare configuration lives in `wrangler.jsonc`; the assets directory is set to `"."`, so files at the repository root are deployable. Do not commit credentials, local Wrangler state, or environment-specific secrets.
