# Obsidian Patterns

Use this file when the user wants a more usable vault, not just a correct folder tree.

## Recommended top-level additions

Add these folders only if they solve a real problem:

- `templates/` — reusable note templates
- `indexes/` — navigation notes such as home, active projects, people, or memory dashboards
- `attachments/` — images and files embedded in notes
- `archive/` — retired projects, stale plans, and frozen notes

A compact vault is better than a sprawling one.

## Good starter notes

### `indexes/home.md`

Use as the main landing page in Obsidian.

Suggested sections:

- active projects
- recent memory logs
- important directives
- key people / entities
- inbox or next actions

Example:

```markdown
# Home

## Active projects
- [[projects/project-a/README]]
- [[projects/project-b/README]]

## Recent memory
```dataview
LIST FROM "memory"
SORT file.name DESC
LIMIT 7
```

## Important notes
- [[MEMORY]]
- [[USER]]
- [[directives/weekly-review]]
```

### `indexes/people.md`

Track recurring people, collaborators, or communities.

Recommended fields:

- name
- relation
- context
- linked projects
- last interaction

### `indexes/projects.md`

Act as a project map. Link each project root note or README.

## Template suggestions

### Daily memory log template

Store in `templates/daily-memory.md`.

```markdown
# {{date:YYYY-MM-DD}}

## What happened

## Decisions

## Things to remember

## Follow-ups

## Linked notes
- [[MEMORY]]
```

### Project note template

Store in `templates/project.md`.

```markdown
# Project: {{title}}

## Goal

## Status

## Key decisions

## Open questions

## Related notes
- [[MEMORY]]
```

### Concept note template

Store in `templates/concept.md`.

```markdown
# {{title}}

## Summary

## Why it matters

## Related projects

## Related notes
```

## Linking conventions

Prefer links that reflect actual relationships:

- person ↔ project
- decision ↔ project
- concept ↔ directive
- daily log ↔ notes created that day

Do not force every note to link to everything.

## Dataview patterns

### Recent memory list

```dataview
LIST FROM "memory"
SORT file.name DESC
LIMIT 14
```

### Active projects table

```dataview
TABLE status, owner
FROM "projects"
WHERE status != "archived"
SORT file.name ASC
```

### Notes changed recently

```dataview
TABLE file.mtime
FROM ""
SORT file.mtime DESC
LIMIT 20
```

## Graph hygiene

To make Graph View useful:

- use stable note names
- create a handful of hub notes instead of many isolated leaves
- link dashboards to real content, not just other dashboards
- avoid duplicate notes for the same concept with slightly different names
