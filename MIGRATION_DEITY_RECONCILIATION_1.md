# MIGRATION_DEITY_RECONCILIATION_1

**Type:** Content reconciliation — first pilot of the per-topic reconciliation format
**Scope:** All three deity files in `10_world/deities/`
**Source vault:** `Exnahelo/mystic-weave`, branch `main`
**Predecessor:** `MIGRATION_NORMALIZE_1` (commit `68204ed`)

---

## What this is

The first per-topic content reconciliation patch. Where `MIGRATION_NORMALIZE_1` was schema-only and limited to the geography layer, this patch reframes content in the deity layer based on canonical-framing decisions made during reconciliation review (V1 → V2 → V3).

Three vault files updated:
- `10_world/deities/Solveris.md`
- `10_world/deities/Mordrax.md`
- `10_world/deities/The Unchanged.md`

No new entities authored. No other layers touched.

---

## Canonical framing established

Five framing decisions now treated as canon:

1. **Solveris and Mordrax are a primal cosmic polarity, not good vs. evil.** The conflict between them is the dynamic by which the world holds and changes. Mortal civic religion reads this as moral struggle; that reading is interpretation imposed externally. What they are is preservation-pole and dissolution-pole.

2. **Drakenvale's pantheon is the oldest known religion of the planet.** The dragons worshipped Solveris and Mordrax before the Cataclysm. Mortal faith on the planet, where it developed at all, descended from this older draconic understanding. Drakenvale is the most concentrated and theologically articulated expression currently known. The "oldest known" framing is deliberate — it does not foreclose other religions that may exist and simply aren't established in canon.

3. **The names "Solveris" and "Mordrax" are themselves of unknown origin.** No one knows where they came from. The dragons have always called them by these names. A religion whose own naming-history is lost is older than any preserved record. (Newly established this round.)

4. **Mordrax-worship outside the Hollow Crown is not necessarily forbidden.** The sanctuary's prohibition is sanctuary policy. Drakenvale does not police the wider world. Specific external societies are not currently established in canon, but their existence is plausible and not foreclosed.

5. **The Unchanged is the trickster archetype.** Its ambiguity is design, not unresolved canon. The figure plays the structural role tricksters play in mythologies generally. It is *not* part of the draconic-derived religion; it co-occurs alongside that religion in folk practice across cultures.

---

## Specific changes per file

### Solveris.md

**Frontmatter:**
- Added `vault_id: solveris`
- `aliases: [Solveris]` → `aliases: []` (single-name redundant)
- `tags: [solveris, deity, sacred, justice]` → `tags: [deity, planetary, primal-pole, preservation, sacred, justice]`
- `domains: [justice, mercy, law, protection]` → `domains: [justice, mercy, law, protection, preservation, continuity]` (added cosmic-pole framings)

**Body:**
- **Overview** rewritten: cosmic-polarity framing replaces "primary sacred anchor / moral foundation" framing. Added planetary-religion lineage (dragons → mortals).
- **Domains** restructured: list preserved, deeper-frame paragraph added explaining the mortal-civic / cosmic distinction.
- **Origin and scope** — *new section.* Establishes planetary-religion canon, names-of-unknown-origin canon, presence of other faiths, elven-religion separateness.
- **Worship** lightly tweaked: opening explicitly scoped to Drakenvale ("Within Drakenvale...") to align with planetary framing.
- **Mythology** rewritten: Platinum Warden's role reframed as "devotee whose acts shape Drakenvale's articulation," not "the deity's defining act." Establishes that Solveris is older than the Warden by an unknown depth of time.
- **Iconography** lightly extended with a paragraph noting iconography varies outside the Crown.
- **Connections** — *new section* (file previously had none). Lists Mordrax, Platinum Heart, Platinum Warden, Codex, Cataclysm, Elves.
- **Open questions** rewritten per V3 revisions: resolves cosmological-status questions under new framing, keeps deeper metaphysical questions, adds two-or-one polarity question.

### Mordrax.md

**Frontmatter:**
- Added `vault_id: mordrax`
- `aliases: [Mordrax]` → `aliases: []` (single-name redundant)
- `tags: [mordrax, deity, forbidden, contested]` → `tags: [deity, planetary, primal-pole, dissolution, forbidden, contested]`
- `domains: [corruption, ambition, power-without-restraint]` → `domains: [dissolution, unmaking, corruption, ambition, power-without-restraint]` (added cosmic-pole framings)
- `contested: true` retained

