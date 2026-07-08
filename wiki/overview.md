---
type: overview
title: "Wiki Overview"
created: 2026-04-07
updated: 2026-07-08
tags:
  - meta
  - overview
  - para
status: developing
related:
  - "[[index]]"
  - "[[hot]]"
  - "[[log]]"
  - "[[dashboard]]"
  - "[[LLM Wiki Pattern]]"
  - "[[projects/_index]]"
  - "[[areas/_index]]"
  - "[[resources/_index]]"
  - "[[archives/_index]]"
sources:
---

# Wiki Overview

Navigation: [[index]] | [[hot]] | [[log]] | [[dashboard]]

---

## Purpose

This vault is configured as a **Segundo Cerebro** (personal second brain, Vault Use Case D) built on claude-obsidian, following the [[LLM Wiki Pattern]] — a system for building persistent, compounding knowledge bases using Claude and Obsidian.

It also happens to be the claude-obsidian plugin's own source repository, so `wiki/` originally held the plugin's dogfooded development history (v1.0-v1.9.2). That content stays in place; the vault now organizes by **PARA** (Tiago Forte) going forward.

---

## Methodology: PARA (since 2026-07-08)

Organizes by actionability, not topic:

- **Projects** (`wiki/projects/`) — active work with a deadline and an outcome. New session notes triage into `projects/inbox/`.
- **Areas** (`wiki/areas/`) — ongoing responsibilities with no end date.
- **Resources** (`wiki/resources/`) — reference material, filed by topic. New ingests land in `resources/incoming/`, entities in `resources/people/`, concepts in `resources/concepts/`.
- **Archives** (`wiki/archives/`) — completed projects and sunsetted areas, filed by year.

Mode is declared in `.vault-meta/mode.json` and consumed automatically by `wiki-ingest`, `save`, and `autoresearch` (see [[../docs/methodology-modes-guide.md|methodology modes guide]]). Pre-existing pages (concepts, entities, sources, comparisons, questions from the pre-PARA era) were **not** auto-migrated — see [[resources/_index]] for details and how to triage them manually.

---

## Current Seed Content


**Concepts seeded:**
- [[LLM Wiki Pattern]] — the core architecture
- [[Hot Cache]] — session context mechanism
- [[Compounding Knowledge]] — why the pattern works

**Entities seeded:**
- [[Andrej Karpathy]] — originated the pattern

**Sources seeded:**
- [[claude-obsidian-ecosystem-research]] — 16+ projects, 13 cherry-picks identified (2026-04-08)

---

## Current State

- Sources ingested: 2
- Wiki pages: 34+ (pre-PARA content) + new PARA skeleton (projects/areas/resources/archives, empty, ready for use)
- Plugin version: v1.9.2 (public canonical)
- Methodology mode: PARA (configured 2026-07-08)
- Last activity: see [[hot]] for current state and pending items

---

## Canvases

- [[claude-obsidian-presentation]] — Full presentation: hero, overview, skills, architecture, Wiki vs RAG, visual demos (2026-04-07)
- [[AI Marketing Hub Cover Images Canvas]] — Cover image library for AI Marketing Hub brand assets

---

## Key Themes

**Knowledge compounds.** Unlike RAG, the wiki pre-compiles synthesis. Cross-references are already there. Contradictions are flagged. Every ingest enriches existing pages rather than adding isolated chunks.

**The hot cache is the force multiplier.** A ~500-word file captures recent context. New sessions start with full context at minimal token cost.

**Obsidian is the IDE, Claude is the programmer.** The graph view shows what's connected. The human curates sources and asks questions. Claude writes and maintains everything else.
