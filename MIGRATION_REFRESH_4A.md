---
type: meta
status: locked
date: 2026-05-07
---

# Migration Refresh 4a — Feywood interior sub-locations

## What's in this refresh

### Refreshed (1)

- **`Feywood Border.md`** — parent reverted to `parent_location: "[[Western Temperate Forest]]"` per your correction (the Border zone is geographically *in* the WTF, outside the Feywood). Connected nodes remain just `[[Vaelmere]]` (the one sanctioned road in). Added a note at the top about the Border being a perimeter zone — one road in, but the perimeter is long.

### New entity notes (11)

Under `10_world/geography/hollow-crown/regions/feywood/`:

**Silent Grove sub-files (`silent-grove/`):**

- **`Reading Glade.md`** — type `location`. Druidic study site within the [[Silent Grove]]. Observation circles for ambient-field reading; oral-tradition seats for transmission across generations; individual study spaces. **The Feywood's highest continuous ambient-field intensity** outside the Heartwood itself. Drawn from vault.
- **`Training Grounds.md`** — type `location`. The [[Heartwarden]] seven-year cycle training site. Cohorts of 8-16. Five named training spaces (Long Path, Sparring Circles, Archery Lanes, Quiet Spaces, Ritual Ground). Drawn from vault.

**Thornveil districts (`thornveil/`):**

- **`Heartwood Approach.md`** — type `district`. Innermost ring around the [[Heartwood]]. [[Council of Elders]]' primary chambers. **House Heartwood's Thornveil seat** is here (NOT in the Noble Groves). Drawn from vault.
- **`Noble Groves.md`** — type `district`. Ring of noble family estates. **Names the seven major elven houses.** [[Greenshield]] HQ here. Drawn from vault.
- **`Common Hearth.md`** — type `district`. [[Thornveil]]'s largest residential district. **Cluster dwelling structure** (4-20 dwellings per cluster) explicit. Lunar-and-event observance rhythm. Drawn from vault.
- **`Crafthall.md`** — type `district`. Institutional craft district. **Five major craft lineages** (Weaving, Metalwork, Coaxed Woodcraft, Feywood Alchemy, Specialty trades). Drawn from vault.
- **`Outer Bounds.md`** — type `district`. Realm-facing edge of [[Thornveil]]. Trade staging, integration zone for newer residents. Drawn from vault.

**Vaelmere sub-buildings (`vaelmere/`):**

- **`Trade Hall.md`** — type `location`. Largest building in [[Vaelmere]]. Trade Master's offices. **Trade Envoy professional corps** (distinct from diplomats and military). **Hard export exclusions** (Oathbloom, Heartwood material, Witheroak — never leave the Feywood). Drawn from vault.
- **`Wardens Hall.md`** — type `location`. Vaelmere civic seat. Modest by realm standards. Distinct from Trade Master and Greenshield Captain authorities. Drawn from vault.
- **`Guest House.md`** — type `location`. Standing accommodation for sanctioned realm visitors. Three meals daily, plant-forward Feywood food, no realm ale routinely available. Drawn from vault.
- **`Commons Hearth.md`** — type `location`. Vaelmere's shared kitchen / social anchor. Distinct from [[Common Hearth]] (which is a [[Thornveil]] district — note added explaining the distinction). Drawn from vault.

### Conventions update

- **`conventions-frontmatter.md`** — added `district` type for sub-zones of a settlement (the five Thornveil ring-zones use this; vault canon).

## Apply

```bash
cd ~/Documents/Vaults/mystic-weave/
unzip -o ~/Downloads/mystic-weave-refresh-4a.zip
rm ~/Downloads/mystic-weave-refresh-4a.zip
```

Overwrites: `conventions-frontmatter.md`, `Feywood Border.md`. Creates 11 new files in three new subfolders (`silent-grove/`, `thornveil/`, `vaelmere/`) under `regions/feywood/`.

## New canonical content surfaced

Substantial. Worth reading the manifest section carefully.

### The seven major elven houses

The Noble Groves note canonically names **seven major elven houses**:

