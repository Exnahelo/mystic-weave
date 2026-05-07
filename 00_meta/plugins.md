---
type: meta
status: locked
---

# Plugins — minimum viable

Install these. Skip everything else until a need surfaces.

## Core (settings → core plugins)

Enable:
- Backlinks
- Outgoing links
- Tag pane
- Templates (built-in, lighter than Templater for simple use)
- Graph view
- Outline
- Word count

Disable:
- Daily notes (unless you actually want a journaling workflow)
- Random note (noise)

## Community plugins

Install in this order:

1. **Dataview** — non-negotiable. Provides queries across notes via frontmatter. The mechanics MOC and inbox triage already use it.
2. **Templater** — replaces the built-in Templates with a more capable version. The `_templates/` folder is configured for this. Settings → Templater → Template folder location → `_templates`.
3. **Excalidraw** — diagrams. Use for relationship maps, faction trees, magic-field assignments. Saves as `.excalidraw` files; embed in notes with `![[diagram-name]]`.
4. **Tag Wrangler** — rename and merge tags from the tag pane. Prevents tag drift.

## Optional (add only when a need surfaces)

- **Map View** — only if geographic queries become a thing
- **Kanban** — only if a workflow needs board view
- **Timeline plugins** — none yet recommended; era frontmatter + Dataview covers most timeline needs

## Templater configuration

After installing:
1. Settings → Templater → Template folder location: `_templates`
2. Settings → Templater → Trigger Templater on new file creation: ON
3. Settings → Templater → Folder templates: map each entity folder to its template (e.g. `10_world/npcs/` → `_templates/npc.md`)

This makes new files in entity folders auto-apply the right template.
