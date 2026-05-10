# Aura — Claws x Code Shopify Theme

A custom Shopify theme for [Claws x Code](https://clawsxcode.com), forked from [Shopify Dawn](https://github.com/Shopify/dawn) and rebuilt for motion and vibe.

## Vision

Dawn is the starting point. Aura is the destination.

The goal is a highly interactive storefront experience with morphing UI animations — shapes that breathe, transitions that feel alive, and a visual language that matches the Claws x Code brand. Less static template, more living interface. Welcome to the House of Thock.

## Architecture

```
assets/       Static files — CSS, JS, images, fonts
blocks/       Reusable nestable components (theme editor–editable)
config/       Global theme settings schema
layout/       Site-wide HTML wrapper (head, nav, footer)
locales/      Translation strings
sections/     Full-width modular page components
snippets/     Reusable Liquid fragments
templates/    Page structure definitions
workspace/    Local only — plans, backups, scratch (gitignored)
```

## Dev Rules

**JSON is never committed to git.** Settings, templates, locales — all JSON stays out of version control. Source of truth for JSON lives in Shopify, not here.

**Push to dev with Liquid and assets only:**
```bash
shopify theme push --store your-store.myshopify.com --theme <theme-id> \
  --only '*.liquid' 'assets/*' 'snippets/*' 'sections/*' 'blocks/*' 'layout/*' 'templates/*.liquid'
```

**Backup before any major change:**
```bash
shopify theme pull --store your-store.myshopify.com --path ./workspace/backups/live-$(date +%Y%m%d)
```

## Branch Strategy

| Branch | Purpose |
|--------|---------|
| `main` | Live theme mirror — pull only |
| `dev` | Active development — push to unpublished dev theme |
| `feature/*` | New sections, blocks, experiments |

## Animation Stack

TBD — evaluating [GSAP](https://gsap.com) vs [Material Design 3 Expressive](https://m3.material.io/styles/motion/overview) for morphing / motion primitives. Decision tracked in backlog.

## Backlog

See [workspace/plans/BACKLOG.md](workspace/plans/BACKLOG.md).
