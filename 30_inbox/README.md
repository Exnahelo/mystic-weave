---
type: meta
status: locked
---

# Inbox

Drop zone for unsorted material. Anything you want to keep but haven't placed yet goes here.

## Workflow

1. Drop the file in. Tag it `#triage`.
2. When processing: open it, decide where it goes, move it, add proper frontmatter, remove `#triage`.
3. Don't bulk-process. Touching each file one at a time is how you find the cross-references that should be wikilinks.

## Specifically for the existing project files

The current `world.md`, `history.md`, `groups.md`, `geography.md`, `npcs.md` files are large. Don't migrate them as single notes — split them into individual entity notes as you process. One NPC = one file. One faction = one file. The graph is the payoff for granularity.

## Triage queue

```dataview
LIST
FROM "30_inbox"
WHERE contains(file.tags, "#triage")
SORT file.mtime DESC
```
