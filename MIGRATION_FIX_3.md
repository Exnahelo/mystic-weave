---
type: meta
status: locked
date: 2026-05-07
---

# Migration Fix 3 — Border connections + Sylvara naming

## What this fix does

### Feywood Border connections corrected

I had pulled the Border's connections directly from vault canon, which listed five connected nodes (Dracelune, Dewhollow, Feywood, Western Temperate Forest, Vaelmere). That overconnects the graph — the Border is the boundary around the [[Feywood]], and its only meaningful node-to-node connection is the inward route to [[Vaelmere]].

**Changes:**

- `parent_location: "[[Western Temperate Forest]]"` → `parent_region: "[[Feywood]]"`. The Border isn't a sub-location of WTF; it's the threshold around the Feywood.
- Connected nodes reduced to **just `[[Vaelmere]]`** — the common inward route after sanctioned crossing.
- Aliases tag list — removed `western-forest` since it's no longer the parent.
- Body text retained where it accurately describes the realm-side approach (the road through the western temperate forest still exists; it's just not encoded as a graph edge).

The road from [[Dracelune]] still leads to the Border in the world's geography — that's accurate scene texture in the description. It's not a connected node because the Border is a threshold, not a hub.

### Heartwood Estate — Sylvara and Dusk named

Per your direction, the family roster now names [[Sylvara Heartwood]] explicitly in the immediate family section. **Dusk** appears alongside her as her bonded moonthorn wolf companion.

Sylvara remains flagged as the player character: the NPCs section notes that her current state is tracked in the character system rather than in world data. This preserves the canonical reference to her presence at the Estate without locking her in-game state into static world description.

[[Caelthir Vaelaryn]] also added to the NPCs list (was previously only mentioned in the in-laws prose).

## Apply

Straight overwrite — no file moves, no folder changes:

```bash
cd ~/Documents/Vaults/mystic-weave/
unzip -o ~/Downloads/mystic-weave-fix-3.zip
rm ~/Downloads/mystic-weave-fix-3.zip
```

## What changed

- `Feywood Border.md` — frontmatter (`parent_region` instead of `parent_location`), connected nodes reduced to Vaelmere only, tags adjusted
- `Heartwood Estate.md` — Sylvara named in family, Dusk named, Caelthir added to NPCs, explicit PC-status note

## Wikilinks introduced

- [[Sylvara Heartwood]] — will resolve to nothing until/unless a PC note is created. That's deliberate; the reference exists, the note is the user's decision.
- [[Caelthir Vaelaryn]] — referenced in two places now; will resolve when NPC notes get migrated or when a Vaelaryn-cluster refresh happens.
- [[House Vaelaryn]] — referenced in two places now; will resolve when house/faction notes get migrated.

## Process note

The Border connection error was a different failure mode than the Varethyn's Lair one. There the file existed and I missed it. Here I did read the file, but I copied vault graph edges directly without weighing whether each one made sense in your model. Vault is canon for content; for graph topology, I should weigh whether each edge serves the world's structure rather than transcribe the vault's edge list. Going forward: when a vault file lists 4+ connections, I'll examine each one and flag any that look spurious, instead of carrying them all forward.

## After applying

Open `Feywood Border.md` and `Heartwood Estate.md` in Reading view. Confirm the Border now shows just `Vaelmere` as connected, and the Estate's family roster reads naturally with Sylvara and Dusk named.

Then ready for **Refresh 4a** (sub-locations: 11 files — Reading Glade + Training Grounds + Thornveil's 5 districts + Vaelmere's 4 sub-buildings) when you give the go.
