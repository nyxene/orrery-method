---
title: Classification
tagline: the four axes, and where every kind of work is routed
lead: Work is classified on four axes. An item carries exactly one type, at most one area and one priority, any number of independent flags — and every value is applied by an agent, never by the Owner.
---

## Four axes · *Rule*

An axis answers one question, and an item carries at most one of its values — the flags axis alone excepted, each flag being its own independent fact. An axis earns its place by answering a question that is actually asked, or by selecting a behaviour downstream; an axis that does neither is decoration with a maintenance cost.

| Axis | Question | Per item | Read by |
|---|---|---|---|
| type | What kind of thing is this? | Exactly one | Routing, every query, the exclusivity check |
| area | Which part of the system? | At most one | Batching — "is this the place I am already in" |
| priority | Does urgency deviate from normal? | At most one; absent means normal | The Owner, ordering work |
| flags | Which cross-cutting fact holds? | Each flag independent | Queries; `needs-owner` and `triage` by the Owner |

![Four axes: type exactly one of six, area at most one, priority at most one of three, flags any number of four.](../diagrams/axes.svg "One axis answers one question. Only the flags axis admits more than one value, because each flag is an independent fact rather than a choice between alternatives.")

> [!WHY]
> Selection cost, not storage, is what caps a classification — and it is paid by an agent starting cold, with the list of values as its whole guide. One value per axis keeps every choice small: pick one of six types, one of a few areas, and done. Abandon that, and the question becomes "which subset of twenty applies", which no name and description can answer reliably.

There is no fifth axis. Status is derived, sizing is refused because the measured resource is tokens, sequencing lives in releases, and there are no teams to route between.

How an axis value is physically recorded — a label, a field, a native type — is the tracker's concern, and [Mapping](10-mapping.md) settles it per tracker. Nothing in this document depends on the answer.

## Routing · *Rule*

The routing test routes every piece of work, asked at two scales: **does X ship without this?** Asked of a feature, no makes it a task under that feature. Asked of a release, no pulls it into that release — on the Owner's word, because what blocks a shipment is theirs to say.

Everything else has no home at all. A home is a commitment, not a filing cabinet: membership in a release states "this ships together", an item that states nothing carries no membership — the default is carried by absence — and a query over type and area finds the item wherever it is not.

Membership answers what was promised and what blocked. What actually shipped is the repository's own record at the tag, and the changelog derives from merges — never from membership.

| Kind of work | Object | Type | Home |
|---|---|---|---|
| Any outcome, decomposable | Feature | feature | A release once the Owner commits it; none while it waits |
| One pull request of an outcome | Task | task | Its feature's release |
| Defect in shipped behaviour, one pull request | Flat item | bug | None — or a release that cannot ship while it lives |
| Defect whose fix needs more than one | Feature | feature | A release once the Owner commits it |
| Upkeep, no behaviour change | Flat item | chore | None |
| A question to be answered | Flat item | research | None — it blocks by link, never by membership |
| Documentation-only change | Flat item | docs | None — unless a feature cannot ship without it, which makes it that feature's task |
| Infrastructure | its real type | + the infrastructure area | by its type |
| Security | its real type | + the security flag | by its type |
| Defect inside an open task's boundary | not an item | — | that task's pull request |

The test outranks the table. The rows are defaults for work nothing claims; the moment a feature or a release cannot ship without an item, the test has spoken and the row has not.

Infrastructure is a place, not a kind — a pipeline outage is a bug in the infrastructure area. Security spans every kind — a vulnerability is a bug, hardening is a feature — so it is a flag on top of the real type, never a type competing for the slot. A type that is really an area, a flag, or a priority collides with its own axis the first time both statements are true, and every filing after that is decided arbitrarily.

That is why "deferred mess" is not a type: deferral is the priority axis speaking, and the mess itself is a bug, a chore, or a task like any other.

A defect too large for one pull request is not one unit of work, and filing it as one does not make it fit. It passes framing like any other goal and becomes a feature whose tasks are the steps of the repair, carrying its `Origin` and `Escaped` lines — written once, at that framing, by whoever frames the repair, since the defective line is already known by then — unchanged by any task. The census counts what carries those lines rather than what carries a type, so a defect repaired as a feature is counted once, in the right place, with no second home invented for it.

A bug that turns out not to be a defect is not forced closed as one. The question it was actually asking — is this behaviour wrong — has been answered, so it becomes research — retyped by the party that found the answer, who writes where the answer is recorded before writing the answer itself — and closes on it. Nothing is invented to fill an `Origin` line with no commit behind it.

A research item is a question. It states where the answer will be written and closes when the answer exists, whether or not any pull request merged; research that must precede a feature blocks it by a dependency link, never by containment, because research that concludes "do not build this" has succeeded.

An inquiry that produces work is that same research item — an audit, a teardown, a review pass. What it finds is filed as flat items linked back to it, never as its children: the inquiry ships nothing, so the routing test has no answer on it, and containment would promise a delivery nobody made. What remains of one is a query over those links, not a rollup.

