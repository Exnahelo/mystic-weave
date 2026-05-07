---
type: meta
status: locked
date: 2026-05-07
---

# Migration Refresh 2 — Stronghold sub-locations

## What's in this refresh

### New sub-location notes (9)

All 9 sub-locations of the [[Stronghold of Drakenvale]] now exist as their own notes, nested under `10_world/geography/hollow-crown/locations/stronghold-of-drakenvale/`.

- **`Draconic Hall.md`** — Council chamber. Mirrored mosaic of [[Solveris]] and [[Mordrax]], wing-shaped wall ledges, sound that refuses to amplify anger, [[Heartstone]] at the center weighing in silently as a fourth Council voice. Drawn from vault.
- **`Platinum Heart.md`** — High sanctum at the Stronghold's summit. Open platform, twelve standing stones bearing facets of the [[Codex of Remembrance]], the eternal Platinum Flame. The two recorded historical responses of the Flame are preserved (Vindrael's death, Codex amendment after [[Discordant War]]). Drawn from vault.
- **`Amethyst Vault.md`** — [[Varethyn of the Amethyst Gaze|Varethyn]]'s public seat for mediation and clarification. Four cardinal pools, enchanted mirrors, hidden under-Vault passage to [[Varethyn's Lair]]. Drawn from vault.
- **`Sacred Pools.md`** — Descending water terrace from the [[Platinum Heart]] to the [[Southern Lake]]. Healing, reflective, sanctifying, memorial properties. Listening-Acolyte presence at the lowest terrace. Drawn from vault.
- **`Aeries.md`** — Three platforms plus alcoves for Council and resident dragons. Wards filter weather and lightning; wind passes through. Drawn from vault.
- **`Arcane Conservatory.md`** — Five-tower elite magical institution: Reading, Practicum, Theory, Convergence, Restricted Spires. Distinct from the [[Hall of Scales]] (broad education vs. refined practice). Arch-Scholar runs daily ops; Varethyn oversees. Drawn from vault.
- **`Administrative Quarter.md`** — Civic core. Petition hall, Records Halls (open / restricted / Council-sealed), Treasury, Correspondence Wing. Petition-vetting by stewards before Council audience. Drawn from vault.
- **`Draconic Forge.md`** — Sacred subterranean forge fueled by dragon breath. Distinct from the industrial [[Infernal Forge]] at [[Zarkharath]]. Different dragons' breath produces different qualities. Drawn from vault.
- **`Varethyn's Lair.md`** — **Stub-quality.** No vault file exists yet. The Lair is a real and canonical location (in the [[Crystal Caverns]] underlayer, connected to the [[Amethyst Vault]] via hidden passage), but most detail has not been authored. Status `wip`. Develop when needed.

### Refreshed artifact note

- **`Heartstone.md`** — refreshed from [[Draconic Hall]] vault canon. Now includes: discovery during Stronghold carving from the [[Heartmass]], infusion by the three founding Council dragons embodying all nine magical fields, the "weighs in silently" Council-member function, the not-removable status, the deadlock-consultation function. Cross-links to [[Draconic Hall]] (location) and to founding dragons.

### Frontmatter cleanup (2 files refreshed)

Per the descriptive-not-mechanical principle, `threat_level` is mechanical and should not appear in entity notes. Removed from:

- **`Feywood.md`** — removed `threat_level: 3` from frontmatter. Body content unchanged.
- **`Heartwood.md`** — removed `threat_level: 1` from frontmatter. Body content unchanged. `contested: true` retained (it's a status descriptor, not a mechanic).

Going forward: no new notes will carry `threat_level`. If `discovered` shows up in vault frontmatter, I'll drop that too.

## Apply

```bash
cd ~/Documents/Vaults/mystic-weave/
unzip -o ~/Downloads/mystic-weave-refresh-2.zip
rm ~/Downloads/mystic-weave-refresh-2.zip
```

The `-o` flag overwrites `Heartstone.md`, `Feywood.md`, and `Heartwood.md`. Creates new `stronghold-of-drakenvale/` subfolder under `locations/` with all 9 sub-location notes inside.

## Folder structure additions

```
10_world/geography/hollow-crown/locations/
  Drakenvale City.md
  Stronghold of Drakenvale.md
  stronghold-of-drakenvale/        ← NEW subfolder
    Draconic Hall.md
    Platinum Heart.md
    Amethyst Vault.md
    Sacred Pools.md
    Aeries.md
    Arcane Conservatory.md
    Administrative Quarter.md
    Draconic Forge.md
    Varethyn's Lair.md
```

This nests the Stronghold sub-locations under their parent location's folder, mirroring how [[Heartwood]] is nested under `regions/feywood/`. The two-letter rule of thumb: if a parent location has many sub-locations, give it a folder.

## Wikilinks now resolved

These previously-unresolved wikilinks across earlier batches now point to real notes:

- `[[Draconic Hall]]`, `[[Platinum Heart]]`, `[[Amethyst Vault]]`, `[[Sacred Pools]]`, `[[Aeries]]`, `[[Arcane Conservatory]]`, `[[Administrative Quarter]]`, `[[Draconic Forge]]`, `[[Varethyn's Lair]]`

## Wikilinks introduced but still unresolved

These notes reference targets that don't yet exist:

- **Geography:** [[Southern Lake]], [[Alpine Peaks]], [[Crystal Caverns]], [[Shadowed Hollows]], [[Draconic Grasslands]], [[Hall of Scales]], [[Infernal Forge]], [[Zarkharath]]
- **Institutions:** [[Silver Wing Envoys]], [[Sapphire Sentinels]], [[Vigil]] (already exists?), [[Silver Scale Trading Company]], [[Draconic Conclave]]
- **Doctrines/historical:** [[Vindrael]] (links to existing [[The Platinum Warden]] note — alias?)

I'll handle [[Vindrael]] vs. [[The Platinum Warden]] as a small fix if needed — possibly add `Vindrael` to the Platinum Warden note's aliases.

## What's still ahead

In rough order of canonical importance:

- **Refresh 3:** Feywood interior — [[Silent Grove]], [[Thornveil]], [[Vaelmere]], [[Heartwood Estate]], [[House Heartwood]], [[Heartwarden]] order, [[Greenshield]] order
- **Refresh 4:** Wounded quadrant — [[Temple of Mordrax]], [[Rift of Discord]], [[Dark Hold]], [[Shadowed Hollows]]
- **Refresh 5:** Major regions — [[Volcanic Highlands]], [[Mystic Wetlands]], [[Crystal Caverns]], [[Zarkharath]], [[Infernal Forge]], [[Hall of Scales]] settlement, [[Hall of Scales]] institution
- **Refresh 6:** Faction refreshes from vault `groups/` directory (Council, Wardens, Dragon Guard, Platinum Acolytes, Vigil, Mordraxian Rebels)
- **Refresh 7:** NPC refreshes from vault — anchor NPCs at minimum ([[Kaerys Emberclaw]], [[Lethira Vale]], [[Tazrik Flameweaver]] for [[Drakenvale City]]; possibly Council dragons, Lethariel, Ardrynn, Vindrael)
- **Possible later refreshes** for events, deities, peoples — depending on what vault contains

Each is its own checkpoint.

## After applying

Open `Draconic Hall.md` and `Heartstone.md` in Reading view. The Heartstone canon is the most consequential addition in this pass — it's the structural reason the Council has the character it does, and it's now properly captured. Verify the cross-link between the two reads cleanly.

If anything looks off, surface it before Refresh 3 starts.
