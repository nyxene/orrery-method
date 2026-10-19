---
title: Playbooks
group: Practice
groupdesc: Illustrates. Binds nothing.
tagline: the method walked end to end
lead: The method walked end to end, from a vague wish to a cost forecast. Every act shown here is abstract — what a step looks like in a concrete tracker is Mapping's subject, not this one's.
---

Nothing on this page carries a badge, and that is the rule rather than an omission: force is what deviating costs, and a page that binds nothing has no force to declare. The worked examples come from one project — a chart-drawing application — named here once so that no reader has to infer a domain from a defect.

## An evidence package, written out

The specification is in [Artifacts](03-artifacts.md). This is one filled in, for a task that added a second chart to a workspace that held one.

```spec An evidence package, filled
Item — Render two wheels side by side.
Built — A workspace showing two charts at once, each with its own controls. Selecting a second chart no longer replaces the first.
Decided — Rendered both charts into one canvas rather than two, because the shared aspect lines are drawn between them and two canvases cannot carry a line across the seam. The alternative was two canvases with an overlay for the lines, which was rejected as a third surface to keep in sync.
Checks — `npm run typecheck` clean · `npm test -- workspace` 41 passed · `npm run lint` clean · the visual regression suite green on 12 of 12 baselines.
Parties — executed by session 4f21, model family A. Verified by session 9c07, model family B, started from this package and the repository alone. The plan ruling is on the feature: session 1a88, family A. No session held two of the three.
Result — `npm run dev`, open /workspace, add a second chart from the picker. Both render, aspect lines cross between them.
```

The verifier appends one line and stops there.

```spec The verdict, appended
Verdict — Passed. One finding: the picker allows a third chart the layout cannot fit, filed as #812. Disposition: filed.
```

Six lines and a verdict, in that order, every time. The Owner reads a shape they already know instead of learning a new one on each item — which is the whole of why the form is closed.

## A feature, from wish to shipped

The Owner says "I want to compare two charts side by side", and an agent files it deliberately thin — a feature item whose one-line body ends in "not yet scoped". Framing happens in conversation; the agent edits the body until the goal names an observable end state, and the body carries the plan as a checklist.

As each line's work begins, that line becomes a task and is struck from the body; the rest of the list stays, so the feature always shows what it still owes. Each task runs the same arc: a branch opens from the task, a fresh session implements from the item alone, the pull request references it, the gates run, the verification dispositions its findings, and the merge closes the task with the evidence package already posted on it.

The executor that merges the last task finds no child open and no checklist line left, so it closes the feature — reading the `Ship condition` against what shipped, and splitting delivered from cut in the closing comment. The Owner reads the evidence afterwards — the same day or weeks later, nothing waits. The release ships when its content ships; no date was ever set on it.

## An incident in the middle of a task

A live bug arrives while a task is in flight. An agent files it flat — a bug, no parent, no home — and the Owner decides it displaces the current work, which is a judgement, not a rule; were the Owner away, the agent would make that call itself under `needs-owner`, as the [Cycle](04-cycle.md) allows.

Before the slot is surrendered, the interrupted session posts its handoff on the task: what was tried, what failed, where it left off. The fix runs as its own item with its own evidence; afterwards the interrupted task is restarted by a fresh session whose only memory of the first attempt is that comment — which is the whole reason the comment exists.

## A discovery noticed while implementing

Mid-task, the executor sees a table copy-pasted instead of shared. It is filed in the same session — a chore, its body opening with a link to the task that produced it — because the origin is only known while the context is live. No triage flag: the discovery will be done, and its evidence reaches the Owner through the unread queue.

The routing test gives the place — the feature ships fine with the duplication, so the item is flat and homeless — and the discovery rule gives the time: first in line after this task, while the context is hot. Had the unification mattered only once a second consumer existed, the item would instead carry a Trigger line naming that condition, and wait.

## A task that must wait for the next release

