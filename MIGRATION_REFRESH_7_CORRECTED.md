---
type: meta
status: locked
date: 2026-05-07
supersedes: MIGRATION_REFRESH_7
---

# Migration Refresh 7 (Corrected) — Mystic Wetlands + Inner Ramparts + Alpine Peaks

## Why this is a corrected refresh

The previous Refresh 7 bundle had two significant errors that are addressed here:

1. **Lastmark and Eryndor's Lair were placed in `inner-ramparts/`** based on geography.md's terrain-cell classification (C5 = `I` terrain). **This was wrong.** Source vault canon and user verbal canon both place these in [[Alpine Peaks]] — Lastmark is the realm's only viable mountain pass entry, sited at the alpine threshold, and Eryndor's Lair is positioned there for diplomatic acceleration leveraging Lastmark's choke point. **I shouldn't have let geography terrain-cell classification override structural canon.**

2. **Several entities in the source vault were missed entirely.** The previous bundle did not include: Valley Edge Overlook (Mystic Wetlands), Glacial Stream Crossing (Inner Ramparts), Stonemark Deep Cuts (Inner Ramparts subterranean sub-feature), Alpine Pass (Alpine Peaks), Misty Descent (Alpine Peaks), Wardline Threshold (Alpine Peaks). I should have probed the source vault more thoroughly before producing.

This corrected bundle **fully supersedes the original Refresh 7**. Apply commands include cleanup of the wrong directory structure (no-op if original was not applied).

## What this refresh delivers

**14 entity notes covering three regions** with corrected structure and full source coverage:

