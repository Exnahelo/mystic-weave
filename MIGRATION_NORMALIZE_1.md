# MIGRATION_NORMALIZE_1

**Type:** Frontmatter normalization sweep — no content changes
**Scope:** 51 earlier-batch geography notes across all regions
**Source state:** post-Refresh-11 (commit `da84e24`)
**User vault:** `Exnahelo/mystic-weave`, branch `main`

---

## What this is

A normalization-only refresh that reconciles convention drift between earlier-batch geography content (R1–R7-era) and the user-vault schema established in the migration refreshes (R8 onward). No source-vault content is re-migrated. No new entities are authored. Only frontmatter is changed; body content is preserved verbatim.

Triggered by structural inspection findings from both Claude (programmatic check via Python script) and Claude Code (Explore agent scan). Both inspections converged on the same problem space.

---

## What gets fixed

### 1. R9 vault_id collision (1 file)

`Beneath the Southern Dark Quadrant.md` had `vault_id: southern-dark-quadrant`, colliding with the surface region's note. Fixed: now `vault_id: beneath-southern-dark-quadrant`.

### 2. `region` field normalization (~46 files)

Earlier-batch convention used wikilink-string form: `region: "[[Hollow Crown]]"`.
User-vault schema expects kebab-case id: `region: hollow-crown`.

All affected files normalized.

### 3. `status` field normalization (~45 files)

Earlier-batch notes carried `status: working` (and one `status: stub`).
User-vault schema expects `status: locked` for migrated content.

All affected files set to `status: locked`.

### 4. `parent_location` field normalization (35 files)

Earlier-batch convention: `parent_location: "[[Region Name]]"`.
User-vault schema: `parent_location: region-id` (kebab-case, matching `vault_id`).

Mapping applied:

| Wikilink form | Resolved id |
|---|---|
| `[[Alpine Peaks]]` | `alpine-peaks` |
| `[[Inner Ramparts]]` | `inner-ramparts` |
| `[[Northeastern Volcanic Highlands]]` | `northeastern-volcanic-highlands` |
| `[[Southern Dark Quadrant]]` | `southern-dark-quadrant` |
| `[[Southwestern Mystic Wetlands]]` | `southwestern-mystic-wetlands` |
| `[[Western Temperate Forest]]` | `western-temperate-forest` |
| `[[Lastmark]]` | `lastmark` |
| `[[Stonemark]]` | `stonemark` |
| `[[Zarkharath]]` | `zarkharath` |
| `[[Feywood]]` | `feywood` |
| `[[Silent Grove]]` | `silent-grove` |
| `[[Thornveil]]` | `thornveil` |
| `[[Vaelmere]]` | `vaelmere` |

### 5. `parent_region` legacy field (5 files)

A separate earlier-batch field name `parent_region:` was used in 5 Feywood files. Translation rule:

- `parent_region: "[[Hollow Crown]]"` (region-root pointing at world) → field dropped (region: hollow-crown captures it)
- `parent_region: "[[Feywood]]"` → renamed to `parent_location: feywood`

Applied to: `Feywood.md` (region root, dropped), `Heartwater Basin.md`, `Heartwood Estate.md`, `Silent Grove.md`, `Thornveil.md`, `Vaelmere.md`.

### 6. `type` field normalization (10+ files)

Non-standard type values translated to schema-valid types, original preserved as tag:

| Source `type` | Target `type` | Tag added |
|---|---|---|
| `route-node` | `location` | `route-node` |
| `region-zone` | `location` | `region-zone` |
| `sacred-site` | `location` | `sacred-site` |
| `district` | `location` | `district` |
| `wilderness` | `location` | `wilderness` |

Affected: `Feywood Border` (route-node), `Heartwater Basin` (region-zone), `Heartwood` (sacred-site), all 5 Thornveil sub-locations (district).

### 7. Region-root `type` correction (5 files)

Region-root files had `type: location` (legacy convention) — overridden to `type: region`:

- `Alpine Peaks.md`
- `Inner Ramparts.md`
- `Northeastern Volcanic Highlands.md`
- `Southern Dark Quadrant.md`
- `Southwestern Mystic Wetlands.md`

### 8. Settlement-shape `type` correction (1 file)

`Silent Grove.md` was `type: location` but has its own folder of sub-locations (`silent-grove/Reading Glade.md`, `silent-grove/Training Grounds.md`) — overridden to `type: settlement`. Mirrors Stronghold-of-Drakenvale, Lastmark, Thornveil, Vaelmere conventions where folder-owners are settlement type.

### 9. Top-level realm files — missing fields added (3 files)

| File | Added |
|---|---|
| `Drakenvale.md` | `region: hollow-crown`, `vault_id: drakenvale` |
| `Hollow Crown.md` | `region: hollow-crown`, `status: locked` |
| `regions/Feywood.md` | `region: hollow-crown`, `status: locked` |

