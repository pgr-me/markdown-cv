# Repository Guidelines

## Project Structure & Module Organization

This repository is a Jekyll-powered, single-page CV template. Edit `index.md` for CV content and its YAML front matter (`layout` and `title`). `_layouts/cv.html` is the shared HTML shell and loads the selected stylesheet. `_config.yml` configures Kramdown and chooses the active style. Keep paired screen and print styles in `media/`, following the pattern `<style>-screen.css` and `<style>-print.css` (for example, `kjhealy-screen.css`). `README.md` documents user-facing setup; update it when the workflow or available styles change.

## Build, Test, and Development Commands

Install the local Jekyll tooling if needed:

```sh
gem install bundler jekyll
jekyll serve
```

`jekyll serve` builds the site and watches for edits; inspect the result at `http://localhost:4000`. Stop the server and run it again after changing `_config.yml`. There is no automated test suite or lint configuration in this repository. Verify changes by viewing both the browser rendering and print preview; print to PDF from the browser when checking print CSS.

## Coding Style & Naming Conventions

Use two-space indentation in HTML and CSS, matching the existing layout and styles. Preserve valid YAML front matter at the start of `index.md`, and use Markdown headings to organize CV sections. Keep CSS selectors scoped to the CV markup where practical. Add a new theme only as a complete screen/print pair and set `style: <name>` in `_config.yml` to exercise it. Avoid unrelated reformatting of content or stylesheets.

## Testing Guidelines

Manually test every content, layout, or CSS change with `jekyll serve`. Check at least one normal browser viewport and print preview, including page breaks, headings, links, dates, and both configured styles when modifying shared layout behavior. Confirm the selected `style` value has matching files in `media/`.

## Commit & Pull Request Guidelines

Make repository changes only on the `gh-pages` branch; do not modify `master`. Use short, imperative commit subjects consistent with project history, such as `Update index.md` or `Fix print header positioning`. Keep each commit focused. Pull requests should explain the visible change, identify any related issue, and include screenshots or print-preview images for layout or CSS updates. Note the browser and style tested, and update `README.md` when contributor-facing behavior changes.
