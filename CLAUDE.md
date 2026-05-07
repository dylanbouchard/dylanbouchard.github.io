# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

`dylanbouchard.github.io` — a personal academic site for Dylan Bouchard, served by GitHub Pages from the `main` branch of this repo. It is plain HTML + CSS with no build step; GitHub Pages publishes the files as-is.

## Files

- `index.html` — the entire site (single page). All content lives here: header/links bar, About, Open-Source Projects, Publications, Selected Talks.
- `style.css` — minimal academic styling. Single column, ~720px max width, serif body, restrained color palette, dark-mode via `prefers-color-scheme`.
- `Dylan_Bouchard_Resume.pdf` — linked from the header as "CV".

## Local preview

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

There is no test suite, no linter, and no CI. Pushing to `main` deploys.

## Editing content

Each content section in `index.html` is a `<section>` whose entries are list items under `<ul class="entries">` (or `<ol class="entries pubs">` for publications). To add a publication, append a new `<li>` matching the existing structure (`authors`, `ptitle`, `venue`, link). To add a project, follow the UQLM/LangFair `<li>` pattern (`title` + `desc` + `links-inline`).

Two header links are intentionally placeholders pending URLs: Google Scholar and ORCID (search for `<!-- TODO` in `index.html`).

## Style conventions

- Keep the aesthetic minimal and academic: no shadows, no gradients, no icon fonts, no JS frameworks.
- Avoid adding dependencies or build tooling unless the content scale genuinely outgrows hand-edited HTML (current scale: 5 publications, 2 projects, 3 talks).
- Colors and rhythm are controlled by CSS custom properties at the top of `style.css` — prefer adjusting those over hardcoding values in rules.
