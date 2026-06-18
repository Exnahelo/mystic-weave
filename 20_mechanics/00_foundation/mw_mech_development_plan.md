---
type: meta
status: wip
tags: [development-plan, foundation]
---

# MW Mechanical Foundation — Development Plan

**Purpose:** Ordered checklist of foundational design layers, with
the next steps detailed and longer-horizon steps sketched.

**How to read this:** Items marked `[x]` are done. Items in the
**current phase** are detailed enough to act on. Items in **later
phases** are provisional — the actual shape of those layers will
depend on what earlier layers reveal. Don't treat the later-phase
ordering as locked.

---

## Phase 1 — Physical Substrate

The container everything else lives in. Space, time, environment,
and movement through them. No entities, no characters, no
capability yet.

- [x] **Cosmic frame.** Star, planet (physical class), calendar,
      twin co-orbital moons with two-scale swap cadence,
      extra-solar Cataclysm. Documented in
      `mw_mech_cosmic_foundation.md`.

- [ ] **Planet surface — macro geography.** Continents, oceans,
      major climate zones, where the Hollow Crown sits on the
      globe. Not exhaustive lore — just enough that "the rest of
      the world exists and has shape." Hooks for eventual
      external travel and trade. The Hollow Crown is already
      mapped in detail; this layer is the rest of the planet.

- [ ] **Spatial model.** How places are represented mechanically.
      How places nest (planet → continent → region → settlement
      → district → structure → room). How containment works.
      How non-Euclidean pockets (Feywood) fit into a Euclidean
      base. How underground layers stack. What "location" means
      for an entity. This is the abstraction; the geography
      above is data filling it.

- [ ] **Time mechanics.** How time advances mechanically.
      Granularity (the smallest unit; the largest unit). What
      triggers an advance. What state changes during an advance.
      How scheduled events get tracked and fire. How variable
      advances (minutes vs. weeks vs. years) work without
      breaking. The calendar is already specified; this is the
      *machinery* of time, not the calendar.

- [ ] **Environmental state.** State that places carry and that
      varies with time: weather, season, hazards, ambient magic,
      resource availability. Distinct from geography (structural,
      stable) — environment is temporal state on top of
      geography. The canonical "weather mirrors dragons'
      emotional state" goes here.

- [ ] **Movement.** How entities traverse space. Travel time,
      terrain effects, routes vs. off-path, the existing 16km
      grid coexisting with named routes. Probably more
      exploration than recommendation, since it depends heavily
      on what space, time, and environment resolve to.

**End of Phase 1:** The physical substrate is complete. There is
a world with shape, time, and weather, and entities can move
through it — but no entities have been designed yet.

---

## Phase 2 — Entity Substrate (provisional)

What counts as a thing in the world. The abstraction characters,
NPCs, places, items, factions all flow from. Comes after Phase 1
because entities live *in* the physical substrate.

- [ ] **Entity model.** What qualifies as an entity. Identity,
      lifecycle, history. The vision principle "entities have
      identity, lifecycle, and history" is hard input here.

- [ ] **State shape.** Cross-cutting: mutable vs. append-only vs.
      transient vs. derived. Probably touched at every layer
      from here on; worth deciding the framework here.

- [ ] **Relationships.** How entities relate. Ownership, alliance,
      debt, oath, kinship, custody. Whether this is its own
      layer or implicit in entity state.

- [ ] **Knowledge.** Per-knower information. Propagation. How
      omniscience is avoided. The vision principle "knowledge
      is per-knower" is hard input here.

---

## Phase 3 — Character Layer (provisional)

The player's agent. A specialization of entity. Capability
representation lives here.

- [ ] **Character as entity specialization.** What's added on
      top of the entity abstraction.
- [ ] **Capability representation.** The big open question.
      Numerical scores, discrete competencies, mastery curves,
      tags-with-levels, hybrid? Innate vs. trained vs. acquired.
- [ ] **Possessions, condition, momentary state.** What persists
      vs. what's transient.

---

## Phase 4 — Action and Resolution (provisional)

When the character does things and the system determines outcomes.
Treated as one bundle: action, resolution math, outcome bands,
consequence application.

- [ ] **Action unit.** What constitutes one action.
- [ ] **Resolution mechanic.** The math.
- [ ] **Outcome bands.** Graduated success/failure.
- [ ] **Approach generality.** The test: one architecture serves
      combat, social, economic, magical, infiltration,
      performance, scholarship.

---

## Phase 5 — Specialized Capability (provisional)

- [ ] **Magic.** Cataclysm-derived. Whether it's a specialization
      of capability/action/resolution or its own subsystem.
- [ ] **Growth and advancement.** How characters change over time.

---

## Phase 6 — Narrative Containers (provisional)

- [ ] **Scene.** Moment-to-moment container.
- [ ] **Arc.** Longer thread.
- [ ] **Larger containers.** Quests, campaigns, generational
      threads — or whether these emerge from arcs rather than
      being formal structures.

---

## Phase 7 — External Faces (provisional)

- [ ] **Persistence.** Save model.
- [ ] **Narrator interface.** What the AI sees and how it
      interacts.

---

## Notes on the Plan

**Phase 1 is the only phase with detailed item shapes.** Later
phases are sketched in dependency order but their internal
structure will likely change as Phase 1 (and then Phase 2)
clarify what the higher layers actually need.

**Phases are not equal in size.** Phase 1 is probably 5–7
focused conversations. Phase 4 (action/resolution) is probably
the densest single layer in the whole plan. Don't read the
phase list as time-equal.

**Drift watch.** If a phase starts pulling in implementation
detail, scope expansion, or lore redesign, that's the signal to
stop and reset. The project exists to escape that drift.

**Document per layer, not per phase.** Each completed layer gets
its own `mw_mech_<topic>.md` so decisions are attributable to a
specific layer and can be referenced cleanly from later layers.
