---
type: meta
status: locked
date: 2026-05-07
---

# Migration Refresh 7 — Mystic Wetlands + Inner Ramparts + Alpine Peaks

## What this refresh delivers

Eight entity notes covering three regions of the [[Hollow Crown]]: the southwestern wetlands cluster, the Inner Ramparts (with [[Lastmark]] and [[Stonemark]]), and the outer Alpine Peaks. **This is a three-region refresh** — larger in scope than recent bundles but each region's content base is small (one to three rich files plus stubs), so the bundle still ships clean.

### New entity notes

In `10_world/geography/hollow-crown/regions/southwestern-mystic-wetlands/`:

- **Southwestern Mystic Wetlands.md** — `type: location`. Region root. Drainage terminus of the basin's hydrology. Civic anchors: Hallkeeper of Mirefall, Fenwarden of Brackenmoor. Synthesized — vault root file is sparse stub.
- **mirefall/Mirefall.md** — `type: location`. Stilt-city, raised platforms, the Hall (collective dining + civic anchor) and the Second Hall (craft). Quiet sanctuary character.
- **brackenmoor/Brackenmoor.md** — `type: location`. Wild-harvest gathering village at the transition biome. Three functional zones (forest margin, fen, deeper pools). Family-adjacent cultural connection to Mirefall.

In `inner-ramparts/`:

- **Inner Ramparts.md** — `type: location`. Region root. Broken escarpment belt between Alpine Peaks and basin. Two settlements ([[Lastmark]], [[Stonemark]]). Synthesized — vault root is sparse stub.
- **stonemark/Stonemark.md** — `type: location`. Quarry village. Three stone types (pale [[Heartmass]]-related, working granite, specialty carving). Deep cuts adjacent to upper [[Crystal Caverns]]. Lastmark-cultural-connection.
- **lastmark/Lastmark.md** — `type: location`. Border fort. Sole sanctioned realm entry. Wardstones, Dragon Guard garrison, Ward-Keeper corps, supply elevator. [[Lethira Vale]] recurring presence.
- **lastmark/Eryndors Lair.md** — `type: location`. [[Eryndor the Radiant]]'s residence. Reception Hall, Shrine of [[Solveris]], audience chambers, disorienting-wagon protocol. Strategic placement near [[Lastmark]] for diplomatic acceleration.

In `alpine-peaks/`:

- **Alpine Peaks.md** — `type: location`. Region root. Outer crater rim wilderness beyond [[Lastmark]]. Hidden entry points, glacial crystals, no settlements. Synthesized — vault root is sparse stub.

## Apply

```bash
cd ~/Documents/Vaults/mystic-weave/
unzip -o ~/Downloads/mystic-weave-refresh-7.zip
rm ~/Downloads/mystic-weave-refresh-7.zip
git add -A
git commit -m "Migration: Refresh 7 — Mystic Wetlands + Inner Ramparts + Alpine Peaks (8 notes covering three regions, including Lastmark, Stonemark, Eryndor's Lair)"
git push
```

## Wikilinks introduced

### Now resolved by this refresh

- [[Southwestern Mystic Wetlands]] (with aliases `the Mystic Wetlands`, `the wetlands`, `the southwestern wetlands`)
- [[Mirefall]] (with aliases `the stilt-city`, `the wetland city`)
- [[Brackenmoor]] (with aliases `the gathering village`)
- [[Inner Ramparts]] (with aliases `the rampart belt`, `the escarpments`)
- [[Stonemark]] (with aliases `the quarry village`)
- [[Lastmark]] (with aliases `the border fort`, `the realm's gate`, `the high fort`)
- [[Eryndors Lair]] (with aliases `the Lair`, `the Radiant's Lair`)
- [[Alpine Peaks]] (with aliases `the crater rim`, `the outer mountain`, `the alpine wilderness`)

### Introduced but unresolved (future refreshes)

- **[[Eryndor the Radiant]]** — Council dragon resident at [[Eryndors Lair]]; major NPC pending
- **[[Lethira Vale]]** — administrative/transport coordinator; recurring presence at [[Lastmark]]; major NPC pending
- **[[Hallkeeper of Mirefall]]**, **[[Fenwarden of Brackenmoor]]** — Tier-3 generative roles, may want light NPC notes
- **[[Silver Wing Envoys]]** — diplomatic order operating from [[Eryndors Lair]]; faction pending
- **[[Silver Scale Trading Company]]** — referenced as SSTC in Lastmark context; faction pending
- **[[Heartmass]]** — central geological feature; concept entity pending in Drakenvale City migration
- **[[Solveris]]** — deity; pending
- **[[Platinum Heart]]** — high sanctum at the [[Stronghold of Drakenvale|Stronghold]]; pending
- **[[Draconic Hall]]** — at the [[Stronghold of Drakenvale|Stronghold]]; pending
- **[[Draconic Grasslands]]** — central ring around [[Drakenvale City]]; pending
- **[[Southern Lake]]** — south of the [[Stronghold of Drakenvale|Stronghold]]; pending
- **[[Drakenvale City]]**, **[[Stronghold of Drakenvale]]** — capital; pending (likely needs hand-crafting from project canon — see vault reconciliation flag below)
- **[[Crystal Caverns]]**, **[[Deephollow]]** — subterranean; pending
- **[[Dewhollow]]**, **[[Dracélune]]**, **[[Dragon Guard]]**, **[[Wardens]]**, **[[Arcane Conservatory]]**, **[[Infernal Forge]]** — pending in their respective domains

