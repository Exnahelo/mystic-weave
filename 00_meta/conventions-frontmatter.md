---
type: meta
status: locked
---

# Frontmatter conventions

Every entity note carries YAML frontmatter. Templates enforce this.

## Required fields

```yaml
---
type: <entity type>
status: <lifecycle state>
---
```

## Optional fields (use when meaningful)

```yaml
aliases: [name, alternate, epithet]
tags: [theme, cross-cutting]
related: ["[[Other Entity]]"]
region: "[[Hollow Crown]]"
era: pre-cataclysm | cataclysm | post-cataclysm | current
contested: true   # in-world disagreement is canonical
vault_id: kebab-case-id   # canonical world vault id when sourced from vault
---
```

## `type` values

Entity types — keep this list small and stable:

- `npc`
- `faction`
- `location`
- `region` — major geographic region (Feywood, Crystal Caverns, Volcanic Highlands)
- `region-zone` — sub-region within a larger region; ecologically or functionally distinct distributed system rather than a point location (Heartwater Basin within the Feywood)
- `settlement` — for cities, towns, named civic settlements
- `district` — sub-zone of a settlement; canonically distinct functional/social ring of a larger settlement (the five Thornveil districts)
- `route-node` — threshold zones, approach corridors, sanctioned crossings; not a settlement, not a region, but a defined zone whose function is passage or boundary (Feywood Border, the Approach files)
- `lair` — for personal sanctums, typically draconic; distinct from generic `location` because the resident defines the space
- `sacred-site` — for spaces canonically distinct from ordinary location (Heartwood, Silent Grove)
- `deity`
- `dragon`
- `people` (ancestry / cultural group)
- `artifact`
- `concept` (magic field, doctrine, abstract notion)
- `event` (historical event)
- `era` (historical age)

Mechanical / meta types:

- `analysis` — `mw_mech_*` analysis docs
- `decision` — committed mechanical positions
- `exploration` — wip mechanical thinking
- `meta` — vault docs, conventions

## `status` values

**Default for lore content is `working`, not `locked`.** Lore is current canon, in active use, may be revised for gameplay reasons. `locked` reserves for structural elements where revision would cascade widely.

- `working` — current canon, in active use, may be revised. **Default for most lore notes.**
- `locked` — settled at structural level. Revision would force cascade across many notes. Reserve for cosmology, governing framework, the basic shape of the world.
- `wip` — actively being written, not yet stable
- `draft` — rough, unreviewed
- `open-question` — flagged for resolution
- `contested` — in-world canonically disputed (Heartstone origin, Unchanged nature, Heartwood origin traditions)
- `deprecated` — superseded; kept for archive

## Mechanical fields are out of scope

Frontmatter does not carry gameplay mechanics. The world vault includes fields like `threat_level` and `discovered` that serve runtime gameplay; these are not migrated into entity notes. Migration captures the world descriptively, not its game-mechanical handling.

## Notes

Don't add fields speculatively. Add when a query or view needs them.
