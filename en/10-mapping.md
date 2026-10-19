---
title: Mapping
tagline: two bindings in full, four more as their differences
lead: The method's objects are not platform features, so they survive a change of tracker. A binding says which native primitive carries each one — and what it deliberately leaves unused.
---

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
