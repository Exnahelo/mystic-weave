# MIGRATION_REFRESH_11

**Type:** Refresh (Western Temperate Forest cluster — closes geography migration)
**Scope:** Western Temperate Forest region root + Dracelune (with Lantern and Mule sub-location) + Silvercut (with Herbalist's Cabin and Hunter's Hall sub-locations) + Dewhollow + Silverwood Trail + Ironwood Ridge (relocated to Inner Ramparts)
**Notes shipped:** 10 entity notes
**Source vault:** `Exnahelo/mystic_weave_2.0`, branch `main`
**User vault:** `Exnahelo/mystic-weave`, branch `main`

---

## Summary

Closes the Western Temperate Forest gap — the last unmigrated surface region with substantial source canon. Resolves the heaviest remaining batch of broken wikilinks across the user vault: every prior reference to [[Dewhollow]], [[Silvercut]], [[Dracelune]], [[Silverwood Trail]], [[Lantern and Mule]], [[Herbalist's Cabin]], and [[Hunter's Hall]] now resolves cleanly.

Bundles in [[Ironwood Ridge]] as a corrected-region patch: source vault placed it at `surface/western_temperate_forest/` but its content is unambiguously alpine and its connectors point to [[Glacial Stream Crossing]] (Inner Ramparts) and [[Wardline Threshold]] (Alpine Peaks). Authored under [[Inner Ramparts]] per content and connector logic.

After R11, all named-entity wikilinks present in user-vault geography notes resolve to authored nodes within the geography layer. Remaining forward-references are NPCs, groups/factions, and Tier-3 generative roles — to be addressed in non-geography migration batches.

---

## Notes inventory

### NEW (10 notes)

| Note | Path | Source character |
|---|---|---|
| Western Temperate Forest | `regions/western-temperate-forest/Western Temperate Forest.md` | Sparse source stub (27 lines) — synthesized from constituents and project canon. |
| Dracélune | `regions/western-temperate-forest/dracelune/Dracelune.md` | Rich (151 lines). Source-rebuilt with Lethira→Vetra correction (see below). |
| Lantern and Mule | `regions/western-temperate-forest/dracelune/Lantern and Mule.md` | Sparse but complete (42 lines). Source-rebuilt. |
| Silvercut | `regions/western-temperate-forest/silvercut/Silvercut.md` | Rich (134 lines). Source-rebuilt. |
| Herbalist's Cabin | `regions/western-temperate-forest/silvercut/Herbalist's Cabin.md` | Rich (79 lines). Source-rebuilt. Anchors [[Marren Oake]]. |
| Hunter's Hall | `regions/western-temperate-forest/silvercut/Hunter's Hall.md` | Rich (76 lines). Source-rebuilt. Anchors [[Tova Kerrin]]. |
| Dewhollow | `regions/western-temperate-forest/Dewhollow.md` | Rich (137 lines). Source-rebuilt. |
| Silverwood Trail | `regions/western-temperate-forest/Silverwood Trail.md` | Rich (126 lines). Source-rebuilt. |
| Ironwood Ridge | `regions/inner-ramparts/Ironwood Ridge.md` | Sparse (39 lines). Source content preserved verbatim; relocated from western-temperate-forest path to Inner Ramparts per content + connector logic. |

### Status transitions

All 10 notes authored at `status: locked` directly (new authoring, no `working` predecessor).

### Folder structure decisions

- **Dracelune folder** (`dracelune/`) — created because Dracelune has a sub-location ([[Lantern and Mule]]) anchoring its own NPC ([[Hob Denner]]). Mirrors the Stronghold pattern from R8.
- **Silvercut folder** (`silvercut/`) — created because Silvercut has two sub-locations ([[Herbalist's Cabin]] anchoring [[Marren Oake]], [[Hunter's Hall]] anchoring [[Tova Kerrin]]).
- **Dewhollow** — flat (no folder) because no sub-locations exist in source. Same pattern as Stonemark, Greymantle, Mirefall in earlier batches.

---

## Pre-build verification

Per the workflow established in R10 (user vault is public, direct read access enabled):

