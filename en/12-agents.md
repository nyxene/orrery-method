---
title: Agents
tagline: one way to staff the accountabilities and stations — the one this method grew up under
lead: The execution profile the method was written for, one human above a cast of agents. No project has yet worked to this method, so this is a design rather than a record. It illustrates and binds nothing — the separations bind, this staffing does not.
---

## The cast

Every accountability below the Owner is held by an agent, and no agent holds two of them on one piece of work. The Framer is an agent here, framing in conversation with the Owner and dissolving when its output lands in the tracker.

The cast names the four seats that remain: the Planner is the Feature Lead's seat, the Implementer is the executor's, the Critic holds the plan ruling, and the Auditor holds the verification. The last two stations need no cast — the gates are scripts, and the Owner reads.

![The Planner is checked by the Critic, the Implementer by the Auditor, and the Owner decides over both pairs.](../diagrams/role-pairing.svg "Two producers, two checkers, one human above both pairs. No agent appears twice in a row.")

```cards
Produces | Planner
An agent per feature. It reads the code and the sources before it writes a line of plan, and it hands the plan to a critic it has never spoken to.
- One feature, one planner, re-entered each time the plan grows.

Produces | Implementer
One agent, one session, one task. It starts with no memory of any earlier session, receives the item and the standing instructions, and nothing else exists for it.
- Interrupted, it writes the handoff before the slot is surrendered.

Checks | Critic
An agent that did not write the plan. The deeper loop — planner, architect, critic, until approval — is bought only where a wrong approach would surface after implementation.
- One verdict, recorded on the feature.

Checks | Auditor
An agent on a different model than the implementer. Two runs of one model share their blind spots; the failure that survives review is the one both parties share.
- Its verdict is appended to the evidence package, never edited in.
```

## Why one session per task

The session boundary is this profile's forcing function for the cold-start test: an implementer that begins with no memory cannot lean on anything the item does not carry, so an underspecified task fails loudly at its first step instead of silently at its last.

It is also what makes interruption cheap. A session holds nothing durable, so ending one loses only what the handoff rule already saves — the approaches tried and abandoned.

## Parallel attempts

Several implementers may take one task in parallel, each in its own session and working tree, and the best result is kept. N attempts add one item to the Owner's unread queue, so the limit is untouched — this is the exception the cycle names, exercised deliberately.

## What this profile substitutes

The profile spec asks for distinguishable parties, and this profile supplies them by session rather than by credential. Every agent acts under one credential, so which account held a station cannot be shown after the fact — but every seat runs as a session of its own, every session names itself, and the `Parties` and `Ruling` lines carry those names. Token counts are read from the runtime's usage report for each of those sessions, at the close.

What it substitutes for identity is the dispatch itself. Each seat is started as its own session against its own input, so a party is never handed work it produced — the separations hold at the moment work is handed out rather than at the moment it is inspected.

A consumer whose parties leave distinct identities gets the first three separations as checkable facts. This profile gets them as a property of how sessions are started, and the fourth as a recorded one — the sessions named on `Framed`, `Planned`, `Ruling` and `Parties` are what the fourth separation asks for, two to a check, and they are the thing this profile can show. It states that difference rather than claiming the stronger thing.
