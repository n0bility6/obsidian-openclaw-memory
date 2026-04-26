---
name: obsidian-openclaw-memory
description: Build, organize, or improve an Obsidian-based memory workspace for OpenClaw. Use when setting up a vault, designing file structure for persistent AI memory, adding templates or dashboards, improving wiki-link graph structure, configuring Dataview/Templater workflows, or documenting how OpenClaw memory files, heartbeats, and semantic search should work together.
---

# Obsidian + OpenClaw Memory Workspace

Treat this skill as a workspace-design and memory-operations guide. The goal is to make the workspace useful both to the human in Obsidian and to OpenClaw at runtime.

## Core model

Assume the system has three distinct layers:

1. **Runtime memory**: files OpenClaw reads directly (`AGENTS.md`, `SOUL.md`, `USER.md`, recent `memory/YYYY-MM-DD.md`, and sometimes `MEMORY.md` depending on session type)
2. **Human knowledge layer**: notes, dashboards, concepts, journals, and project pages that are mainly browsed in Obsidian
3. **Retrieval layer**: semantic search or indexing tools that help the agent find relevant context without loading everything

Design changes so these layers support each other instead of duplicating each other.

## Do first

1. Inspect the current workspace layout
2. Identify whether the user wants one of these outcomes:
   - initial setup
   - restructuring an existing vault
   - better templates / dashboards
   - better long-term memory hygiene
   - semantic-search integration
   - graph-friendly linking and taxonomy
3. Keep the runtime-critical files lightweight and high signal
4. Prefer additive, reversible changes over disruptive reorganization

## Workspace design rules

- Keep root-level operational files concise because they are likely to be injected or read often
- Separate **raw logs** from **curated memory**
- Use folders with clear roles rather than one giant note pile
- Prefer note links and shared vocabulary over excessive tags
- Avoid storing secrets in files that may be widely read by agents
- Do not turn `MEMORY.md` into a transcript dump
- Keep heartbeat instructions short because they are checked repeatedly

## Recommended structure

Read `references/file-structure.md` when designing or explaining the vault layout.

Use this baseline split:

- `MEMORY.md`: curated long-term memory
- `memory/YYYY-MM-DD.md`: daily raw logs
- `second-brain/`: human-oriented knowledge base
- `directives/`: repeatable workflows and SOPs
- `projects/`: project-specific working material
- `templates/`: note templates for recurring note types

If the user wants a more complete vault, also read `references/obsidian-patterns.md`.

## Obsidian setup workflow

When helping with Obsidian:

1. Point the vault at the OpenClaw workspace folder
2. Enable core navigation features the user will actually use
3. Add lightweight templates before adding fancy dashboards
4. Create a small set of index notes instead of many orphaned notes
5. Add Dataview queries only where they solve a real navigation problem

For practical templates, dashboards, and note conventions, read `references/obsidian-patterns.md`.

## Memory hygiene workflow

When improving memory quality:

1. Keep `memory/YYYY-MM-DD.md` loose and capture-oriented
2. Distill durable facts, decisions, preferences, and lessons into `MEMORY.md`
3. Move project-specific detail into project notes instead of bloating `MEMORY.md`
4. Archive stale or superseded operational notes instead of endlessly appending
5. Ensure important notes link back to related concepts, people, or projects

For decision rules on what belongs where, read `references/memory-ops.md`.

## Semantic search and retrieval

If the user wants semantic lookup, QMD, MCP tools, or search-friendly note structure, read `references/retrieval.md`.

General rules:

- Prefer a few high-value notes over many tiny fragmented notes
- Use descriptive titles that will match natural-language search
- Keep one concept per note when possible
- Re-embed or re-index after major content changes
- Do not assume semantic search replaces curated memory

## Deliverables to produce

Depending on the request, create some combination of:

- improved folder structure
- note templates
- dashboard/index notes
- linking conventions
- memory-maintenance instructions
- retrieval setup notes
- migration plan from the current layout

## Output style

When explaining the setup to the user:

- explain the purpose of each major folder in plain language
- distinguish what the human uses in Obsidian from what OpenClaw reads operationally
- call out tradeoffs if suggesting a reorganization
- prefer concrete examples over abstract theory
