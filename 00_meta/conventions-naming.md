---
type: meta
status: locked
---

# Naming conventions

## File naming

- **Entity notes**: title case, full canonical name. `Eryndor the Radiant.md`, `Hollow Crown.md`, `The Unchanged.md`
- **Concept notes**: title case, descriptive. `Nine Magical Fields.md`, `Draconic Maturity.md`
- **Mechanical analysis**: `mw_mech_<topic>.md` — snake case, lowercase. `mw_mech_character_assessment.md`
- **Mechanical decisions**: `mw_mech_decisions_<scope>.md`
- **Convention / meta docs**: `conventions-<topic>.md`, lowercase with hyphens

## Why mixed casing

Entity notes are read in prose ("see [[The Unchanged]]") — title case fits.
Mechanical docs are referenced by filename in workflows — snake case fits the project's existing convention from `mw_vision.md`, `mw_design_problem.md`.

Don't try to unify. They serve different reading contexts.

## Aliases handle "the"

Files like `The Unchanged.md` are titled with the article. Prose flows better with `[[The Unchanged|the Unchanged]]`. The canonical filename keeps "The" so it sorts and displays as a proper noun.

## Folder naming

Numbered prefixes on top-level folders only (`00_meta/`, `10_world/`, etc.). Subfolders use lowercase with hyphens: `hollow-crown/`, `magic-fields/`. Keep depth shallow — three levels max under a top-level folder.
