---
title: The cycle
tagline: six stages, and what each one hands to the next
lead: Work passes six stages. Each hands a named artifact to the next, the Owner gates the passage into a release and nothing after it, and their reading comes last of all.
---

| Stage | Enters as | Leaves as | Passes when |
|---|---|---|---|
| Framing | A wish | A goal in one sentence, with an observable end state | Its two plausible readings agree on the acceptance criteria |
| Planning | A goal | A feature with its tasks | The plan ruling — and every task passes the cold-start test |
| Execution | One unit of work | A change and its evidence package | The change is inside the item's stated boundary |
| Verification | A change and its evidence | A verdict appended to the evidence | Gates green; every finding fixed, filed, or refused |
| Closing | A verified change | A closed item | Its closing act — [Artifacts](03-artifacts.md) names the five. Nothing else forces it, nothing delays it |
| Acceptance | A closed task and its evidence package | The Owner's judgement | Nothing. Acceptance gates nothing |

![Four stages in a band, fanning at verification into five closing acts, with acceptance sitting after and gating nothing.](../diagrams/item-lifecycle.svg "The fan is the point. Everything upstream of the verification is one path; what an item closes on depends on what it produced, and acceptance sits outside the flow entirely.")

## A stage is a passage, not a status {rule}

No stage is recorded anywhere. Framing is an item whose body carries no `Goal`; Planning is a `Goal` with no child items; Execution is an open branch or pull request; Verification is a pull request carrying an evidence package; Closing is the closing act; Acceptance is a closed item newer than the review mark. A stage that cannot be read off a fact the tracker already holds is not a stage in this method.

## Every kind runs this cycle, and they differ at two points only {rule}

There is one cycle, not six. What changes between a feature, a bug and a research question is where the work enters it and what act closes it — everything between those two points is identical, and identical on purpose: the stations are what make a result trustworthy, and no kind of work is exempt from them because it looked small.

| Kind | Enters at | Produces | Closes on | Lives until |
|---|---|---|---|---|
| Feature | Framing | Tasks, and the plan that orders them | Its last child leaving | Its checklist is spent and no child is open |
| Task | Planning, inside its feature | One pull request | The merge, or a refusal | Its closing act |
| Bug | Execution — the reproduction is already the goal | One pull request, plus `Origin` and `Escaped` | The merge, or a refusal | Its closing act |
| Chore | Execution — the title is already the end state | One pull request | The merge, or a refusal | Its closing act |
| Docs | Execution, unless a feature cannot ship without it, which makes it that feature's task | One pull request | The merge, or a refusal | Its closing act |
| Research | Framing — the question is what gets framed | An answer, written where the item said it would be | The answer existing there | Its closing act |

Two rows are worth reading twice. A **feature closes when its last child leaves** — by whichever door — and the party whose act emptied it closes it there; [Automation](09-automation.md) owns the two questions that party answers first. And **research closes without a merge**, because a question that concludes "do not build this" has succeeded; its answer is its evidence, and the item states in advance where that answer will be written so the close is checkable rather than declared.

Where a bug or a chore enters at Execution, it is because framing already happened — the reproduction or the title *is* the stated goal. That skip is the one *Framing ends with one sentence* governs, and it is earned rather than claimed.

> [!WHY]
> A method that gave small work a shorter path would be read as a method that grades work by size, and everything would then arrive small. The path is one path; what differs is the act that ends it, and that is a property of what the work produced rather than of how much it was worth.

## Framing ends with one sentence {rule}

Framing is finished when the goal names an observable end state and survives one test: write down two plausible readings, and if they would produce different acceptance criteria, it is not finished.

A wish becomes that goal through converging questions put to the Owner, one at a time — the answer to the first changes what the second one is. Only questions the Owner alone can answer are asked: intent, priority, taste, risk. Everything technical is researched, decided without asking, and recorded in the feature's `Decided` line with the alternative it beat.

What the questions ruled out is kept: it becomes the feature's boundary.

An absent Owner does not block framing. Work proceeds on the best-evidenced reading, the unasked questions ship beside the plan, and the plan ruling treats an unconverged reading as what it is — a risk.

Framing has two scales, like everything here. A wish that outgrows one feature goes to the Framer: research first, then features with their boundaries, their links, and a checklist in each body — and the Framer dissolves the moment that knowledge lands in the tracker, the Owner's commit being the verdict on its work.

> [!EXCEPTION]
> **There is one exception.** Framing is skipped when the goal arrives already stated — a bug with a reproduction, a chore whose end state is its own title — and the skip is earned, not claimed: two readings that differ on acceptance send even these back through framing.

> [!WHY]
> A framing error fails last. The plan is faithful to the misreading, the implementation is faithful to the plan, and every check confirms that faithfulness — so the error is first detectable at acceptance, after every token is spent, by the one guardian whose attention the method exists to protect.

