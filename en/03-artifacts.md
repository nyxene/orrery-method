---
title: Artifacts
tagline: the four things that exist
lead: Four things exist. Everything else a tracker shows is a rendering over them — the last of the eight invariants says so.
---

## Four things exist · *Rule*

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
One line per closing act. [Measurement](08-measurement.md) owns the fields.
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

A container is closed by none of them. A feature is emptied: its last child leaves by one of the five acts, or is detached or promoted away, and the party whose act left it empty closes it on the spot. A release is membership rather than parentage, so it does not empty: it closes on the Owner's word once its content has shipped and its census report and conformance ruling are on it. Both are transitions rather than a sixth act, [Automation](09-automation.md) owns how each is performed, and neither writes a ledger line — the ledger prices acts, and closing a container is not one.

## The feature is the plan · *Rule*

There is no plan document. A feature's item states the goal, the boundary, the tasks it decomposes into, and their order. The plan ruling is passed on that item, and work begins only after it.

```spec A feature states
Goal — one sentence, in terms of what becomes possible, not what gets written.
Framed — who framed it, in what session. Written at framing, by the Framer, so the ruling on the split can be shown to have run elsewhere.
Out of scope — what this feature deliberately does not include.
Decided — every technical decision framing made that the wish did not make for it, each with the alternative it beat and the reason, so that no task re-derives a choice already paid for. A feature's decisions are the Framer's; a task's are its executor's, and live in the evidence package.
Tasks — as a checklist, in the order that resolves uncertainty fastest. Each line carries its task's payload until the line becomes an item; the [Cycle](04-cycle.md) states what that payload is.
Planned — who wrote the tasks, in what session. Written at planning, by the Feature Lead, so the ruling that follows can be shown to have run elsewhere.
Ruling — the plan ruling's verdicts, one line per ruling, appended and never edited: who passed it, in what session, and the verdict — `passed`, `required` with what must change, or `refused` with why the goal returns to framing. A task opens only while the newest line reads `passed`. A feature born of a Framer's split carries the ruling on that split as its first line.
Ship condition — what must be true for the feature to be finished. Every demand that is not behaviour lives here and nowhere else: what it must survive, how fast, for whom, under what load. A feature that states none is claiming it has none.
```

A checklist line becomes a child item when *that line's* work begins, and the line is struck at that moment — one line at a time, never the list at once. One fact has one home, and a line that has become an item is no longer a plan.

So the list is spent rather than deleted, and what remains of it is the feature's unwritten work, standing where anyone can read it. That is what the executor closing the feature checks, and it is why just-in-time decomposition does not silently empty a parent that still owes tasks.

> [!WHY]
> A plan kept beside the tracker diverges from it, and nothing compares the two, so the divergence produces no signal. Keeping the plan in the object it plans makes divergence impossible rather than merely discouraged.

## The evidence package is a closed form · *Rule*

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

## Independence is recorded, or it is not independence · *Rule*

The `Parties` line exists because the method's central claim is checkable only if the arrangement it describes leaves a trace. A verifier who did not write the change is worth nothing after the fact if nothing says who wrote it.

Where the parties are agents, the line names the model family each ran under, so that a reader pricing the verdict can see whether one family was doubled. Whether the families must differ is [Roles](02-roles.md)' rule, not this one: it is an amplifier bought where the stake earns it, and this line only records what was bought.

A profile that cannot make its parties distinguishable states what it substitutes, in the package, on every item. The session each party ran in is never among what is substituted — every session can name itself, and it is the one fact the fourth separation is checked against. A blank there is a defect, and it is the defect that quietly voids every other check.

## Provenance runs in both directions, and is derived · *Rule*

Nothing is traced by keeping a trace. Every link in the chain already exists for its own reason, so the chain is a query and cannot go stale.

Forward: a wish becomes a goal, the goal becomes a feature, the feature's checklist becomes tasks, a task names its pull request, the pull request names its commits, and the commits reach a release at its tag. Backward: a defect names the task that shipped it and the check that missed it, and the platform's own mirroring puts that reference on the feature's page without anyone writing it there.

A tracker that cannot walk that chain in both directions has not bound the method — [Mapping](10-mapping.md) states it as a requirement on the binding rather than a hope about the platform.

## Every artifact has one writer · *Rule*

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

## Lifetimes differ, and the difference is load-bearing · *Principle*

Confusing a durable record with a disposable one is what turns a tracker into a dumping ground. Each artifact has a defined end.

![Task lives until merge, feature until its last child leaves, evidence package as long as its item, ledger forever.](../diagrams/artifact-lifetimes.svg "The evidence package outlives the work it describes, because the Owner may read it long after. The ledger outlives everything, because a forecast is built from history.")

## Session residue is written on the task · *Rule*

An executor that stops mid-task leaves behind the approaches it already tried and abandoned. That record — the handoff — is written as a comment on the task, and it dies with the task. When the task splits, the remainder is filed with it copied across, because the dead ends belong to the work and not to the number.

It is not promoted to an artifact because it has no reader beyond the next session on the same task. Anything worth keeping longer is a decision, and belongs in the evidence package.

> [!WHY]
> A dead end is the one thing a context reset destroys completely. The item and the change survive; the knowledge that an approach was tried and failed does not, so the next session walks into the same wall at full speed.
