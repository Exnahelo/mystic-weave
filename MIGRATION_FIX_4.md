---
type: meta
status: locked
date: 2026-05-07
---

# Migration Fix 4 — District topology + Lethariel-Sylvara relationship

## What this fix corrects

Four files updated. All overwrites; no file moves, no folder changes.

### 1. Heartwood Approach reframed

The 4a version treated House Heartwood as the named-and-special house with a "Thornveil seat" section, while other great houses got a generic "other noble residences" footnote. That was structurally wrong. **The Heartwood Approach is the innermost ring around the [[Heartwood]] tree, and *all* the great houses keep their estates here** — House Heartwood is one among several, not the named exception.

Changes:

- The "House Heartwood's Thornveil seat" section is replaced with a "great-house estates" section that names House Heartwood as one great house among several.
- The vault's "Heartwood Approach Estate" framing (which I had introduced in conversation as a coined proper name for House Heartwood's specific estate) is dropped. House Heartwood's estate here is just *House Heartwood's estate in the Approach* — descriptive prose, no proper-name treatment.
- House detail (tradition, lineage, ethos, senior figures) is **deferred to forthcoming house entity notes** rather than being captured here. The Approach note describes the *district*; house information lives with the house.
- Wikilinks placed for [[House Heartwood]], [[House Vaelaryn]], [[House Silverbow]], [[House Thornmere]], [[House Dawnvale]], [[House Greybranch]], [[House Ironsap]] — all unresolved until Refresh 4b reads `groups/noble_families.md`.

### 2. Noble Groves reframed

The 4a version inherited the vault's listing of the great houses as Noble Groves residents. **Per verbal canon, that's wrong: minor houses live in the Noble Groves; great houses live in the Approach.**

Changes:

- The "seven major elven houses" section is **stripped entirely**. That content belongs in [[Noble Families]] (canonical home, coming in Refresh 4b) and possibly individual [[House <Name>]] entity notes.
- The district is reframed as the **minor-houses district**.
- A "Distinction from the Approach" section explicitly states the great-vs-minor split and what determines it (public ethos, civic standing, historical depth — not wealth or scale).
- The Greenshield HQ stays in the Noble Groves. The Thornmere reference is reframed: the family estate proper is in the Approach (with the other great houses), but the HQ remains in the Groves on grounds long associated with the order. They're "down the path from each other," not co-located.
- The bottom note about specific noble estates being elevatable is dropped (no longer relevant since the great-houses content moved out).

### 3. Heartwood Estate — Sylvara is Lethariel's daughter

The 4a version named Sylvara in the family roster but didn't make the relationship explicit. Per verbal canon: **Sylvara is Lethariel's daughter. Caelthir Vaelaryn is Sylvara's father.** Elven longevity makes the timeline (Lethariel a Discordant War commander, ~300-600 years old; Sylvara the current Proving candidate at ~80) entirely consistent.

Changes:

- Opening paragraph names Sylvara as Lethariel's daughter explicitly.
- Family roster reorganized so Lethariel-and-Sylvara are presented as mother-daughter together.
- Caelthir is named as Sylvara's father (in addition to being Lethariel's partner / current generation's father-of-Heartwood-children).
- NPCs section updated to make these relationships explicit.
- The "Thornveil seat" reference is reframed to "estate in the [[Heartwood Approach]] district" — descriptive, no proper-name treatment, consistent with the Approach note's reframing.

### 4. Training Grounds — granddaughter → daughter

A one-word fix. The 4a version called Sylvara "her granddaughter" in the Instructors section. Corrected to "her daughter."

## Apply

```bash
cd ~/Documents/Vaults/mystic-weave/
unzip -o ~/Downloads/mystic-weave-fix-4.zip
rm ~/Downloads/mystic-weave-fix-4.zip
```

## Vault reconciliation flags

The vault's `prompts/world_vault/hollow_crown/surface/feywood/thornveil/noble_groves.md` currently lists the great houses (Vaelaryn, Silverbow, etc.) as residents of the Noble Groves. **Per your verbal canon, that's stale.** This file should eventually be updated to reflect: minor houses in Noble Groves, great houses in Heartwood Approach. Surfacing here so you can decide whether/when to update vault canon to match.

The vault's Heartwood Approach file describes the district as "where the oldest families have built their estates" — which is consistent with the corrected framing. No conflict there.

The vault's `feywood/thornveil/heartwood_approach.md` and the elf-side group files (`groups/noble_families.md`, etc.) may carry additional naming/topology that conflicts with the verbal canon. Refresh 4b will surface these as it reads through the groups/ directory.

## Wikilinks introduced (unresolved until Refresh 4b)

- [[House Heartwood]], [[House Vaelaryn]], [[House Silverbow]], [[House Thornmere]], [[House Dawnvale]], [[House Greybranch]], [[House Ironsap]] — house entity notes; canonical roster will come from `groups/noble_families.md` in Refresh 4b
- [[Noble Families]] — likely the canonical home of the full house roster + ethos descriptions

## After applying

Open `Heartwood Approach.md` and `Noble Groves.md` in Reading view. Confirm:

- Approach reads as "innermost ring, all great houses live here, Council chambers here, House Heartwood is one among several" — not as a Heartwood-specific note
- Groves reads as "outer ring, minor houses live here, Greenshield HQ here on traditional military grounds even though Thornmere itself is now in the Approach"
- The Heartwood Estate's family roster reads cleanly with the mother-daughter relationship explicit

Then ready for **Refresh 4b** when you give the go: 8 Feywood groups files (Council of Elders, Heartwardens, Greenshields, Hall of Guides, Hall of Trade, Elder Roots, Noble Families, Rangers). The Noble Families file is likely the canonical home for the seven-houses roster plus minor-houses-of-note, and may resolve some of the wikilinks introduced here.
