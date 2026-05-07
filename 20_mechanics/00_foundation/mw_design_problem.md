---
type: meta
status: locked
tags: [design-problem, foundation]
---

# Mystic Weave — The Design Problem

**Purpose:** This document frames the abstract problem the
mechanical architecture must solve. It deliberately does not name
specific structures — those are the design work this is input to.
The problem is described in terms of what the system must do, not
what shape the answers must take.

Read alongside the vision document, which describes what kind of
game this is. This document describes what the mechanical layer
must accomplish, given that game.

---

## The core problem

A character takes actions in a world. The system must determine:

- **What the character can attempt.** Some actions are universally
  available (move, speak, observe). Some require capability the
  character has acquired or possesses. The system needs a way to
  represent what a character can do.
- **How well they do it.** Outcomes are not binary. A character
  can succeed brilliantly, succeed at a cost, fail in a useful
  way, or fail catastrophically. The system needs a way to produce
  graduated outcomes that reflect both the character's capability
  and the difficulty of what they attempted.
- **What changes as a result.** Actions have consequences in
  fiction and in state. The world updates. Characters learn,
  spend, gain, lose. The system needs a way to translate outcomes
  into durable state changes.
- **How the character grows.** Through what they do, characters
  become better at things. Through neglect, they don't atrophy
  necessarily, but they also don't improve. The system needs a way
  to track and apply growth in capability over time.

These are interlocked. Capability gates what's attemptable.
Outcomes update capability through growth. State changes shape
what the character faces next. Each loop produces the next loop.

## Layers of the problem

The system has several layers that compose. The architecture must
solve at each layer and ensure the layers compose cleanly.

### The character

The character is the player's agent in the world. The system needs
to represent:

- Who the character is in ways that matter mechanically — what
  they're capable of, what they have, what they're carrying, what
  shape they're in physically and otherwise.
- What persists across time — durable identity, durable
  capabilities, durable possessions.
- What changes moment to moment — current condition, current
  location, current intent, current state of fatigue or injury or
  resource.
- How the character relates to other entities — known to whom,
  trusted by whom, owed by whom, owing to whom.

Open question: what are the right primitives for representing
"what a character is capable of"? Numerical scores in some set of
dimensions? Discrete competencies that are had or not? Continuous
mastery curves per skill? Tags with levels? Some hybrid? The vision
demands flexible representation that supports both broad ability
(a character is *generally* strong, agile, perceptive, etc.) and
specific trained capability (this character can pick locks, that
one can navigate by stars, this third one can negotiate with the
goblin clans). The structure of how these compose is open.

### The world

The world is what the character is in. The system needs to
represent:

- Things that persist: people, places, factions, items,
  organizations, structures.
- Where things are: spatial relationships, who's at which place,
  what's in which container.
- What things own or owe each other: ownership, custody, debt,
  obligation, alliance, enmity.
- What things know: per-entity knowledge of facts, events, other
  entities. What an NPC knows depends on what they've experienced
  or been told.
- The state of things: a building is intact or damaged, a person
  is healthy or wounded, a faction is rising or in decline.
- Time: what's happening in time, what's happening to things over
  time, what's scheduled to happen.

Open question: what are the right primitives for representing
the world? A flat collection of named-entity records? A graph of
relationships between entities? A spatial layer for places, a
relational layer for organizations, a knowledge layer for what's
known? What lifecycle do entities have — when do they get created,
when do they get archived, when (if ever) do they get destroyed?

### Resolution

When the character attempts something whose outcome is uncertain,
the system must resolve. Resolution involves:

- Determining whether the attempt is even possible.
- Computing a probability or threshold that represents the
  difficulty of the attempt for this character in this situation.
- Producing an outcome — almost always with some randomness
  involved, possibly with deterministic components.
- Translating the outcome into graduated bands of success and
  failure.
- Applying the appropriate consequences in fiction and in state.

Open question: what's the resolution mechanic? Roll-against-target
on a dice or random-number? Threshold comparison? Probability
distribution sampling? Something else? Given the answer, what
goes into the target — capability composed how, situation
composed how, randomness composed how? How many graduated bands
of outcome, and what does each represent? How does the system
decide when to roll versus when to narrate without rolling?

### Approach generality

The vision requires that combat, social, economic, magical,
infiltration, performance, scholarship — all are first-class
approaches with comparable mechanical depth. The resolution layer
must serve all of them with one architecture. This means:

- The resolution math is the same shape regardless of the
  approach being used.
