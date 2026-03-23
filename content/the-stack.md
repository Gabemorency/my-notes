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

The open question in this stack is selective access. GitHub Pages with a public repository means everything is public. There are several approaches to adding access control — Cloudflare Access, private repository settings, the Quartz private pages plugin — each with different tradeoffs between simplicity, cost, and security.

This remains an active area of exploration in the research.

---

*You've reached the end of the main path. The graph view reveals more, if you're looking.*
