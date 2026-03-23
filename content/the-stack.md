---
title: "The Stack"
description: "The technical architecture behind this research — and why each component was chosen."
---

# The Stack

Every architectural decision is an argument. The components chosen here each make a specific claim about what matters in a knowledge system built for durability, affordability, and institutional continuity.

## Obsidian — The Local-First Brain

Obsidian is a markdown-based knowledge editor that stores everything as plain text files on your local machine. There is no cloud sync required, no proprietary format, no vendor dependency.

Its defining feature is bidirectional linking: every note can reference any other note, and the system tracks those references in both directions. This is what makes it relational rather than just organizational. A flat file system has folders. Obsidian has a graph — a living map of how ideas connect to each other.

The graph view is not decorative. It reveals structure that would otherwise be invisible: which concepts are central to your thinking, which notes are isolated, which ideas cluster together. Over time, the graph becomes a kind of external memory — one that reflects not just what you know, but how you know it.

## Markdown — The Durable Format

Markdown is plain text with lightweight syntax for formatting. A markdown file can be opened by any text editor on any operating system. It can be version-controlled, searched, indexed, and rendered by hundreds of different tools.

The choice of markdown is a bet on durability over convenience. Rich text formats and proprietary databases offer more formatting options, but they introduce format lock-in. A markdown-based knowledge base written today will be readable in any environment — including environments that don't exist yet.

## Quartz — The Publishing Layer

Quartz is an open-source static site generator designed specifically for Obsidian vaults. It takes the markdown files and the wikilinks and produces a full website — with a graph view, full-text search, backlinks, and popover previews — that can be deployed anywhere.

The result is a knowledge base that functions like a website: navigable, linkable, searchable, shareable. The same relational structure that makes Obsidian useful locally becomes navigable publicly.

This site was built with Quartz.

## GitHub Pages — The Free Deployment Layer

GitHub Pages provides free static site hosting for any public GitHub repository. Combined with a Quartz build workflow using GitHub Actions, the entire publishing pipeline — write a note, commit it, push to the repository, site updates — is free and version-controlled.

Every change to the knowledge base is a commit. Every commit is traceable. The entire history of the archive is preserved and recoverable.

## The Access Control Question

The open question in this stack is selective access. GitHub Pages with a public repository means everything is public — which works for a research site, but breaks the use case of an organization that needs to manage what different people can see.

The target architecture for selective access looks like this:

**Step 1 — Custom domain.** Cloudflare Access requires controlling DNS, which means a custom domain. A `.com` domain through Cloudflare Registrar runs about $10/year. GitHub Pages supports custom domains natively — you add a `CNAME` file to the repository root and configure the domain in repository settings.

**Step 2 — Route through Cloudflare.** Once the domain is pointed at Cloudflare, all traffic runs through their network. This is free on Cloudflare's basic plan and adds CDN, DDoS protection, and — critically — the ability to attach access policies.

**Step 3 — Cloudflare Access.** Cloudflare Access (free tier: up to 50 users) lets you put a login wall in front of specific URL paths. A policy like "require Google login for `/private/*`" means those pages are only reachable by authenticated users you approve. Everything outside that path remains public.

**Step 4 — Private content in Quartz.** Quartz's `ignorePatterns` config already excludes a folder called `private` from the build. Reversing this — or creating a separate build target — means private notes stay out of the public site entirely and only surface through a separately managed access layer.

The result: a single knowledge base with a public-facing research site and a private layer for internal or restricted content. One repository. One publishing pipeline. Two access tiers. Zero ongoing cost beyond the domain.

This is the piece that makes the system viable for actual organizations — not just researchers publishing notes publicly. It is the next phase of this implementation.

---

*You've reached the end of the main path. The graph view reveals more, if you're looking.*
