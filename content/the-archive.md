---
title: "What Should Exist"
description: "The shape of a knowledge infrastructure built for continuity, not just storage."
---

# What Should Exist

The alternative to fragmented knowledge is not more storage. It is structure.

The distinction sounds simple. In practice, it requires rethinking what a knowledge system is actually for — and that rethinking turns out to be harder than adopting a new tool.

> *The goal is not a place to put things. The goal is a system that understands what it holds.*

## The Properties That Matter

A knowledge infrastructure worth building has a specific set of properties. Not all of them are intuitive.

| Property | What it means | Why it matters |
| --- | --- | --- |
| **Local-first** | Knowledge lives on your machine, not in a vendor's cloud | Survives pricing changes, shutdowns, and platform lock-in |
| **Relational** | Notes link to each other bidirectionally | Context is preserved alongside content |
| **Durable** | Plain text format, no proprietary encoding | Readable in twenty years, on any device, with any tool |
| **Selectively publishable** | Some content public, some private, some restricted | Useful for organizations, not just personal publishing |
| **Version-controlled** | Every change is tracked and reversible | Institutional memory survives even when files change |

> [!tip] Why plain text matters more than it seems
> A knowledge base written in markdown today will be readable by any text editor that exists in the future. A knowledge base written inside a proprietary platform will be readable only as long as that platform chooses to keep it alive. The format is the infrastructure.

## Local-First Is Not the Same as Offline

> [!info] A common misunderstanding
> "Local-first" does not mean the system can't be shared or published. It means ownership stays with the creator. The knowledge lives in files you control — and from those files, you can publish anywhere, sync anywhere, and collaborate with anyone.

This is the fundamental advantage over cloud-locked platforms: portability. You can move the system without moving your data. You can change the publishing layer without rebuilding the archive.

## What This Looks Like in Practice

The architecture that meets these requirements is not a single tool. It is a stack — a set of components that each handle one layer of the problem well, and compose cleanly.

```
Local files (Markdown)
    ↓  authored in
Obsidian (knowledge graph)
    ↓  published via
Quartz (static site generator)
    ↓  deployed to
GitHub Pages (free hosting)
    ↓  optionally secured by
Cloudflare Access (access control)
```

The research this site documents is exploring whether this specific combination of components can form a coherent, affordable, and deployable system for the organizations that need it most.

The [continuity](continuity) question sits at the center of this exploration.

→ [[in-practice|In practice]]
