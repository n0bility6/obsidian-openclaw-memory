# Retrieval and Semantic Search

Use this file when the user asks about QMD, embeddings, semantic lookup, MCP querying, or search-aware workspace design.

## Goal

Help the agent find the right note without stuffing the whole vault into context.

## Search-friendly note design

- Use specific titles with real nouns
- Keep each note focused on one concept, project, or entity
- Avoid giant mixed-topic notes when the content should be separable
- Include natural-language summaries near the top of important notes
- Prefer explicit names over cryptic abbreviations

## QMD-style workflow

Typical flow:

1. Add the workspace as a collection
2. Build embeddings or index content
3. Query semantically when looking for past context
4. Re-run indexing after major additions or reorganizations

Illustrative commands from the original setup:

```bash
qmd collection add ~/clawd --name clawd
qmd embed
```

If the environment differs, adapt paths and commands instead of assuming this exact layout.

## Operational advice

- Re-index after renaming many files
- Re-index after large imports or migrations
- Keep generated or junk files out of the index if possible
- Treat retrieval as a pointer system, not a truth system

## Retrieval vs memory

Use retrieval for:

- locating relevant notes
- finding older discussions
- surfacing project context on demand

Use curated memory for:

- things the agent should remember regularly
- persistent preferences
- durable operating context

Best results come from using both.
