---
title: "The Stack"
description: "The technical architecture behind this research — and why each component was chosen."
---

# The Stack

Every architectural decision is an argument. The components chosen here each make a specific claim about what matters in a knowledge system built for durability, affordability, and institutional continuity.

| Component | Layer | Cost |
| --- | --- | --- |
| Obsidian | Knowledge creation + linking | Free |
| Markdown | File format | Free |
| Quartz | Static site generation | Free |
| GitHub Pages | Hosting + deployment | Free |
| Cloudflare Access | Access control | Free (≤50 users) |
| Custom domain | DNS | ~$10/yr |

## Obsidian — The Local-First Brain

Obsidian is a markdown-based knowledge editor that stores everything as plain text files on your local machine. There is no cloud sync required, no proprietary format, no vendor dependency.

Its defining feature is bidirectional linking: every note can reference any other note, and the system tracks those references in both directions. This is what makes it relational rather than just organizational. A flat file system has folders. Obsidian has a graph — a living map of how ideas connect to each other.

> [!info] The graph view is not decorative
> It reveals structure that would otherwise be invisible: which concepts are central to your thinking, which notes are isolated, which ideas cluster together. Over time, the graph becomes a kind of external memory — one that reflects not just what you know, but how you know it.

## Markdown — The Durable Format

Markdown is plain text with lightweight syntax for formatting. A markdown file can be opened by any text editor on any operating system. It can be version-controlled, searched, indexed, and rendered by hundreds of different tools.

> *The choice of markdown is a bet on durability over convenience. What you write today will be readable in any environment — including environments that don't exist yet.*

## Quartz — The Publishing Layer

Quartz is an open-source static site generator designed specifically for Obsidian vaults. It takes the markdown files and the wikilinks and produces a full website — with a graph view, full-text search, backlinks, and popover previews — that can be deployed anywhere.

The result is a knowledge base that functions like a website: navigable, linkable, searchable, shareable. The same relational structure that makes Obsidian useful locally becomes navigable publicly.

> [!tip] You're looking at it right now
> This site was built entirely with Quartz. Every link, every graph node, every backlink panel — generated from plain markdown files.

## GitHub Pages — The Free Deployment Layer

GitHub Pages provides free static site hosting for any public GitHub repository. Combined with a Quartz build workflow using GitHub Actions, the entire publishing pipeline is free and version-controlled.

```
Write note → Commit → Push → GitHub Actions builds → Site updates
```

Every change to the knowledge base is a commit. Every commit is traceable. The entire history of the archive is preserved and recoverable.

## The Access Control Question

> [!warning] The open problem
> GitHub Pages with a public repository means everything is public — which works for a research site, but breaks the use case of an organization that needs to manage what different people can see.

The target architecture for selective access:

| Step | Action | Cost |
| --- | --- | --- |
| 1 | Buy a custom domain | ~$10/yr |
| 2 | Route traffic through Cloudflare | Free |
| 3 | Enable Cloudflare Access policies | Free (≤50 users) |
| 4 | Separate public/private Quartz builds | Free |

**Step 1 — Custom domain.** Cloudflare Access requires controlling DNS. A `.com` through Cloudflare Registrar runs about $10/year. GitHub Pages supports custom domains natively via a `CNAME` file.

**Step 2 — Route through Cloudflare.** All traffic runs through Cloudflare's network — adding CDN, DDoS protection, and the ability to attach access policies.

**Step 3 — Cloudflare Access.** A policy like "require Google login for `/private/*`" means those pages are only reachable by authenticated users you approve. Everything else stays public.

**Step 4 — Private content in Quartz.** Quartz's `ignorePatterns` already excludes a `private` folder. Private notes stay out of the public site entirely and surface only through the controlled access layer.

The result: one repository, one pipeline, two access tiers, near-zero cost.

---

*You've reached the end of the main path. The graph view reveals more, if you're looking.*
