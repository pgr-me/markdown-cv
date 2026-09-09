# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A Jekyll-powered, single-page CV (fork of elipapa/markdown-cv). All CV content lives in `index.md`; everything else is rendering machinery.

## Commands

```sh
jekyll serve            # build + watch; view at http://localhost:4000
```

Restart `jekyll serve` after changing `_config.yml`. There is no test suite or linter — verify changes visually in the browser **and** in print preview (print CSS differs from screen CSS; PDF output comes from printing the browser page).

## Architecture

The rendering chain is: `index.md` (content + YAML front matter) → `_layouts/cv.html` (HTML shell) → a screen/print CSS pair from `media/` selected by the `style:` value in `_config.yml`.

- Styles come in pairs: `media/<style>-screen.css` and `media/<style>-print.css` (e.g. `davewhipp`, `kjhealy`). A new theme must add both files, and `style: <name>` in `_config.yml` activates it.
- `index.md` uses Markdown headings for CV sections (`## EXPERIENCE`, `### <employer>`, …) with dates in backticks (`` `Nov 2025-Present` ``). Preserve the YAML front matter (`layout: cv`, `title`).

## Conventions (from AGENTS.md)

- Two-space indentation in HTML/CSS; keep CSS selectors scoped to the CV markup.
- Short, imperative commit subjects (`Update index.md`); one focused change per commit.
- When modifying shared layout/CSS, check both configured styles and print page breaks.
- CV changes land on `gh-pages` (the branch GitHub Pages publishes), not `master`. Base feature branches and PRs on `gh-pages`.