## Planning resolves uncertainty first {rule}

The feature is decomposed so that each task makes the next one specifiable: the first task is the one resolving the largest uncertainty a task can resolve. An uncertainty that is a question resolves as research instead — filed flat, blocking the feature by link.

Slices are vertical: each passes through every layer it needs and is independently readable, so results reach the Owner one at a time instead of arriving as one batch at the end.

A task is ready when it passes the cold-start test: a session with no other context can execute it. It names its acceptance criteria as observable outputs, the files or areas it touches, what is out of scope, and anything external it depends on — everything the item does not carry is rediscovered at token cost, or guessed.

That payload is written at planning, into the feature's body under each checklist line. The line becomes the task's own item when work begins — it moves, and never copies.

The plan is argued before it is priced. The plan ruling is what Planning passes on, and a deeper adversarial pass is bought only where a wrong approach would surface after implementation rather than during it. If two approaches that would have to be chosen between cannot be named, there is nothing for that pass to converge on, and running it anyway produces an endorsement the plan did not earn.

## Execution is one session against one item {rule}

The executor receives the task's item, the repository's standing instructions, and the handoff if one was written on the item — nothing else, because nothing else survives between sessions. Every technical decision is the executor's, recorded in the evidence package with the alternatives that existed; anything product-level, any change to the criteria, any breach of the boundary, and any new external dependency is escalated to the item while the code is still unwritten.

## A discovery is filed now and done next {rule}

Work discovered mid-task is filed at the moment of the discovery, and never folded into the running pull request. Inside the boundary it belongs to this pull request and is not a discovery at all; outside it — or ambiguous — the routing test gives it its place.

What is filed is not parked: it is next. A discovery takes the freed slot ahead of any new scope, and where the unread limit blocks all starting it waits first in line — a position, not a parking lot. It yields to a critical item and to nothing else.

The discoverer files, and the separations decide who does the work.

Conditional work waits longer, on its Trigger line — [Classification](07-classification.md) owns that rule. A limitation accepted for good is not filed at all: it is recorded beside the code it describes.

## A task that outgrows one pull request splits {rule}

A task that turns out to be bigger than one pull request is not one task. The executor stops and says so, and the Feature Lead splits it — the boundary is that accountability's line to write — never delivered large with an apology in the description.

A task blocked mid-flight splits the same way: the pull request narrows to the slice it honestly delivers, the boundary is rewritten before the merge, and the remainder is a new task blocked by what stopped it.

A second pull request on one task is never the answer — it is a decomposition error, and it is analysed like one.

## Verification runs cheapest first {rule}

No check forwards what an earlier check could have caught. Scripts run first and cost nothing but machine time; the verification runs on tokens against a change that already passes its tests; the Owner reads last, and only what the first two could not have judged.

> [!WHY]
> The Owner's queue is served by one reader with no spare capacity, so the dominant loss is not a missed defect but the time work spends waiting there. A findings list padded with what a type-check would have caught makes the Owner read noise to find signal — at the one station that cannot absorb it.

A verification finding has three dispositions: fixed in this task, filed with an item number in the evidence package, or refused. "Noted" is not a disposition — a finding with neither a fix, an item number, nor a refusal leaves nothing anything can act on, and nothing returns to it.

A filed finding follows the discovery rule: it is work found in flight, first in line after the merge, never parked.

## The verification can refuse {rule}

Refusal is the disposition for a finding that filing cannot answer: the change does what it was asked to do, and what it was asked to do is wrong. A verifier that can only fix or file cannot stop anything, and a station that cannot stop anything is not a station.

A refusal names the defect as one of the plan rather than the code, and it costs the work. The pull request closes unmerged, the task closes with the outcome `refused`, and the refusal is appended to the evidence package like any other verdict. The tokens are spent and the ledger records them; that is what the forecast is built from.

The defect then goes where it belongs. The feature stays open and returns to planning, because a wrong plan is an outcome judged wrong — a refusal is the one act that never empties a parent, [Automation](09-automation.md) says so — and the corrected work is new tasks under it, opened only once a new `Ruling` line reads `passed`. Where the plan was right and the item misread it, the finding is a bug against framing, carrying the `Escaped` line that says so.

The verifier is the closing agent for a refusal, and it is the only act that makes it one. Nobody else can be: there is no merge, the Owner has not spoken, and the executor was dismissed when its session ended. So the same append that carries the verdict closes the item, and the ledger line is written from it.

The verdict carries an `Escaped` line naming the station that let the approach through — the plan ruling, or the framing test where the goal itself was wrong. That is what puts a refusal into the census: it counts every item closed carrying that line, whatever type the item wears, so the station whose failure costs most is the one the feedback loop can finally see. Without it a refusal is invisible to everything except its ledger line, and a line that only said `abandoned` could not say what failed.

A refusal is never overridden. The Owner may reopen the feature and instruct differently — that is their decision, made in the open, on a task that is already closed and already counted.