1. **R10 confirmed applied.** R10 commit `3c401c0` present at HEAD; all 8 R10 notes in place under `central-draconic-grasslands/`. Manifest at vault root.
2. **All 9 western-temperate-forest target entities verified missing in user vault.** Region folder did not exist before this refresh.
3. **Ironwood Ridge verified missing.** Not present anywhere in user vault.
4. **Connector targets verified present.** [[Glacial Stream Crossing]] confirmed in `regions/inner-ramparts/`. [[Wardline Threshold]] confirmed in `regions/alpine-peaks/`.

---

## NPC canon resolution: Lethira Vale and Vetra Ebony

Source vault `dracelune.md` contained an inconsistency: `known_npcs` listed `Vetra Ebony`, the section header was "Vetra Ebony", but the second paragraph of that section said "characters... end up talking to **Lethira**, one way or another." This appeared to conflict with R8 Drakenvale City, which had [[Lethira Vale]] anchored there as a [[Silver Wing Envoys|Silver Wing]] envoy.

**Resolution per user direction:**

- **[[Lethira Vale]]** was originally created as a [[Silver Wing Envoys|Silver Wing]] envoy agent anchored at [[Drakenvale City]]. Got accidentally dropped into Dracelune authoring during an earlier migration pass.
- **[[Vetra Ebony]]** was created later as the intended Dracelune-anchored fixer character — replacing Lethira in the Dracelune slot.
- Lethira's role evolved into a more general realm-wide [[Silver Wing Envoys|Silver Wing]] envoy, anchored at Drakenvale City (R8 placement is canonical).
- The "Lethira" reference inside the Vetra Ebony section is a migration artifact from when the swap was happening.

**Applied:** The user-vault Dracelune note silently corrects "Lethira" → "Vetra" in that paragraph. Vetra Ebony is authored as the Dracelune anchor NPC. Both characters exist as separate canonical figures.

---

## Ironwood Ridge: source-vault region mismatch

**Discovery:** Source `surface/western_temperate_forest/ironwood_ridge.md` contains content that is unambiguously alpine — frost-tolerant ironwood trees, ice-rimed bark, Frostwing Owls, Snowbound Yeti territory, "clinging to the mountain slope," tags `alpine, forest, shelter, yeti-territory`. Its connectors are `glacial-stream-crossing` (Inner Ramparts) and `wardline-threshold` (Alpine Peaks). Despite its file path, the content is not western temperate forest.

**Per user direction:** "Ironwood Ridge was a connector. It's pretty old and doesn't and hasn't actually been used in gameplay for a long time... I would guess Inner Ramparts. Honestly, you can put it wherever fits best."

**Resolution:** Authored under [[Inner Ramparts]] (`regions/inner-ramparts/Ironwood Ridge.md`). Reasoning:

1. **Content** — alpine throughout.
2. **Connector proximity** — [[Glacial Stream Crossing]] (Inner Ramparts) is the more natural adjacent node for a frost-tolerant mountain-slope ridge.
3. **User instinct** — Inner Ramparts was the user's first guess.

Source content preserved verbatim; the node is acknowledged as an "old connector" with potentially stale details. Future expansion can refresh the canon if gameplay returns to it.

Pattern matches Varethyn's Lair from R8 (placed under `locations/` flat folder in source despite belonging structurally in Crystal Caverns, resolved during R8's reconcile-in-place migration).

---

## Source-vault discoveries (flagged for upstream)

### 1. `region_id: hollow_crown` underscore typo — fourth occurrence

`lantern_and_mule.md` and `ironwood_ridge.md` both have the underscore form. Cumulative occurrences across the migration:

| File | Refresh |
|---|---|
| `surface/central_draconic_grasslands/.../draconic_forge.md` | R8 |
| `surface/southern_dark_quadrant/.../deephollow_lower_tunnels.md` | R9 |
| `surface/western_temperate_forest/dracelune/lantern_and_mule.md` | R11 |
| `surface/western_temperate_forest/ironwood_ridge.md` | R11 |

A single upstream sweep can fix all four with one find-replace. Pattern is consistent enough that other source files outside this migration's scope may have it too — worth a vault-wide grep.

### 2. Ironwood Ridge path/content mismatch (resolved this refresh)

Source path is `western_temperate_forest/ironwood_ridge.md`; content is alpine. Resolved in user vault per region relocation; flagged for source-vault correction (move file to alpine-peaks or inner-ramparts source folder).

### 3. Dracelune `dracelune.md` Lethira→Vetra migration artifact (resolved this refresh)

