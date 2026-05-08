---
type: location
aliases: []
tags:
  - alpine
  - forest
  - shelter
  - yeti-territory
  - wilderness
  - ironwood-ridge
  - inner-ramparts
vault_id: ironwood-ridge
region: hollow-crown
parent_location: inner-ramparts
status: locked
---

# Ironwood Ridge

A dense stand of frost-tolerant ironwood trees clinging to the mountain slope, their dark bark rimed with ice crystals. The canopy breaks the wind and muffles sound, creating pockets of eerie stillness. Frostwing Owls roost silently in the upper branches. Snowbound Yeti territory lies nearby — large tracks and claw marks on the trunks make that clear. Frostfire Lilies grow in clusters along the trail, their faint glow drawing the eye. Shelter is available among the root systems, but anything resting here is being watched.

## Tags

- alpine
- forest
- shelter
- yeti-territory
- wilderness
- inner-ramparts

## Connected Nodes

- [[Glacial Stream Crossing]]
- [[Wardline Threshold]]
- [[Inner Ramparts]]

## Authoring Notes

**Region relocation.** Source vault places Ironwood Ridge at `surface/western_temperate_forest/ironwood_ridge.md`, but the content is unambiguously alpine — frost-tolerant trees clinging to mountain slope, snowbound yeti territory, ice-rimed bark, Frostwing Owls. Connectors point to [[Glacial Stream Crossing]] (Inner Ramparts) and [[Wardline Threshold]] (Alpine Peaks), both authored in Refresh 7 under alpine sub-regions. The user-vault relocation places this node under [[Inner Ramparts]] based on:

1. **Content** — alpine character throughout frontmatter, description, and tags.
2. **Connector proximity** — Glacial Stream Crossing (Inner Ramparts) is the more proximate connector node; the ridge would naturally sit adjacent to it on a frost-tolerant mountain slope.
3. **Per user direction** — old connector node, low gameplay use, parent assignment based on connector logic. Inner Ramparts chosen.

The source-vault path-vs-content discrepancy is flagged for upstream cleanup. Same pattern as Varethyn's Lair (placed under `locations/` in source despite belonging in Crystal Caverns, resolved in R8).

**Frontmatter normalization.** Source had `region_id: hollow_crown` (underscore typo) — fourth occurrence in the migration. Normalized to `hollow-crown` here. Other instances: `draconic_forge.md` (R8), `deephollow_lower_tunnels.md` (R9), `lantern_and_mule.md` (R11). One upstream sweep can fix all four.

**Type normalization.** Source `type: wilderness` translates to user-vault `type: location` with `wilderness` preserved in tag set.

**Status.** Per user direction, this is "an old connector node" not actively used in gameplay for some time, "probably a few things out of date with it." Content preserved verbatim from source. If a future storyline pulls Ironwood Ridge back into active use, the node can be expanded with current canon at that time. Source content is preserved as-is to honor the original authoring even where some details may be stale.

**Connector reciprocity.** Existing user-vault notes for [[Glacial Stream Crossing]] and [[Wardline Threshold]] (R7) do not currently list Ironwood Ridge as a Connected Node. Reciprocal edges will resolve through Obsidian's backlink graph naturally; explicit reciprocal patches are deferred to a future topology pass if needed.
