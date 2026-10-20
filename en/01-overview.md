---
title: Overview
group: Method
groupdesc: Normative. Read in order, once. Every section carries its force on its face — Rule, Principle, or Guide — and its standing beside it.
tagline: what is scarce, and what follows from it
lead: A method for software that agents write, that agents and automated gates check, and that one person directs. It is built around the two things in that arrangement that are genuinely scarce, and it discards everything that serves neither.
---

```chips
3 | accountabilities
4 | stations
4 | artifacts
6 | stages
8 | invariants
```

## What is scarce · *Principle*

Implementation capacity is not the constraint. Agents produce changes faster than anyone can examine them, and adding more of them moves nothing.

Two things are finite. **The Owner's attention** — one reader, unscalable, and the only source of judgement in the arrangement. **Tokens** — the only input that is spent and does not return.

Justified confidence is what those two buy: warranted trust in a result nobody read line by line. Every rule here raises the confidence bought per token, or per unit of the Owner's attention. A practice that raises neither is removed, however respectable it looks.

> [!WHY]
> Optimising throughput in a system whose bottleneck is verification produces more unverified work, which is worth less than none: it still has to be examined, and now there is more of it.

## Confidence is manufactured · *Principle*

The Owner accepts a result they did not read because four independent checks stand around it — three before anything is built on it, one after. Each catches a class of failure the others cannot, and no two share a failure mode — because no two share a context. [Roles](02-roles.md) states the separation that delivers that; without it the checks are one judgement counted four times.

![Four checks guard the passage: the plan ruling before cost, the gates on every change, the verification before merge, and the Owner after merge.](../diagrams/confidence-gates.svg "Position is the point. A check placed after the spend cannot prevent it, and a check placed before the change cannot see it.")

Trust follows from the arrangement, not from any single verdict. [Roles](02-roles.md) states what each station catches and what disqualifies a party from holding it.

## Derive, do not maintain · *Rule*

Every answer is computed at the moment of asking, from state that exists for another reason.

A maintained answer starts decaying the instant it is written, and it decays silently — nothing compares it to reality, so nothing reports the drift. A derived answer cannot go stale, because between two questions it does not exist.

Maintaining an answer is permitted only where derivation is impossible, and the impossibility is stated where the answer lives.

> [!WHY]
> A status field is wrong from the moment reality moves, and it announces nothing. The same fact is already in the branch, the pull request and the merge — asking those costs one query and cannot lie.

## What binds, and what does not · *Rule*

Every statement carries its force on its face. The badge beside a heading is the whole of its authority.

| Tier | Force | Deviating |
|---|---|---|
| Rule | Binding. The method does not hold without it | Is a defect |
| Principle | The reason the rules take the shape they do | Requires an argument from the principle itself |
| Guide | A recommended default | Requires a reason, recorded |

Unbadged prose explains. It binds nothing, and no tooling reads it.

A badge is required wherever force exists and forbidden where it does not: every section of Method and Reference carries one, and no section of Practice does. Practice illustrates, so it has no force to declare, and a badge there would assert one. The build holds both halves of that.

## Force and standing are different axes · *Rule*

Force is what deviating costs. Standing is whether practice has confirmed the section yet. They are independent, and collapsing them into one badge is how a corpus stops binding anything.

Every section carries a standing, and it is written where the force badge is. **Proven** — a real feature has been carried through it unchanged — is written as a second word: `· *Rule, proven*`. **Pending** is the absence of that word, because it is the default and a default nobody has to write cannot drift out of date.

Pending never softens force. A Pending Rule binds exactly as a Proven one does, and deviating from it is a defect, not a licensed experiment. What Pending adds is that the deviation is *also* evidence: it is filed as a bug against the corpus, its `Escaped` line naming the section that failed to hold.

Standing changes on an event, never on attention. The census at a release close lists the sections every shipped feature passed through unchanged; those are the candidates, and the Owner's word promotes them — by adding the word to the heading, which is a diff like any other. A section demoted by a defect loses the word in the same act.

> [!WHY]
> A corpus that marks itself unproven and licenses deviation on that ground can be adopted whole, obeyed nowhere, and reported as compliant. Marking the same fact without touching force keeps the honesty and removes the escape: the reader knows what has been tested, and owes the method the same obedience either way.

## What conformance requires · *Rule*

A project conforms when all six hold. Nothing else is asked, and none of the six is waived by a section being Pending.

```spec Conformance requires
The artifacts — every closed item carries the ones its kind demands, and the ledger holds a line per closing act.
The stations — each passed by a party independent of what it checks: the plan ruling named in its feature's `Ruling` line, the verification and the gates in the task's evidence package.
The separations — never violated, and each station passed in a session of its own; where a profile cannot show a party was distinct, it states what it substitutes.
The invariants — held, and the consistency check run on both its events.
The axes — one type per item, values from the declared set, every one applied by an agent.
The derivation rule — no status, no progress and no rollup maintained by hand.
```