Section header and `known_npcs` list "Vetra Ebony"; paragraph body references "Lethira." Migration artifact from an earlier authoring pass. User-vault note silently corrects to "Vetra"; flagged for source-vault correction.

### 4. `settlement_id` field appears in three R11 sources

`lantern_and_mule.md`, `herbalists_cabin.md`, `hunters_hall.md` all carry `settlement_id` alongside `parent_location_id`. The user-vault convention drops `settlement_id` as redundant — `parent_location` carries the same information. Not a bug per se but worth a convention sweep upstream.

---

## Frontmatter normalization (applied to all 10 notes)

Same conventions as R8/R9/R10:

| Source field | User-vault field | Transformation |
|---|---|---|
| `id` | `vault_id` | dashed-form preserved |
| `name` | (dropped, in H1) | — |
| `type` | `type` | normalized: `region_zone` → `region` (region root); `route-node` → `location` with route-node tag (Silverwood Trail); `wilderness` → `location` with wilderness tag (Ironwood Ridge); `settlement` and `location` preserved |
| `region_id` | `region` | preserved as `hollow-crown`; underscore form normalized for two notes |
| `parent_location_id` | `parent_location` | preserved/added for all child nodes |
| `connections` | (dropped from frontmatter) | translated to inline wikilinks + `## Connected Nodes` section |
| `tags` | `tags` | preserved; original type-name added where reclassified |
| `known_npcs` | (dropped) | NPCs surfaced via inline wikilinks in body |
| `threat_level` | (dropped) | mechanical/runtime field |
| `discovered` | (dropped) | mechanical/runtime field |
| `settlement_id` | (dropped) | redundant with `parent_location` |

---

## Topology decisions

### Reciprocal edges established

- **Dracelune ↔ Silvercut, Dewhollow, Silverwood Trail, Lantern and Mule** — all inbound and outbound listed.
- **Silvercut ↔ Herbalist's Cabin, Hunter's Hall** — both child sub-locations linked.
- **Silvercut ↔ Silverwood Trail ↔ Dracelune** — triangle complete.
- **Dewhollow ↔ Silverwood Trail, Dracelune, Feywood Border, Western Temperate Forest** — complete.
- **Western Temperate Forest** ↔ all constituents listed.

### Forward-references still pending after R11

| Wikilink | Resolution |
|---|---|
| [[Feywood]], [[Feywood Border]] | Already authored in earlier batches under `regions/feywood/`. Verify on apply. |
| [[Mirefall]] | Already authored under `regions/southwestern-mystic-wetlands/`. |
| [[Scalemere]], [[Ashfield]] | Authored in R10. |
| [[Drakenvale City]], [[Stronghold of Drakenvale]], [[Sacred Pools]], [[Platinum Heart]] | Authored in R8. |
| [[Zarkharath]], [[Infernal Forge]] | Authored in earlier batch. |
| [[Hall of Scales]] | Authored in R10. |
| [[Stonemark]] | Authored in R7. |
| [[Glacial Stream Crossing]], [[Wardline Threshold]] | Authored in R7. |

NPC and group forward-references (deferred to non-geography batches):

- NPCs: [[Vetra Ebony]], [[Hob Denner]], [[Marren Oake]], [[Tova Kerrin]], [[Kaerys Emberclaw]], [[Tazrik Flameweaver]], [[Lethira Vale]], [[Ardrynn the Measured]], [[Eryndor the Radiant]], [[Solveris]]
- Tier-3 generative roles: [[Cultivar Warden]], [[Senior Herbalist]], [[Woodwarden]], [[Hunts-Master]], [[Master of Guides]], [[Harbor Steward of the Inbound]], plus all earlier-batch role stubs ([[Ashfield Reeve]], [[Grange Master]], [[Harbor Reeve]], [[Fishmaster]], [[Shore Warden]], [[Senior Retreatant]], [[Rector of the Hall of Scales]], etc.)
- Groups: [[Silver Scale Trading Company]], [[Silver Wing Envoys]], [[Sapphire Choir]], [[Hall of Guides]], [[Dragon Guard]], [[Wardens]], [[Platinum Acolytes]], [[Arcane Conservatory]], [[Draconic Council]]

---

## What this refresh closes

