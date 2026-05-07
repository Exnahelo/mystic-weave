---
type: meta
status: locked
date: 2026-05-07
---

# Migration Fix 1 — Heartmass clarification

## What this fixes

The source materials describe Heartmass with present-tense phrasing ("rises the Heartmass") that reads as if the Heartmass currently exists alongside the Stronghold. It does not. The Heartmass was the formation; the [[Stronghold of Drakenvale]] is what it was carved into. There is no present-day Heartmass distinct from the Stronghold.

I introduced this misreading into batch 1 and propagated it across batches 2 and 3. This bundle corrects it.

## What's in this fix

- **`10_world/concepts/Heartmass.md`** — new note. Explicitly defines Heartmass as a historical/origin term and disambiguates it from the Stronghold. Existing wikilinks `[[Heartmass]]` across the corpus will now resolve here.
- **`10_world/geography/hollow-crown/Drakenvale.md`** — replaces the existing file. Fixed present-tense language: now reads "At the center of the Hollow Crown rises the Stronghold of Drakenvale — a monumental fortress carved from the Heartmass."
- **`10_world/geography/hollow-crown/Hollow Crown.md`** — replaces the existing file. Same fix.

## What's NOT being changed

References to the Heartmass in historical contexts (carving, founding, excavation) remain as-is in:

- `The Founding.md`
- `War of the Fallen.md`
- `Stronghold of Drakenvale.md`
- `The Cataclysm.md`
- `Heartstone.md`

Those references describe historical events ("carved the Stronghold from the Heartmass") and read correctly as past tense or origin context. They don't need patching.

## How to apply

Standard merge — files with the same path and name will overwrite the existing ones:

```bash
cd ~/Documents/Vaults/mystic-weave/
unzip -o ~/Downloads/mystic-weave-fix-1.zip
rm ~/Downloads/mystic-weave-fix-1.zip
```

The `-o` flag forces overwrite without prompting. Drakenvale.md and Hollow Crown.md will be replaced; Heartmass.md will be created new.

## Related correction to my batch 3 manifest

Batch 3's manifest listed Heartmass as a missing location for batch 4. Disregard that. Heartmass does not need a location note — the concept note in this fix is the right form. Batch 4 should focus on actual present-day locations.

## What I should have done differently

I read "rises the Heartmass" in the source and treated it as describing a current physical feature. The user's clarification is the correction: the source is using a slightly misleading present-tense for what is actually historical formation. This is the kind of source-material ambiguity that needs explicit resolution rather than literal interpretation, and I should have flagged the ambiguity at the time rather than locking it in across multiple notes.

For future migrations: when source materials use present-tense for historical formations, I'll surface the ambiguity before encoding it.