Each is checkable against the tracker and the repository, by someone who was not there. That is the whole of what conformance means here, and a claim to it that cannot survive those six queries is not a claim, it is a preference.

A project may take the parts it wants and leave the rest. What it may not do is take the parts and keep the name.

## Conformance is ruled on, not asserted · *Rule*

A criterion nobody applies is a preference with a table around it, so the six are put to a party rather than left to the reader's conscience.

The ruling rides the release close, beside the census, and is performed by a party that executed none of the work in that release — the separations reach here exactly as they reach a plan or a change. It answers each of the six over everything the release closed, cites the query or the file it read for each, and lands on the release itself, where the census report already goes.

It holds until the next release close and no longer. Conformance is a statement about a body of work rather than a badge a project keeps, and a project that has closed no release since its last ruling has none — which is the honest answer, not a lapse.

> [!WHY]
> The moment conformance can be claimed without being ruled on, the claim costs nothing and means nothing, and the six criteria become decoration on a page nobody checks against. Riding the release close puts the ruling on an event that already has an actor, a record and an audience, so it is obeyed as a side effect of shipping rather than by anyone remembering to be honest.

## The tracker holds four facts, and derives the rest · *Rule*

An item carries its body, its classification, its parent if it has one, and whether it is open or closed. Nothing else is stored about it, ever. Every question a board answers — what stage is this at, how far along is that, what is in progress — is computed from those four at the moment of asking.

| The fact | What it is | Stated in |
|---|---|---|
| Body | The payload: goal, boundary, criteria, and the lines its kind carries | [Artifacts](03-artifacts.md) |
| Classification | One type, at most one area, at most one priority, any number of flags | [Classification](07-classification.md) |
| Parent | A feature owns its tasks. Two live levels, and releases above as membership rather than parentage | [Invariants](05-invariants.md) |
| Open or closed | The only state there is. One of five closing acts sets it for a unit of work; a container's emptying, or the Owner's word on a release, sets it for a container — [Artifacts](03-artifacts.md) states both | [The cycle](04-cycle.md) |

There is no status field. Its absence is a decision this method is built on rather than a gap in it, and the reason is the one stated above: a stage is read off facts the work produces anyway, which [The cycle](04-cycle.md) sets out stage by stage.

How the four are physically recorded — a label, a field, a native type, a link — is the tracker's business, settled per tracker in [Mapping](10-mapping.md). Nothing on this page depends on the answer, which is what lets the method outlive a change of tooling.

## A rule rides an event, or it rides attention · *Principle*

A rule holds when it is attached to something that happens anyway and leaves a trace behind. The ledger rides the close, the handoff rides the interruption, the evidence package rides the merge: each is obeyed as a side effect of work already being done, and each neglect shows up as a missing artifact.

A rule attached to no event, or to an event that leaves nothing behind, is carried by attention alone — and attention is the one thing this arrangement cannot supply.

> [!WHY]
> Human methods lean on habit and on a cost the breaker eventually feels. A party that begins each session with no memory has neither, so a norm here converts to structure or it evaporates. Adding a rule therefore begins with finding the event it can ride, never with wording it more firmly.

## The boundary · *Rule*

The method covers one person directing agents against one codebase. Outside that it states nothing, and it does not extend by analogy.

| Excluded | Because |
|---|---|
| Estimates in time | Duration is not the scarce quantity. Work is forecast in tokens, or not at all |
| Recurring ceremony | Every ritual in the method is triggered by an event in the work, never by a date |
| Hand-maintained status | Derivable, therefore derived |
| Sizing in shared units | They measure a team's calibration against itself. There is one actor and no calibration to share |
| Coordination between people | There are none to coordinate |
| A standing risk register | A risk is an input to a decision, never a record kept beside it. It is raised where it changes a choice — a framing question, a plan ruling, a boundary — and the decision is its trace |
| Continuity past the Owner | The arrangement has exactly one source of judgement, by construction. Work that must outlive its holder is a different arrangement and needs a different method |

Exclusion is not disapproval. These are answers to questions this method does not have.

## How to read this · *Rule*

A document's part decides its force: **Method** is normative and read in order, once; **Reference** is looked up, never read through; **Practice** illustrates and binds nothing.

A **Why** block carries the reason a rule exists. A rule whose reason has gone is deleted rather than obeyed, so the reason is the part worth reading twice.

The shortest useful path is this page, then [Roles](02-roles.md), then [Playbooks](11-playbooks.md).
