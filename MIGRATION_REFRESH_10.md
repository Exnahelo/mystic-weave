# MIGRATION_REFRESH_10

**Type:** Refresh (surface adjacencies cluster — central grasslands closure)
**Scope:** Southern Lake + Ashfield + Ashfield Fields + Draconic Grasslands Edge + Grasslands Edge Post + Hall of Scales + Scalemere + Crystalhaven
**Notes shipped:** 8 entity notes
**Source vault:** `Exnahelo/mystic_weave_2.0`, branch `main`
**User vault:** `Exnahelo/mystic-weave`, branch `main`

---

## Summary

Closes the central grasslands adjacency cluster — every named-entity wikilink that R8 ([[Drakenvale City]], [[Stronghold of Drakenvale]], [[Central Draconic Grasslands]]) and R9 ([[Crystal Caverns]] note) forward-referenced from this region now resolves cleanly. The Southern Lake is authored as a child-location of the central grasslands per the (b) topology decision — source vault placed it in its own folder (`central_body_of_water/`), but user-vault structure treats it as constituent of the basin region.

Hall of Scales authoring brings [[Ardrynn the Measured]] online as a wikilink resolving against future NPC migration, and resolves the heaviest single institutional forward-reference.

---

## Notes inventory

### NEW (8 notes)

| Note | Path | Source character |
|---|---|---|
| Southern Lake | `regions/central-draconic-grasslands/Southern Lake.md` | Rich (164 lines). Source-rebuilt verbatim/near-verbatim. |
| Ashfield | `regions/central-draconic-grasslands/Ashfield.md` | Rich (104 lines). Source-rebuilt. |
| Ashfield Fields | `regions/central-draconic-grasslands/Ashfield Fields.md` | Rich (160 lines). Source-rebuilt. |
| Hall of Scales | `regions/central-draconic-grasslands/Hall of Scales.md` | Rich (103 lines). Source-rebuilt. |
| Scalemere | `regions/central-draconic-grasslands/Scalemere.md` | Rich (112 lines). Source-rebuilt with internal-inconsistency flag (see below). |
| Crystalhaven | `regions/central-draconic-grasslands/Crystalhaven.md` | Rich (142 lines). Source-rebuilt. |
| Draconic Grasslands Edge | `regions/central-draconic-grasslands/Draconic Grasslands Edge.md` | Sparse (19 lines). Placeholder route-node; light contextual framing added from references in surrounding notes. |
| Grasslands Edge Post | `regions/central-draconic-grasslands/Grasslands Edge Post.md` | Sparse (26 lines). Placeholder watch station; light contextual framing. |

### Status transitions

All 8 notes authored at `status: locked` directly (new authoring, no `working` predecessor).

---

## Pre-build verification (new — direct vault read enabled this refresh)

Mid-refresh, the user-vault repo (`mystic-weave`) was made public, enabling direct verification of vault state before authoring. Pre-build checks:

1. **R8 and R9 confirmed applied.** All R8 and R9 commits present at HEAD; all R8 and R9 geography content in place under `central-draconic-grasslands/`, `crystal-caverns/`, `beneath-southern-dark-quadrant/`. Manifests at vault root.
2. **All 8 R10 target entities verified missing in user vault.** No conflicts; all are net-new authoring.
3. **Inner Ramparts stonemark cluster verified present.** R7 had authored `Stonemark.md`, `Stonemark Deep Cuts.md`, and `Glacial Stream Crossing.md`. No further action needed for that cluster.

This is the first refresh where vault state was verified before authoring rather than asserted by the user. Future refreshes will use the same workflow.

---

## Source-vault discoveries

### 1. Scalemere internal contradiction (frontmatter vs. authoring notes)

Source `scalemere.md` includes `crystalhaven` in its frontmatter `connections` array, while its own Authoring Notes section says: "The Crystalhaven connection is forward-referenced in scene texture but not listed in the connections array." The frontmatter is authoritative for actual data, so the user-vault note preserves the connection. Flagged in the note's authoring section and here for upstream cleanup.

### 2. Two genuine source-vault placeholder stubs

`draconic_grasslands_edge.md` (19 lines) and `grasslands_edge_post.md` (26 lines) are explicitly placeholder content per their own description text. The user-vault notes preserve source content and add minimal contextual framing drawn from the surrounding nodes that reference these locations. No invention beyond what existing canonical references establish.

### 3. Source-vault region-zone topology decision (b)

Source vault places Southern Lake at `central_body_of_water/southern_lake.md` — its own region-zone folder, structurally suggesting region treatment. User-vault decision per the (b) call: lake is a child of central grasslands, not its own region. Reasoning recorded in the note's authoring section. The source-vault folder structure is acknowledged as an authoring convenience that doesn't dictate user-vault topology.

---

## Frontmatter normalization (applied to all 8 notes)

Same conventions as R8/R9:

| Source field | User-vault field | Transformation |
|---|---|---|
| `id` | `vault_id` | dashed-form preserved |
| `name` | (dropped, in H1) | — |
| `type` | `type` | normalized: `region_zone` → `location` (Southern Lake, Ashfield Fields); `route-node` → `location` (Draconic Grasslands Edge); `settlement` preserved |
| `region_id` | `region` | preserved as `hollow-crown` |
| `parent_location_id` | `parent_location` | added/normalized for all 8 notes (some source files lack this field; all user-vault notes have it set to `central-draconic-grasslands`) |
| `connections` | (dropped from frontmatter) | translated to inline wikilinks + `## Connected Nodes` section |
| `tags` | `tags` | preserved |
| `known_npcs` | (dropped) | NPCs surfaced via inline wikilinks in body |
| `threat_level` | (dropped) | mechanical/runtime field |
| `discovered` | (dropped) | mechanical/runtime field |