> [!WHY]
> Two dispositions make every finding survivable by filing it, and filing is free. The one class of defect that must stop a merge — the approach itself being wrong — is exactly the class filing handles worst, because the item it files against is built on the thing it disputes. Without a refusal the verification is a comment, the check count is three where it is two, and the confidence the Owner is asked to extend rests on a station that was never able to withhold it.

## The merge closes, and nobody waits {rule}

On green gates and a verification that did not refuse, the pull request merges and the task closes with the merge. The evidence package is written before the verification and posted on the item no later than the merge, so the closed item carries it; the executor that merged the last task closes the feature, reading its `Ship condition` against what shipped as it goes.

A task is never reopened — it records what became of one pull request, merged or refused, and that does not stop being true. A feature is reopened freely, because it records an outcome, and an outcome can be judged wrong later. Corrective work is always new tasks.

> [!WHY]
> Holding a verified branch open for a human puts a wait on the critical path of every change, including every change that would have been approved without comment. The trunk stays deployable because unfinished work merges behind a switch in the code — which is also what makes interruption affordable.

## Acceptance is retrospective {rule}

The Owner reads the evidence package after the work has closed, at a time of their choosing. Nothing waits for the reading, and no state is held open pending it.

A reading that finds a problem has exactly two remedies: new items where what closed still stands, and a reopened feature where it does not. A reopened feature continues under its original statement, with new tasks.

Reopening is the method working, not the method failing.

> [!WHY]
> A check that held the merge would pay the full wait on every change, including all the ones that turn out to be fine. The reopen cost is paid only on the ones that are not, and the unread limit is what keeps that cost bounded.

## Starting is governed by the unread queue {rule}

Work is started by how much is waiting to be read by the Owner, never by how many agents are available. The unread limit is two closed-but-unread results and one task in flight; nothing new starts while the queue is at it — not a smaller task, not an unrelated one, not "to keep an agent busy".

Unread is derived from one recorded fact — the review mark: the close moment of the newest item whose evidence the Owner has read, written once per reading pass by the agent acting on their instructions, and never overwritten. Everything closed after the newest mark is unread, and the count is a query. Reading leaves no trace of its own, so this is the one fact the method cannot derive and therefore records — on the event that produces it, and nowhere else. The mark is a high-water mark, so a reading pass reads oldest first: a newer item read before an older one would mark the older read unseen. A container's emptying is a close and counts like one: what the Owner reads for it is the closing comment — delivered against cut, and the `Ship condition` read against what shipped — which is the only place a feature's outcome is ever stated whole.

The unread limit is never raised because agents are idle. Idle agents cost nothing — that is the whole benefit of an abundant resource — and occupying them converts a free surplus into queue depth at the one place that cannot absorb it. It is tuned on evidence, one step at a time: raised when the queue never once stood at the limit across a full period, lowered when the oldest unread item is older than the time a reading takes, twice in a row.

Both readings come from close moments and review marks, so the tuning rests on no record kept for its own sake.

> [!EXCEPTION]
> **There is one exception: a stream that adds nothing to the Owner's queue does not count against the limit.** It parallelises freely, whatever the agent capacity, and everything else counts.

The exception is carried on the item, by the `unread-exempt` flag, and nowhere else. Without it the count is a query over one predicate — closed after the mark — and that query counts exactly what the exception excludes, so the limit blocks on work that never reaches the Owner at all. The flag is set at the filing by whoever files, because that is when the reason is known; set later it is an excuse.

Three streams qualify. Several independent attempts at one task add one result for N drafts.

Work whose whole verification is the test suite — a codemod, a dependency bump — never reaches the Owner at all, and research delivers a conclusion rather than a diff.

## An incident displaces, and leaves a handoff {rule}

An urgent item enters flat: no parent, no home, framing skipped because the outage states the goal. It does not queue behind the starting limit — restoring service is not discretionary — but it takes the in-flight slot, and its change is verified, merged and read like any other.

An incident is declared by whoever finds it. The Owner's word declares one outright; an absent Owner does not block it any more than they block framing — the agent that found it declares it, flags it `needs-owner`, and proceeds, and the Owner confirms or withdraws it on their return, which is a judgement on the agent's call and never a gate in front of the outage.

An incident that outgrows one pull request becomes a feature by the route [Classification](07-classification.md) states, and its tasks inherit the incident's standing: each takes the in-flight slot ahead of the queue, one at a time, and each is read like any other — the work whose outcome the Owner most needs to see is the last that leaves their queue.

The interrupted session ends, and everything held only in it is lost. Before the slot is surrendered, a handoff is written on the interrupted task carrying the one thing a fresh session cannot re-derive — the approaches already tried and abandoned. The task is then restarted from its item plus that comment, never resumed: a session that believes it has context it does not have cannot know what it is missing.
