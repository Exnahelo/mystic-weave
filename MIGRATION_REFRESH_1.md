---
type: meta
status: locked
date: 2026-05-07
---

# Migration Refresh 1 — Foundational vault refresh

## Why this exists

Earlier batches were built from project-knowledge snapshot files (`world.md`, `geography.md`, etc.), which I treated as complete. They aren't. The canonical source is the world vault (`prompts/world_vault/**` in the GitHub repo), which is substantially richer and structured differently. I was instructed to ask before reading vault files; I didn't ask, and I built ~70 notes from incomplete source.

This refresh starts the correction. Per your decision, **Option B** — refresh existing batches from vault before continuing forward.

## What's in this refresh

### Updated convention (`00_meta/`)

- **`conventions-frontmatter.md`** — Status convention loosened. New default for lore is `status: working` (current canon, may revise). `locked` reserved for structural elements where revision cascades. `contested` available for canonically-disputed content. `vault_id` field added for traceability.

### Refreshed lore notes (5)

- **`Hollow Crown.md`** — refreshed. Vault root is structural-only; my snapshot version is more useful for navigation. Adjusted to align with vault canon (added [[Drakenvale City]] as separate from [[Stronghold]]).
- **`Drakenvale.md`** — restructured as **realm/sanctuary concept**, not city. Type changed from `region` to `concept`. File stays at the same path so it overwrites cleanly. Internal content rewritten to clarify it is the realm-identity, with the city and Stronghold as separate notes.
- **`Stronghold of Drakenvale.md`** — refreshed from vault. New content: scene texture from canon, internal layout, list of 9 sub-locations (each will be its own note in Refresh 2). Mentions [[Varethyn's Lair]] as discovery-gated, not in standard connections.
- **`Feywood.md`** — refreshed comprehensively from vault. Was the thinnest of my existing notes. Now includes liminal geometry, Heartwood-as-source-of-field, three military orders correctly (Heartwardens parallel to Greenshields, Rangers *within* Greenshields), trust-based protection, weather-as-health-signal, full diplomatic context.

### New note (1)

- **`Heartwood.md`** — created. The sentient living tree at the [[Feywood]]'s center. Long, comprehensive, drawn directly from vault. Covers: scene texture, three coexisting origin traditions, sentience canon, Council Chamber and Pool as internal features, Root Network displacement mechanic with four canonical outcomes, weather-as-health-signal, trust-based protection extending to non-elves, sacred features (First Root, Elder Stone, Reading Hollow, Watchpost), health linkage with the Feywood ("their health is one health").

## Apply

```bash
cd ~/Documents/Vaults/mystic-weave/
unzip -o ~/Downloads/mystic-weave-refresh-1.zip
rm ~/Downloads/mystic-weave-refresh-1.zip
```

The `-o` flag overwrites the existing `Hollow Crown.md`, `Drakenvale.md`, `Stronghold of Drakenvale.md`, `Feywood.md`, and `conventions-frontmatter.md`. Creates new files: `Drakenvale City.md`, `Heartwood.md`, and the `feywood/` subfolder.

## Folder structure additions

- `10_world/geography/hollow-crown/regions/feywood/` — new subfolder. The Feywood is rich enough to warrant a sub-tree for its locations (Heartwood now; Silent Grove, Thornveil, Vaelmere, Heartwood Estate in Refresh 2 or 3).

## Wikilink resolution after applying

These previously-unresolved or thin links now resolve:

- `[[Heartwood]]` — was unresolved across many notes; now points to the new comprehensive note
- `[[Drakenvale City]]` — newly distinguished from `[[Drakenvale]]` and `[[Stronghold of Drakenvale]]`

These wikilinks across earlier batches now point to a richer target:

- `[[Feywood]]` — substantially expanded
- `[[Stronghold of Drakenvale]]` — substantially expanded with sub-location enumeration
- `[[Drakenvale]]` — reframed as realm-concept

## Wikilinks that remain unresolved (worklist for Refresh 2)

Notes in this refresh reference entities that don't exist yet. These are the targets for Refresh 2:

**Stronghold sub-locations (9):**
- [[Draconic Hall]], [[Platinum Heart]], [[Amethyst Vault]], [[Arcane Conservatory]], [[Aeries]], [[Administrative Quarter]], [[Draconic Forge]], [[Sacred Pools]], [[Varethyn's Lair]]

**Feywood sub-locations (4):**
- [[Silent Grove]], [[Thornveil]], [[Vaelmere]], [[Heartwood Estate]]

**Feywood orders (3):**
- [[Heartwarden]], [[Greenshield]], [[Ranger]]

**Other Hollow Crown:**
- [[Southern Lake]], [[Draconic Grasslands]], [[Temperate Forest]], [[Volcanic Highlands]], [[Mystic Wetlands]], [[Crystal Caverns]], [[Shadowed Hollows]], [[Rift of Discord]], [[Dark Hold]], [[Alpine Peaks]], [[Inner Ramparts]]
- [[Temple of Mordrax]]
- [[Heartmass]] (already exists)
- [[Hall of Scales]] (institution location), [[Arcane Conservatory]] (institutional duplicate of Stronghold sub-location?)
- [[Zarkharath]], [[Infernal Forge]], [[Ashfield]], [[Crystalhaven]], [[Scalemere]], [[Stonemark]], [[Lastmark]], [[Greymantle]]
- [[Draconic Grasslands Edge]], [[Hall of Guides]]

**NPCs from vault:**
- [[Kaerys Emberclaw]], [[Lethira Vale]], [[Tazrik Flameweaver]] (anchor NPCs for Drakenvale City)

**House/family:**
- [[House Heartwood]]

This is a lot. Refresh 2 will not cover all of it — it'll focus on the Stronghold cluster (9 sub-locations).

## What I haven't refreshed yet (and why)

Notes from earlier batches that I have NOT refreshed in this pass. Their existing content is correct as far as it goes; richer vault content may exist for some.

**Need vault check in later refreshes:**

- Council dragons — Eryndor, Zarkeros, Varethyn (probably need vault check)
- Other dragons — Ardrynn (probably needs vault check)
- Other NPCs — Lethariel Heartwood, Platinum Warden (probably need vault check)
- Factions — Council, Wardens, Dragon Guard, Platinum Acolytes, Vigil, Mordraxian Rebels (groups/ folder in vault has these; need vault read)
- Sacred sites referenced from Stronghold — coming in Refresh 2

**Probably vault-stable (cosmology-level):**

- The eight peoples
- The Two
- The Unchanged
- Nine Magical Fields
- The Cataclysm
- Codex of Remembrance
- Oath of the Fallen
- Trial of Wings
- Heartstone (may need vault check; check in Refresh 2)
- Solveris, Mordrax (may have vault entries)
- Historical events (War of the Fallen, The Founding, Age of Harmony, Discordant War)
- Heartmass (just created, definition is mine)

## After applying

Spot-check `Heartwood.md` — open in Reading view. Verify the wikilinks render and the note is comprehensive. The Heartwood is the most important new content in this pass; it's the entity the entire Feywood structure depends on.

Then tell me to proceed to Refresh 2 (Stronghold sub-locations) or redirect.

## Process commitment going forward

For every entity from Refresh 2 onward, I will:

1. Read the relevant vault node(s) before writing
2. Cite the vault node in the note's `vault_id` frontmatter
3. Flag in the manifest which vault sources I drew from
4. Surface ambiguities or contradictions between vault and snapshot at the time of refresh, not after

This is what should have been happening from batch 1.
