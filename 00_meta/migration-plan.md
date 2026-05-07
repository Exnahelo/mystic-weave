---
type: meta
status: locked
---

# Migration plan

Order of operations for moving existing material into the vault.

## Phase 0: vault setup

- [ ] Create vault in Obsidian (point at this folder)
- [ ] Install plugins per [[plugins]]
- [ ] Configure Templater folder mappings
- [ ] Verify Dataview queries render in the MOC files

## Phase 1: drop existing files into inbox

The current project files:
- `world.md`
- `history.md`
- `groups.md`
- `geography.md`
- `npcs.md`
- `mw_vision.md`
- `mw_design_problem.md`
- `mw_mech_development_plan.md`
- `mw_mech_cosmic_foundation.md`
- `mw_mech_planet_geography.md`

Plus the "added text" you mentioned that's probably out of date.

Action: drop all of them into `30_inbox/` first. Don't try to place them upfront.

## Phase 2: place the foundation docs

These are easy. They go straight to `20_mechanics/00_foundation/`:
- `mw_vision.md` → `20_mechanics/00_foundation/mw_vision.md`
- `mw_design_problem.md` → `20_mechanics/00_foundation/mw_design_problem.md`

Add frontmatter:
```yaml
---
type: meta
status: locked
---
```

## Phase 3: archive deprecated mechanical work

The existing `mw_mech_*` files in the project may or may not still represent current thinking. Per the project instructions, design from the vision, not from prior strategic documents. So:

- `mw_mech_development_plan.md` — likely planning artifact; review and either archive to `90_archive/` or extract still-current pieces into `20_mechanics/decisions/` or `20_mechanics/analysis/`
- `mw_mech_cosmic_foundation.md` — same
- `mw_mech_planet_geography.md` — same

Default: archive. Pull forward only what's actively load-bearing.

## Phase 4: split the lore files

This is the work. One file at a time. Don't bulk-process.

### `world.md` and `history.md`

Read through. Each distinct entity (deity, dragon, era, event, concept) becomes its own note. Wikilink as you go.

Likely yields:
- Cosmology notes (The Two, Cataclysm, Origin of Magic, Unchanged)
- Era notes (Pre-Cataclysm, Cataclysm, Post-Cataclysm)
- Event notes (Discordant War, etc.)
- Dragon notes (Eryndor, Zarkeros, Varethyn, Ardrynn)
- Concept notes (Nine Magical Fields, Draconic Maturity, etc.)

### `groups.md`

Each people, faction, conclave, order = its own note.

### `geography.md`

Hollow Crown becomes a region. Each named region inside (Grasslands, Forest, Wetlands, Highlands, Caverns, Hollows, Rift) = its own note. Specific locations (Stronghold, Heartstone Hall, Platinum Heart, Amethyst Vault, Sacred Pools, Feywood Glade) = their own notes.

### `npcs.md`

One NPC per file. No exceptions.

### The "out of date" added text

Process last. Tag everything `#stale` along with `#triage`. As you process, decide: integrate (rare), archive (most), drop (some).

## Phase 5: backlink pass

After everything is split: walk through each note and ensure entity mentions are wikilinks. Obsidian's unresolved-links pane is the worklist — entries there mean either the link target should exist (create the note) or the link is wrong (fix the text).

## Phase 6: graph review

Open graph view. Look for:
- Orphans (entities with no links — usually means under-linked, occasionally means genuinely isolated)
- Hubs (entities with many links — confirm they should be central)
- Missed clusters (entities that should be linked but aren't)

This is the QA pass. Iterate as needed.

## What not to do during migration

- Don't redesign the lore. It's input. Locked.
- Don't redraft prose for style during migration. Move first, edit later if needed.
- Don't add mechanical analysis during the lore migration. Different mode of work.
- Don't create the `20_mechanics/analysis/` notes during migration. Those come from design conversations, not from re-reading old docs.
