# Orrery Method 0.0.3

> Directed AI development. A way of running a software project where the work is done by AI agents, and one person directs, judges, and decides.


Work is described as features and tasks, executed by agents one task per
session, checked by independent agents and automated gates, and read afterwards
by the Owner against the evidence package each task leaves behind. Spend is
measured in tokens and recorded at every close.

---

# 1. Overview

*A method for software that agents write, that agents and automated gates check, and that one person directs. It is built around the two things in that arrangement that are genuinely scarce, and it discards everything that serves neither.*

```chips
3 | accountabilities
4 | stations
4 | artifacts
6 | stages
8 | invariants
```

## What is scarce {principle}

Implementation capacity is not the constraint. Agents produce changes faster than anyone can examine them, and adding more of them moves nothing.

Two things are finite. **The Owner's attention** — one reader, unscalable, and the only source of judgement in the arrangement. **Tokens** — the only input that is spent and does not return.

Justified confidence is what those two buy: warranted trust in a result nobody read line by line. Every rule here raises the confidence bought per token, or per unit of the Owner's attention. A practice that raises neither is removed, however respectable it looks.

> [!WHY]
> Optimising throughput in a system whose bottleneck is verification produces more unverified work, which is worth less than none: it still has to be examined, and now there is more of it.

## Confidence is manufactured {principle}

