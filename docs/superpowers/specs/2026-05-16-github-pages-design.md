# GitHub Pages site for worksafe-agent — design

## Goal

Publish the repo's markdown documents as a readable browsable site at the repo's GitHub Pages URL, preserving the existing folder organization (`research/`, `opportunities/`, `log/`) as sidebar sections.

## Stack

**Jekyll + just-the-docs** as a remote theme.

- Native GitHub Pages build — no `Gemfile`, no GitHub Actions workflow needed.
- Sidebar nav, built-in client-side search, clean docs-style typography.
- Pages is already configured: Deploy from branch `main` at `/` (root).

## Site structure

| URL path | Source file | Sidebar treatment |
|---|---|---|
| `/` | `README.md` (via `permalink: /`) | Home (always visible) |
| `/sources/` | `sources.md` | Top-level page, `nav_order: 99` |
| `/research/` | `research/index.md` (new) | Section parent |
| `/research/<slug>/` | `research/*.md` | Children of Research |
| `/opportunities/` | `opportunities/index.md` (new) | Section parent |
| `/opportunities/<slug>/` | `opportunities/*.md` | Children of Opportunities |
| `/log/` | `log/index.md` (new) | Section parent |
| `/log/<slug>/` | `log/*.md` | Children of Log, sorted newest-first |

## Front-matter additions

Each existing `.md` file gets a minimal front-matter block prepended. GitHub's own markdown renderer ignores Jekyll front-matter, so repo viewing is unaffected.

**`README.md`:**
```yaml
---
title: Home
layout: home
nav_order: 1
permalink: /
---
```

**`sources.md`:**
```yaml
---
title: Sources
nav_order: 99
---
```

**`research/*.md`, `opportunities/*.md`, `log/*.md`:**
```yaml
---
title: <Human-friendly title>
parent: <Research | Opportunities | Log>
nav_order: <integer>
---
```

Log entries use `nav_order` derived from date — newest = lowest order so they sort to the top of the section.

## Section landing pages

Three new files, each just a bulleted list of the section's documents with one-line descriptions pulled from the source files' opening lines.

`research/index.md`:
```yaml
---
title: Research
nav_order: 2
has_children: true
---

# Research

Durable findings on the BC WorkSafe domain.

- [Domain primer](domain-primer.md) — how the BC appeal system actually works
- [Landscape](landscape.md) — competitors and their edges
- [CanLII deep dive](canlii-deep-dive.md) — why CanLII is a weaker threat than first framed
```

`opportunities/index.md` (nav_order: 3) and `log/index.md` (nav_order: 4) follow the same pattern.

## `_config.yml`

```yaml
title: worksafe-agent
description: Long-term R&D on AI products for the BC WorkSafe ecosystem
remote_theme: just-the-docs/just-the-docs

# just-the-docs config
search_enabled: true
heading_anchors: true
color_scheme: light
aux_links:
  "GitHub":
    - "https://github.com/shuped/worksafe-agent"

# Jekyll core
markdown: kramdown
exclude:
  - docs/
  - Gemfile
  - Gemfile.lock
  - README-pages.md
```

The `exclude: docs/` line keeps the superpowers spec/plan files out of the published site.

## Inter-document links

Existing relative links like `[domain primer](research/domain-primer.md)` in `README.md` work as-is — Jekyll + just-the-docs resolves `.md` links to the rendered page URL.

## Deployment

GitHub Pages is already configured (main / root). Once these files land on `main`, the site builds automatically. Expected URL: `https://shuped.github.io/worksafe-agent/`.

## What's explicitly out of scope (YAGNI)

- Custom domain
- Custom CSS / theme overrides
- GitHub Actions workflow (remote theme avoids it)
- Tag or category system
- Dark mode toggle (default light is fine for a research site)
- Auto-generated changelog or last-updated stamps

## File inventory

**New files (5):**
- `_config.yml`
- `research/index.md`
- `opportunities/index.md`
- `log/index.md`
- `docs/superpowers/specs/2026-05-16-github-pages-design.md` (this file)

**Modified files (9):**
- `README.md`
- `sources.md`
- `research/canlii-deep-dive.md`
- `research/landscape.md`
- `research/domain-primer.md`
- `opportunities/product-ideas.md`
- `opportunities/defensible-edges.md`
- `log/2026-05-14-initial-scan.md`
- `log/2026-05-15-canlii-deep-dive.md`

Modifications are all front-matter prepends — no content changes.
