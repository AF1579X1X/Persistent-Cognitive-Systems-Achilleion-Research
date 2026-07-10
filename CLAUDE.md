# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

This is a static content repository, not an application codebase. It publishes **Achilleion Vivens / Q_ANIMA**, an independent research project by Francesco Mattioli, as a GitHub Pages site. There is no build system, package manager, compiler, linter, or test suite — every file under `docs/` is hand-authored, deploy-ready HTML/XML/JSONL, served as-is by GitHub Pages.

There are no "commands to build, lint, or run tests" because none exist in this repo. Do not introduce a build step (bundler, static-site generator, npm scripts, etc.) unless the user explicitly asks for one — the project's own conventions (see the editorial manifesto in `docs/research/`) deliberately favor a single hand-authored canonical source over generated pipelines.

## Publishing model

- GitHub Pages serves directly from `docs/` (see `docs/.nojekyll`, which disables Jekyll processing so files are served verbatim).
- The live site is https://af1579x1x.github.io/Persistent-Cognitive-Systems-Achilleion-Research/ — every page's `<link rel="canonical">`, Open Graph, and JSON-LD metadata hardcodes this full URL, so any file moved or renamed must have its internal canonical/OG URLs and `docs/sitemap.xml` entry updated to match the new path.
- There is no `CNAME` file, so all canonical URLs include the `/Persistent-Cognitive-Systems-Achilleion-Research/` path prefix. Relative links between pages use `../` / `./` paths (e.g. `../author/francesco-mattioli.html`), not absolute paths — preserve this when adding pages so the site keeps working if ever moved.
- `docs/robots.txt` and `docs/sitemap.xml` are hand-maintained. Any new HTML page intended to be publicly indexed should be added to `docs/sitemap.xml` with a `<lastmod>` date.
- `docs/googl*.html`, `docs/BingSiteAuth.xml`, and the two `docs/<hash>.txt` files are search-engine ownership-verification files. Do not delete or "clean up" these — they look like cruft but are required for Google/Bing Search Console verification.
- `docs/llms.txt` is a hand-curated, plain-text summary of the entire site aimed at LLM crawlers/agents (topics, canonical URLs, keyword glosses for each concept/paper/book). When adding or renaming a page under `docs/`, update `llms.txt` alongside `sitemap.xml` so the two stay in sync.

## Content architecture

Top-level sections under `docs/`, each with its own `index.html` hub page:

- `concepts/` — short `DefinedTerm`-schema pages for individual theoretical terms (e.g. `homo-transducer.html`, `sense-graviton.html`, `soglia-teta.html`, `pleroma.html`). Each links to sibling concepts via a `.concept-links` nav block at the bottom.
- `papers/` — longer theoretical/technical articles (public abstracts and working papers).
- `research/` — the manifesto, operational-ecosystem writeups, and terminology guides. Some source articles have a paired `*.editorial.md` file (YAML front matter + Markdown) alongside the published `.html` — the Markdown is the editorial/authoring source, the HTML is the published rendering. When editing an article that has both, update both and keep them in sync.
- `specifications/` — canonical terminology and operator/spec documents treated as normative reference.
- `essays/` — standalone essays outside the core research line.
- `books/` — published-book landing pages (metadata only: ISBN, ASIN, retailer links; not full text).
- `author/` — author identity/bio pages.
- `corpus/` — the semantic retrieval corpus (see below).
- `assets/` (repo root) and `docs/assets/` — images, author photo, book covers, and SVG diagrams. Root-level `assets/` and `docs/assets/` are separate directories serving different consumers (README on GitHub vs. the published site); don't assume they're mirrors of each other.

### Corpus (`docs/corpus/`)

Two parallel JSONL/Markdown corpora, each entry a flat JSON object with `id`, `title`, `type`, `source_basis`, `keywords[]`, `content`:

- `chunks/achilleion-canonical-chunks.jsonl` (+ `.md` twin) — IDs prefixed `ACH-CANON-###`. Authoritative, source-of-truth definitions.
- `chunks/achilleion-source-mediated-chunks.jsonl` (+ `.md` twin) — IDs prefixed `ACH-SRC-###`. Content derived/curated from internal source syntheses, explicitly **not** raw internal material or private technical artefacts (see the distinction called out in `llms.txt`).

The `.md` file for each corpus is a human-readable rendering of the same entries as the `.jsonl` — if you edit one, regenerate/edit the other so they don't drift. Preserve the `ACH-CANON-NNN` / `ACH-SRC-NNN` ID numbering scheme (zero-padded, sequential, never reused) when adding entries.

## Conventions when editing HTML pages

Every content page under `docs/` follows the same template — study a sibling page in the same directory (e.g. `docs/concepts/homo-transducer.html`) before adding a new one:

- `<!doctype html>` with a leading UTF-8 BOM (`﻿`) preserved at the top of the file — this appears in existing files and should not be stripped.
- `lang="it"` on `<html>` for Italian-primary pages (most of `concepts/`, `research/`); the root `docs/index.html` uses `lang="en"`. Match the language of the surrounding section.
- Full meta block: description, keywords, author, robots, canonical link, Open Graph (`og:*`), Twitter card tags, then a `<script type="application/ld+json">` schema.org block (`DefinedTerm` for concepts, `Article`/`WebSite`/`Person`/`ResearchProject` elsewhere as appropriate).
- An inline `<style>` block defining CSS custom properties (`--bg`, `--surface`, `--text`, `--accent`, etc.) with a `[data-theme="neutral"]` dark-mode override — copy an existing page's palette rather than inventing new variable names.
- A `<nav>` bar near the top of `<main>` linking back to Home/Author/Corpus/Specifications/section-index, and (for concept pages) a `.concept-links` block at the end cross-linking related terms.
- Content is in dense, unindented single-line HTML (no per-tag line breaks) — this is the existing style; match it rather than reformatting into multi-line pretty HTML, since reflowing whitespace produces noisy diffs across an otherwise hand-authored file.

## Language and tone

Most research/manifesto/concept content is written in Italian, with English used for the site root (`docs/index.html`), `llms.txt`, and some paper abstracts. The project draws a careful, explicit line between describing Q_ANIMA/Achilleion as *reflective*, *observable*, *governable* systems versus making unverifiable claims of machine "consciousness" or "sentience" — preserve this framing (e.g. "riflessività dialogica osservabile", "non rivendica sentienza artificiale") when editing or extending theoretical content; don't rewrite it into stronger AI-consciousness claims than the source material makes.

## Repo root vs. `docs/`

- `README.md` and root `assets/achilleion-vivens.svg` / `achilleion-master-architecture.{png,svg}` are what GitHub shows on the repository landing page — separate from and not synced with the published `docs/` site.
- `docs/` is the deployed GitHub Pages site — treat it as the primary content the public sees.