---

## Topology decisions

### Reciprocal edges established

The following Connected Nodes relationships now resolve cleanly with two-way edges:

- **Southern Lake ↔ Sacred Pools** — R8 Sacred Pools already lists `[[Southern Lake]]`; this refresh's Southern Lake lists `[[Sacred Pools]]`. Reciprocal complete.
- **Southern Lake ↔ Drakenvale City** — R8 Drakenvale City already lists `[[Southern Lake]]`; this refresh's Southern Lake lists `[[Drakenvale City]]`. Reciprocal complete.
- **Ashfield ↔ Drakenvale City** — R8 Drakenvale City already lists `[[Ashfield]]`; this refresh's Ashfield lists `[[Drakenvale City]]`. Reciprocal complete.
- **Hall of Scales ↔ Drakenvale City** — R8 Drakenvale City already lists `[[Hall of Scales]]`; this refresh's Hall of Scales lists `[[Drakenvale City]]`. Reciprocal complete.
- **Scalemere ↔ Drakenvale City** — same pattern.
- **Ashfield ↔ Ashfield Fields** — both refresh-authored; two-way edges set.
- **Ashfield ↔ Hall of Scales** — both refresh-authored; two-way edges set; weekend student migration acknowledged on both sides.

### Forward-references still pending

| Wikilink | Resolves in |
|---|---|
| [[Mirefall]] | already authored in user vault under southwestern-mystic-wetlands (verified at clone) |
| [[Dewhollow]] | already authored under western-temperate-forest |
| [[Silvercut]] | already authored under western-temperate-forest |
| [[Dracelune]] | already authored under western-temperate-forest |
| [[Ardrynn the Measured]] | future NPC migration batch |
| [[Codex of Remembrance]] | possibly already authored (verify), or future artifact/document batch |
| [[Silver Scale Trading Company]], [[Circle of Artisans]], [[Silver Wing Envoys]] | future groups/factions batch |
| [[Ashfield Reeve]], [[Grange Master]], [[Harbor Reeve]], [[Fishmaster]], [[Shore Warden]], [[Senior Retreatant]], [[Rector of the Hall of Scales]] | future Tier-3 generative role-stub batch |

---

## Realm-note patch

The realm note `10_world/geography/hollow-crown/Drakenvale.md` may need additions to reference the 8 new entities. Manual review step. If the realm note's Major places section uses bare `[[Wikilinks]]`, no path edit is needed — Obsidian will resolve by filename. If paths are encoded explicitly, edit accordingly.

---

## Apply commands

From inside the user vault repo (`mystic-weave`):

```bash
cd /Users/danielhowe/Documents/Vaults/mystic-weave

unzip -o MIGRATION_REFRESH_10.zip

git add 10_world/ MIGRATION_REFRESH_10.md
git commit -m "Refresh 10: surface adjacencies cluster — Southern Lake + Ashfield + Ashfield Fields + Draconic Grasslands Edge + Grasslands Edge Post + Hall of Scales + Scalemere + Crystalhaven"

git push
```

Bundle has NO wrapper folder this time — `unzip -o` extracts `10_world/` and `MIGRATION_REFRESH_10.md` directly into the vault root, no rsync step needed.

The commands here have no `#`-prefixed comment lines, so zsh won't choke on them when pasted as a block.

---

## Reconcile rule audit

| Rule | Application |
|---|---|
| Source vault wins on content where richer | Applied to Southern Lake, Ashfield, Ashfield Fields, Hall of Scales, Scalemere, Crystalhaven (verbatim/near-verbatim). |
| Source content preserved with light framing where source is sparse | Applied to Draconic Grasslands Edge and Grasslands Edge Post — both placeholder stubs in source. Framing drawn only from references in surrounding notes; no invention. |
| User vault wins on alias/path/frontmatter conventions | Applied — `type`, `tags`, `vault_id`, `region`, `parent_location`, `status` follow user-vault convention. Mechanical fields dropped. |
| Translate source `connections` arrays into inline wikilinks + Connected Nodes section | Applied throughout. |
| Mechanical fields out of scope | `threat_level`, `discovered` dropped from all 8 notes. |
| Pre-build vault state verification (new this refresh) | Applied — user vault cloned and inspected before authoring; all R10 targets confirmed missing; existing R7-R9 content confirmed present. |

---

## What this refresh does NOT do

- Does not author NPC nodes ([[Ardrynn the Measured]], [[Ashfield Reeve]], [[Grange Master]], [[Harbor Reeve]], [[Fishmaster]], [[Shore Warden]], [[Senior Retreatant]], [[Rector of the Hall of Scales]]).
- Does not author groups/factions ([[Silver Scale Trading Company]], [[Circle of Artisans]], [[Silver Wing Envoys]]).
- Does not patch existing Refresh 7/8/9 notes for reciprocal edges. Two-way edges from those earlier notes already point to entities now authored in this refresh, but if any one-way edges existed in source vault that would benefit from reciprocal completion, those are deferred to a future topology pass.
- Does not patch the realm note `Drakenvale.md` directly — manual step.
- Does not address the Scalemere source-vault internal contradiction upstream — flagged for upstream fix.
- Does not touch any 2.0 implementation, prompt files, or registries (out of scope).

---

## Process notes

Three procedural improvements landed in this refresh:

1. **User vault made public** — direct read access via `git clone` enables pre-build state verification. Future refreshes will check vault state before authoring rather than relying on user audits.

2. **Bundle structure fixed** — no wrapper folder. `unzip -o` extracts directly into vault root with no rsync step needed.

3. **Apply commands stripped of `#`-prefix comments** — zsh interprets `#` at line start as a command in some configurations, generating noise. Comments removed from the apply block; explanatory text moved to surrounding manifest sections.