The Owner defers searchable chart selection to the next release. Left in place under its feature, it would hold the rollup at 2/3 forever and pin a task to a release its parent is not in — so it is promoted: its type changes from task to feature in one edit, it moves to the later release, the containment link is detached, and a comment on the parent states what was cut and why.

A replacement task with the shipped scope — a plain dropdown — takes its place, so the feature still closes with real content. The rollup tells the truth at both ends.

## A task that grew

Halfway through, "shared aspect table" turns out to contain a second decision surface — reconciling two configurations that disagree about which rows count. The executor stops before the diff grows unreviewable: the open pull request is narrowed to the one coherent slice it can deliver, and the task's boundary is rewritten to say so before the merge, because the boundary is what the merged code actually respects.

The removed piece becomes a new task under the same feature, blocked by this one — a dependency link, not a sentence in the body. The rollup grows from three to four, which is just-in-time decomposition working, not a planning failure.

## What will this cost

The Owner weighs a body of work about five tasks like the last few. The answer comes from the ledger: cost per merged task over comparable slices, segmented per model, recency-weighted, multiplied by five — and presented as a range, because the honest form of a forecast is the historical spread, not a point.

The figure is re-derived close to the decision rather than reused. An average computed against a different model tier is a snapshot of what that combination cost then, and it is presented as such.

## Returning after two weeks

Five reads, in order, all run by the Owner because none mutates anything.

The ready queue — open and unblocked. What is moving — items with a branch or an open pull request, reading the handoff on anything that was interrupted. The blocked list, checking whether each blocker still holds.

Then each active feature's rollup, one glance apiece, and finally everything that closed since they left — evidence packages oldest first, because that queue is the one nothing else is watching.

Nothing in the reconstruction depends on a document anyone kept current. That is the point of deriving: two weeks of absence cost the truth nothing.

What they did cost is throughput. The unread queue reached its limit within days and new starts stopped there, leaving only the streams that add nothing to it — parallel attempts on one task, work the test suite verifies whole, research. The reading is what restarts the rest, which is the limit working rather than the absence being free.

## The first week

```spec Adopting, one useful step at a time
Stop maintaining a status board — delete or freeze every hand-updated column and estimate field. This alone removes the thing that decays silently.
Create the first release — the moment the first commitment to ship exists, and not before. Cross-cutting work needs no container at all.
Adopt the axes — the six types are fixed; declare the area values, and remove the tracker's default categories before the first item is filed.
File everything, flat by default — one-line items; a feature not yet started is a single item with a checklist.
Run one feature through — decompose just in time, carry one task to merge, and read its evidence package.
Wire dependencies — real links instead of list order, which is what makes the ready queue mean something.
Confirm the ledger writes itself — the closing agent appends a line per closing act; every unwired week is cost history nothing can reconstruct.
```

Each step is useful standing alone, and the first four need nothing that follows them. A project that stops after step four is already better off than one running a hand-maintained board.

## Knowing where the adoption actually is

A list of steps answers what to do next and never answers whether it worked. These three states do, and each is recognised by something a machine or a stranger can check — never by how far down the list anyone feels they are.

| State | What it means | How you know |
|---|---|---|
| **Wired** | Every write rides its event, and nothing waits on anyone remembering | One task has gone to merge and its ledger line carries that merge as its Date; one feature has closed on its last child's leaving, with a closing comment that splits delivered from cut |
| **Carrying** | The method is holding the real work, not a pilot beside it | A release closed, and its conformance ruling answered all six criteria over everything in it |
| **Settled** | It is holding, and practice has started confirming the text | Two consecutive releases ruled conformant, and the census promoted at least one section out of Pending |

Wired is machinery, and a project can reach it in days. Carrying is the one that costs: it means no work runs alongside the method, and the ruling is the proof rather than the intention. Settled cannot be reached quickly by anyone, because it is measured in shipped releases and not in effort.

Going backwards is ordinary. A release that fails its ruling drops the project to the previous state, and that is information rather than failure — it names which of the six broke, on work that has already shipped, while the cause is still findable.
