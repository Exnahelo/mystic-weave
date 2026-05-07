---
type: meta
status: locked
date: 2026-05-07
---

# Migration Refresh 4b — Feywood factions

## What this refresh delivers

Eight new faction notes covering the [[Feywood]]'s institutional life, plus a small spelling correction to [[Heartwood Approach]]. All files are working canon migrations from the world vault's `prompts/world_vault/hollow_crown/surface/feywood/groups/` directory.

### New faction notes (in `10_world/factions/feywood/`)

- **Noble Families.md** — `type: concept`. Canonical roster of the seven major elven houses (Heartwood, Vaelaryn, Silverbough, Thornmere, Dawnveil, Greybranch, Ironsap) with the common-but-not-exclusive mechanism. House detail lives here in concept-doc form rather than in per-house entity notes (which are deferred to a future refresh).
- **Council of Elders.md** — `type: faction`. The Feywood's governing body. ~20 members, three-category composition (~10–12 house representatives, ~6–8 common-origin elders, ~1–2 specialized seats), Elder Druid as recognized counselor. Two working sites: routine chambers in [[Heartwood Approach]], land-weight Chamber beneath the [[Heartwood]].
- **Heartwardens.md** — `type: faction`. Sacred guardian order of the [[Heartwood]] and [[Silent Grove]]. ~100 sworn, century oath (10yr training/renewal + 90yr active), Captain Lethariel emeritus.
- **Greenshields.md** — `type: faction`. Primary defensive military. ~600 active across four doctrinal pillars (settlement defense, border watch, interior patrol, crisis deployment). 50yr initial oath, at-pleasure continuation. [[Discordant War]] deployment ~180 plus ~30 Rangers and ~20 Heartwardens.
- **Rangers.md** — `type: faction`. Greenshield specialist branch (NOT a separate order). ~150 active across four service pillars (threshold-watch ~50, outer-range recon ~70, escort ~20, realm-side contact rare). Two-year specialist program on top of Greenshield training.
- **Hall of Guides.md** — `type: faction`. Civilian-coded escort, liminal-geometry navigation. ~60 active. House Silverbough association. Master of Guides at [[Thornveil]] [[Outer Bounds]] district. 7–10 year apprenticeship.
- **Hall of Trade.md** — `type: faction`. Primary trade organization. ~150–180 active across [[Vaelmere]]'s [[Trade Hall]] (~80), Border (~25), [[Thornveil]] (~10), distribution (~30). House Vaelaryn association. **Distinction noted: "Hall of Trade" is the organization, "[[Trade Hall]]" is the building** in Vaelmere's Central Commons.
- **Elder Roots.md** — `type: faction`. Druidic community. ~180 active + 20–30 apprentices. Elder Druid + Druid Master leadership pair. Four working sites: [[Silent Grove]] (~80), [[Heartwood]] (~10), [[Reading Glade]] (~30–40), distributed (~50). Cross-tradition druidic interaction is canonically NOT assumed friendly.

### Heartwood Approach.md (correction)

Spelling fixes applied per vault canon: **Silverbow → Silverbough**, **Dawnvale → Dawnveil**. Both spellings come from the canonical `noble_families.md` source file. House references now also point to the [[Noble Families]] canonical home rather than placeholder wikilinks.

## Apply

```bash
cd ~/Documents/Vaults/mystic-weave/
unzip -o ~/Downloads/mystic-weave-refresh-4b.zip
rm ~/Downloads/mystic-weave-refresh-4b.zip
```

## Type-system note

All eight order/group entities use `type: faction` (not `order`). Keeps the type list small and stable per project conventions; the orders' nature as orders is captured in content. Noble Families uses `type: concept` since it's a cross-reference/roster doc rather than a faction itself.

## Aliases

Each faction note includes aliases for common variant references — singular forms (`Heartwarden`, `Greenshield`, `Ranger`, `Guide`), "The X" forms (`The Heartwardens`, `The Council of Elders`), and "X order" forms. **This means existing wikilinks like `[[Heartwarden]]` and `[[Greenshield]]` in prior-migrated files will resolve correctly** without needing to chase down and rewrite each reference.

## Vault reconciliation flags

### Source vault staleness

