---
title: Roles
tagline: three accountabilities, four stations, and the one human at the top
lead: Three accountabilities carry the work, and their lifetimes differ on purpose — one is permanent, one exists for a moment, one lives with its feature. Beside them stand four stations every execution keeps.
---

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

[Agents](12-agents.md) is one profile: the one this method was written for. It has not been run — no project has yet worked to this method — so it illustrates a design rather than a practice, and this document is what binds.

## The Owner does not operate the tracker {rule}

Every item, classification, link, release and reopening is performed by an agent. The Owner reads, judges, and instructs in words.

A rule whose enforcement depends on the Owner remembering a convention is a defect in that rule.

> [!WHY]
> Classification is only useful if it is applied consistently, and consistency is what agents are reliable at. Moving it to the Owner makes the taxonomy decorative within a month.
