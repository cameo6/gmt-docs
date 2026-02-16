# CLAUDE.md

## Project Overview

This is the documentation site for **Get My TG** — a Telegram account store. Built with [Mintlify](https://mintlify.com/), it serves bilingual (Russian and English) documentation.

## Tech Stack

- **Framework:** Mintlify (documentation platform)
- **Content format:** MDX (Markdown + JSX)
- **Theme:** willow
- **Icons:** Lucide
- **Deployment:** Auto-deploy on push to `main` via Mintlify

## Development

```bash
# Install Mintlify CLI (one-time)
npm i -g mint

# Start local dev server on http://localhost:3000
mint dev
```

## Project Structure

```
docs.json          # Main Mintlify configuration (navigation, theme, colors)
en/                # English documentation (16 pages)
ru/                # Russian documentation (16 pages, mirrors en/)
images/            # Screenshots and hero images
logo/              # Light/dark theme logos
```

Both `en/` and `ru/` share identical structure:
- `index.mdx` — Home page
- `getting-started/` — Overview, first steps, supported clients
- `accounts/` — Structure, sessions, environment, app-id, limits
- `network/` — Overview, proxy, VPN
- `security/` — Overview
- `issues/` — Troubleshooting
- `faq.mdx`, `glossary.mdx`

## Conventions

- Every MDX page starts with YAML front matter: `title`, `description`, `icon`
- Content components: `<Steps>`, `<Step>`, `<Card>`, `<CardGroup>`, `<Note>`, `<Warning>`, `<Table>`
- Internal links use absolute paths: `[text](/en/path)` or `[text](/ru/path)`
- English and Russian pages must be kept in sync (same structure and content)
- Git commit messages use `feat:` / `fix:` prefixes

## Configuration

All site configuration lives in `docs.json`:
- Navigation structure (separate trees for en/ru)
- Theme and color settings
- Logo and favicon paths
- External API spec: `https://api.getmytg.com/docs/openapi.json`
