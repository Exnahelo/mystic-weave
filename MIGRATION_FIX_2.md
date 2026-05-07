---
type: meta
status: locked
date: 2026-05-07
---

# Migration Fix 2 — Varethyn's Lair correction + conventions update

## What went wrong

In Refresh 2, I built a stub for Varethyn's Lair claiming "no vault file exists yet." That was wrong. The vault file is at `prompts/world_vault/hollow_crown/underworld/varethyns_lair.md` — listed in the file tree in the project instructions from the start of our conversation. I tried two guessed paths under `stronghold_of_drakenvale/` and `crystal_caverns/`, didn't find the file, and built a stub from your verbal description rather than searching the file tree systematically or asking.

The vault file is substantively richer than my stub. It includes scene texture, specific furnishings, the discovery mechanism, an outward exit into the Crystal Caverns, and a new NPC reference (Serevane at Platinum Oath Monastery).

## What this fix does

### Replaces Varethyn's Lair note (canonical content + canonical path)

- **Old path:** `10_world/geography/hollow-crown/locations/stronghold-of-drakenvale/Varethyn's Lair.md`
- **New path:** `10_world/geography/hollow-crown/regions/crystal-caverns/Varethyn's Lair.md`

The new path reflects vault canon: the Lair's `parent_location_id` is `crystal-caverns`, not the Stronghold. The connection to the Amethyst Vault is a hidden tunnel; the Lair's home is the Caverns.

The new note includes everything in the vault file:

- Long spiral tunnel descending through the Heartmass into living crystal stone
- Specific furnishings: stone resting platform, reading ledge with three volumes, standing mirrors (older cousins of the Vault mirrors, structurally different), crystal music instrument
- Outward exit from the Lair into the broader Crystal Caverns — unmarked, indistinguishable from a hundred other crystal alcoves
- Discovery mechanism: tunnel's upper entrance masked by an arrangement of standing stones in the Vault that attuned visitors do not normally perceive
- Function: sanctum, deep-privacy mediation, hidden Caverns access, preserved knowledge
- New NPC reference: **Serevane** at [[Platinum Oath Monastery]] — knew [[The Platinum Warden]], old enough to remember when the tunnel was cut

### Updates conventions-frontmatter.md

Adds `lair` as a recognized type alongside `location`, `settlement`, and `sacred-site`. Other dragon lairs exist in the world vault file tree (`eryndors_lair.md`, `zarkeros_lair.md`) and will use this type when migrated. Also adds an explicit note that mechanical fields like `threat_level` and `discovered` are out of scope for migration.

## Apply

The fix involves moving a file. Two steps:

```bash
# 1. Delete the old stub at the wrong path
cd ~/Documents/Vaults/mystic-weave/
rm "10_world/geography/hollow-crown/locations/stronghold-of-drakenvale/Varethyn's Lair.md"

# 2. Apply the fix bundle
unzip -o ~/Downloads/mystic-weave-fix-2.zip
rm ~/Downloads/mystic-weave-fix-2.zip
```

If the old subfolder ends up empty after step 1, that's fine — leave it; subsequent batches will populate it (it's the right home for other Stronghold-internal sub-locations, just not this one).

## What I'm changing in process

When a vault file should plausibly exist per source materials and I can't find it on the first guess, I will:

1. Re-scan the file tree provided in the project instructions, more carefully than I did this time
2. If still nothing, ask you for the path rather than fabricate a stub

Stub notes implying "no canon" when canon plainly exists somewhere I haven't searched is a worse failure than asking.

## Wikilinks introduced but unresolved

These are now newly referenced and don't yet have notes:

- **Serevane** — NPC at Platinum Oath Monastery; knows the Lair tunnel's history. Will need an NPC note eventually.
- [[Platinum Oath Monastery]] — referenced in earlier notes too; will need a location note.
- [[Crystal Caverns]] — the canonical parent. Will need its own region note when Refresh 5 (regions) lands.
- [[Deephollow]] — referenced in passing; will need a location note when Refresh 5 lands.

## After applying

Open `Varethyn's Lair.md` in Reading view. Verify the path is `regions/crystal-caverns/Varethyn's Lair.md`. The note replaces the previous stub and should read as substantive canon, not a placeholder.

If anything else in the world vault file tree is in a folder I might miss (a non-obvious parent), surface it and I'll handle it as I encounter it.
