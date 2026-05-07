---
type: meta
status: locked
date: 2026-05-07
---

# Migration Batch 1

This batch contains the first round of migrated content. Unzip this archive at the **root of your vault** (the `mystic-weave/` directory). Files will land in the correct folders.

## What's in this batch

### Mechanical foundation (5 files)

Placed in `20_mechanics/00_foundation/`:

- `mw_vision.md`
- `mw_design_problem.md`
- `mw_mech_development_plan.md`

Placed in `20_mechanics/decisions/`:

- `mw_mech_cosmic_foundation.md`
- `mw_mech_planet_geography.md`

All wrapped with frontmatter; original content unchanged.

### Lore samples (8 entity notes)

These are a representative sample exercising every major template type. They demonstrate the migration pattern. Once you're satisfied with the shape, the rest of the corpus follows the same approach.

| Note | Type | Source files |
| --- | --- | --- |
| `Drakenvale.md` | region (overview hub) | world.md |
| `Hollow Crown.md` | region | world.md, geography.md |
| `The Cataclysm.md` | event | history.md, world content |
| `Eryndor the Radiant.md` | dragon | npcs.md, world content |
| `Heartstone.md` | artifact | world.md, history.md |
| `Codex of Remembrance.md` | concept | world.md |
| `Solveris.md` | deity | world.md, history.md |
| `Draconic Council.md` | faction | world.md, npcs.md, groups.md |

## What's deliberately not in this batch

The remaining ~50+ entity notes from the corpus. Specifically:

- Other Council dragons: Zarkeros, Varethyn
- Other named dragons: Ardrynn, Platinum Warden (Vindrael), Lethariel Heartwood, Seraphine, Vorseth, Serevane, Syndra, Lethira, Kaerys, Tazrik, Warden of Greymantle
- Other deities: Mordrax, the Two, the Unchanged
- All other factions: Wardens, Dragon Guard, Platinum Acolytes, Hall of Scales, Arcane Conservatory, Vigil, Silver Scale, Infernal Forge Guild, Amethyst Veil, Sapphire Sentinels, Mordrax Cults, etc.
- All other regions and locations: Stronghold, Draconic Hall, Platinum Heart, Amethyst Vault, Sacred Pools, Temple of Mordrax, Rift of Discord, Feywood, Thornveil, Vaelmere, Zarkharath, Greymantle, Volcanic Highlands, Mystic Wetlands, Crystal Caverns, Shadowed Hollows, etc.
- All historical events as separate notes: War of the Fallen, The Founding, Age of Harmony, Discordant War
- All peoples: Humans, Elves, Dwarves, Orcs, Halflings, Gnomes, Vulkar, Drakari
- All concepts: Nine Magical Fields, Trial of Wings, Oath of the Fallen, etc.

These are the work for batches 2 and beyond.

## Cross-references

Notes in this batch link aggressively to entities that don't yet have notes. Obsidian will show these as **unresolved links** in the right pane and graph. That's expected — those are the worklist for the next batches.

Don't try to "fix" the unresolved links yet. They resolve as their target notes get created.

## Issues surfaced during migration

1. **Source inconsistency on Hollow Crown size.** `world.md` says ~350km. `geography.md` says ~280km. Flagged in `Hollow Crown.md` open questions. You may want to reconcile in the source files.

2. **Council command structure ambiguity.** `world.md` and `npcs.md` agree that Eryndor commands Wardens in peacetime and Zarkeros in crisis, but `world.md` says Drakari Stewards "directly enforce Council rulings" while `npcs.md` shows command lines through individual dragons. The two are compatible but the relationship between Stewards and dragon-specific command isn't fully specified in source.

3. **Foundation date on `mw_mech_*` decisions.** The decision frontmatter uses `date: 2026-04` based on the project files' April 2026 version stamp. Adjust if you have actual decision dates.

## After unzipping

Open Obsidian. Verify:

- Foundation docs render with frontmatter visible (Source view) and as styled prose (Reading view)
- Wikilinks in `Drakenvale.md` show as blue (resolved) for entities I created notes for, and as gray/unresolved for entities I didn't
- Graph view shows the eight entity notes as a small connected cluster
- Dataview queries in `_mechanics-moc.md` populate with the foundation and decisions notes

If any of those don't work, the issue is plugin config (likely Templater or Dataview), not the files themselves.

## Next batch — what to do

Tell me which entities you want prioritized in batch 2. Sensible defaults:

- The other two Council dragons (Zarkeros, Varethyn) — completes the governance picture
- Mordrax — pairs with Solveris and is referenced everywhere
- The major factions (Wardens, Dragon Guard, Platinum Acolytes) — referenced everywhere
- War of the Fallen and Discordant War — the two missing major events
- The eight peoples — they're self-contained and their notes don't depend on other notes existing

Or pick what you actually need first.