1. **[[House Heartwood]]** — wild heritage, [[Heartwood]] custodianship, proving-wild tradition. *Does not hold a Noble Groves estate.* Two seats: [[Heartwood Estate]] (Outer Wild) and the Thornveil seat in the [[Heartwood Approach]].
2. **[[House Vaelaryn]]** — diplomacy, outsider-facing, **highest non-elf integration**. [[Caelthir Vaelaryn]] currently senior figure.
3. **[[House Silverbow]]** — wild harvest, hart-tradition, old-growth estate stewardship.
4. **[[House Thornmere]]** — [[Greenshield]] tradition, defensive vinework, founding-myth secondary role.
5. **[[House Dawnvale]]** — major druidic family; bloom, lunar, field-reading tradition.
6. **[[House Greybranch]]** — oral law, memory-keeping, [[Council of Elders|Council]] process.
7. **[[House Ironsap]]** — sanctioned deadfall, tools, woodcraft, material restraint.

Several dozen minor houses also hold groves but lack the distinctive public ethos of the seven majors.

### Specific canonical references

- **Cluster dwellings.** [[Common Hearth]] (Thornveil) organizes around clusters of 4-20 dwellings with shared hearth, garden, and gathering space. Most Thornveil residents live in clusters; cluster identity precedes district identity.
- **Drake currency.** Realm currency referenced canonically in the Common Hearth note. Used in Thornveil mostly for realm-import goods passed from Vaelmere; elves do not coin their own commerce internally.
- **Crafthall's five lineages.** Weaving, Metalwork, Coaxed Woodcraft (the elven method of shaping living wood), Feywood Alchemy (slower and more relational than realm alchemy), Specialty trades.
- **Trade Envoy corps** is a distinct professional category — not diplomats, not military. Career path from Vaelmere trade community, century-spanning careers, realm-counterpart relationships across multiple realm-side generations.
- **Hard export exclusions.** Oathbloom, Heartwood-derived material of any kind, living Witheroak wood — *never* leave the Feywood under any circumstances. Enforced rigorously at [[Trade Hall]].
- **Sylvara Heartwood** is named in the [[Heartwood Approach]] vault canon as Lethariel's granddaughter — confirming the family relationship I'd been guessing at.
- The **Feywood's seven-stage decline order** is referenced in Heartwater Basin canon — Thornveil's plots register Heartwood stress first, the Basin second. The full seven-stage sequence isn't laid out in the files I've read so far; I'll surface it when a vault file with it appears.

### New Tier-3 generative roles surfaced

- Trade Envoy Crafthall Liaison
- Trade Envoy Outer Bounds Liaison
- Trade Envoy (Vaelmere-based)
- Commons Keeper
- Guest House Keeper
- Heartwarden Captain (interim) — distinct from Lethariel-as-emeritus

## Wikilinks now resolved

- All 11 new entities, plus the Feywood Border revert
- Sub-locations referenced from the parent settlement notes (Refresh 3) now have targets

## Wikilinks introduced but unresolved (for Refresh 4b and beyond)

**Refresh 4b — Feywood groups (8 files):**
- [[Council of Elders]] (already widely referenced; will get its own note)
- [[Heartwardens]] / [[Heartwarden]] (the order)
- [[Greenshields]] / [[Greenshield]] (the order)
- [[Hall of Guides]]
- [[Hall of Trade]]
- [[Elder Roots]]
- [[Noble Families]] (likely the canonical roster of the seven majors plus minors)
- (Rangers — already noted as a sub-branch of Greenshields per earlier canon)

**Houses (need notes; possibly part of Refresh 4b through `noble_families.md`):**
- [[House Heartwood]], [[House Vaelaryn]], [[House Silverbow]], [[House Thornmere]], [[House Dawnvale]], [[House Greybranch]], [[House Ironsap]]

**NPC references:**
- [[Caelthir Vaelaryn]] (Vaelaryn senior)
- [[Sylvara Heartwood]] (PC; possibly no note required, but link will resolve to nothing for now)

**Geography from later refreshes:**
- [[Western Temperate Forest]], [[Dracelune]], [[Dewhollow]] — coming in Refresh 8

## After applying

Open `Noble Groves.md` in Reading view. The seven-houses canon is the most consequential addition in this batch — it gives the Feywood's noble structure proper depth and surfaces several houses (Vaelaryn, Silverbow, etc.) that haven't been in our migration before. Spot-check that the wikilinks read clean in the Reading-view rendering and that the housing distinction (Heartwood NOT in Noble Groves; Heartwood Approach holds the Thornveil seat) is unambiguous.

Then ready for **Refresh 4b** when you give the go: the 8 Feywood groups files, which should add the Council of Elders, the orders (Heartwardens, Greenshields, Rangers), the Hall of Guides, the Hall of Trade, Elder Roots, and likely the canonical noble-houses roster.
