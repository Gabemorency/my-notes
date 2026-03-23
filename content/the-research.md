---
title: "The Research"
description: "A formal framing of the problem, the question, and the approach."
---

# The Research

## The Problem Statement

Small businesses, emerging organizations, and new institutions consistently struggle with fragmented, unsecured, and decentralized knowledge. Their information is distributed across tools like Google Drive, email, Slack, and Notion — platforms optimized for storage, communication, or task coordination, but not for structured knowledge retrieval or long-term institutional continuity.

Enterprise-grade knowledge management solutions exist but carry costs and complexity that most resource-constrained organizations cannot absorb. As a result, these organizations face recurring knowledge loss at leadership transitions, compounding documentation gaps, and retrieval systems that degrade in usefulness over time rather than improving.

> [!note] The pattern
> Most knowledge loss in small organizations is not caused by negligence. It is caused by the absence of infrastructure designed to prevent it. The people were there. The information existed. The system just wasn't built to hold it.

## The Research Question

> [!quote]
> Can a markdown-based, local-first knowledge architecture built on open-source tooling provide an affordable, relational, and selectively publishable knowledge infrastructure for small organizations and individuals — one that supports long-term institutional memory, structured retrieval, and version-controlled continuity?

## The Approach

This research is both conceptual and practical. The conceptual layer examines the structural gap between how organizations currently manage knowledge and what a well-designed knowledge infrastructure would require. The practical layer involves the design, implementation, and evaluation of an actual system.

The system under development uses:

| Component | Role |
| --- | --- |
| **Obsidian** | Local-first knowledge creation and relational linking |
| **Markdown** | Durable, format-agnostic file standard |
| **Quartz** | Static site publishing layer |
| **GitHub Pages** | Version-controlled, free deployment pipeline |
| **Cloudflare Access** | Selective access control and private page management |
| **AI workflows** | Synthesis, pattern recognition, and structured retrieval |

The research treats this stack not as a collection of tools but as a coherent architecture — one designed to address the specific failure modes of existing approaches.

## What Success Looks Like

A successful outcome of this research would be a system that:

1. Allows an individual or small organization to build a structured, relational knowledge base from scratch
2. Provides meaningful version control and traceability for all knowledge changes
3. Enables selective publication — some notes public, some private, some restricted to specific audiences
4. Requires no ongoing financial investment beyond a domain name
5. Is durable enough to remain useful and accessible over a multi-year time horizon
6. Can be extended with AI-assisted workflows as those capabilities mature

> [!tip] This site is the proof of concept
> The site you are reading was built using this exact stack. Every page is a markdown file. Every change is a git commit. The graph view exposes the relational structure. The hidden pages test the navigational layer. The system works — the question is how far it scales.

→ [[the-stack|The stack]]
