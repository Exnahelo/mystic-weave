---
type: meta
status: locked
date: 2026-05-07
---

# Migration Refresh 3 — Feywood top-level

## What's in this refresh

### New entity notes (6)

All under `10_world/geography/hollow-crown/regions/feywood/`:

- **`Feywood Border.md`** — type `route-node`. The realm-side threshold. Stone waymarkers, Hall of Guides station with Border Steward, periodic mercantile exchange windows with Elven Trade Envoy. "Awaiting" character distinct from Hollows' "watching" or Rift's "pulsing." Drawn from vault.
- **`Heartwater Basin.md`** — type `region-zone`. The Feywood's freshwater system. Second decline-register zone for [[Heartwood]] stress. Specific signal species (Silverstream trout, Heartpond frog chorus, Cranemoor heron) and ecology. Drawn from vault.
- **`Heartwood Estate.md`** — type `location`. [[House Heartwood]]'s wild-heritage seat in the Outer Old-Growth Wild. 40-70 residents. [[Lethariel Heartwood]] in residence; Heartwood bow kept here when not in active Captaincy. Wild-upbringing tradition + Proving at 90. Anti-monumental. Drawn from vault.
- **`Silent Grove.md`** — type `sacred-site`, status `locked`. The elven origin point of civilization in this world. Founding witnesses (first trees from the elven sacrifice still standing). [[Heartwarden]] 7-year training cycle. [[Reading Glade]] oral tradition. ~50-80 elves. Drawn from vault.
- **`Thornveil.md`** — type `settlement`. The elven capital, several thousand residents, grown around the [[Heartwood]]. Five district-level zones (each its own future note). [[Council of Elders]] meeting structure, [[Greenshield]] HQ, coming-of-age trial tradition. Drawn from vault.
- **`Vaelmere.md`** — type `settlement`. Outer settlement and trade waypoint. ~600 residents. Higher (5-10%) non-elf integration than [[Thornveil]]. Diplomatic buffer for non-Council-level realm contact. Trade Envoys for [[Feywood Border]] exchanges drawn from here. Drawn from vault.

### Conventions update

- **`conventions-frontmatter.md`** — added two types from vault canon:
  - `region-zone` — sub-region within a larger region; ecologically/functionally distinct distributed system rather than point location (Heartwater Basin, Outer Old-Growth Wild)
  - `route-node` — threshold zones, approach corridors, sanctioned crossings; not a settlement, not a region, but a defined zone whose function is passage or boundary (Feywood Border, the Approach files)

## Apply

```bash
cd ~/Documents/Vaults/mystic-weave/
unzip -o ~/Downloads/mystic-weave-refresh-3.zip
rm ~/Downloads/mystic-weave-refresh-3.zip
```

Overwrites: `conventions-frontmatter.md`. Creates 6 new files in `regions/feywood/`.

## Wikilinks now resolved

- [[Feywood Border]], [[Heartwater Basin]], [[Heartwood Estate]], [[Silent Grove]], [[Thornveil]], [[Vaelmere]]

## Wikilinks introduced but unresolved (worklist for Refresh 4 and beyond)

**Feywood interior sub-locations (planned for Refresh 4):**

Silent Grove sub-files:
- [[Reading Glade]], [[Training Grounds]]

Thornveil district sub-files:
- [[Heartwood Approach]], [[Noble Groves]], [[Common Hearth]], [[Crafthall]], [[Outer Bounds]]

Vaelmere sub-files:
- [[Trade Hall]], [[Wardens Hall]], [[Guest House]], [[Commons Hearth]]

**Feywood orders/groups (also Refresh 4 — vault has these in `feywood/groups/`):**
- [[Heartwarden]], [[Greenshield]], [[Ranger]] (already partially resolved through Feywood region note)
- [[Council of Elders]], [[Hall of Guides]], [[Hall of Trade]], [[Heartwardens]], [[Greenshields]], [[Elder Roots]], [[Noble Families]]

