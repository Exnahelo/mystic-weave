---
type: meta
status: locked
date: 2026-05-07
---

# Migration Batch 2

Unzip at the **root of your vault** (`mystic-weave/`). Files merge into existing folders.

If macOS Archive Utility wraps the contents in a `mystic-weave-batch-2/` subfolder again, use:

```bash
cd ~/Documents/Vaults/mystic-weave/
ditto mystic-weave-batch-2/ .
rm -rf mystic-weave-batch-2/
rm mystic-weave-batch-2.zip
```

Or extract via Terminal directly:

```bash
cd ~/Documents/Vaults/mystic-weave/
unzip -o ~/Downloads/mystic-weave-batch-2.zip
rm ~/Downloads/mystic-weave-batch-2.zip
```

## What's in this batch (12 entity notes)

### Council completion (2)
- `Zarkeros the Inferno.md` — Council seat of strength, fields: Elemental, Alchemy, Runecraft
- `Varethyn of the Amethyst Gaze.md` — Council seat of wisdom, fields: Druidry, Necromancy, Illusion

### Deity (1)
- `Mordrax.md` — forbidden counterweight to Solveris

### Central NPC (1)
- `The Platinum Warden.md` — founder figure; Vindrael in personal name

### Historical arc (3 events + 1 era)
- `War of the Fallen.md` — pre-founding conflict
- `The Founding.md` — sanctuary establishment
- `Age of Harmony.md` — long peace
- `Discordant War.md` — civil rupture

### Major factions (3)
- `The Wardens.md` — internal security
- `The Dragon Guard.md` — external defense
- `The Platinum Acolytes.md` — religious order

### Central location (1)
- `Stronghold of Drakenvale.md` — central fortress

## Cross-references resolved this batch

Notes from batch 1 had unresolved links to most of these entities. After applying batch 2, the following batch 1 → batch 2 links should turn from gray to colored:

- `Drakenvale.md` → Stronghold, Wardens, Dragon Guard, Platinum Acolytes
- `Codex of Remembrance.md` → Discordant War, Oath of the Fallen (still unresolved — that's a future batch)
- `Heartstone.md` → Discordant War connection
- `Solveris.md` → Platinum Warden, Vigil (Vigil still unresolved)
- `Eryndor the Radiant.md` → Wardens, Platinum Acolytes, Discordant War
- `The Cataclysm.md` → various
- `Hollow Crown.md` → various
- `Draconic Council.md` → Wardens, Dragon Guard, Platinum Acolytes, Discordant War, Discordant War aftermath

## Cross-references still unresolved after this batch

A non-trivial portion of links across batch 1 + batch 2 will still be gray. Major missing entities:

- **Locations**: Draconic Hall, Platinum Heart, Amethyst Vault, Sacred Pools, Temple of Mordrax, Rift of Discord, Dark Hold, Heartmass, Aeries, Sacred Pools, Zarkharath, Infernal Forge, Hall of Scales, Arcane Conservatory, Feywood, Thornveil, Vaelmere, Heartwood Estate, Greymantle, Volcanic Highlands, Mystic Wetlands, Crystal Caverns, Shadowed Hollows
- **Concepts**: Oath of the Fallen, Trial of Wings, Nine Magical Fields, Drakari Stewards, Heartwood, Modern Era
- **Factions**: Mordraxian Rebels, Vigil, Mordrax Cults, Infernal Forge Guild, Silver Wing Envoys, Sapphire Sentinels, Amethyst Veil, Hall of Scales, Arcane Conservatory, Silver Scale Trading Company, Heartwarden, Greenshield, Ranger
- **NPCs**: Lethariel Heartwood, Ardrynn the Measured, Seraphine of the Still Pool, Vorseth Ashmantle, Serevane, Syndra Veilwatch, Lethira Vale, Kaerys Emberclaw, Tazrik Flameweaver, Warden of Greymantle, plus the various stable role definitions
- **Peoples**: Humans, Elves, Dwarves, Orcs, Halflings, Gnomes, Vulkar, Drakari
- **Other deities**: The Two, the Unchanged

That's batch 3 and beyond.

## Issues surfaced during this batch

1. **Era note vs event note for Age of Harmony.** I put it in `10_world/history/ages/` and used `type: era` rather than `type: event` to distinguish ages from discrete events. The conventions doc only listed `event` as a type — adding `era` is a small extension. If you'd rather collapse them into one type, tell me and I'll adjust the convention.

2. **Vindrael / Platinum Warden naming.** I used "The Platinum Warden" as the canonical filename and Vindrael as an alias. The npcs.md source had two separate entries (one as "The Platinum Warden" and one as "Vindrael, the Platinum Warden") — that's a duplicate in source, not two separate figures. I consolidated. If you want them separated, tell me.

3. **Ardrynn the Measured** is referenced (Hall of Scales overseer) but doesn't have a note in this batch. She's a substantive NPC and probably worth batch 3.

4. **The Vigil** comes up repeatedly in this batch (Solveris worship, Platinum Warden tomb, Rift monitoring) but doesn't have a note yet. High priority for batch 3.

## What to do after applying

1. Open the graph view. The connected cluster should be visibly larger and denser.
2. Spot-check one or two of the new notes — open `Discordant War.md` and verify links resolve correctly to the entities created in this batch.
3. Tell me what to prioritize for batch 3.

## Suggested batch 3 scope

- **The Vigil** (faction) — overdue
- **Lethariel Heartwood** (NPC) — central to the Discordant War story
- **Ardrynn the Measured** (NPC) — Hall of Scales
- **Mordraxian Rebels** (faction) — antagonist of the Discordant War
- **Oath of the Fallen** (concept) — heavily referenced founding agreement
- **Nine Magical Fields** (concept) — heavily referenced
- **Trial of Wings** (concept) — heavily referenced
- **Feywood** (region) — separate sovereign realm
- **The Two** + **The Unchanged** (deities/cosmology) — foundational cosmology
- **Eight Peoples** (Humans, Elves, Dwarves, Orcs, Halflings, Gnomes, Vulkar, Drakari) — referenced everywhere; mostly self-contained

That's roughly 15-17 notes. After that, batch 4 picks up the remaining locations and minor NPCs.