The world vault's `prompts/world_vault/hollow_crown/surface/feywood/thornveil/noble_groves.md` lists the great houses (Vaelaryn, Silverbough, Thornmere, etc.) as residents of the Noble Groves. **Per the verbal canon applied in Fix 4 and now reinforced by this refresh, that's stale** — great houses live in the [[Heartwood Approach]], minor houses in [[Noble Groves]]. Surfacing here in case you want to update the source vault to match.

The world vault's `heartwood_estate.md` calls House Heartwood's wild-heritage seat the "Outer Wild Estate" while the file is named `heartwood_estate.md` and our entity note follows the user-vault filename convention as `Heartwood Estate.md`. **Naming inconsistency in the source itself, not in our migration.** Flagged for awareness; no action needed unless you want to reconcile.

### Existing user-vault touch-ups deferred

Two files I created in earlier refreshes have minor content drift from the canonical groups files just read:

- **`Heartwood.md`** (Refresh 1): The Elder Druid description should expand to acknowledge head-of-all-druids role beyond Heartwood-specific stewardship. The `Elder Roots.md` authoring notes specifically flag this.
- **`Reading Glade.md`** (Refresh 4a): "study spaces" section currently frames specific-questions research; should pivot to land-reading practice. Observation circles and oral-tradition seats remain canonical and require no change.

Both deferred to a future fix. Neither is structurally wrong; both are framing refinements per vault authoring notes.

## Wikilinks introduced

### Now resolved by this refresh

- [[Heartwardens]] (with aliases `Heartwarden`, `Heartwarden order`, `The Heartwardens`)
- [[Greenshields]] (with aliases `Greenshield`, `Greenshield Order`)
- [[Rangers]] (with aliases `Ranger`, `Ranger Branch`)
- [[Hall of Guides]] (with aliases `the Hall`, `Guides`)
- [[Hall of Trade]] (with aliases `Trade Hall organization`)
- [[Elder Roots]] (with aliases `druids of the Feywood`, `Feywood druids`)
- [[Council of Elders]] (with aliases `the Council`, `Elven Council`)
- [[Noble Families]] (with anchor links like `[[Noble Families#House Heartwood]]`)

This means old wikilinks across all prior-migrated files (Heartwood, Silent Grove, Reading Glade, Vaelmere, Thornveil, Heartwood Approach, Noble Groves, Crafthall, Common Hearth, Outer Bounds, Heartwood Estate, Training Grounds) will now resolve.

### Introduced but unresolved (future refreshes)

- **[[Aelarion]]** — Sylvara's sibling per Noble Families (Caelthir's other child with Lethariel). NPC.
- **[[Silver Scale Trading Company]]** — realm-side primary trade counterpart. Probably already exists in vault from an earlier batch — if not, will surface in a realm-side refresh.
- **[[Drakenvale]]** — realm-side anchor.
- **[[Dragon Guard]]**, **[[Wardens]]** — realm-side military bodies referenced for parallel/coordination.
- **[[Oath of the Fallen]]** — the canonical Feywood-realm treaty/compact.
- **[[The Platinum Warden]]** / **Vindrael** — the canonical Discordant War sacrificial figure.
- **[[Trade Hall]]** — building in Vaelmere's Central Commons (distinct from Hall of Trade organization). Probably already exists from Vaelmere refresh; if not, future flag.
- **[[Feywood Border]]** — referenced extensively as the realm-to-realm threshold. Probably already exists; if not, future flag.

The first three (Drakenvale, Dragon Guard, Wardens, Oath of the Fallen, Platinum Warden) are realm-side anchors that will likely come through a realm-side refresh batch. The last two (Trade Hall, Feywood Border) probably exist already in earlier batches; verify after applying.

## After applying

In Reading view, open the eight new faction notes and Heartwood Approach to confirm:

- Cross-references between factions all resolve (Heartwardens ↔ Greenshields ↔ Rangers ↔ Hall of Guides ↔ Elder Roots ↔ Council of Elders)
- House anchor links work (`[[Noble Families#House Heartwood]]`, etc.)
- Aliases catch existing singular references (`[[Heartwarden]]` resolves to Heartwardens.md)
- Spelling corrections applied to Heartwood Approach (Silverbough, Dawnveil)

Then ready for **Refresh 5** when you give the go: wounded quadrant — [[Temple of Mordrax]], [[Rift of Discord]], [[Dark Hold]], [[Shadowed Hollows]]. Or some other direction if priorities have shifted.
