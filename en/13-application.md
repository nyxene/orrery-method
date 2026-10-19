---
title: Application
group: Appendix
groupdesc: Beside the method, not part of it.
tagline: how a project takes the method up, and one tool that follows it
lead: How a project starts working to the method, and one tool built to follow it. This appendix stands outside the twelve documents: it binds nothing, and the method does not depend on anything it names.
---

## Starting

The method is text, and taking it up means doing what it says, not installing anything. A project that wants to start does five things, in this order.

1. **Name the Owner.** One person whose attention gates every decision the method leaves to a human. Without one, nothing else in the method has anyone to report to — read [Roles](02-roles.md) first.
2. **Pick the tracker and map it.** The artifacts live in whatever tracker the project already uses. [Mapping](10-mapping.md) says which of its objects carries a feature, a task and an evidence package.
3. **Staff the seats.** Decide who or what holds each accountability, keeping the separations: no party checks its own work. [Agents](12-agents.md) shows one staffing.
4. **Make the gates run by themselves.** A gate that runs when someone remembers is not a gate. Whatever the project's checks are, they run on every change without being asked.
5. **Walk one item end to end.** [Playbooks](11-playbooks.md) shows the walk. One feature taken from wish to merge teaches more than another reading.

A project may take the parts it wants and leave the rest. What it may not do is take the parts and keep the name.

## Orrery, one tool that follows the method

[Orrery](https://github.com/nyxene/orrery) is a Claude Code plugin written to follow this method. It is one way to staff the seats of [Agents](12-agents.md) with tooling, not the only one, and nothing in the method requires it.

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