After R11, geography migration is **substantively complete**. Every major surface region has a region root authored in user vault. Every named settlement referenced in earlier-batch wikilinks now has its own note. Every region-zone-shape location and route-node referenced in scene texture now resolves.

| Region | Status after R11 |
|---|---|
| Central Draconic Grasslands | Complete (R8 + R10) |
| Crystal Caverns | Complete (R9) |
| Beneath the Southern Dark Quadrant | Complete (R9) |
| Alpine Peaks | Complete (pre-R8) |
| Inner Ramparts | Complete + Ironwood Ridge added (R7 + R11) |
| Southwestern Mystic Wetlands | Complete (R7) |
| Northeastern Volcanic Highlands | Complete (pre-conversation) |
| Southern Dark Quadrant (surface) | Complete (pre-conversation) |
| Feywood | Complete (pre-conversation) |
| **Western Temperate Forest** | **Complete (R11)** |

Remaining work is non-geographic:

- NPC nodes (Tier-1 named characters and Tier-3 generative roles)
- Groups/factions
- History, artifacts, documents
- Topology pass for any reciprocal-edge gaps surfaced during play

Whether to continue with these or pivot to mechanical foundational assessment is the next decision point.

---

## Apply commands

From inside the user vault repo (`mystic-weave`):

```bash
cd /Users/danielhowe/Documents/Vaults/mystic-weave

unzip -o ~/Downloads/MIGRATION_REFRESH_11.zip

git add 10_world/ MIGRATION_REFRESH_11.md
git commit -m "Refresh 11: Western Temperate Forest cluster — region root + Dracelune (with Lantern and Mule) + Silvercut (with Herbalist's Cabin and Hunter's Hall) + Dewhollow + Silverwood Trail; relocate Ironwood Ridge to Inner Ramparts per content + connector logic"

git push
```

Bundle has no wrapper folder — `unzip -o` extracts `10_world/` and `MIGRATION_REFRESH_11.md` directly into the vault root. No rsync step. Adjust the zip path if it landed somewhere other than `~/Downloads/`.

---

## Reconcile rule audit

| Rule | Application |
|---|---|
| Source wins on content where richer | Applied to Dracelune, Silvercut, Herbalist's Cabin, Hunter's Hall, Dewhollow, Silverwood Trail, Lantern and Mule (verbatim/near-verbatim). |
| Synthesize from constituents where source is sparse | Applied to Western Temperate Forest region root (source stub of 27 lines plus tags/footer; user-vault note adds geographic role and constituent inventory drawn from project canon and the constituent notes authored in this batch). |
| Source content preserved verbatim where node is "old/stale but canonical" | Applied to Ironwood Ridge per user direction. |
| User vault wins on alias/path/frontmatter conventions | Applied — `type`, `tags`, `vault_id`, `region`, `parent_location`, `status` follow user-vault convention. Mechanical and redundant fields dropped. |
| Translate source `connections` arrays into inline wikilinks + Connected Nodes section | Applied throughout. |
| Pre-build vault state verification | Applied — user vault cloned and inspected before authoring. |
| User-verbal canon supersedes vault-internal contradictions | Applied to Lethira/Vetra (user clarified separation; corrected the source artifact) and Ironwood Ridge (user directed region placement based on connector logic). |

---

## What this refresh does NOT do

- Does not author NPCs (Vetra Ebony, Hob Denner, Marren Oake, Tova Kerrin, etc.).
- Does not author groups/factions (Silver Scale Trading Company, Hall of Guides, etc.).
- Does not patch existing R7 [[Glacial Stream Crossing]] and [[Wardline Threshold]] notes for reciprocal edges to Ironwood Ridge. Obsidian backlinks surface the relationship in the graph; explicit reciprocal patches deferred to a future topology pass if needed.
- Does not patch the realm note `Drakenvale.md` for the new entities — manual review step.
- Does not address the four flagged source-vault issues upstream — flagged for batched cleanup.
- Does not touch any 2.0 implementation, prompt files, or registries (out of scope).

---

## Process notes

This refresh applied the workflow established in R10 (public user vault, pre-build verification, no-wrapper-folder bundle structure, comment-free apply commands). No process changes this round.

The pre-build verification confirmed that the western-temperate-forest folder did not exist in the user vault before this refresh, validating the expectation that R11 is closing a real geographic gap rather than reconciling against draft content.