**Body:**
- **Overview** rewritten: cosmic dissolution-pole framing replaces "forbidden but theologically unavoidable" framing. Establishes that the Codex's framing is interpretation, not the deity's nature.
- **Domains** restructured: list preserved, deeper-frame paragraph added.
- **Origin and scope** — *new section.* Establishes planetary-religion canon, names-of-unknown-origin canon, that the Temple was inherited from older articulation, and that Mordrax-worship outside the Crown is not foreclosed.
- **Worship** rewritten: opening reframes the prohibition as sanctuary-choice rather than moral verdict ("not because Mordrax is evil — the cosmological frame holds her as one of the two oldest principles, not an evil one — but because the sanctuary chose Solveris's pole..."). Existing illicit-cult content preserved.
- **Mythology** rewritten: dissolution-pole / preservation-pole framing replaces "dark counterweight" framing. Closing line: "The conflict simply *is* the deities. They are their opposition."
- **Iconography** extended: notes iconography is suppressed within the Crown but varied outside, and adds a theologian's note that "voracious" reads as moral judgment rendered structural.
- **Connections** preserved and extended: Solveris added explicitly as cosmic counterpart, Dark Hold and Mordrax Cults added, Cataclysm added.
- **Open questions** rewritten per V3 revisions: resolves what-is-Mordrax questions under new framing, keeps deeper questions, adds two-or-one polarity question, retains Modern Era and cult-network questions.

### The Unchanged.md

**Frontmatter:**
- Added `vault_id: the-unchanged`
- `aliases` preserved (real cross-cultural names, not redundant)
- `tags: [unchanged, change, threshold, contested, folk-practice]` → `tags: [deity, trickster, change, threshold, folk-practice, contested]` (added `trickster`, dropped `unchanged`-as-name-tag since `vault_id` covers it)
- `contested: true` retained
- `domains: [change, threshold, transition]` retained (already clean)

**Body:**
- **Overview** rewritten: trickster-archetype framing leads the file. Existing ambiguity content preserved and tightened. **"Unknowability is the point"** added as explicit canonical statement.
- **Role** — *new section.* Names the trickster archetype directly, distinguishes it from Solveris/Mordrax central pantheon, establishes that the figure is "canonical *as ambiguity*, not despite it."
- **Domain** — preserved verbatim, no changes.
- **Nature** — preserved with one closing line added: "This shapeshifting quality is consistent with the trickster role: a figure that cannot be pinned to a form is also a figure that cannot be pinned to an outcome."
- **Worship** — preserved verbatim, no changes.
- **Doctrinal silence** — preserved verbatim, no changes.
- **Connections** — preserved and lightly extended: explicit note that the Unchanged co-occurs alongside the central pantheon in folk practice but is not part of the same religion.
- **Open questions** — preserved, with one new sub-question added: whether the trickster role this figure plays is *the* trickster of the planet, or one of several.

---

## Schema decisions taken (DEI-X2)

Defaults applied across all three files:

| Decision | Choice |
|---|---|
| `vault_id` | Added to all three (kebab-case) |
| `region` | **Not added.** Solveris and Mordrax are now planetary in scope per canon; The Unchanged is cross-cultural. `region: hollow-crown` would contradict the new framing. |
| `status` | `locked` retained on all three |
| Single-name `aliases` arrays | Dropped on Solveris and Mordrax (redundant with file name and vault_id). The Unchanged's multi-alias array kept (real cross-cultural names). |
| `domains` frontmatter ↔ body sync | Synced. Frontmatter now carries both mortal-civic and cosmic-pole domains where applicable. |
| `contested: true` | Retained on Mordrax and The Unchanged |
| Tags | Cleaned: dropped name-as-tag where vault_id covers it; added structural tags (`planetary`, `primal-pole`, `trickster`) reflecting new framing |

---

## Decisions deferred