Work that is real only under a condition waits with a **Trigger** line naming that condition — filed, homeless, and untouched until the condition holds. A Trigger names an observable condition, in the same sense a goal names an observable end state: something can answer whether it has happened. An item whose Trigger nobody can name, or nobody can evaluate, is not waiting work — it is either work now, or nothing.

## A bug names its provenance · *Rule*

A bug carries three lines in its body, each written by its own author at its own moment.

| Line | Names | Written by | At |
|---|---|---|---|
| Found-in | Where it surfaced — production, a reading, an audit, a planner's pass. Free prose, not a governed axis | The filer | The filing |
| Origin | The task or pull request that shipped the defect | The executor that fixes it; the framer of a repair feature | The fix; the framing of a repair feature |
| Escaped | The check that let it through — the framing test, or one of the four stations [Roles](02-roles.md) names | The executor that fixes it; the framer of a repair feature | The fix; the framing of a repair feature |

Origin and Escaped are written at the fix because the executor already stands on the defective line, and the chain from there is mechanical: the repository's history names the commit, the commit its pull request, the pull request its task and feature.

A bug does not close without its Origin line — filled, or honestly not: *predates the method*, *interaction* with two links, *unknown*. False precision is worse than a recorded gap, and Escaped works without Origin: the nature of the defect names the missed check even when no commit is found.

> [!WHY]
> These three lines are what makes the retrospective mechanical instead of archaeological. And the reverse half costs nothing where the binding supplies the mirrored link: a closed feature then accumulates the record of what it left behind — derived, never maintained.

## A label is an axis, a link is a fact · *Rule*

A label carries a value from a small closed set that queries read constantly. A link carries a fact between two items — an origin, a blocker, a supersession.

Encode a fact as a label — one label per feature that ever shipped a bug — and the axis loses its ceiling: the set grows with history rather than with the system, and every future filing pays selection cost over all of it. A fact encoded as a label is an axis without a ceiling; an axis encoded as links is a query that does not exist.

## The values · *Rule*

The type axis is fixed at the six values above. The area axis is project-defined: each value names a place that can be pointed at — a value whose directories cannot be named is a topic, and topics belong in titles — and the axis is capped at eight values.

The priority axis has three values and no middle: *critical* pre-empts the task in flight, *high* goes before new scope in the same area, *low* waits until something is already in the file. A value meaning "the default" is applied to most items and read by nobody, so the default is carried by absence.

Two trackers were counted against this rule and both had used a middle value — 28 times each — before the rule existed. By the [Invariants](05-invariants.md)' rule on history before a rule, those counts describe the default this axis removes rather than a need it denies; the first middle value applied *under* the rule would be the counter-example these are not.

Four flags exist. The *security* flag marks a change to the security posture, and the *unread-exempt* flag marks a close that never reaches the Owner's queue — [The cycle](04-cycle.md) owns which streams qualify.

The *needs-owner* flag marks work stopped on a judgement only the Owner can make — the one fact no dependency link can express, because there is no item to point at.

The *triage* flag marks an item an agent filed on its own initiative and left. The Owner reads that queue, instructs, and the agent removes the flag by acting, so a lapse stays visible in the query instead of vanishing.

A discovery being done immediately after its task carries no triage: its evidence reaches the Owner through the unread queue.

## The first words classify · *Guide*

The opening words of an item's statement name its type. An agent filing work reads its own first words against this table before it reads anything else.

| It opens like | Type | A real opening |
|---|---|---|
| "Make it possible to…" — what becomes possible | feature | "Compare two charts side by side" |
| "Add / change / wire X in Y" — one change, one place | task | "Render two wheels side by side" |
| "X does Y, expected Z" — shipped behaviour, gone wrong | bug | "South Node glyph displaced ~176px" |
| "Bump / rotate / regenerate / clean" — upkeep, behaviour untouched | chore | "Swap the plugin source to GitHub" |
| "How / which / whether…" — a question | research | "Which mechanism can switch Caddy upstreams?" |
| "Verify / prove / measure X" — establish a fact about the system | research | "Verify SOURCE_COMMIT resolves to a real SHA post-deploy" |
| "Describe / correct the description of…" — prose about the system | docs | "The README claims isolation the config does not enforce" |

The verbs are specimens, not a fence: match the essence in the middle of each row, never the letter. A statement matching two rows is two items unsplit; one matching none is framing unfinished — and in both cases the routing rule, not this table, decides.

## Governance · *Rule*

Addition is costly and removal is cheap, by design. A new value replaces an existing one in its axis; a new axis replaces an axis. The one exception is the area axis, which grows without a swap while the codebase grows a genuinely new part, until the cap.

An agent never invents a value on its own initiative. The value set is the interface every later session reads, so extending it is the Owner's call; an agent that finds the set insufficient files the case under the needs-owner flag and waits.

Retirement is the default response to doubt. Removing a value leaves its items otherwise untouched and restoring one is a single act, so nothing is lost by retiring early.

The census — [Automation](09-automation.md) owns it — carries this axis's half: a value at zero lifetime uses is removed and reported, nothing being there to decide, and a value under ten is reported as the candidate for the next swap, which is the Owner's call.
