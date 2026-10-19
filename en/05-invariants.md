---
title: Invariants
tagline: the eight properties that always hold, and the tooling that checks them
lead: Eight properties hold in every valid state of the tracker, and a structure that violates one is a defect, whoever produced it. The consistency check rules on what the tracker shows; a violation it cannot see is still a violation.
---

## The eight invariants {rule}

A structure that breaks one of these is defective, whoever produced it and however green everything else reads.

```spec The eight invariants
One task, one pull request — a task closes at the merge of its one pull request, or at the refusal that closes that pull request unmerged. Work that cannot fit one pull request is not one task.
A feature and its tasks ship together — a task belongs to its feature's release, never to a different one.
Every parent can close — permanent categories of work are classifications and queries, never parent items.
A parent closes when its last child leaves — performed by the party whose act emptied it, never by a machine.
Cross-cutting work is flat — if the feature ships without it, it is nobody's child.
A deferred task is promoted — moving work to a later release makes it a feature there, never an orphan on a shipped release.
One fact, one home — nothing is recorded in two places.
Items, their classification and their state are the source of truth — every board, view and chart is a rendering, deletable and rebuildable without loss.
```

## History before a rule does not refute it {rule}

Two corpora have been counted against invariant 1, and both report it true of most work rather than all: 3 of 22 pull-request-closed items in one, 17 of 250 in the other. Neither count is a counter-example, and the reason is not a defence of the invariant but a fact about the measurement.

**Both bodies of work predate the convention.** Nothing required one task to be one pull request while they were produced, so what the counts measure is how often that shape occurred by itself — not how often a rule was broken. A rule is refuted by work that was subject to it, and no work has been.

This is stated here rather than left for a reader to rediscover, because the numbers are real and will be met again. The honest reading is that the invariant is untested, which its `Pending` standing already says. The dishonest one is to treat a base rate gathered before the rule as evidence against it.

The same holds for every count in the evidence base taken before its rule existed. When work produced *under* the convention breaks an invariant, that is a different thing entirely, and it enters the analysis a bug gets.

## Two live levels {rule}

The hierarchy is a feature and its tasks. Releases sit above as membership rather than parentage, holding what ships together; nothing sits below.

![A feature owns its tasks; releases sit above as membership; flat items hang outside with no parent.](../diagrams/hierarchy.svg "Two live levels. The release encloses without owning — membership records what ships together, and a flat item is found by query rather than by looking under a parent.")

An item with no parent is a **flat item** — a bug, a chore, a research question — typed, and homeless: a query finds it, and it enters a release only when that release cannot ship while it lives. [Classification](07-classification.md) routes every kind of work.

> [!WHY]
> With no parent, a feature's tasks are related only by a prefix in their titles, and "what remains" stops being answerable except by reading. With a third level, every grouping view starts duplicating rows, and every added level is one more structure that must be kept true. Two is where both failures are avoided.

## The last child closes its parent {rule}

A task's closure is forced by the platform: the merge closes it. A parent's closure is forced by nothing, so it is performed by the party at the event — whoever's act left it with no open child closes it, having answered the two questions [Automation](09-automation.md) states.

That document owns the procedure. This invariant says only that the transition has a party and never a machine, and it holds for every door a last child leaves by — a close, a detachment, a deletion, a promotion to a release of its own.

> [!WHY]
> Zombie parents are how hierarchies rot: every child done, the parent open, its progress reading as unfinished forever. The transition nothing forces is exactly the one that goes unperformed.

## A deferred task is promoted {rule}

Deferring a task to a later release means promoting it to a feature there, or re-attaching it to a feature still open. It is never left on a parent that shipped.

A shipped feature with an open child reports false progress permanently. The record of what a release contained is the one history the tracker holds, and an orphan falsifies it.

## One fact, one home {rule}

Any fact lives in exactly one primitive. The plan lives in the feature, the type lives in its classification, the state lives in the item — and no fact is recorded twice.

> [!WHY]
> The tracker never compares two copies of a fact, so they diverge silently and every consumer trusts a different one. The failure produces no signal until a decision lands on the stale copy.

## Ceilings are lower than limits {guide}

Every primitive stops communicating long before the platform stops permitting it. The method treats the useful ceiling as the limit, and the platform's number as irrelevant.

| Primitive | Useful ceiling |
|---|---|
| Tasks per feature | ~20 |
| Hierarchy | 2 live levels |
| Values across the four axes | 21 — six types, eight areas, three priorities, four flags. Only the area axis grows |
| Open flat items, total | ~30–50 |

Exceeding a ceiling raises no error. It produces a structure that is technically valid and no longer readable — a worse failure than an error, because nothing announces it.

## The check runs, memory does not {rule}

Every invariant is ruled on by the consistency check, never by anyone's intention. These eight describe a state rather than an act, so they ride no event of their own and nothing makes them visible as they break — and breaking one costs the breaker nothing, because a false rollup bills whoever reads it next.

The check runs on two events and reports — a release close, and every pass in which the Owner reads. It blocks nothing, so an invariant can be broken between two runs and stand until one. [Automation](09-automation.md) states what the report carries and who acts on it.
