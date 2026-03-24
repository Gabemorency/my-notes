---
title: "On Continuity"
description: "What happens to an organization's knowledge when people leave — and what it would take to build something that survives."
---

# On Continuity

The real test of a knowledge system isn't whether it works while everyone is still there.

It's what survives a transition.

---

## The Leadership Transition Problem

Leadership changes are the most visible version of this, but not the only one. Any time a person leaves a team — or moves to a different project, or shifts focus, or simply gets busy — they take a piece of the organization's knowledge with them.

In most organizations, there is no mechanism for capturing what they knew that wasn't in a document. The tacit knowledge. The reasoning behind decisions that seemed obvious at the time and got written down as conclusions rather than arguments. The relationships between things that only existed in someone's mental model.

This is not a failure of the people. It's a failure of the infrastructure. If the infrastructure doesn't have a way to represent that kind of knowledge, it can't preserve it.

---

## What Continuity Requires

Continuity isn't achieved by writing things down. It's achieved by writing things down *in a structure that preserves meaning over time.*

That structure has a few requirements:

**Relationships must be explicit.** A document that says "we decided X" is less durable than a document that links to the context, the alternatives considered, and the reasoning. When the person who made the decision is gone, the links are what remain.

**Format must be stable.** A decision captured in a tool that no longer exists is, for practical purposes, lost. The format should be readable without the tool.

**History must be preserved.** Not just the current state of the archive, but how it got there. Version control is not a developer luxury — it's a memory mechanism.

**Access must be managed.** Continuity requires that the right people can get to the right information. A system that preserves everything but makes nothing findable has failed at the core task.

---

## The Prototype

What you are reading right now is built on a system designed with these requirements in mind. The markdown files are readable without any software. The git history preserves every change. The Quartz graph makes relationships navigable. The publishing layer makes it shareable.

It is not complete. It is not perfect. But it demonstrates that the architecture is possible — that something [remains](what-remains) when you build with continuity as a first-order concern.

---

*You followed a link most people missed. There is one page deeper.*

→ [[what-remains|What remains]]
