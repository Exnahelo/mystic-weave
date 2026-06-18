---
type: meta
status: locked
---

# Archive

Deprecated material kept for reference. Do not edit. Do not link from active notes (except to mark something as superseded).

## Why archive instead of delete

History is occasionally load-bearing. Knowing what was tried and rejected is sometimes more valuable than the thing that replaced it.

## When to archive

- A note is superseded by a newer note: archive the old, mark `status: deprecated`, add `superseded_by:` frontmatter pointing to the replacement.
- Strategic docs from earlier design rounds that don't fit the current project's discipline.
- Old prompt files, schema docs, structure proposals from prior 2.0 design eras.

## Frontmatter for archived notes

```yaml
---
type: <original type>
status: deprecated
archived_date: YYYY-MM-DD
superseded_by: "[[Replacement Note]]"  # optional
reason: "Why this was archived. One sentence."
---
```
