---
type: meta
status: locked
tags: [vision, foundation]
---

# Mystic Weave — Vision

**Purpose:** This document describes what kind of game Mystic Weave
is and what the design must serve. It does not specify how the
mechanical layer works — that is the design work this is input to.

---

## What the game is

A single-player text-based RPG set in Drakenvale and the wider
Hollow Crown world. AI-narrated, structurally backed by persistent
state. The player commands a single character (eventually a party,
eventually a household, eventually a small kingdom) and engages with
a world that responds to what they do.

Reality with magic. The setting is grounded — economies have
inflation, contracts have signatories, people remember insults,
debts compound, crops fail, weather happens. Magic exists and is
real, but it costs something every time and doesn't trivialize the
mundane systems it operates within.

Real consequences for real choices. The player's decisions matter
because the world remembers them. Killing the merchant changes who
runs the shop next month. Owing the gambling den means the gambling
den knows where you live. Burning a bridge means crossing the river
takes longer.

Many viable approaches to any goal. Combat, social, economic,
political, magical, performative, scholarly. None of these is
flavor layered on the others. Each is a first-class way of engaging
with the world. A scholar should be able to play through scenarios
without combat. A diplomat should be able to resolve crises through
relationships. A thief should be able to acquire by means other
than violence. The system must let the world be addressed by any of
these approaches; the choice of how is the player's.

The freedom is in choosing which problems to engage with. The
realism is in those problems having teeth.

## What gameplay feels like

The player makes decisions in fiction. The system determines
outcomes. Some outcomes succeed, some fail, some succeed at a cost,
some fail in interesting ways. The cost-and-tradeoff loop is the
core gameplay rhythm — every meaningful action has weight, every
outcome has follow-on effects, every situation contains real
choice.

A grounding example: a character loses a hand. Magical restoration
is possible but expensive. They need money. They use their
remaining skills (now operating one-handed) to find work or
opportunity. They learn of a pearl that could pay for restoration
but it's underwater and guarded. They acquire a time-limited
underwater-breathing potion. They dive. They face the guardian.
The chain isn't a designer-authored quest — it emerges from the
player's situation interacting with what the world contains. Every
link in the chain depends on real representation: the injury is
real, the magical economy is real, the one-handedness is real, the
potion's time mechanic is real, the pearl's location is real, the
guardian is real. None of these is hand-waved. Each is something
the system actually tracks and responds to.

Long arcs are part of the design. Not just multi-session quests,
but generational play. Characters can age. Heirs can inherit
imperfectly. Fiefdoms grow over years. Reputation accrues across
decades. Wealth attracts attention. The mechanical architecture
must support play that spans hundreds or thousands of turns within
a single character or across multiple generations.

NPCs are agents, not props. They have motivations, knowledge,
goals. They take actions. They form opinions and revise them. They
work with the player when it suits them and against the player
when it suits them. They scheme, ally, betray. When the player
isn't looking, they do not freeze; they continue pursuing what they
want, within whatever fidelity the architecture supports.

The player is not a designer. The system surfaces affordances —
what's possible here, who's nearby, what the character knows. It
does not enumerate menu choices that pre-shape solutions. The
player decides what to attempt; the system determines what's
attemptable and what happens.

## What the design must support

The architecture must serve the vision without compromise for what
was easy to build. It must support, eventually:

- Combat with real depth: tactical positioning, equipment quality,
  injury, fatigue, environmental conditions, varied weapons and
  styles. Variable resolution: tactical when granularity matters,
  abstracted when it doesn't, auto-resolved when it doesn't matter
  at all. Player choice of resolution depth.
- Social interaction with real weight: relationships persist, trust
  shifts on real events, reputation has audience-specific
  meaning, leverage and information are tradeable resources.
- Economic systems: prices, scarcity, debt, contracts,
  transactions that change ownership and obligation. Crafting that
  matters. Trade that compounds. Property that generates income
  or loses to neglect.
- Magic as a developed approach: time-cost, real consequence, no
  free abilities. Distinct flavors of magic with their own
  characteristic shapes, costs, and trade-offs. Magical research
  and learning as gameplay.
- Long-arc systems: fiefdom development, kingdom-building, faction
  influence, dynastic concerns. None of these are bolt-ons; the
  base architecture has to support them when they land.
- Persistent NPC state with archetype identities and accumulating
  history. NPCs change as a result of what happens to them.
- Knowledge as per-entity: information has a propagation graph;
  who knows what depends on who was present, who was told, what
  they've heard rumored. The world doesn't have global knowledge.
- Time-aware consequence: state decays during time advances unless
  maintained. Property deteriorates. Relationships drift. Schemes
  proceed. Crops grow or fail.
- Generational continuity: characters age and die. Heirs inherit.
  Some things carry forward; some things don't.
- Variable scale of action: personal (a fight, a conversation),
  local (a neighborhood, a village), regional (a county, a barony),
  world (a kingdom, a continental crisis). The system handles each
  scale with appropriate fidelity.

This list is not exhaustive. It illustrates the demands the
architecture must accommodate. The design should anticipate growth
into capabilities not yet enumerated.

## Design principles

These principles guide every architectural decision. Where choices
feel arbitrary, return here.

**Consequence over convenience.** When a design choice trades
realism for ease, prefer realism. The point is a world that
responds to what the player does, not a system that's easy to
extend.

**Best form, not first form.** Existing structures are not evidence
of correctness. If something is wrong-shape, replace it. Age is not
authority.

**Backend is authoritative.** The narrator AI describes; the
backend records and enforces. State that lives only in narration is
not state. Anything load-bearing has structured representation.

**Approach-agnostic resolution.** One resolution architecture
serves all approaches. Special-casing per approach is a sign the
architecture isn't unified enough.

**Entities have identity, lifecycle, and history.** Anything in the
world worth tracking has a stable ID, a defined lifecycle, and an
event history. Flat strings and prose mentions don't count.

**Knowledge is per-knower.** Information has propagation, not a
global state. Entities know what their experience gave them, not
what an omniscient narrator thinks they should know.

**Time consumes.** State decays during time advances unless
maintained. Maintenance is an action; neglect is a default with
cost.

**The player is not a designer.** The player chooses what to do.
The system surfaces affordances. The system does not enumerate menu
choices that pre-shape solutions.

**The narrator is fallible and constrained.** AI narrators
hallucinate, drift, and forget. The architecture must contain
hallucination by structuring the things that matter, validating at
write time, and ensuring read paths surface what's actually true.

**Hardware-portable.** The design works whether the AI narrator is
ChatGPT, Claude, a local model, or a multi-agent system. Lock-in to
specific AI providers happens at adapter layers, not in the core
design.

## What stays

Drakenvale and the Hollow Crown world. The cosmology, deities,
factions, places, history, named NPCs, magical traditions, calendar.
These are the setting. The setting is locked. The mechanical layer
runs *in* this setting; it does not redesign the setting.

## What is on the table

Every mechanical structure. None survives automatically. Whether
the system tracks competence as scores or as something else,
whether it resolves attempts with dice or with something else,
whether it advances characters with points or with something else,
whether it organizes narrative as scenes-and-arcs or as something
else — all open. The vision tells you what the game is. It does
not tell you what the mechanical structures are. That is the design
work.
