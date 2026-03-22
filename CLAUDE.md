# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Continuum SaaS documentation site built on Mintlify. Pages are MDX files with YAML frontmatter. Site configuration is in `docs.json`. An AGENTS.md file also exists with Mintlify-specific agent instructions.

## Color palette — Continuum brand

Monochromatic (grayscale) palette with a single vibrant accent: neon green. The green is used sparingly for maximum visual impact.

- **Accent (Neon Green):** `#9bff8b` — primary brand color
- **Accent hover:** `#7fe86d`
- **Accent muted (20% alpha):** `#9bff8b33`
- **Light mode:** backgrounds `#ffffff`/`#fafafa`, text `#000000`/`#666666`/`#999999`, card borders `#f0f0f0`
- **Dark mode:** backgrounds `#1a1a1a`/`#111111`, text `#ffffff`/`#a0a0a0`/`#666666`, card bg `#141414`, borders `#222222`
- **Status colors:** success `#9bff8b`, warning `amber-400`, error `rose-400` (each on 10% alpha background)
- **Glow shadow:** `0 0 40px rgba(155,255,139,0.15)`
- **Text selection:** bg `#9bff8b`, text `#000000`

These are configured in `docs.json` under `colors`. When adding custom CSS or components, use these values.

## Commands

```bash
# Install CLI (requires Node.js >= 19)
npm i -g mint

# Local preview at http://localhost:3000
mint dev

# Custom port
mint dev --port 3333

# Check for broken links
mint broken-links

# Update CLI to latest version
npm mint update

# Install Mintlify AI skill for component reference
npx skills add https://mintlify.com/docs
```

## Architecture

- `docs.json` — Central config: theme, navigation structure (tabs, groups, pages), colors, logos, navbar, footer, contextual options
- `index.mdx` — Landing page
- `essentials/` — Core docs on markdown, code, images, navigation, settings, snippets
- `api-reference/` — API docs; `openapi.json` defines the OpenAPI spec, endpoint pages are auto-generated MDX
- `ai-tools/` — Setup guides for Cursor, Claude Code, Windsurf
- `snippets/` — Reusable MDX snippets (imported with `<Snippet>`)
- `images/`, `logo/` — Static assets
- `.mintignore` — Files excluded from Mintlify builds (drafts/, *.draft.mdx)

## Navigation structure

Navigation is defined in `docs.json` under `navigation.tabs`. Each tab contains groups of pages. When adding a new page, it must be added to the appropriate group in `docs.json` to appear in navigation.

## Writing conventions (from AGENTS.md)

- Active voice, second person ("you")
- One idea per sentence
- Sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, code references

## Deployment

Changes pushed to the default branch are auto-deployed via the Mintlify GitHub app. No manual build/deploy step needed.
