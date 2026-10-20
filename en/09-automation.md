---
title: Automation
tagline: what is enforced, what is derived, and what must never be built
lead: Every answer the method gives is obtained one of three ways — a gate enforces it, a query derives it, or a judgement supplies it. Confusing the three is how tracking systems rot, so the boundary is drawn here and everything is on one side of it.
---

## Three categories · *Rule*

Every answer the method gives is obtained one of three ways, and a project that cannot say which way it got one is maintaining it by memory.

**Enforced** — a gate blocks it or performs it: a script, never anyone's memory. **Derived** — computed at the moment of asking, as the [Overview](01-overview.md) requires. **Human** — a judgement, not a fact, which no query can produce.

Human names where the judgement originates, never whose hands perform the write. The Owner does not operate the tracker, so an agent performs every mutation — including the one that records the Owner's decision — and the verifier's verdict is Human too: reasoning about content is judgement, whichever party holds it.

## No transition is automated · *Rule*

The platform forces a task closed at its merge. A container's closure is forced by nothing — and the answer is not a machine watching for it, but the party already standing at the moment it becomes true.

**The party whose act leaves a parent with no open child closes that parent.** For nearly every feature that is the executor merging its last task; it is equally the agent withdrawing the last one on the Owner's word, or whoever detached, deleted or promoted it away to a release of its own. Each is an act with a party, and that party answers two questions on the way out: does the body still carry unwritten checklist lines, and is any child still open. Where both answers are no, the feature closes and its `Ship condition` is read against what shipped — the one moment in the method where that line is read at all. Where either answer is yes, the feature stays open and nothing is decided.

A refusal is the one act that empties nothing. A verifier's refusal that closes a feature's last open child leaves the feature open and sends it back to planning — a refused approach is a plan judged wrong, and the [Cycle](04-cycle.md) owns that return — so the feature is emptied only by a child that left successfully or on the Owner's word. And a feature the Owner withdraws before its children have left is emptied on their word: the agent acting on it strikes the remaining checklist lines as cut, closes or detaches the open children as the Owner directs, and then closes it by the same procedure, with a closing comment that reads all cut.

A release is membership rather than parentage, so it has no children to leave and is not emptied. It closes on the Owner's word, by an agent's act, once its content has shipped and the census report and the conformance ruling are both on it — the report is what the close is refused without, not the close itself. That too is a transition and not an act, and it writes no ledger line.

That is what removes the last piece of unattended machinery from this method. **Nothing here runs without a party standing behind it**, and the transition rides an event that happens anyway rather than a process that has to be kept alive.

This document owns both procedures. The [Invariants](05-invariants.md) state that the transition has a party, the [Cycle](04-cycle.md) states when a feature's life ends, the [Terms](06-terms.md) say when a release closes, and none of them restates how — one fact, one home.

```spec Closing a feature refuses
To close over an open child — read live, never from a rollup that may lag.
To close over a remaining checklist line — an unwritten task is work the feature still owes, and a feature closed above one reports a delivery nobody made.
To close silently — the closing comment splits delivered from cut, because a rollup reading 6/6 without the split lies about what shipped.
To reopen — a feature reopens on the Owner's word alone, and a task never does.
```

> [!WHY]
> An automation here would be watching for a state a party already has in hand, and it would be the only thing in the method running when nobody asked it to. The transition was never hard to perform; it was hard to *remember*, and an event with an actor solves remembering without adding a machine that can fail silently in a quiet repository.

## Three automations are never built · *Rule*

Three machines are refused outright, and the refusals hold for anything shaped like them.

A **stale bot** converts Owner inactivity into item invalidity, and no clock can tell those two facts apart. It exists to manage inbound volume from strangers; there are no strangers here, so it would have nothing to do except close deliberately deferred decisions on a timer.

**Automated prioritisation** computes a rank from metadata, and priority is not in the metadata. Staleness is a fact about elapsed time; priority is intent, held by the Owner alone, and a formula that writes one anyway produces a number nobody has grounds to trust.

**Any writer sharing a field with a human.** Where automation and a person set the same value they eventually disagree, and the automation wins by being tireless — the bot re-applies what the human just removed until the human turns it off. Automation writes fields no human touches, and nothing else; that constraint binds every future automation, not just these three.

## The middle of an item's life belongs to nobody · *Principle*

Reliable enforcement exists at exactly two moments: creation and close. Between them no event fires, nothing compares recorded state to reality, and any fact written there is maintained by memory alone.

This is not a gap left unclosed — it is the reason state is derived rather than kept. What cannot be maintained honestly is not maintained at all.

## Each check rides its own event · *Rule*

The consistency check over the [Invariants](05-invariants.md) and the census each ride an event that has an actor — never a schedule and never a memory. Each surfaces a decision: retire the value, promote the task, prune the link. The surfacing is derived; the decision stays with the Owner.

Their events differ because their subjects do. The census reads a shipped set, so it runs at a release close, performed by the closing agent. The consistency check reads the state of the tracker, which is wrong from the moment it is wrong, so it runs at every reading pass as well — performed by the agent writing the review mark.

The census is a closed list.

```spec What the census reports
Value use — each classification value's lifetime uses, removing those at zero and reporting those under ten.
Fired Triggers — every waiting item whose Trigger has become true.
Escaped defects — every item closed since the last release carrying an Escaped line, grouped by that line and area, whatever type the item wears.
Standing — the sections every feature in this release passed through unchanged, offered as candidates for Proven, and the sections a defect sent back to Pending.
```

The conformance ruling rides the same close and lands on the same release, and it is not part of the census: the census is counted by the closing agent, and the ruling is passed by a party that executed none of the release — the [Overview](01-overview.md) owns it, and the [Artifacts](03-artifacts.md) give each its writer.

That report is where the project's own instructions and checks get their evidence: a cluster on regression is a missing class of test, a cluster on correctness is a weak audit, a cluster on framing is a question nobody asks.

The grouping is derived. What to change is a judgement, and the change itself is an act — filed and executed like any other work.

The census leaves its report on the release it closed. A release closed without one is not closed — the report is a condition of the close rather than a courtesy, so a skipped census is as visible as a missing evidence package.

The census is as frequent as the releases and no more, so a project that has not closed one has not run it. That is the price of refusing a schedule, and it is paid where it costs least: a project with nothing shipped has no shipped history to be wrong about.

Every run of the consistency check lists the invariants broken since its last one — a task closed by two pull requests, a task closed by neither a merge nor a refusal, a parent left open — and the axes broken with them: an item carrying a second value on one axis, which is a fact about live state and belongs to this check for the same reason the check has a second event. At a release close that list rides the census report; at a reading pass it sits beside the review mark. A broken invariant is never an exception: it means the work was decomposed or executed wrongly, and it gets the analysis a bug gets.

> [!WHY]
> A scheduled check is a standing commitment, and the method admits none. It also fails in the worst direction: scheduled jobs die silently in quiet repositories, so the check stops running exactly when the backlog has drifted unwatched the longest — green by absence, at the moment green means least.
