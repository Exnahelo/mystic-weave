---
type: meta
status: locked
---

# Mechanics — Map of Content

Top-level entry point into `20_mechanics/`.

## Foundation

- [[mw_vision]]
- [[mw_design_problem]]
- [[NEXT]] — concise re-entry point and immediate TODO

## Analysis

```dataview
LIST
FROM "20_mechanics/analysis"
SORT file.name ASC
```

## Decisions

```dataview
TABLE status, date
FROM "20_mechanics/decisions"
WHERE type = "decision"
SORT date DESC
```

## Exploration

```dataview
LIST
FROM "20_mechanics/exploration"
WHERE status = "wip" OR status = "draft"
SORT file.mtime DESC
```

## Open questions

```dataview
LIST
FROM "20_mechanics/open-questions"
SORT file.name ASC
```

## Discipline

This work designs from the vision and the design problem, not from existing implementation. Drift signals: anchoring on prior structures, optimizing for ease of migration, treating exploration as decision. Surface drift when it appears.
