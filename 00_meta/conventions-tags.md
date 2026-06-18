---
type: meta
status: locked
---

# Tag conventions

Two layers. No more.

## Layer 1: Status (rarely on entities — frontmatter handles this)

Use status frontmatter, not status tags. Exception: `#triage` for inbox items.

## Layer 2: Cross-cutting themes

Tags describe *themes that cut across entity types*. They are not entity types (frontmatter `type` handles that) and they are not status (frontmatter `status` handles that).

### Cosmological / historical

- `#cataclysm`
- `#pre-cataclysm`
- `#celestial`
- `#cosmology`
- `#origin-of-magic`

### Thematic

- `#sacrifice`
- `#stewardship`
- `#bloodline`
- `#inheritance`
- `#endurance`
- `#change`
- `#wound`

### Magic fields (nested)

- `#field/sacred`
- `#field/warding`
- `#field/binding`
- `#field/elemental`
- `#field/alchemy`
- `#field/runecraft`
- `#field/druidry`
- `#field/necromancy`
- `#field/illusion`

### Geographic regions

Prefer wikilinks over tags for regions. Use a tag only if you want it to surface in a tag query alongside non-region cross-cutting themes.

## Anti-patterns

- ❌ `#npc`, `#faction`, `#location` — frontmatter `type` covers this
- ❌ `#wip`, `#locked` — frontmatter `status` covers this
- ❌ `#mountain`, `#sword`, `#tree` — too generic to be useful
- ❌ Per-character tags like `#elara` — wikilinks do that job

## When to add a new tag

Add a tag when:
1. You want to query across multiple entity types by theme
2. The theme is recurring (3+ notes will use it)
3. No existing tag covers it

If only one note will ever use it, it doesn't need a tag.