**Houses and house-related:**
- [[House Heartwood]] (referenced in many notes; needs its own note)
- [[House Vaelaryn]] (newly referenced — Sylvara's father Caelthir lives at their estate)
- [[Caelthir Vaelaryn]] (newly referenced NPC)

**Geographic targets in other refreshes:**
- [[Western Temperate Forest]] (region; later refresh)
- [[Dewhollow]] (referenced); already in batches 1-3? — verify
- [[Dracelune]] (settlement; later refresh)
- [[Hall of Guides]] is both an institution AND a location reference — vault has it in `feywood/groups/` so it's institutional

## New canonical references surfaced in this refresh

These are facts now in the vault that hadn't been in the project knowledge snapshots:

1. **House Heartwood maintains TWO seats** — Heartwood Estate (wild-heritage, in Outer Old-Growth Wild) and a Thornveil seat (political-ceremonial, in [[Heartwood Approach]] district). My earlier notes treated House Heartwood as a single-seat house; correcting in this refresh.

2. **House Vaelaryn exists** — second major elven house, distinct from Heartwood. Caelthir Vaelaryn is the in-law father of the current generation's Heartwood children. Not in the project knowledge files I've seen; is canon in the vault.

3. **Sylvara Heartwood is the player's PC** — current House Heartwood Proving candidate in the preparation phase at Heartwood Estate. The vault flags her PC status explicitly in authoring notes. I've kept the Heartwood Estate note generic on this (referring to "the current Proving candidate" rather than naming her in static description) per vault guidance: PC state should be read from character-system context, not from world data.

4. **Dusk** — Sylvara's bonded moonthorn wolf companion. Referenced but tracked through PC character record, not as a standalone NPC.

5. **The "first trees" / founding witnesses** — several specific elder trees in the [[Silent Grove]] are canonically the original first trees that rose from the elven sacrifice. Druids know which they are; realm visitors do not.

6. **Heartwarden 7-year training cycle** — explicit four-stage structure (Foundation, Integration, Specialization, Sworn preparation). Oaths sworn at the [[Heartwood]], not the Grove.

7. **Council of Elders size** — roughly 30-50 members; not fixed. Includes rotating seats for senior [[Greenshield]] commanders and [[Heartwarden]] captains.

8. **Greenshield deployment history** — exactly one combat deployment in recorded history: the [[Discordant War]]. The order's combat capability significantly exceeds what realm standards predict.

9. **Coming-of-age trial tradition** — roughly a dozen noble families maintain the practice. House Heartwood's variant (Proving at 90, alternate-identity demonstration) is one of these.

10. **Topology corrections** — [[Feywood Border]] does NOT connect directly to [[Thornveil]] (geometry doesn't extend the path). [[Feywood Border]] does NOT connect to the Silverwood Trail (which runs Dracelune-to-Silvercut). I've noted these explicitly in the relevant notes.

## What I noticed I want to flag

- **House Vaelaryn** is referenced but not yet a vault file I've found. May exist in `feywood/groups/noble_families.md` (which is in the file tree). Will read in Refresh 4.
- **Caelthir Vaelaryn** is a new NPC. Belongs in NPC notes when those get refreshed.
- **The PC's name (Sylvara) and her companion (Dusk)** appearing in vault authoring notes is interesting — the vault treats the PC's existence as canonical context. I'll continue keeping migration notes generic about PC state.

## After applying

Open `Silent Grove.md` and `Heartwood Estate.md` in Reading view. The Silent Grove note carries the deepest historical anchor in the elven world (the founding sacrifice, the first trees). The Heartwood Estate note carries the current narrative weight (Lethariel, the Heartwood bow, the house's living tradition).

If anything reads off, surface it before Refresh 4. Otherwise: Refresh 4 will pick up the sub-locations of Silent Grove (2), Thornveil (5), Vaelmere (4), plus the 8 Feywood groups files. That's 19 files — substantial. I'll likely split it into 4a (sub-locations, 11 files) and 4b (groups, 8 files) for cleaner review checkpoints.
