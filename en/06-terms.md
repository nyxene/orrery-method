---
title: Terms
group: Reference
groupdesc: Looked up, never read through.
tagline: the vocabulary, fixed in English for every locale
lead: Every term below is normative and binds every other document. A term is never translated — a locale translates the prose around it, and the term itself stays English on every page, in every language.
---

## The terms {rule}

One term, one meaning, one line. A document using one of these words uses it in exactly this sense; a document needing a different sense needs a different word.

| Term | Meaning |
|---|---|
| item | One record in the tracker: a feature, a task, or a flat one. What a tracker calls it — issue, work item — is [Mapping](10-mapping.md)'s concern |
| release | A named set of work that ships together. It closes on the Owner's word, by an agent's act, once its content has shipped and its census and conformance ruling are on it — [Automation](09-automation.md) owns that transition; never a span of time |
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
| execution profile | Who or what holds each accountability and station in a given project. [Agents](12-agents.md) is one |
| session | One uninterrupted run of one party at one piece of work. What is not written down does not survive it |
| gate | A scripted check that blocks or performs — machinery, never memory |
| cold-start test | Could a session with no other context execute this? A task is ready only if yes |
| routing test | "Does X ship without this?" — asked of a feature to make tasks, of a release to make membership |
| discovery | Work noticed while doing something else, filed and done next |
| finding | What a verification reports on one change. It has three dispositions — fixed here, filed as its own item, or refused. The [Cycle](04-cycle.md) owns them |
| evidence package | Six named lines — Item, Built, Decided, Checks, Parties, Result — and the verifier's appended Verdict. [Artifacts](03-artifacts.md) owns the form and the moment |
| ledger | The append-only record of spend, with the dated price table beside it. [Measurement](08-measurement.md) owns its unit, its fields and its writer |
| handoff | Session residue — the approaches already tried and abandoned, written as a comment on the task |
| standing instructions | The repository's own written rules for every session — the one input an executor receives beside the item |
| framing | The passage from a wish to a goal |
| rollup | The derived tally of a feature's closed children against all of them |
| in flight | A task a party is working on right now |
| review mark | The close moment of the newest item whose evidence the Owner has read, written once per reading pass by the agent acting for them, and never overwritten |
| unread | Closed after the review mark — its evidence not yet read by the Owner |
| consistency check | The check that rules on the eight invariants and on every axis's exclusivity |
| exclusivity check | The check that lists items carrying a second value on one axis |
| census | What the closing agent runs at a release close. [Automation](09-automation.md) owns the list |
| incident | Work that displaces what is in flight — on the Owner's word, or on the finding agent's with `needs-owner` until the Owner rules |
| effort | The reasoning depth a run executed at, recorded in the ledger to explain variance — never to compute cost |
| Found-in · Origin · Escaped | The three lines a bug carries: where it surfaced, what shipped it, which check missed it |
| Trigger | The condition that turns a waiting item into real work, stated on the item when it is filed |
| Owner · Framer · Feature Lead | The three accountabilities. [Roles](02-roles.md) owns their definitions |
| Planner · Critic · Implementer · Auditor | The cast of the [Agents](12-agents.md) profile — staffing, never accountabilities |
| Rule · Principle · Guide | The tiers of force. The [Overview](01-overview.md) owns them |
| standing | Whether practice has confirmed a section: *Proven* if a shipped feature has been carried through it unchanged, *Pending* if not. Independent of force — a Pending Rule binds exactly as a Proven one does |
| refusal | The verification's third disposition: the change does what was asked and what was asked is wrong. The pull request closes unmerged and the task closes `refused` |
| conformance | The six statements a project meets to claim the method. The [Overview](01-overview.md) owns them |

## Terms are never translated {rule}

The English term is the identifier, in every locale. Prose around it may be in any language; the word itself does not change, so a reader of any locale meets the same string the queries, the classifications and the other locales use.

The names an item's lines carry are terms of exactly this kind: `Goal`, `Framed`, `Out of scope`, `Decided`, `Tasks`, `Planned`, `Ruling`, `Ship condition` on a feature; `Item`, `Date`, `Outcome`, `Retries`, `Runs` on a ledger line; `Found-in`, `Origin`, `Escaped`, `Trigger` on the items that bear them. They appear verbatim in bodies, in every locale, because a body is what gets grepped.

> [!WHY]
> A translated term is a second name for one object, and two names diverge the way two copies of any fact do. One of them then fails a search that the other passes, and nothing reports the miss.
