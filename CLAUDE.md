# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the **Surf Data** documentation site, built with [Mintlify](https://mintlify.com). It documents a SaaS platform that connects databases to AI agents via the Model Context Protocol (MCP).

## Development

```bash
# Install Mintlify CLI (one-time)
npm i -g mint

# Run local dev server (from this directory, where docs.json lives)
mint dev

# Update CLI if dev environment breaks
mint update
```

Local preview runs at `http://localhost:3000`.

## Architecture

- **docs.json** — Mintlify v2 config: navigation structure, theme, logos, footer, navbar
- **Content files** — `.mdx` files organized by section (platform/, security/, api-reference/, etc.)
- **Navigation** — Two tabs defined in docs.json: "Documentation" and "API Reference", each with grouped pages
- **Deployment** — Pushes to the default branch auto-deploy via Mintlify's GitHub app integration

## Content Structure

| Section | Purpose |
|---------|---------|
| `api-reference/` | REST API and MCP endpoint documentation |
| `platform/` | Core features: projects, datasources, views, tools, publishing |
| `security/` | Auth, tokens, data masking, LGPD compliance |
| `organizations/` | Multi-tenancy, members, billing |
| `monitoring/` | Usage consumption, evals (execution logs), alerts |
| `integrations/` | Claude, Cursor, and custom agent setup guides |

## Conventions

- Token placeholders must use `sk_live_<your-token>` format — never use long alphanumeric strings after `sk_live_` as GitHub push protection will block them as Stripe key false positives.
- Pages are referenced in docs.json without the `.mdx` extension.
- The product name is **Surf Data**; the app URL is `https://surfdata.com.br`.
