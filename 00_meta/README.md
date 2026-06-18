---
type: meta
status: locked
---

# Mystic Weave Vault

This vault holds the worldbuilding and mechanical design corpus for Mystic Weave (Drakenvale / Hollow Crown).

## Top-level structure

- `00_meta/` — vault docs, conventions, this README
- `10_world/` — lore. **Input. Locked.** Setting material.
- `20_mechanics/` — mechanical design. **Active work.**
- `30_inbox/` — unsorted, triage, raw dumps
- `90_archive/` — deprecated material, kept for reference
- `_templates/` — Templater entity templates
- `_attachments/` — images, diagrams

## The lore/mechanics boundary

The folder split is physical. The discipline is not.

`10_world/` is locked input. The mechanical layer runs *in* that world; it does not redesign it. When working in `20_mechanics/`, design from the vision and design problem, not by reverse-engineering or anchoring to specific lore entities.

Cross-linking between the two is fine. Load-bearing dependencies of mechanics on specific lore entities are a smell — that's mechanics-via-lore, which is the drift the project exists to escape.

## Conventions

See:
- [[conventions-frontmatter]]
- [[conventions-tags]]
- [[conventions-linking]]
- [[conventions-naming]]