`Drakenvale.md` retains `type: concept` — it's a realm-level overview note, intentional special case.

### 10. Region short-name aliases added (4 region notes)

To resolve short-form wikilink references like `[[Mystic Wetlands]]` against the canonical full names:

| Region note | Alias added |
|---|---|
| `Central Draconic Grasslands.md` | `Draconic Grasslands` |
| `Western Temperate Forest.md` | `Temperate Forest` |
| `Northeastern Volcanic Highlands.md` | `Volcanic Highlands` |
| `Southwestern Mystic Wetlands.md` | `Mystic Wetlands` |

(`Central Draconic Grasslands` already had `Draconic Grasslands` … wait, let me re-verify that one. It DID get the alias added; existing aliases were "The Grasslands" and "Central Grasslands" which don't match the short form "Draconic Grasslands".)

### 11. "The X" alias coverage (12 files where filename omits the article in H1)

Where filename is `Foo.md` but H1 reads `# The Foo`, ensured the aliased "The Foo" form is in the aliases list so wikilinks like `[[The Foo]]` resolve. Idempotent — files that already had the alias (e.g., `Aeries.md`, R8-authored) are left unchanged.

Applied to: `Silent Grove`, `Reading Glade`, `Training Grounds`, `Common Hearth`, `Crafthall`, `Heartwood Approach`, `Noble Groves`, `Outer Bounds`, `Commons Hearth`, `Guest House`, `Trade Hall`, `Wardens Hall` (H1: "The Warden's Hall").

---

## Total impact

51 files modified. All changes are within YAML frontmatter blocks. Body content (everything after the closing `---`) is byte-for-byte identical to the source.

Files NOT modified (37 of 82): these were either already conformant (R8/R9/R10/R11 notes), or have no work for this normalization pass to do (e.g., `Aeries.md` already had `The Aeries` alias from R8).

## Pre/post inspection comparison

| Check | Pre-normalize | Post-normalize | Notes |
|---|---|---|---|
| Duplicate vault_id | 1 | 0 | R9 collision fixed |
| `parent_location` dangling | 35 | 0 | All wikilink forms resolved |
| Frontmatter required/value issues | 112 | 1* | * Drakenvale.md `type: concept` — intentional special case |
| Forbidden legacy fields | 0 | 0 | clean throughout |
| `region` wikilink form | ~46 | 0 | All normalized to `hollow-crown` |
| `status: working` | ~45 | 0 | All set to `locked` |
| Filename / H1 mismatch | 15 | 15 | Not real issues — aliases added cover wikilink resolution |
| Folder / parent coherence | 12* | 3* | * False positives in inspection logic (settlement files in own folders correctly point to region as parent) |
| Broken wikilinks (unexpected) | 64 | 64 | Unchanged — these are pending NPC/group/concept entities awaiting future migration batches, not normalization scope |

*The 15 filename/H1 flags and 3 folder-coherence flags are false positives in my checking logic, not real defects.* Aliases handle the filename/H1 cases; settlement files in their own folders correctly reference the parent region in `parent_location`.

---

## What this refresh does NOT do

- Does not author new entities. No NPCs, groups, factions, history nodes, artifact nodes.
- Does not resolve the ~64 broken wikilinks for unauthored entities (Heartwarden, Council of Elders, House Heartwood, Discordant War, etc.) — those need future content migration batches.
- Does not touch sub-content within a note's body. Only frontmatter.
- Does not address the source-vault upstream issues (4× `region_id: hollow_crown` underscore typos) — those are upstream cleanup, separate concern.
- Does not modify any 2.0 implementation, prompt files, or registries.

---

## Apply commands

From inside the user vault repo (`mystic-weave`):

```bash
cd /Users/danielhowe/Documents/Vaults/mystic-weave

unzip -o ~/Downloads/MIGRATION_NORMALIZE_1.zip

git add 10_world/ MIGRATION_NORMALIZE_1.md
git commit -m "Normalize 1: frontmatter convention reconciliation across earlier-batch geography notes — region/status/parent_location/type normalization, R9 vault_id collision fix, region short-form aliases, The-X alias coverage; 51 files modified"

git push
```

Bundle has no wrapper folder — `unzip -o` extracts `10_world/` and `MIGRATION_NORMALIZE_1.md` directly into the vault root.

---

## Process notes

Inspection was run twice: once before authoring this patch (revealed the issues), once after applying this patch on top of the post-R11 vault state (verified resolution). Final post-normalize inspection: 0 vault_id collisions, 0 dangling parents, 0 legacy fields, 0 frontmatter required/value defects beyond the intentional Drakenvale.md special case.

After this lands, the geography layer of the vault is structurally uniform. The remaining "issues" surfaced by strict mechanical inspection are either inspection-rule false positives (filename/H1, folder/parent) or pending content authoring (broken wikilinks to future-batch entities).

The user vault is now in a clean state suitable for the migration → mechanical-design pivot.
