---
type: meta
status: locked
date: 2026-05-07
---

# Migration Refresh 6 — Northeastern Volcanic Highlands

## What this refresh delivers

Five entity notes covering the [[Northeastern Volcanic Highlands]]: the region root, both settlements, the connecting corridor, and the [[Infernal Forge]] complex. Source files at `prompts/world_vault/hollow_crown/surface/northeastern_volcanic_highlands/` (with `zarkharath/` and `cinderpit/` subfolders). Two of the five files in the source vault are sparse stubs (region root, Infernal Forge); the other three are richly authored.

### New entity notes

In `10_world/geography/hollow-crown/regions/northeastern-volcanic-highlands/`:

- **Northeastern Volcanic Highlands.md** — `type: location`. Region root. Industrial spine, civic presence (Forge Guild + Pit Master's office), drakari demographics, [[Zarkeros the Inferno]] as patron. Synthesized — vault root file is stub.

- **Volcanic Highlands Trail.md** — `type: location`. Engineered industrial corridor. Trail-day west, day-and-a-half east loaded. Three water stops + midpoint waystation jointly maintained. Loaded-yields-to-empty courtesy convention.

- **Cinderpit.md** — `type: location`. Mining village. Coal pits, deeper ore mines, specialty metal operations. Pit Master + Assay Warden. Drakari-heavy (~50% adults), ancestry-integrated leadership. The Black Seam inn at the Ashyard.

In `northeastern-volcanic-highlands/zarkharath/`:

- **Zarkharath.md** — `type: location`. The realm's industrial city. Active lava bed at center; ward-channeled volcanic heat; concentric working districts (Smelting Yards, Metalwork Quarter, Foundry Residences, Administrative Complex, Guest Quarter). [[Zarkeros the Inferno]]'s Lair across the causeway. Most drakari-concentrated settlement in the realm.

- **Infernal Forge.md** — `type: location`. The enchanted production complex on the platform in the lava bed. Five working zones (smelting halls, casting floors, finishing workshops, ward-anchoring stations, raw-material yards). Two heat sources: volcanic system + Zarkeros's breath. Sole production source for institutional-grade enchanted metalwork. **Synthesized substantially from Zarkharath's source file — the Infernal Forge's own source file is sparse stub.**

## Apply

```bash
cd ~/Documents/Vaults/mystic-weave/
unzip -o ~/Downloads/mystic-weave-refresh-6.zip
rm ~/Downloads/mystic-weave-refresh-6.zip
git add -A
git commit -m "Migration: Refresh 6 — Northeastern volcanic highlands (5 notes: region root, Zarkharath, Infernal Forge, Cinderpit, Volcanic Highlands Trail)"
git push
```

## Wikilinks introduced

### Now resolved by this refresh

- [[Northeastern Volcanic Highlands]] (with aliases `the volcanic highlands`, `the northeastern highlands`, `the highlands`)
- [[Zarkharath]] (with aliases `the Forge City`, `the industrial city`)
- [[Infernal Forge]] (with aliases `the Forge`, `the Forge complex`)
- [[Cinderpit]] (with aliases `the mining village`, `the coal village`)
- [[Volcanic Highlands Trail]] (with aliases `the Highlands Trail`, `the supply trail`)

### Introduced but unresolved (future refreshes)

- **[[Zarkeros the Inferno]]** — dragon of the [[Draconic Council]], Zarkharath's patron. **Major NPC pending.**
- **[[Infernal Forge Guild]]** — realm-recognized institutional body governing metalwork. **Faction pending.**
- **[[Infernal Forge Guildmaster]]** — Tier-3 generative, but role-tier note may eventually want elevation
- **[[Draconic Council]]** — central political body. **Faction/concept pending.**
- **[[Drakenvale City]]** — capital. Pending in core-region migration.
- **[[Stronghold of Drakenvale]]** — referenced as connection from Zarkharath. Pending.
- **[[Stonemark]]** — referenced in mining network. Pending in alpine peaks migration.
- **[[Deephollow]]** — subterranean, referenced in dwarvish origin contexts. Pending in subterranean migration.
- **[[Arcane Conservatory]]** — institutional buyer for rare metals. Pending.
- **[[Inner Ramparts]]** — referenced as adjacent boundary. Pending.
- **[[Silverwood Trail]]** — Feywood-side corridor referenced in courtesy-convention comparison. **Pending — may already exist or be authored elsewhere; verify after applying.**

## Vault reconciliation flags

### Source vault: region root file is sparse

`prompts/world_vault/hollow_crown/surface/northeastern_volcanic_highlands/northeastern_volcanic_highlands.md` is a stub. This refresh's region-root note is synthesized from constituent files plus realm canon (`world.md`, `geography.md`, `groups.md` references to Forge Guild and Dragon Guard).

### Source vault: Infernal Forge file is sparse

`prompts/world_vault/hollow_crown/surface/northeastern_volcanic_highlands/zarkharath/infernal_forge.md` is a stub. The canonical Forge content lives in `zarkharath.md`. This refresh's Infernal Forge note **pulls forward the Forge-specific detail from Zarkharath's source file**, organized as a focused production-complex entity. The decision to give the Forge its own note (vs. folding into Zarkharath) follows the source-vault structure (separate file) and the canonical importance of the Forge as the realm's sole institutional-grade enchantment production source.

**Recommendation:** the source vault's `infernal_forge.md` could be expanded with the Forge-specific content already present in `zarkharath.md`, or the two could be reconciled by deciding which location holds the canonical authoring weight. This is a vault-side authoring question, not a migration blocker.

### Sources are consistent

Cross-references between Zarkharath, Cinderpit, and the Trail are internally consistent in the source vault. The economic-spine framing (Cinderpit feedstock → Trail → Forge → realm) is canonical and stable.

## Cross-region references

This refresh introduces forward-references to:
- The [[Silverwood Trail]] (Feywood-side corridor) — referenced in the [[Volcanic Highlands Trail]]'s courtesy-convention comparison. If the Silverwood Trail entity exists in the user vault from a prior refresh, the link resolves; if not, it's a forward reference for a future Feywood-side corridor refresh.
- [[Stronghold of Drakenvale]] — referenced from Zarkharath as a connected node, consistent with the source vault's connections list. Pending.

## After applying

In Reading view, open Zarkharath.md and Infernal Forge.md to confirm:

- The two notes cross-reference cleanly (Forge as sub-feature of Zarkharath, but with its own focused content)
- Aliases catch wikilinks (e.g., `[[the Forge]]` → Infernal Forge.md, `[[the Forge City]]` → Zarkharath.md)
- The volcanic highlands feels like a coherent two-settlement region with a connecting corridor

Then ready for **Refresh 7** when you give the go. Logical next options:

- **Inner Ramparts + Alpine Peaks** — Lastmark, Stonemark, the realm's high frontier and mining network upstream of Cinderpit
- **Mystic Wetlands cluster** — Mirefall, Brackenmoor (resolves Greymantle's western connection)
- **Subterranean** — Temple of Mordrax (when located), Crystal Caverns, Deephollow (resolves dwarvish-origin references)
- **Drakenvale City + Stronghold** — capital, Draconic Hall, the Aeries, Administrative Quarter, Arcane Conservatory (resolves the most cross-cutting references)
- **Realm-side factions** — Vigil/Platinum Accord, Wardens, Sapphire Sentinels, Dragon Guard, Infernal Forge Guild, Council of Elders... (clears the most accumulated unresolved wikilinks)

My recommendation: **Drakenvale City + Stronghold next**. The capital and the Stronghold are referenced from nearly every refresh so far, and migrating them resolves more accumulated wikilinks than any other single move. After that, factions clear the institutional layer; then the remaining geography fills in.