The Owner accepts a result they did not read because four independent checks stand around it — three before anything is built on it, one after. Each catches a class of failure the others cannot, and no two share a failure mode — because no two share a context. [Roles](#2-roles) states the separation that delivers that; without it the checks are one judgement counted four times.

![Four checks guard the passage: the plan ruling before cost, the gates on every change, the verification before merge, and the Owner after merge.](diagrams/confidence-gates.svg "Position is the point. A check placed after the spend cannot prevent it, and a check placed before the change cannot see it.")

Trust follows from the arrangement, not from any single verdict. [Roles](#2-roles) states what each station catches and what disqualifies a party from holding it.

## Derive, do not maintain {rule}

Every answer is computed at the moment of asking, from state that exists for another reason.

A maintained answer starts decaying the instant it is written, and it decays silently — nothing compares it to reality, so nothing reports the drift. A derived answer cannot go stale, because between two questions it does not exist.

Maintaining an answer is permitted only where derivation is impossible, and the impossibility is stated where the answer lives.

> [!WHY]
> A status field is wrong from the moment reality moves, and it announces nothing. The same fact is already in the branch, the pull request and the merge — asking those costs one query and cannot lie.

## What binds, and what does not {rule}

Every statement carries its force on its face. The badge beside a heading is the whole of its authority.

| Tier | Force | Deviating |
|---|---|---|
| Rule | Binding. The method does not hold without it | Is a defect |
| Principle | The reason the rules take the shape they do | Requires an argument from the principle itself |
| Guide | A recommended default | Requires a reason, recorded |

Unbadged prose explains. It binds nothing, and no tooling reads it.

A badge is required wherever force exists and forbidden where it does not: every section of Method and Reference carries one, and no section of Practice does. Practice illustrates, so it has no force to declare, and a badge there would assert one. The build holds both halves of that.

## Force and standing are different axes {rule}

Force is what deviating costs. Standing is whether practice has confirmed the section yet. They are independent, and collapsing them into one badge is how a corpus stops binding anything.

Every section carries a standing, and it is written where the force badge is. **Proven** — a real feature has been carried through it unchanged — is written as a second word: `{rule proven}`. **Pending** is the absence of that word, because it is the default and a default nobody has to write cannot drift out of date.

Pending never softens force. A Pending Rule binds exactly as a Proven one does, and deviating from it is a defect, not a licensed experiment. What Pending adds is that the deviation is *also* evidence: it is filed as a bug against the corpus, its `Escaped` line naming the section that failed to hold.

Standing changes on an event, never on attention. The census at a release close lists the sections every shipped feature passed through unchanged; those are the candidates, and the Owner's word promotes them — by adding the word to the heading, which is a diff like any other. A section demoted by a defect loses the word in the same act.

> [!WHY]
> A corpus that marks itself unproven and licenses deviation on that ground can be adopted whole, obeyed nowhere, and reported as compliant. Marking the same fact without touching force keeps the honesty and removes the escape: the reader knows what has been tested, and owes the method the same obedience either way.

## What conformance requires {rule}

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

## Conformance is ruled on, not asserted {rule}

A criterion nobody applies is a preference with a table around it, so the six are put to a party rather than left to the reader's conscience.

The ruling rides the release close, beside the census, and is performed by a party that executed none of the work in that release — the separations reach here exactly as they reach a plan or a change. It answers each of the six over everything the release closed, cites the query or the file it read for each, and lands on the release itself, where the census report already goes.

It holds until the next release close and no longer. Conformance is a statement about a body of work rather than a badge a project keeps, and a project that has closed no release since its last ruling has none — which is the honest answer, not a lapse.

> [!WHY]
> The moment conformance can be claimed without being ruled on, the claim costs nothing and means nothing, and the six criteria become decoration on a page nobody checks against. Riding the release close puts the ruling on an event that already has an actor, a record and an audience, so it is obeyed as a side effect of shipping rather than by anyone remembering to be honest.

## The tracker holds four facts, and derives the rest {rule}

An item carries its body, its classification, its parent if it has one, and whether it is open or closed. Nothing else is stored about it, ever. Every question a board answers — what stage is this at, how far along is that, what is in progress — is computed from those four at the moment of asking.

| The fact | What it is | Stated in |
|---|---|---|
| Body | The payload: goal, boundary, criteria, and the lines its kind carries | [Artifacts](#3-artifacts) |
| Classification | One type, at most one area, at most one priority, any number of flags | [Classification](#7-classification) |
| Parent | A feature owns its tasks. Two live levels, and releases above as membership rather than parentage | [Invariants](#5-invariants) |
| Open or closed | The only state there is. One of five closing acts sets it for a unit of work; a container's emptying, or the Owner's word on a release, sets it for a container — [Artifacts](#3-artifacts) states both | [The cycle](#4-the-cycle) |

There is no status field. Its absence is a decision this method is built on rather than a gap in it, and the reason is the one stated above: a stage is read off facts the work produces anyway, which [The cycle](#4-the-cycle) sets out stage by stage.

How the four are physically recorded — a label, a field, a native type, a link — is the tracker's business, settled per tracker in [Mapping](#10-mapping). Nothing on this page depends on the answer, which is what lets the method outlive a change of tooling.

## A rule rides an event, or it rides attention {principle}

A rule holds when it is attached to something that happens anyway and leaves a trace behind. The ledger rides the close, the handoff rides the interruption, the evidence package rides the merge: each is obeyed as a side effect of work already being done, and each neglect shows up as a missing artifact.

A rule attached to no event, or to an event that leaves nothing behind, is carried by attention alone — and attention is the one thing this arrangement cannot supply.

> [!WHY]
> Human methods lean on habit and on a cost the breaker eventually feels. A party that begins each session with no memory has neither, so a norm here converts to structure or it evaporates. Adding a rule therefore begins with finding the event it can ride, never with wording it more firmly.

## The boundary {rule}

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

## How to read this {rule}

A document's part decides its force: **Method** is normative and read in order, once; **Reference** is looked up, never read through; **Practice** illustrates and binds nothing.

A **Why** block carries the reason a rule exists. A rule whose reason has gone is deleted rather than obeyed, so the reason is the part worth reading twice.

The shortest useful path is this page, then [Roles](#2-roles), then [Playbooks](#11-playbooks).

---

# 2. Roles

*Three accountabilities carry the work, and their lifetimes differ on purpose — one is permanent, one exists for a moment, one lives with its feature. Beside them stand four stations every execution keeps.*

## Three accountabilities carry the work {rule}

Each of the three decides something no other decides, and the method names what each one is, never who holds it.

```cards
Permanent | Owner
Owns the product. Speaks wishes, sets the order, commits features to releases, reads evidence and refuses what misses the intent. The only human.
- Never operates the tracker.

Momentary | Framer
Takes a wish that outgrows one feature, researches it, and gives it form: features, their boundaries, the links between them, a checklist in each body. Deliberately blind to implementation.
- Dissolves when its knowledge has landed in the tracker.

Lives with its feature | Feature Lead
Runs one committed feature from start to ship: turns its goal into tasks just in time, answers questions inside the boundary, reacts to discoveries.
- Appears at the commit, closes with the feature.
```

## Authority is not shared {rule}

Each decision belongs to exactly one accountability. The others advise, dispute, or execute — they do not overrule.

| Accountability | Decides | Checked by |
|---|---|---|
| Owner | What is built, in what order, and whether the result satisfies | Nobody |
| Framer | How a wish splits into features, and what links them | The plan ruling, then the Owner's commit |
| Feature Lead | How the goal decomposes into tasks, and every question inside the boundary | The plan ruling, then the stations on everything it produces |

> [!EXCEPTION]
> **There is one exception.** The Owner overrules any verdict on licensing or business risk, because that judgement is theirs by definition.

## Four stations guard the flow {rule}

A defect must pass three unrelated checks before anything is built on it and a fourth after it ships, each held by a party independent of what it checks. That is what makes a result trustworthy without the Owner reading a diff — and what makes retrospective acceptance safe at all.

| Station | Catches | When | Held by |
|---|---|---|---|
| The plan ruling | The wrong approach, or one that cannot be verified | Before cost | A party that did not write the plan |
| The gates | Something adjacent broken silently | Every change | Machinery |
| The verification | A wrong claim, a deviation from the plan | Before merge | A party that did not write the change |
| The Owner's reading | Correct work that was not the work wanted | After merge | The Owner |

The plan ruling is passed twice, because planning happens twice: once on a Framer's split of a wish into features, once on a Feature Lead's split of a goal into tasks. The Framer's lands as the first `Ruling` line of every feature the split produced, and the Feature Lead's follows on its own feature. A `required` on the split is answered by the Feature Lead of the first feature the Owner commits, because the Framer has dissolved by design; a `required` on the tasks is answered by the Feature Lead that wrote them, and the second ruling is passed by a party that did not write the amendment.

> [!WHY]
> When one party produces and the same party checks, the failure that survives is the one they share. Independence breaks the correlation — the ruling has no stake in the plan, the verifier did not write the code, the gates hold no opinion, and the Owner brings context nothing else has.

## The separations are what bind {rule}

Four pairings are forbidden, and they are the whole of what an execution profile may not arrange away.

```spec The four separations
The plan and its ruling — a party never rules on a plan it wrote.
The change and its verification — a party never verifies a change it wrote.
The plan and its execution — a party never implements the plan it wrote.
The reasoning and its judgement — a station never runs in the session that produced what it judges.
```

The fourth is the one that makes the other three worth anything, and it is about context rather than about who is nominally seated. A station passed inside the conversation that produced the artifact inherits the reasoning whole: the same files read in the same order, the same alternatives already dismissed, the same blind spot. Nothing is found there, because whatever was missed is missing from the judge as well.

So a station is passed in **a session of its own**. It receives the artifact under judgement and the repository's standing instructions, reads the repository itself as much as it likes — and receives nothing of the session that produced what it reads. A plan written, ruled on and audited in one conversation is one judgement wearing three hats, whatever the roster says.

Different model families on top of that are an improvement rather than the mechanism. Two fresh sessions of one model already have separate contexts; two families additionally have separate blind spots, which is worth buying where the stake earns it and is not what independence rests on.

An accountability is not a hire and a station is not a job title. Who holds each — a person, an agent, several agents, one party in two of them where the separations allow — is the consumer's execution profile. Two stations are held by definition: the gates are machinery, and the Owner's reading is the Owner.

```spec A profile supplies
Distinguishable parties — who held which accountability is recoverable afterwards, or the profile names what it substitutes.
A party for each station the method does not staff by definition.
Where token counts are read from — the source a closing agent takes an item's spend from, per model and effort, so the ledger's `Runs` is a reading and not a guess.
Its own limits — what it arranges by construction and cannot show once the work is done. A session's identity is never among them: every session can name itself, and the fourth separation is checked against nothing else.
```

[Agents](#12-agents) is one profile: the one this method was written for. It has not been run — no project has yet worked to this method — so it illustrates a design rather than a practice, and this document is what binds.

## The Owner does not operate the tracker {rule}

Every item, classification, link, release and reopening is performed by an agent. The Owner reads, judges, and instructs in words.

A rule whose enforcement depends on the Owner remembering a convention is a defect in that rule.

> [!WHY]
> Classification is only useful if it is applied consistently, and consistency is what agents are reliable at. Moving it to the Owner makes the taxonomy decorative within a month.

---

# 3. Artifacts

*Four things exist. Everything else a tracker shows is a rendering over them — the last of the eight invariants says so.*

## Four things exist {rule}

Nothing else is an artifact, and anything a project keeps beside these four is either one of them under a different name or a fact with no home.

```cards
Container | Feature
A deliverable outcome, and the plan for reaching it. Owns tasks.
- Lives until its last child leaves.

Unit of work | Task
One pull request. Self-contained, with criteria and the commands that check them. Under a feature it is that feature's task; standing alone it is a flat item, and nothing else about it changes.
- Lives until its change merges, or a refusal closes it.

Record | Evidence package
What was built, what was decided, who stood where, what the checks said, and how to see the result.
- Lives as long as its item does.

Record | Ledger
One line per closing act. [Measurement](#8-measurement) owns the fields.
- Append-only. Never expires.
```

The unit of work is one closing act, and a parent is not part of its definition. For nearly all work that act is the merge of one pull request: a bug, a chore and a documentation change carry exactly the payload a task carries and pass exactly the same stations, with no feature above them. Parentage decides where an item is found, never what it owes.

Five acts close a unit of work and there is no sixth, so they are named here rather than improvised at the moment one turns up.

```spec What closes a unit of work
A merge — one pull request lands. Every task, and nearly every flat item.
A refusal — the verification rejects the approach; the pull request closes unmerged and the item closes `refused`.
An answer — a research question closes when its answer exists where the item said it would be written, whether or not anything merged. The answer is its evidence.
An act outside the repository — a setting changed, a branch removed, a value confirmed after a deploy. It closes when the change has been made, and its evidence package carries the observation that proves it in place of a diff.
A withdrawal — the Owner stops the work. The pull request closes unmerged and the item closes `withdrawn`, on their word rather than on any station's verdict.
```

None of the five is a lighter path. Each passes every station and each writes its ledger line, because what makes a result trustworthy is the arrangement around it, not the shape of the thing it produced.

A container is closed by none of them. A feature is emptied: its last child leaves by one of the five acts, or is detached or promoted away, and the party whose act left it empty closes it on the spot. A release is membership rather than parentage, so it does not empty: it closes on the Owner's word once its content has shipped and its census report and conformance ruling are on it. Both are transitions rather than a sixth act, [Automation](#9-automation) owns how each is performed, and neither writes a ledger line — the ledger prices acts, and closing a container is not one.

## The feature is the plan {rule}

There is no plan document. A feature's item states the goal, the boundary, the tasks it decomposes into, and their order. The plan ruling is passed on that item, and work begins only after it.

```spec A feature states
Goal — one sentence, in terms of what becomes possible, not what gets written.
Framed — who framed it, in what session. Written at framing, by the Framer, so the ruling on the split can be shown to have run elsewhere.
Out of scope — what this feature deliberately does not include.
Decided — every technical decision framing made that the wish did not make for it, each with the alternative it beat and the reason, so that no task re-derives a choice already paid for. A feature's decisions are the Framer's; a task's are its executor's, and live in the evidence package.
Tasks — as a checklist, in the order that resolves uncertainty fastest. Each line carries its task's payload until the line becomes an item; the [Cycle](#4-the-cycle) states what that payload is.
Planned — who wrote the tasks, in what session. Written at planning, by the Feature Lead, so the ruling that follows can be shown to have run elsewhere.
Ruling — the plan ruling's verdicts, one line per ruling, appended and never edited: who passed it, in what session, and the verdict — `passed`, `required` with what must change, or `refused` with why the goal returns to framing. A task opens only while the newest line reads `passed`. A feature born of a Framer's split carries the ruling on that split as its first line.
Ship condition — what must be true for the feature to be finished. Every demand that is not behaviour lives here and nowhere else: what it must survive, how fast, for whom, under what load. A feature that states none is claiming it has none.
```

A checklist line becomes a child item when *that line's* work begins, and the line is struck at that moment — one line at a time, never the list at once. One fact has one home, and a line that has become an item is no longer a plan.

So the list is spent rather than deleted, and what remains of it is the feature's unwritten work, standing where anyone can read it. That is what the executor closing the feature checks, and it is why just-in-time decomposition does not silently empty a parent that still owes tasks.

> [!WHY]
> A plan kept beside the tracker diverges from it, and nothing compares the two, so the divergence produces no signal. Keeping the plan in the object it plans makes divergence impossible rather than merely discouraged.

## The evidence package is a closed form {rule}

This is the artifact the Owner reads instead of the diff, so it is specified to the same standard as the ledger line and not one word looser. Six lines, named, in this order. A package missing a line is incomplete, and the item does not close.

```spec An evidence package states
Item — the task, named once, so the package can be found from the work and the work from the package.
Built — what changed in the world, in terms of behaviour rather than files. Where nothing was built — a research question, an act outside the repository — it states what is now true that was not, and says plainly that no code moved.
Decided — every decision the executor made that the item did not make for it, each with the alternative it beat and the reason. A decision with no alternative recorded was not a decision, it was a default, and it is not listed.
Checks — every gate that ran, by name, with its command and its result. Nothing summarised: a check reported without its command is a claim. Where no gate ran, it says so and names what stood in their place — the observation, the transcript, the source the answer was read from.
Parties — who executed and who verified, each with the session it ran in, identified as the execution profile makes them distinguishable, and what makes them independent. Where the parties are agents, that includes the model family each ran under.
Result — how to see it for yourself, from a cold start. A command, an address, a screen; for a research question, where the answer is written; for an act outside the repository, the observation that proves the change is in place. One of them, exact.
```

The verifier appends `Verdict` and nothing else: passed, or the finding and its disposition. That line is the only writing a second party performs, and it never edits what stands above it.

> [!WHY]
> Confidence is extended to a result nobody read line by line, and the package is the entire basis for extending it. Left to judgement, it comes out a different shape every time, and by the fifth one the Owner is reading five documents to find one fact — at the station the method says cannot absorb noise. The rational response to that is to read the diff instead, and at that moment the method has become a filing convention.

## Independence is recorded, or it is not independence {rule}

The `Parties` line exists because the method's central claim is checkable only if the arrangement it describes leaves a trace. A verifier who did not write the change is worth nothing after the fact if nothing says who wrote it.

Where the parties are agents, the line names the model family each ran under, so that a reader pricing the verdict can see whether one family was doubled. Whether the families must differ is [Roles](#2-roles)' rule, not this one: it is an amplifier bought where the stake earns it, and this line only records what was bought.

A profile that cannot make its parties distinguishable states what it substitutes, in the package, on every item. The session each party ran in is never among what is substituted — every session can name itself, and it is the one fact the fourth separation is checked against. A blank there is a defect, and it is the defect that quietly voids every other check.

## Provenance runs in both directions, and is derived {rule}

Nothing is traced by keeping a trace. Every link in the chain already exists for its own reason, so the chain is a query and cannot go stale.

Forward: a wish becomes a goal, the goal becomes a feature, the feature's checklist becomes tasks, a task names its pull request, the pull request names its commits, and the commits reach a release at its tag. Backward: a defect names the task that shipped it and the check that missed it, and the platform's own mirroring puts that reference on the feature's page without anyone writing it there.

A tracker that cannot walk that chain in both directions has not bound the method — [Mapping](#10-mapping) states it as a requirement on the binding rather than a hope about the platform.

## Every artifact has one writer {rule}

Nothing is co-authored. For each artifact exactly one party writes it, and the moment of writing is fixed rather than left to judgement.

| Artifact | Written by | At | Read by |
|---|---|---|---|
| Feature | The Framer | At framing | The plan ruling, then the Owner's commit |
| Task | The Feature Lead | At planning, in the feature's body; as its own item when work begins | Its executor |
| Flat item | Its discoverer | At the filing, whole — it has no feature to be planned inside | Its executor |
| Planned | The Feature Lead | At planning, on the feature | The plan ruling |
| Ruling | The party that passed the plan ruling | At each ruling, on the feature | The Feature Lead, then the conformance ruling |
| Evidence package | The executor | Before the verification | The verifier, then the Owner |
| Ledger line | The closing agent | At the close | Forecasts |
| Census report | The closing agent | At the release close, on the release | The Owner, and the next census |
| Conformance ruling | A party that executed nothing in the release | At the release close, after the census, on the release | The Owner |

> [!EXCEPTION]
> **There is one exception.** The verifier appends its verdict to the evidence package. It is the only case of a second writer, and it is append-only — the verifier never edits what the executor wrote.

## Lifetimes differ, and the difference is load-bearing {principle}

Confusing a durable record with a disposable one is what turns a tracker into a dumping ground. Each artifact has a defined end.

![Task lives until merge, feature until its last child leaves, evidence package as long as its item, ledger forever.](diagrams/artifact-lifetimes.svg "The evidence package outlives the work it describes, because the Owner may read it long after. The ledger outlives everything, because a forecast is built from history.")

## Session residue is written on the task {rule}

An executor that stops mid-task leaves behind the approaches it already tried and abandoned. That record — the handoff — is written as a comment on the task, and it dies with the task. When the task splits, the remainder is filed with it copied across, because the dead ends belong to the work and not to the number.

It is not promoted to an artifact because it has no reader beyond the next session on the same task. Anything worth keeping longer is a decision, and belongs in the evidence package.

> [!WHY]
> A dead end is the one thing a context reset destroys completely. The item and the change survive; the knowledge that an approach was tried and failed does not, so the next session walks into the same wall at full speed.

---

# 4. The cycle

*Work passes six stages. Each hands a named artifact to the next, the Owner gates the passage into a release and nothing after it, and their reading comes last of all.*

| Stage | Enters as | Leaves as | Passes when |
|---|---|---|---|
| Framing | A wish | A goal in one sentence, with an observable end state | Its two plausible readings agree on the acceptance criteria |
| Planning | A goal | A feature with its tasks | The plan ruling — and every task passes the cold-start test |
| Execution | One unit of work | A change and its evidence package | The change is inside the item's stated boundary |
| Verification | A change and its evidence | A verdict appended to the evidence | Gates green; every finding fixed, filed, or refused |
| Closing | A verified change | A closed item | Its closing act — [Artifacts](#3-artifacts) names the five. Nothing else forces it, nothing delays it |
| Acceptance | A closed task and its evidence package | The Owner's judgement | Nothing. Acceptance gates nothing |

![Four stages in a band, fanning at verification into five closing acts, with acceptance sitting after and gating nothing.](diagrams/item-lifecycle.svg "The fan is the point. Everything upstream of the verification is one path; what an item closes on depends on what it produced, and acceptance sits outside the flow entirely.")

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

Two rows are worth reading twice. A **feature closes when its last child leaves** — by whichever door — and the party whose act emptied it closes it there; [Automation](#9-automation) owns the two questions that party answers first. And **research closes without a merge**, because a question that concludes "do not build this" has succeeded; its answer is its evidence, and the item states in advance where that answer will be written so the close is checkable rather than declared.

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

Conditional work waits longer, on its Trigger line — [Classification](#7-classification) owns that rule. A limitation accepted for good is not filed at all: it is recorded beside the code it describes.

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

The defect then goes where it belongs. The feature stays open and returns to planning, because a wrong plan is an outcome judged wrong — a refusal is the one act that never empties a parent, [Automation](#9-automation) says so — and the corrected work is new tasks under it, opened only once a new `Ruling` line reads `passed`. Where the plan was right and the item misread it, the finding is a bug against framing, carrying the `Escaped` line that says so.

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

An incident that outgrows one pull request becomes a feature by the route [Classification](#7-classification) states, and its tasks inherit the incident's standing: each takes the in-flight slot ahead of the queue, one at a time, and each is read like any other — the work whose outcome the Owner most needs to see is the last that leaves their queue.

The interrupted session ends, and everything held only in it is lost. Before the slot is surrendered, a handoff is written on the interrupted task carrying the one thing a fresh session cannot re-derive — the approaches already tried and abandoned. The task is then restarted from its item plus that comment, never resumed: a session that believes it has context it does not have cannot know what it is missing.

---

# 5. Invariants

*Eight properties hold in every valid state of the tracker, and a structure that violates one is a defect, whoever produced it. The consistency check rules on what the tracker shows; a violation it cannot see is still a violation.*

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

![A feature owns its tasks; releases sit above as membership; flat items hang outside with no parent.](diagrams/hierarchy.svg "Two live levels. The release encloses without owning — membership records what ships together, and a flat item is found by query rather than by looking under a parent.")

An item with no parent is a **flat item** — a bug, a chore, a research question — typed, and homeless: a query finds it, and it enters a release only when that release cannot ship while it lives. [Classification](#7-classification) routes every kind of work.

> [!WHY]
> With no parent, a feature's tasks are related only by a prefix in their titles, and "what remains" stops being answerable except by reading. With a third level, every grouping view starts duplicating rows, and every added level is one more structure that must be kept true. Two is where both failures are avoided.

## The last child closes its parent {rule}

A task's closure is forced by the platform: the merge closes it. A parent's closure is forced by nothing, so it is performed by the party at the event — whoever's act left it with no open child closes it, having answered the two questions [Automation](#9-automation) states.

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

The check runs on two events and reports — a release close, and every pass in which the Owner reads. It blocks nothing, so an invariant can be broken between two runs and stand until one. [Automation](#9-automation) states what the report carries and who acts on it.

---

# 6. Terms

*Every term below is normative and binds every other document. A term is never translated — a locale translates the prose around it, and the term itself stays English on every page, in every language.*

## The terms {rule}

One term, one meaning, one line. A document using one of these words uses it in exactly this sense; a document needing a different sense needs a different word.

| Term | Meaning |
|---|---|
| item | One record in the tracker: a feature, a task, or a flat one. What a tracker calls it — issue, work item — is [Mapping](#10-mapping)'s concern |
| release | A named set of work that ships together. It closes on the Owner's word, by an agent's act, once its content has shipped and its census and conformance ruling are on it — [Automation](#9-automation) owns that transition; never a span of time |
| feature | A deliverable outcome and the plan for reaching it. Owns tasks. An outcome, not a product function — a documentation overhaul and a hardening pass are features |
| task | One pull request of work under a feature. The same unit with no feature above it is a flat item |
| flat item | An item with no parent. Homeless, and found by query — unless a release cannot ship while it lives |
| bug | A defect in shipped behaviour |
| chore | Upkeep with no change in behaviour |
| research | A question. Closes when the answer exists where the item said it would be written |
| docs | A documentation-only change |
| wish | What the Owner says they want, before anyone has stated what would satisfy it |
| goal | One sentence naming an observable end state. What framing produces |
| acceptance criteria | The observable outputs a task is judged by. A feature's equivalent is its `Ship condition` |
| boundary | What an item states it touches and refuses to touch. The diff stays inside it |
| primitive | One structural facility of a tracker — parentage, a link, a classification, a state |
| accountability | A named responsibility for deciding something. Not a hire |
| station | A check the flow must pass, held by a party independent of what it checks |
| party | Whoever holds an accountability or a station. A person, an agent, several |
| separation | A pairing the method forbids. Three are about a party on both sides of a check; the fourth is about a context — a station never runs in the session that produced what it judges |
| executor | The party performing one task |
| verifier | The party checking a change it did not write, before the merge |
| plan ruling | The verdict of a party that did not write the plan, delivered before cost |
| closing agent | The party whose act closes a unit of work: the executor merging or enacting, the researcher answering, the verifier refusing, or the agent closing on the Owner's word. A container has no closing agent — a feature is closed by the party whose act emptied it, a release by the agent acting on the Owner's word |
| execution profile | Who or what holds each accountability and station in a given project. [Agents](#12-agents) is one |
| session | One uninterrupted run of one party at one piece of work. What is not written down does not survive it |
| gate | A scripted check that blocks or performs — machinery, never memory |
| cold-start test | Could a session with no other context execute this? A task is ready only if yes |
| routing test | "Does X ship without this?" — asked of a feature to make tasks, of a release to make membership |
| discovery | Work noticed while doing something else, filed and done next |
| finding | What a verification reports on one change. It has three dispositions — fixed here, filed as its own item, or refused. The [Cycle](#4-the-cycle) owns them |
| evidence package | Six named lines — Item, Built, Decided, Checks, Parties, Result — and the verifier's appended Verdict. [Artifacts](#3-artifacts) owns the form and the moment |
| ledger | The append-only record of spend, with the dated price table beside it. [Measurement](#8-measurement) owns its unit, its fields and its writer |
| handoff | Session residue — the approaches already tried and abandoned, written as a comment on the task |
| standing instructions | The repository's own written rules for every session — the one input an executor receives beside the item |
| framing | The passage from a wish to a goal |
| rollup | The derived tally of a feature's closed children against all of them |
| in flight | A task a party is working on right now |
| review mark | The close moment of the newest item whose evidence the Owner has read, written once per reading pass by the agent acting for them, and never overwritten |
| unread | Closed after the review mark — its evidence not yet read by the Owner |
| consistency check | The check that rules on the eight invariants and on every axis's exclusivity |
| exclusivity check | The check that lists items carrying a second value on one axis |
| census | What the closing agent runs at a release close. [Automation](#9-automation) owns the list |
| incident | Work that displaces what is in flight — on the Owner's word, or on the finding agent's with `needs-owner` until the Owner rules |
| effort | The reasoning depth a run executed at, recorded in the ledger to explain variance — never to compute cost |
| Found-in · Origin · Escaped | The three lines a bug carries: where it surfaced, what shipped it, which check missed it |
| Trigger | The condition that turns a waiting item into real work, stated on the item when it is filed |
| Owner · Framer · Feature Lead | The three accountabilities. [Roles](#2-roles) owns their definitions |
| Planner · Critic · Implementer · Auditor | The cast of the [Agents](#12-agents) profile — staffing, never accountabilities |
| Rule · Principle · Guide | The tiers of force. The [Overview](#1-overview) owns them |
| standing | Whether practice has confirmed a section: *Proven* if a shipped feature has been carried through it unchanged, *Pending* if not. Independent of force — a Pending Rule binds exactly as a Proven one does |
| refusal | The verification's third disposition: the change does what was asked and what was asked is wrong. The pull request closes unmerged and the task closes `refused` |
| conformance | The six statements a project meets to claim the method. The [Overview](#1-overview) owns them |

## Terms are never translated {rule}

The English term is the identifier, in every locale. Prose around it may be in any language; the word itself does not change, so a reader of any locale meets the same string the queries, the classifications and the other locales use.

The names an item's lines carry are terms of exactly this kind: `Goal`, `Framed`, `Out of scope`, `Decided`, `Tasks`, `Planned`, `Ruling`, `Ship condition` on a feature; `Item`, `Date`, `Outcome`, `Retries`, `Runs` on a ledger line; `Found-in`, `Origin`, `Escaped`, `Trigger` on the items that bear them. They appear verbatim in bodies, in every locale, because a body is what gets grepped.

> [!WHY]
> A translated term is a second name for one object, and two names diverge the way two copies of any fact do. One of them then fails a search that the other passes, and nothing reports the miss.

---

# 7. Classification

*Work is classified on four axes. An item carries exactly one type, at most one area and one priority, any number of independent flags — and every value is applied by an agent, never by the Owner.*

## Four axes {rule}

An axis answers one question, and an item carries at most one of its values — the flags axis alone excepted, each flag being its own independent fact. An axis earns its place by answering a question that is actually asked, or by selecting a behaviour downstream; an axis that does neither is decoration with a maintenance cost.

| Axis | Question | Per item | Read by |
|---|---|---|---|
| type | What kind of thing is this? | Exactly one | Routing, every query, the exclusivity check |
| area | Which part of the system? | At most one | Batching — "is this the place I am already in" |
| priority | Does urgency deviate from normal? | At most one; absent means normal | The Owner, ordering work |
| flags | Which cross-cutting fact holds? | Each flag independent | Queries; `needs-owner` and `triage` by the Owner |

![Four axes: type exactly one of six, area at most one, priority at most one of three, flags any number of four.](diagrams/axes.svg "One axis answers one question. Only the flags axis admits more than one value, because each flag is an independent fact rather than a choice between alternatives.")

> [!WHY]
> Selection cost, not storage, is what caps a classification — and it is paid by an agent starting cold, with the list of values as its whole guide. One value per axis keeps every choice small: pick one of six types, one of a few areas, and done. Abandon that, and the question becomes "which subset of twenty applies", which no name and description can answer reliably.

There is no fifth axis. Status is derived, sizing is refused because the measured resource is tokens, sequencing lives in releases, and there are no teams to route between.

How an axis value is physically recorded — a label, a field, a native type — is the tracker's concern, and [Mapping](#10-mapping) settles it per tracker. Nothing in this document depends on the answer.

## Routing {rule}

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

## A bug names its provenance {rule}

A bug carries three lines in its body, each written by its own author at its own moment.

| Line | Names | Written by | At |
|---|---|---|---|
| Found-in | Where it surfaced — production, a reading, an audit, a planner's pass. Free prose, not a governed axis | The filer | The filing |
| Origin | The task or pull request that shipped the defect | The executor that fixes it; the framer of a repair feature | The fix; the framing of a repair feature |
| Escaped | The check that let it through — the framing test, or one of the four stations [Roles](#2-roles) names | The executor that fixes it; the framer of a repair feature | The fix; the framing of a repair feature |

Origin and Escaped are written at the fix because the executor already stands on the defective line, and the chain from there is mechanical: the repository's history names the commit, the commit its pull request, the pull request its task and feature.

A bug does not close without its Origin line — filled, or honestly not: *predates the method*, *interaction* with two links, *unknown*. False precision is worse than a recorded gap, and Escaped works without Origin: the nature of the defect names the missed check even when no commit is found.

> [!WHY]
> These three lines are what makes the retrospective mechanical instead of archaeological. And the reverse half costs nothing where the binding supplies the mirrored link: a closed feature then accumulates the record of what it left behind — derived, never maintained.

## A label is an axis, a link is a fact {rule}

A label carries a value from a small closed set that queries read constantly. A link carries a fact between two items — an origin, a blocker, a supersession.

Encode a fact as a label — one label per feature that ever shipped a bug — and the axis loses its ceiling: the set grows with history rather than with the system, and every future filing pays selection cost over all of it. A fact encoded as a label is an axis without a ceiling; an axis encoded as links is a query that does not exist.

## The values {rule}

The type axis is fixed at the six values above. The area axis is project-defined: each value names a place that can be pointed at — a value whose directories cannot be named is a topic, and topics belong in titles — and the axis is capped at eight values.

The priority axis has three values and no middle: *critical* pre-empts the task in flight, *high* goes before new scope in the same area, *low* waits until something is already in the file. A value meaning "the default" is applied to most items and read by nobody, so the default is carried by absence.

Two trackers were counted against this rule and both had used a middle value — 28 times each — before the rule existed. By the [Invariants](#5-invariants)' rule on history before a rule, those counts describe the default this axis removes rather than a need it denies; the first middle value applied *under* the rule would be the counter-example these are not.

Four flags exist. The *security* flag marks a change to the security posture, and the *unread-exempt* flag marks a close that never reaches the Owner's queue — [The cycle](#4-the-cycle) owns which streams qualify.

The *needs-owner* flag marks work stopped on a judgement only the Owner can make — the one fact no dependency link can express, because there is no item to point at.

The *triage* flag marks an item an agent filed on its own initiative and left. The Owner reads that queue, instructs, and the agent removes the flag by acting, so a lapse stays visible in the query instead of vanishing.

A discovery being done immediately after its task carries no triage: its evidence reaches the Owner through the unread queue.

## The first words classify {guide}

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

## Governance {rule}

Addition is costly and removal is cheap, by design. A new value replaces an existing one in its axis; a new axis replaces an axis. The one exception is the area axis, which grows without a swap while the codebase grows a genuinely new part, until the cap.

An agent never invents a value on its own initiative. The value set is the interface every later session reads, so extending it is the Owner's call; an agent that finds the set insufficient files the case under the needs-owner flag and waits.

Retirement is the default response to doubt. Removing a value leaves its items otherwise untouched and restoring one is a single act, so nothing is lost by retiring early.

The census — [Automation](#9-automation) owns it — carries this axis's half: a value at zero lifetime uses is removed and reported, nothing being there to decide, and a value under ten is reported as the candidate for the next swap, which is the Owner's call.

---

# 8. Measurement

*Tokens are the one input that is spent and does not return — and the one quantity that is measured rather than guessed. Every rule here exists to keep that measurement honest.*

## Spend is recorded, cost is computed {rule}

The ledger records spend — token counts, the model, and the date. Cost is computed at the moment of asking, from the price in effect on that date, and a computed cost is never stored.

Prices live in a dated table beside the ledger — the same record, extended when a vendor changes a price rather than at a close. It is appended and never edited, so its history is the archive. When no row covers a date, the cost is not computed from a nearby rate — the gap is the finding, and it is closed before the question is asked again.

> [!WHY]
> Prices change on announced dates. A cost stored at close is a fact about the day it was frozen: the same spend has two honest answers on two sides of a price change, and only a stored number can be wrong about both.

## The ledger has one writer {rule}

The closing agent appends one line per closing act, at the moment of the close. Never by hand, never by the Owner, and an existing line is never edited.

A container's close — a feature's emptying, a release's on the Owner's word — is not a closing act and gets no line. Framing and planning are spent before any task exists, and the ledger does not see them: a feature's price is the sum of its tasks' lines plus an overhead this record does not measure, and the forecast says so rather than pretending to a completeness it lacks.

```spec A ledger line states
Item — read from the branch name, so nothing is typed twice.
Date — the close moment every cost computation resolves prices against.
Outcome — the closing act, named: merged, refused, withdrawn, answered, or enacted. Five acts, five values, and no sixth. Only `merged` feeds the forecast's denominator.
Retries — failed attempts absorbed before the outcome was reached.
Runs — per model and effort, the token counts read from where the execution profile says they are read from — [Roles](#2-roles) requires every profile to name that source — cached reads and writes recorded as their own quantities.
```

> [!WHY]
> A ledger maintained by discipline decays the way every maintained answer decays — silently. The close is an event that already happens, carried by an agent already acting, so the write has a forcing function instead of a memory.

## Abandoned work stays visible {rule}

A closed item that merged nothing still gets its line, and its `Outcome` says which act closed it. That distinction is not bookkeeping: `refused` is a station exercising the power the method gave it, `withdrawn` is the Owner cancelling work, and a ledger that wrote one value for both could not tell how often the verification has ever refused — which is the only record of whether the method's newest station has fired at all.

The forecasting unit is **cost per merged task**: every line feeds the numerator, only merged lines feed the denominator.

A task that took three attempts to land is visibly more expensive than one that landed first try. Averaging only the merged lines reports the cheaper, false number, and the variance a forecast exists to expose is smoothed away before anyone looks.

## A forecast is segmented and recency-weighted {rule}

A forecast is computed per model, never blended across them. Spend on two models averages into a figure with two price tables and two efficiency profiles behind it — a number describing no model that exists, offered about a next task that will run on one specific model.

Each line's contribution decays with its age. The task boundary is fixed — one task, one pull request — but what fits inside it grows with model capability, so an old average was measured against smaller tasks and understates today's. The error runs in one direction, toward optimism, and nothing in an unweighted average signals it.

The decay half-life is a stated knob, not a constant; the default is seven months, set against the pace at which models are replaced and measured against nothing yet. A forecast is reported as a property of the model and the half-life together, and it predicts the cost of one already-scoped task — how many tasks a goal needs is not its question.

---

# 9. Automation

*Every answer the method gives is obtained one of three ways — a gate enforces it, a query derives it, or a judgement supplies it. Confusing the three is how tracking systems rot, so the boundary is drawn here and everything is on one side of it.*

## Three categories {rule}

Every answer the method gives is obtained one of three ways, and a project that cannot say which way it got one is maintaining it by memory.

**Enforced** — a gate blocks it or performs it: a script, never anyone's memory. **Derived** — computed at the moment of asking, as the [Overview](#1-overview) requires. **Human** — a judgement, not a fact, which no query can produce.

Human names where the judgement originates, never whose hands perform the write. The Owner does not operate the tracker, so an agent performs every mutation — including the one that records the Owner's decision — and the verifier's verdict is Human too: reasoning about content is judgement, whichever party holds it.

## No transition is automated {rule}

The platform forces a task closed at its merge. A container's closure is forced by nothing — and the answer is not a machine watching for it, but the party already standing at the moment it becomes true.

**The party whose act leaves a parent with no open child closes that parent.** For nearly every feature that is the executor merging its last task; it is equally the agent withdrawing the last one on the Owner's word, or whoever detached, deleted or promoted it away to a release of its own. Each is an act with a party, and that party answers two questions on the way out: does the body still carry unwritten checklist lines, and is any child still open. Where both answers are no, the feature closes and its `Ship condition` is read against what shipped — the one moment in the method where that line is read at all. Where either answer is yes, the feature stays open and nothing is decided.

A refusal is the one act that empties nothing. A verifier's refusal that closes a feature's last open child leaves the feature open and sends it back to planning — a refused approach is a plan judged wrong, and the [Cycle](#4-the-cycle) owns that return — so the feature is emptied only by a child that left successfully or on the Owner's word. And a feature the Owner withdraws before its children have left is emptied on their word: the agent acting on it strikes the remaining checklist lines as cut, closes or detaches the open children as the Owner directs, and then closes it by the same procedure, with a closing comment that reads all cut.

A release is membership rather than parentage, so it has no children to leave and is not emptied. It closes on the Owner's word, by an agent's act, once its content has shipped and the census report and the conformance ruling are both on it — the report is what the close is refused without, not the close itself. That too is a transition and not an act, and it writes no ledger line.

That is what removes the last piece of unattended machinery from this method. **Nothing here runs without a party standing behind it**, and the transition rides an event that happens anyway rather than a process that has to be kept alive.

This document owns both procedures. The [Invariants](#5-invariants) state that the transition has a party, the [Cycle](#4-the-cycle) states when a feature's life ends, the [Terms](#6-terms) say when a release closes, and none of them restates how — one fact, one home.

```spec Closing a feature refuses
To close over an open child — read live, never from a rollup that may lag.
To close over a remaining checklist line — an unwritten task is work the feature still owes, and a feature closed above one reports a delivery nobody made.
To close silently — the closing comment splits delivered from cut, because a rollup reading 6/6 without the split lies about what shipped.
To reopen — a feature reopens on the Owner's word alone, and a task never does.
```

> [!WHY]
> An automation here would be watching for a state a party already has in hand, and it would be the only thing in the method running when nobody asked it to. The transition was never hard to perform; it was hard to *remember*, and an event with an actor solves remembering without adding a machine that can fail silently in a quiet repository.

## Three automations are never built {rule}

Three machines are refused outright, and the refusals hold for anything shaped like them.

A **stale bot** converts Owner inactivity into item invalidity, and no clock can tell those two facts apart. It exists to manage inbound volume from strangers; there are no strangers here, so it would have nothing to do except close deliberately deferred decisions on a timer.

**Automated prioritisation** computes a rank from metadata, and priority is not in the metadata. Staleness is a fact about elapsed time; priority is intent, held by the Owner alone, and a formula that writes one anyway produces a number nobody has grounds to trust.

**Any writer sharing a field with a human.** Where automation and a person set the same value they eventually disagree, and the automation wins by being tireless — the bot re-applies what the human just removed until the human turns it off. Automation writes fields no human touches, and nothing else; that constraint binds every future automation, not just these three.

## The middle of an item's life belongs to nobody {principle}

Reliable enforcement exists at exactly two moments: creation and close. Between them no event fires, nothing compares recorded state to reality, and any fact written there is maintained by memory alone.

This is not a gap left unclosed — it is the reason state is derived rather than kept. What cannot be maintained honestly is not maintained at all.

## Each check rides its own event {rule}

The consistency check over the [Invariants](#5-invariants) and the census each ride an event that has an actor — never a schedule and never a memory. Each surfaces a decision: retire the value, promote the task, prune the link. The surfacing is derived; the decision stays with the Owner.

Their events differ because their subjects do. The census reads a shipped set, so it runs at a release close, performed by the closing agent. The consistency check reads the state of the tracker, which is wrong from the moment it is wrong, so it runs at every reading pass as well — performed by the agent writing the review mark.

The census is a closed list.

```spec What the census reports
Value use — each classification value's lifetime uses, removing those at zero and reporting those under ten.
Fired Triggers — every waiting item whose Trigger has become true.
Escaped defects — every item closed since the last release carrying an Escaped line, grouped by that line and area, whatever type the item wears.
Standing — the sections every feature in this release passed through unchanged, offered as candidates for Proven, and the sections a defect sent back to Pending.
```

The conformance ruling rides the same close and lands on the same release, and it is not part of the census: the census is counted by the closing agent, and the ruling is passed by a party that executed none of the release — the [Overview](#1-overview) owns it, and the [Artifacts](#3-artifacts) give each its writer.

That report is where the project's own instructions and checks get their evidence: a cluster on regression is a missing class of test, a cluster on correctness is a weak audit, a cluster on framing is a question nobody asks.

The grouping is derived. What to change is a judgement, and the change itself is an act — filed and executed like any other work.

The census leaves its report on the release it closed. A release closed without one is not closed — the report is a condition of the close rather than a courtesy, so a skipped census is as visible as a missing evidence package.

The census is as frequent as the releases and no more, so a project that has not closed one has not run it. That is the price of refusing a schedule, and it is paid where it costs least: a project with nothing shipped has no shipped history to be wrong about.

Every run of the consistency check lists the invariants broken since its last one — a task closed by two pull requests, a task closed by neither a merge nor a refusal, a parent left open — and the axes broken with them: an item carrying a second value on one axis, which is a fact about live state and belongs to this check for the same reason the check has a second event. At a release close that list rides the census report; at a reading pass it sits beside the review mark. A broken invariant is never an exception: it means the work was decomposed or executed wrongly, and it gets the analysis a bug gets.

> [!WHY]
> A scheduled check is a standing commitment, and the method admits none. It also fails in the worst direction: scheduled jobs die silently in quiet repositories, so the check stops running exactly when the backlog has drifted unwatched the longest — green by absence, at the moment green means least.

---

# 10. Mapping

*The method's objects are not platform features, so they survive a change of tracker. A binding says which native primitive carries each one — and what it deliberately leaves unused.*

## What a binding supplies {rule}

A tracker may bind the method only if it supplies all of these; anything it lacks, the binding states as lacking rather than approximates.

```spec A binding supplies
Containment — a feature owning its tasks, with a rollup derived from it.
A release container — a named set an item belongs to, closable, and needing no dates.
Closure by merge — the pull request closing its task with no second act.
Dependency links — native, queryable, removed by the blocker closing.
The mirrored link — a reference in one item's body appears on its target, so provenance reads in both directions.
The axes — a home for type, area, priority and flags that an agent can read and write.
A home for the review mark — the one fact the method cannot derive needs somewhere append-only to live, and it is a file in the repository rather than a tracker object.
A record that survives the work — the evidence package and its verdict stay readable on a closed item, because that is where independence is shown after the fact.
```

A primitive the method does not use is left untouched, never repurposed. An unused field costs nothing; a repurposed one carries someone else's semantics into every query that reads it.

## Two bindings in full {rule}

These two are written out object by object because everything after them is stated as a difference from one of the two. Each row fixes one object to one native primitive, and a project on either tracker uses the column as written.

| Object | GitHub | Jira |
|---|---|---|
| Feature | Issue, `type/feature`, sub-issues | Epic |
| Task | Sub-issue, one pull request, `Closes #N` | Story, one pull request, a transition on merge |
| Flat item | Issue with no parent and no milestone | Story, Bug or Task with no Epic and no fixVersion |
| Release | Milestone | Version — released as an act, dates left empty |
| Evidence package | A comment on the issue | A comment on the issue |
| Ledger | A file in the repository — no tracker object | A file in the repository — no tracker object |
| Dependency | `blocked-by` link | The `blocks` issue link |
| Type axis | `type/` labels | Issue type |
| Area axis | `area/` labels | Component |
| Priority axis | `priority/` labels | The Priority field |
| Flags | `flag/` labels | Labels |
| Feature progress | Sub-issue rollup | Epic progress |
| The review mark | A repository file, appended once per reading pass | A repository file, appended once per reading pass |

These two are written out because they are the two most projects are already on: one is where the code lives, the other is where the work lives. Between them they cover both shapes a tracker takes — every axis in labels, or every axis in a field of its own — so a third column would repeat *a file in the repository* four more times and bury the handful of cells that actually differ.

Everything after them is stated as a difference, and each opens by naming which column to read.

| Binding | Read | And expect |
|---|---|---|
| GitHub | — | The most common; derived like the rest |
| Jira | — | Closure needs a configured transition; a blocking link outlives its blocker |
| GitLab | GitHub | Containment and dependencies are paid features; below that tier it does not bind |
| Azure DevOps CMMI | Jira | Most of the platform left deliberately unused |
| Linear | GitHub for closure, Jira for the axes | Cycles are a time box and stay unused |
| YouTrack | Jira | It will model anything, including the method wrongly |

## GitHub {rule}

On GitHub every axis is carried by labels. That is forced rather than chosen, because the platform's structured type primitive exists only for organisations. On a personal account there is no alternative an automation token can read, which is why label discipline is structure rather than hygiene; if the repository ever moves to an organisation, the migration is mechanical — read each issue's single `type/` label, set the type, delete the label.

The binding supplies the naming the axes themselves do not prescribe: `axis/value`, lowercase, hyphens between words, singular nouns. The prefix makes the axes visible to an agent reading a flat label list and checkable by string matching, and every label in an axis wears one colour — two chips of one colour on one issue is exclusivity broken, readable at a glance on every axis but the flags, whose members legitimately share theirs. The platform's default labels are deleted before the first issue is filed, because each is a bare-word second home for a value the axes already carry.

Everything else is native. Sub-issues carry containment and the rollup, `Closes #N` and the linked branch both close a task at merge, dependency links come off when the blocker closes, and the ready queue is the open-and-unblocked search.

A release's bytes are whatever `main` holds at its tag — membership in the milestone records the commitment, and the changelog derives from the merges between two tags. A bug's `Origin: #N` line needs no machinery at all: the platform mirrors every body link onto the target's timeline, so the feature's page carries its own after-history unasked.

## Jira {rule}

Where GitHub puts every axis in a label, Jira gives each one a field of its own: issue type carries type, Component carries area, Priority is its own field, and labels are left to the flags alone. There is no naming convention to keep and no colour to read, because the platform enforces one value per field without being asked.

One primitive here is better than anything else in this document. **A Version is a release exactly as the method defines one** — a named set an item belongs to, released as an act, and carrying no dates unless someone adds them. Every other binding needs a caveat about time at this row; this one needs none.

Containment offers three levels where the method uses two. Epic owns Story, Story owns Sub-task, and the method stops at the first pair: a feature is an Epic, its tasks are Stories, and Sub-task stays unused like every other primitive the method does not need.

Two things this binding states as lacking rather than approximates.

**Closure is not one act.** The platform does not close an issue when a pull request merges; a transition has to be configured to do it. Until that automation exists, the merge and the close are two acts, and the second one is somebody remembering — which is the failure the method names everywhere else. The binding is incomplete until the transition is wired, and a project that has not wired it does not have this binding.

**A blocking link outlives its blocker.** The link stays after the blocker closes, so the ready queue cannot be "open and unblocked" as a plain link query; it is open, minus those whose blockers are still open. The fact is recoverable and the query is one clause longer — but it is a query the other bindings do not need, and it is stated here rather than discovered later.

## GitLab {rule}

Read the GitHub column and change almost nothing. `Closes #N` in a merge request closes its issue at merge, a milestone carries the release, labels carry the axes with the same `axis/value` naming, and mentions mirror onto their target.

What differs is not shape but tier. **Epics, blocking dependencies and scoped labels are paid features.** That matters unevenly:

- Without epics there is no containment above an issue, and the method's two live levels have nowhere to sit. A checklist inside an issue is not containment: it produces no child item, no rollup and nothing a query can find.
- Without blocking links, dependency is prose again — the thing the method replaced with a link precisely because prose is not queryable.
- Scoped labels are what the platform can enforce; without them exclusivity on an axis is discipline, exactly as it is on GitHub.

So on a free tier this binding states two of the eight as lacking, and two lacking is not a binding. On a tier that carries them, GitLab binds the method as completely as GitHub does, and the scoped labels make it stricter — the platform refuses a second value on one axis instead of leaving it to a colour convention.

## Azure DevOps CMMI {rule}

Read the Jira column: the axes have native homes here too. Area dissolves into Area Path, priority into the Priority field, and only type and the flags need tags — so the label discipline shrinks the same way, and for the same reason.

Two rows differ. A task is a Requirement, closed by the pull request's `AB#` completion — which is closure in one act, as GitHub has it and Jira does not.

An Iteration Path serves as the release with its dates left empty: the platform reads an iteration as a time box, and the method forecasts in tokens, so a date would assert something nobody measured. Jira's Version needs no such instruction.

CMMI arrives with more machinery than the method consumes — Change Request, Risk, Review, the estimate fields, a state machine with a Resolved stage. All of it stays unused, and that is the binding's defining feature rather than a footnote: state is derived here as everywhere, the rollup answers progress, and no hand moves a work item across a board.

## Linear {rule}

Read GitHub for closure and Jira for the axes. A merged pull request closes its issue through the native integration, and priority is a field rather than a label, as it is in Jira.

The one thing to get right is the release. **A Cycle is a time box, and the method does not forecast in time** — so Cycles stay unused and a Project carries the release. Leaving that unstated is how a project ends up planning in fortnights inside a method that measures in tokens, having never decided to.

Everything else lands cleanly: sub-issues carry containment and its rollup, blocking relations are native and queryable, comments outlive the work, and the API is a write path an agent can hold. Of the four bindings stated here it is the one that asks for the fewest caveats.

## YouTrack {rule}

Read Jira, and expect the same shape with more of it configurable: the axes are custom fields, so type, area, priority and the flags each get a field rather than sharing a label namespace, and a Version-like field carries the release.

That configurability is the caution. **A tracker that will model anything will let a project model the method wrongly** — a fifth axis, a status field, an estimate in hours — and none of it will be refused. The value set and the eight invariants are the whole of the guard here; the platform supplies none of it.

Closure rides commit commands and the VCS integration, which puts it in the same position as Jira: it works, and it is configuration rather than a property of the platform. The binding is incomplete until that configuration exists.

## What is behind each of these {guide}

Six bindings laid out in a table read as six tested arrangements. They are not, and saying so where a reader meets them costs one paragraph.

**No binding has been run, because no project has yet worked to this method.** All six are derived the same way: from what each platform documents about its own primitives, checked against the eight requirements and nothing else.

**Order on this page is popularity, and nothing else.** GitHub leads because a reader is most likely to already be there; Jira sits beside it in the full table because that is where most projects already keep their work. Neither position claims a binding is better known — the two are equally unproven, along with the four after them.

Their standing is `Pending`, like the corpus carrying them. The first project to run one will find things this page does not say, and when it does, the finding belongs here, on the binding, filed like any other defect.

---

# 11. Playbooks

*The method walked end to end, from a vague wish to a cost forecast. Every act shown here is abstract — what a step looks like in a concrete tracker is Mapping's subject, not this one's.*

Nothing on this page carries a badge, and that is the rule rather than an omission: force is what deviating costs, and a page that binds nothing has no force to declare. The worked examples come from one project — a chart-drawing application — named here once so that no reader has to infer a domain from a defect.

## An evidence package, written out

The specification is in [Artifacts](#3-artifacts). This is one filled in, for a task that added a second chart to a workspace that held one.

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

A live bug arrives while a task is in flight. An agent files it flat — a bug, no parent, no home — and the Owner decides it displaces the current work, which is a judgement, not a rule; were the Owner away, the agent would make that call itself under `needs-owner`, as the [Cycle](#4-the-cycle) allows.

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

---

# 12. Agents

*The execution profile the method was written for, one human above a cast of agents. No project has yet worked to this method, so this is a design rather than a record. It illustrates and binds nothing — the separations bind, this staffing does not.*

## The cast

Every accountability below the Owner is held by an agent, and no agent holds two of them on one piece of work. The Framer is an agent here, framing in conversation with the Owner and dissolving when its output lands in the tracker.

The cast names the four seats that remain: the Planner is the Feature Lead's seat, the Implementer is the executor's, the Critic holds the plan ruling, and the Auditor holds the verification. The last two stations need no cast — the gates are scripts, and the Owner reads.

![The Planner is checked by the Critic, the Implementer by the Auditor, and the Owner decides over both pairs.](diagrams/role-pairing.svg "Two producers, two checkers, one human above both pairs. No agent appears twice in a row.")

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

---

# 13. Application

*How a project starts working to the method, and one tool built to follow it. This appendix stands outside the twelve documents: it binds nothing, and the method does not depend on anything it names.*

## Starting

The method is text, and taking it up means doing what it says, not installing anything. A project that wants to start does five things, in this order.

1. **Name the Owner.** One person whose attention gates every decision the method leaves to a human. Without one, nothing else in the method has anyone to report to — read [Roles](#2-roles) first.
2. **Pick the tracker and map it.** The artifacts live in whatever tracker the project already uses. [Mapping](#10-mapping) says which of its objects carries a feature, a task and an evidence package.
3. **Staff the seats.** Decide who or what holds each accountability, keeping the separations: no party checks its own work. [Agents](#12-agents) shows one staffing.
4. **Make the gates run by themselves.** A gate that runs when someone remembers is not a gate. Whatever the project's checks are, they run on every change without being asked.
5. **Walk one item end to end.** [Playbooks](#11-playbooks) shows the walk. One feature taken from wish to merge teaches more than another reading.

A project may take the parts it wants and leave the rest. What it may not do is take the parts and keep the name.

## Orrery, one tool that follows the method

[Orrery](https://github.com/nyxene/orrery) is a Claude Code plugin written to follow this method. It is one way to staff the seats of [Agents](#12-agents) with tooling, not the only one, and nothing in the method requires it.

| What the method asks for | What Orrery gives it |
|---|---|
| Framer | the `frame` skill — a vague wish turned into a stated goal by asking, before any planning |
| Planner | the `plan` skill — a plan drafted before any cost is spent |
| Critic, the plan ruling | the `critic` agent, joined by the `architect` agent when the approach itself is uncertain |
| Implementer | the `build` skill — an approved plan executed across agents, with the audit before each commit |
| Gates | guards that refuse destructive commands, beside the project's own pre-commit and CI checks |
| Auditor, the verification | the `auditor` agent, a fresh session, on a different model family from the implementer where the budget allows |
| Owner | stays a person: nothing in Orrery holds a merge for them, and they read what merged, the method's last station |
| Handoff | the `handoff` skill — what a session learned, carried across a context reset |

The mapping is Orrery's claim about itself. Where Orrery and the method disagree, the method is the one that binds, and the disagreement is a defect in the tool.