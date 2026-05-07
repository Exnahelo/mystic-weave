---
type: meta
status: locked
---

# Linking conventions

The graph rewards aggressive linking. Tag sprawl punishes aggressive tagging. Tilt accordingly.

## Rules

1. **Wikilink every entity mention.** Even casual ones. The graph is the payoff.
2. **Use alias syntax for prose flow.** `[[Eryndor the Radiant|Eryndor]]` reads naturally and still resolves to the canonical note.
3. **Don't link generic words.** "Mountain", "sky", "blood", "stone" — not entities.
4. **Don't link the same entity twice in the same paragraph.** First mention links, subsequent mentions are bare text. Exception: section headers and bullet lists.
5. **Aliases array carries known variants.** The Unchanged note's frontmatter lists `Far-Come`, `The Visitor`, `The Nameless`, `One-Who-Is-Not`. Any of those mentioned in prose autocompletes to the canonical note.

## When a link doesn't exist yet

Link anyway. Obsidian shows unresolved links in the graph and in the unresolved-links pane. That's a worklist.

## Backlinks vs explicit `related`

Backlinks are automatic and visible in the right pane. Don't duplicate them in a `related:` frontmatter field by default. Use `related:` only when:
- The relationship is asymmetric and you want it surfaced from this side
- The related note doesn't actually mention this one in prose
- A Dataview query needs to traverse the relation

## Cross-folder links

`10_world/` ↔ `20_mechanics/` links are allowed but worth a pause. If a mechanical note links a specific NPC or location, ask: is the mechanic *about* that entity, or is the entity an example? If example, the link is fine. If load-bearing, that's a smell — the mechanic should probably reference an abstract concept, not a specific entity.