- Capability dimensions support all approaches (a character has
  whatever it takes to be a swordsman *and* whatever it takes to
  be a courtier — these aren't different systems).
- Modifiers, conditions, equipment, environment all enter
  resolution the same way regardless of approach.
- Outcome bands have approach-specific cost vocabularies (combat
  has HP/equipment/position; social has reputation/leverage/trust;
  economic has price/debt/opportunity), but the *band structure*
  is uniform.

Open question: what's the approach taxonomy, and what's the
unified resolution architecture that serves all of them? How does
the architecture refuse to special-case combat?

### Magic

Magic exists in the world. It has a flavor specific to Drakenvale —
fields of magic with characteristic shapes, costs, and risks. The
system must represent:

- What a character knows about magic — which fields, to what
  depth.
- What a character can do magically — specific applications, with
  what cost.
- The cost of magical action — time, exhaustion, materials,
  consequence.
- The risk of magical action — what can go wrong, in what bands.

Open question: is magic structurally the same as other capability,
or is it its own subsystem? Are magical applications a kind of
trained competency, or a separate thing? Does magical resolution
use the same architecture as physical resolution? What's the right
representation that lets magic feel distinct without becoming a
special case?

### Growth and advancement

Characters grow over time. The system must represent:

- What constitutes growth — improvement in capability, acquisition
  of new capability, development of relationships, accumulation of
  resources.
- What triggers growth — what the character did to deserve it,
  what conditions it requires, what costs it has.
- How growth gets applied — does the player choose? Does the
  system determine? Some hybrid?
- Whether and how characters can lose capability — through injury,
  through neglect, through circumstance.

Open question: what's the right architecture for growth? Earn-and-
spend points of some kind? Direct improvement through use?
Milestone-based? Some combination? How does the system avoid the
pathological case where the player optimizes for growth-grinding
rather than playing the fiction?

### Narrative containers

Beyond the moment-to-moment, fiction has structure. There's the
single attempt (a roll), the scene (a sustained interaction with a
clear beginning and end), the arc (a longer thread that resolves
across multiple scenes), and possibly larger containers
(campaigns, generational threads). The system must represent:

- Where the fiction is in time and space at this moment.
- What's currently in motion — open arcs, pending obligations,
  scheduled events.
- What constitutes a meaningful unit of completion — when does a
  scene end, when does an arc resolve, when does a longer thread
  finish.
- How outcomes propagate from smaller to larger containers — a
  scene's resolution affects an arc; an arc's resolution affects a
  campaign.

Open question: what containers does the system formally track, at
what granularity, and how do they interact? Is "scene" a thing the
system knows about explicitly, or is it implicit in time and event
flow? What about longer containers — does the system track quests
and missions and campaigns as distinct things, or are these all
just arcs at different scales?

### Time

Time advances. The system must represent:

- What time it is in fiction.
- What changes during time advance — decay, relationship drift,
  scheduled events firing, resources consumed, opportunities
  closing.
- How the system decides what to advance time over — is it
  free-flowing, is it gated by the narrator, is it computed from
  the actions taken?
- Variable time advances — sometimes minutes, sometimes weeks,
  sometimes years.

Open question: what's the time architecture? What state changes
happen on every time advance versus only on major time advances?
How do scheduled events get tracked and fire? How do we avoid the
"reset state" problem where time advances but nothing changes
about the world?

### Persistence

The game must save. The system must represent:

- What's durable across sessions — character, world, knowledge,
  ongoing arcs, scheduled events.
- What's transient — current scene state, momentary conditions
  that resolve before save.
- What's append-only — history, log, audit trail.
- What's mutable — current state.
- What can be exported — character carry-forward across saves or
  generations.

Open question: what's the save model? Continuous? Snapshots?
Forward-only versus rewindable? How does this interact with
multi-character party play, when characters can leave or rejoin
the party?

### The narrator interface

The mechanical layer is consumed by an AI narrator (and possibly
human inspection, possibly multi-agent systems). The system must
represent itself to consumers:

- What state can be read, in what shape.
- What state changes can be requested, with what validation.
- What the narrator can determine on its own (free narrative
  description) versus what must be backed by structured calls.
- How errors and validation failures are surfaced.

Open question: what's the right surface? How thick is the layer
between the AI and the raw data? Does the architecture serve a
single narrator, or is it expected to support multi-agent systems?
How is hallucination contained through the interface design?

## What the system does not have to solve

Not every game design problem is in scope. The mechanical layer
does not have to solve:

- The setting itself. Drakenvale is locked.
- The narrator's prose voice. The narrator decides how to describe
  things; the architecture provides the structured ground truth.
- UI for human players. The narrator handles UI through prose.
- Multiplayer or social-network features. Single player is the
  scope.
- Tooling for content authors who aren't the player. Lore is
  authored separately.

## What this document is

This is the problem statement. It describes what must be solved.
It does not describe how. It does not commit to specific
structures, specific mechanics, specific representations.

The design work is to evaluate possible structures against this
problem statement and the vision, and arrive at the structures that
serve them best. The structures may resemble what other systems
have done. They may resemble what 2.0 has done. They may not. The
test is whether they serve the problem and the vision, not whether
they match prior thinking.

Begin from the problem. Arrive at the structures.
