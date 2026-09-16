# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A single-page static portfolio site for Julien Amsellem (software engineer / indie game developer), deployed with GitHub Pages at https://ju2pom.github.io/portfolio/. There is no build system, no package manager, and no tests — it's plain HTML/CSS with fonts loaded from the Google Fonts CDN.

## Structure

- `index.html` — the French (default) page, served at the site root.
- `en/index.html` — the English translation, served at `/en/`.
- `design/` — **gitignored**, not part of the deployed site. Contains the source files for the original design, authored as a Claude Design canvas (`.dc.html` "Design Component" files, `canvas.json` layout, and the seeded canvas HTML). `index.html` was manually exported from `design/Main.dc.html` (stripped of the canvas-runtime-specific tags/scripts, with the CSS custom-property accent color baked in as a literal hex value). Treat `design/` as reference only — it is not rebuilt or synced automatically.

## Key thing to know when editing

`index.html` and `en/index.html` are **fully independent, self-contained files** — no shared stylesheet, no templating, no build step. Every CSS rule and every piece of markup is duplicated between the two. Any content or design change (copy, colors, layout, new section, etc.) must be applied to **both files by hand** to keep them in sync.

## Deploying

There is no build step. Pushing to `master` is the deploy: GitHub Pages serves the repository root directly from that branch.

```bash
git add index.html en/index.html
git commit -m "..."
git push
```

**Never push automatically.** Commit if asked, but always wait for explicit user confirmation before running `git push` — pushing goes live immediately on the public site.

## Local preview

Just open `index.html` (or `en/index.html`) directly in a browser — no server required.