### Mystic Wetlands (4 notes)
- **Southwestern Mystic Wetlands.md** (region root, updated to list Valley Edge Overlook)
- **Valley Edge Overlook.md** (NEW — landmark stub at the wetland's upper transition)
- **mirefall/Mirefall.md** (unchanged from original)
- **brackenmoor/Brackenmoor.md** (unchanged from original)

### Inner Ramparts (4 notes)
- **Inner Ramparts.md** (region root, updated — removed Lastmark/Eryndor's Lair references, added Glacial Stream Crossing and Stonemark Deep Cuts)
- **Glacial Stream Crossing.md** (NEW — alpine bridge rest-point)
- **stonemark/Stonemark.md** (unchanged from original)
- **stonemark/Stonemark Deep Cuts.md** (NEW — subterranean disputed-jurisdiction sub-feature)

### Alpine Peaks (5 notes)
- **Alpine Peaks.md** (region root, fully rewritten — now includes Lastmark, Eryndor's Lair, and the wilderness chain as constituent entities)
- **Alpine Pass.md** (NEW — high mountain pass, the realm's only viable crossing)
- **Misty Descent.md** (NEW — slope below the Wardline; wetland atmosphere bleeds upslope here)
- **Wardline Threshold.md** (NEW — outer protective magic boundary)
- **lastmark/Lastmark.md** (MOVED from `inner-ramparts/lastmark/`; updated framing to reflect Alpine Peaks parent and the only-pass geography)
- **lastmark/Eryndors Lair.md** (MOVED from `inner-ramparts/lastmark/`; updated to remove Inner Ramparts references)

## Apply

```bash
cd ~/Documents/Vaults/mystic-weave/

# Clean up the wrong directory if original Refresh 7 was applied (no-op otherwise)
rm -rf "10_world/geography/hollow-crown/regions/inner-ramparts/lastmark"

# Apply the corrected bundle
unzip -o ~/Downloads/mystic-weave-refresh-7-corrected.zip
rm ~/Downloads/mystic-weave-refresh-7-corrected.zip

# Commit and push
git add -A
git commit -m "Migration: Refresh 7 (corrected) — Mystic Wetlands + Inner Ramparts + Alpine Peaks (14 notes); Lastmark+Eryndor's Lair moved to Alpine Peaks; Valley Edge Overlook, Glacial Stream Crossing, Stonemark Deep Cuts, Alpine Pass, Misty Descent, Wardline Threshold added"
git push
```

## Wikilinks now resolved

### Resolved by this refresh

- [[Southwestern Mystic Wetlands]] (with aliases `the Mystic Wetlands`, `the wetlands`, `the southwestern wetlands`)
- [[Mirefall]] (with aliases `the stilt-city`, `the wetland city`)
- [[Brackenmoor]] (with aliases `the gathering village`)
- [[Valley Edge Overlook]] (with aliases `the Overlook`, `Valley Edge`)
- [[Inner Ramparts]] (with aliases `the rampart belt`, `the escarpments`)
- [[Stonemark]] (with aliases `the quarry village`)
- [[Stonemark Deep Cuts]] (with aliases `the Deep Cuts`, `the Cuts`)
- [[Glacial Stream Crossing]] (with aliases `the Crossing`, `the Stream Crossing`)
- [[Alpine Peaks]] (with aliases `the crater rim`, `the outer mountain`)
- [[Lastmark]] (with aliases `the border fort`, `the realm's gate`, `the high fort`)
- [[Eryndors Lair]] (with aliases `the Lair`, `the Radiant's Lair`)
- [[Alpine Pass]] (with aliases `the Pass`, `the Alpine Crossing`)
- [[Misty Descent]] (with aliases `the Descent`, `the Misty Slope`)
- [[Wardline Threshold]] (with aliases `the Wardline`, `the Ward Line`, `the Threshold`)

### Still unresolved (future refreshes)

- **Ironwood Ridge** — referenced from [[Glacial Stream Crossing]] and [[Wardline Threshold]] but not found at predictable source-vault paths. Likely pending authoring or at a path I have not located.
- **[[Eryndor the Radiant]]** — Council dragon NPC; pending NPC migration
- **[[Lethira Vale]]** — recurring presence at [[Lastmark]]; pending NPC migration
- **[[Hallkeeper of Mirefall]]**, **[[Fenwarden of Brackenmoor]]** — Tier-3 generative roles, may want light NPC notes
- **[[Silver Wing Envoys]]**, **[[Silver Scale Trading Company]]** — factions pending
- **[[Heartmass]]**, **[[Solveris]]**, **[[Platinum Heart]]**, **[[Draconic Hall]]**, **[[Draconic Grasslands]]**, **[[Southern Lake]]** — pending; most resolve with [[Drakenvale City]] + [[Stronghold of Drakenvale]] migration
- **[[Drakenvale City]]**, **[[Stronghold of Drakenvale]]** — **CONFIRMED IN SOURCE VAULT** at `surface/central_draconic_grasslands/`. **Refresh 8 target.**
- **[[Crystal Caverns]]**, **[[Deephollow]]** — subterranean; pending
- **[[Dewhollow]]**, **[[Dracélune]]**, **[[Dragon Guard]]**, **[[Wardens]]**, **[[Arcane Conservatory]]**, **[[Infernal Forge]]** — pending in their respective domains

## Vault reconciliation flags

### Source vault placement of Lastmark / Eryndor's Lair confirmed

The source vault places `lastmark.md` and `eryndors_lair.md` under `surface/alpine_peaks/` (with `lastmark` as a subfolder). **This is the correct canonical placement** per the user's verbal canon: there's basically one mountain pass into the valley, it comes through Lastmark, and Eryndor's Lair sits near the threshold for the strategic reasons captured in the Alpine Peaks region root and the Lair note. The terrain-cell classification in `geography.md` (C5 = `I`) does not override the structural canon — Lastmark is **functionally Alpine Peaks** as the alpine threshold institution.

### Sparse wilderness-node files

`alpine_pass.md`, `misty_descent.md`, `wardline_threshold.md`, `glacial_stream_crossing.md`, and `valley_edge_overlook.md` are all single-paragraph atmospheric files in the source vault. **The user-vault notes for these expand modestly** — adding connection-context, function framing, and minor elaboration — **without inventing canon beyond what the source clearly implies**. These entities can be expanded substantially in a future authoring pass if storylines require them.

### Stonemark Deep Cuts source-vault placement

Source vault places `stonemark_deep_cuts.md` under `surface/inner_ramparts/` (alongside Stonemark itself), despite its canonically-subterranean nature. **The user-vault placement under `inner-ramparts/stonemark/` reflects the parent-location relationship to [[Stonemark]]**; the subterranean character is captured in tags. When the realm's subterranean migration happens (future Refresh), the [[Stonemark Deep Cuts]] node may want a sibling reference from the subterranean side, but its primary residence stays here as a [[Stonemark]] sub-feature.

### Ironwood Ridge unresolved

Multiple entities (Glacial Stream Crossing, Wardline Threshold) connect to **Ironwood Ridge**, but I could not locate this entity in the source vault at predictable paths (`surface/alpine_peaks/`, `surface/inner_ramparts/`). It is either at a path I have not found, or pending authoring. **Forward reference flagged.**

### Drakenvale City + Stronghold confirmed in source vault

Located at `prompts/world_vault/hollow_crown/surface/central_draconic_grasslands/`:
- `drakenvale_city/drakenvale_city.md` — rich source content
- `stronghold_of_drakenvale/stronghold_of_drakenvale.md` — rich source content

**Plus the Stronghold's sub-locations** (Draconic Hall, Platinum Heart, Amethyst Vault, Arcane Conservatory, Aeries, Administrative Quarter, Draconic Forge, Sacred Pools, Varethyn's Lair) each have their own canonical files. **This is the natural Refresh 8 target** — substantial scope, resolves the most accumulated cross-references.

I missed these in my earlier path probes. **My probing was insufficient; the user pointed it out correctly.**

## After applying

In Reading view, open key files to confirm:

- [[Lastmark]] and [[Eryndors Lair|Eryndor's Lair]] now resolve at their corrected paths under `alpine-peaks/lastmark/`
- [[Inner Ramparts]] no longer references Lastmark or Eryndor's Lair as constituent entities
- The wilderness chain ([[Alpine Pass]] → [[Glacial Stream Crossing]] → [[Wardline Threshold]] → [[Misty Descent]] → [[Valley Edge Overlook]]) cross-references resolve cleanly across regions
- [[Stonemark]]'s [[Stonemark Deep Cuts|Deep Cuts]] sub-feature reference resolves

## Refresh 8 recommendation

**Drakenvale City + Stronghold (and Stronghold sub-locations)**, sourced from the central_draconic_grasslands path I missed. This will be a substantial bundle — likely 10+ entities — but resolves the largest single cluster of accumulated cross-references in the realm.