## Vault reconciliation flags

### Lastmark / Stonemark canonical placement

**Source vault places `lastmark.md` and `eryndors_lair.md` under `surface/alpine_peaks/`**. Per geography canon (`geography.md`), Lastmark is at cell C5 and Stonemark at D5, both in terrain `I` (Inner Ramparts). The user-vault structure in this refresh reflects geography canon: both settlements (and the Lair) live under `inner-ramparts/`. **Source vault reconciliation note:** the source vault's organizational placement may want to be revisited to align with geography canon, or the divergence may be accepted as a vault-side organizational choice. **No content conflict** — the surface text describes Lastmark as built into the rampart escarpment, consistent with Inner Ramparts placement.

The `surface/alpine_peaks/alpine_peaks.md` source file describes the Alpine Peaks region as **specifically the outer wilderness beyond Lastmark** — distinct from the rampart belt that holds Lastmark itself. This refresh's Alpine Peaks region root reflects that scoping (region = outer crater rim wilderness, not the full alpine zone).

### Lastmark's Eryndor's Lair reference

The vault file for Eryndor's Lair includes a note that prior canon placed the Lair with one-way discovery-gated links to `sacred-pools` and `platinum-heart`. **Those links are deprecated.** This refresh's Lair note reflects the current canonical relocation to the Lastmark-adjacent placement. Future refreshes touching Sacred Pools or Platinum Heart should not introduce reverse-links to the Lair.

### Drakenvale City + Stronghold not in source vault

Tried multiple paths under `surface/` for Drakenvale City and the Stronghold of Drakenvale. **No source files found.** The capital and Stronghold are referenced from nearly every other entity but **do not have authored vault entries at this time**. Three options for the next refresh:

1. **Hand-craft from project canon** — `geography.md`, `world.md`, `history.md` provide substantial content for Drakenvale City, the Stronghold, and the Stronghold's interior features (Draconic Hall, Platinum Heart, Administrative Quarter, Arcane Conservatory, Amethyst Vault, Aeries). I can build the entity notes from these sources, flagging that they are derived from project canon rather than world vault.
2. **Defer** — wait until you author or surface the canonical vault files for these locations.
3. **Pivot to subterranean or factions next** — leave Drakenvale City/Stronghold for a later pass.

### Source vault: three sparse region roots

`southwestern_mystic_wetlands.md`, `inner_ramparts.md`, and `alpine_peaks.md` are all sparse stubs. This refresh's region-root notes are **synthesized from constituent files plus realm canon** (`world.md`, `geography.md`, `history.md`, project lore). All three could be expanded in the source vault during a future authoring pass.

## Cross-references resolved

This refresh resolves wikilinks introduced by prior refreshes:

- [[Mirefall]] from [[Greymantle]] (Refresh 5) and from western trade context
- [[Brackenmoor]] from forest-region context (referenced from Refresh 4 [[Heartwood Approach]] and Feywood-edge content if any)
- [[Lastmark]] from [[Stonemark]] context and from any external-realm references
- [[Stonemark]] from the [[Infernal Forge|Forge]]'s feedstock network (Refresh 6)
- [[Eryndors Lair]] from [[Eryndor the Radiant]] (anchor location — pending NPC note will reference)
- [[Inner Ramparts]] from [[Northeastern Volcanic Highlands]] (Refresh 6) and from [[Southern Dark Quadrant]] (Refresh 5) boundary references
- [[Alpine Peaks]] from [[Lastmark]]'s outer-threshold context

## After applying

In Reading view, open key files to confirm cross-region cross-references resolve:

- Open [[Greymantle]]: the [[Mirefall]] connection should now resolve cleanly
- Open [[Northeastern Volcanic Highlands]]'s Cinderpit: the [[Stonemark]] mining-network reference should resolve
- Open [[Lastmark]]: the cross-references to [[Stronghold of Drakenvale]], [[Drakenvale City]], [[Lethira Vale]], [[Silver Scale Trading Company]] remain forward references (pending future refreshes)

Then ready for **Refresh 8** when you give the go. Logical next options:

- **Drakenvale City + Stronghold** — derive from project canon (`geography.md`, `world.md`, `history.md`); resolves the most accumulated cross-references. Recommended.
- **Subterranean** — Crystal Caverns network, Deephollow, Temple of Mordrax (when source located), Stonemark Deep Cuts. Resolves the second-most-cited cross-references.
- **Western forest cluster** — Dracélune, Silvercut, Dewhollow, Scalemere, Crystalhaven, Hall of Scales, Ashfield, plus the SSTC Western Trade Road. Substantial scope.
- **Realm-side factions** — Vigil/Platinum Accord, Wardens, Sapphire Sentinels, Dragon Guard, Council of Elders, Silver Wing Envoys, SSTC, Infernal Forge Guild. Clears the institutional layer comprehensively.

My recommendation: **Drakenvale City + Stronghold next, derived from project canon**, with flag in manifest that the migration is project-derived rather than vault-derived. This unblocks the largest number of accumulated cross-references and gets the realm's central anchor into the vault structure. After that, factions clear the institutional layer; then remaining geography fills in.