| Decision | Status | Why deferred |
|---|---|---|
| **DEI-N2** (Elves.md religious-framing addition) | Deferred to peoples-layer reconciliation | Belongs to peoples layer scope; better to do all peoples-layer changes together |
| **DEI-N3** (future per-species deity development) | Forward work | Not part of stabilization; will surface when future species/region content develops |
| **DEI-X3** (world.md religion section update) | No change | world.md religion table is for formal Drakenvale civic religion; The Unchanged's exclusion is internally consistent. The Solveris/Mordrax religion table row remains accurate at world-overview compression. |

---

## Reconciliation sources

The new canon synthesizes:

| Source | Contribution |
|---|---|
| User session messages (this conversation) | Cosmic-polarity framing; planetary-religion lineage; trickster-archetype framing for The Unchanged; names-of-unknown-origin canon; Mordrax-outside-Crown framing; "oldest known" softening |
| Vault `deities/Solveris.md` (pre-patch) | Platinum Heart, Platinum Acolytes, Trial of Wings, Sacred Pools, Vigil, Codex relationship, Warden devotion |
| Vault `deities/Mordrax.md` (pre-patch) | Temple of Mordrax, Shadowed Hollows, Mordraxian Rebels, Dark Hold, Mordrax Cults, sealing-not-destruction history, suppressed iconography |
| Vault `deities/The Unchanged.md` (pre-patch) | All existing content (most preserved verbatim); ambiguity-by-design framing; cross-cultural names; Council/Codex silence |
| `world.md` Religion section | Solveris/Mordrax as the realm's pantheon; Platinum Acolytes; Codex tolerance of other peaceful faiths |
| `mw_mech_cosmic_foundation.md` Open Question 6 | The Unchanged folk-theology framing; Council/Codex non-naming |
| `peoples/Halflings.md` | The Unchanged's stronger folk presence among halflings (canon preserved, not modified) |

---

## Forward-work flags

Captured for tracking, no vault changes now:

1. **Per-species deity development.** Each established species will likely get its own faith framework eventually. Not at that point of development.
2. **Other planetary regions and their religions.** Drakenvale-internal religion is now well-articulated; planet-scale religious geography is wide-open.
3. **Specific Mordrax-worship societies.** External societies that openly hold Mordrax-aligned faith are now canonically possible, but none are established. If/when they become established, the Mordrax.md "Origin and scope" closing paragraph should be updated to reference them.
4. **Two-or-one theological dispute.** This is now a canonical open theological question. If future cosmology / mechanics work resolves it (e.g., the swap-cycle / moons material may bear on this), update both files' Open questions sections.
5. **Elven-religion explicit framing in Elves.md.** Deferred from this patch; pick up at peoples-layer reconciliation.

---

## Apply commands

From inside the user vault repo:

```bash
cd /Users/danielhowe/Documents/Vaults/mystic-weave

unzip -o ~/Downloads/MIGRATION_DEITY_RECONCILIATION_1.zip

git add 10_world/ MIGRATION_DEITY_RECONCILIATION_1.md
git commit -m "Deity reconciliation 1: cosmic-polarity framing for Solveris/Mordrax, trickster framing for the Unchanged, planetary-religion lineage canon, names-of-unknown-origin canon, Mordrax-outside-Crown softening, schema normalization (vault_id added, redundant aliases dropped, domains synced)"

git push
```

Bundle has no wrapper folder — `unzip -o` extracts `10_world/` and `MIGRATION_DEITY_RECONCILIATION_1.md` directly into the vault root.

---

## Process notes

This is the first per-topic content reconciliation in the new format. Took three rounds (V1 schema audit → V2 framing rewrite → V3 deltas). The format learned through iteration:

- **V1 missed "consistent but misframed" as a failure mode.** Files looked clean against schema but were anchored on the wrong central reading. Format had to expand from divergence-audit to framing-establishment-and-rewrite.
- **V2 produced full proposed text inline.** This worked — it gave a real artifact to react to.
- **V3 used a deltas document instead of re-issuing.** This also worked — kept iteration cheap.
- **One mid-V3 correction handled cleanly:** mistakenly conflated "names of unknown origin" with "names vary across cultures." User caught it; fix was a single paragraph replacement.

The format scales for low-content-divergence layers (deities). Higher-divergence layers (factions, NPCs) will likely need more structure — possibly a per-entity diff matrix rather than per-layer framing.
