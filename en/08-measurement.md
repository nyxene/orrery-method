---
title: Measurement
tagline: the ledger, the cost model, and what a forecast is worth
lead: Tokens are the one input that is spent and does not return — and the one quantity that is measured rather than guessed. Every rule here exists to keep that measurement honest.
---

## Spend is recorded, cost is computed · *Rule*

The ledger records spend — token counts, the model, and the date. Cost is computed at the moment of asking, from the price in effect on that date, and a computed cost is never stored.

Prices live in a dated table beside the ledger — the same record, extended when a vendor changes a price rather than at a close. It is appended and never edited, so its history is the archive. When no row covers a date, the cost is not computed from a nearby rate — the gap is the finding, and it is closed before the question is asked again.

> [!WHY]
> Prices change on announced dates. A cost stored at close is a fact about the day it was frozen: the same spend has two honest answers on two sides of a price change, and only a stored number can be wrong about both.

## The ledger has one writer · *Rule*

The closing agent appends one line per closing act, at the moment of the close. Never by hand, never by the Owner, and an existing line is never edited.

A container's close — a feature's emptying, a release's on the Owner's word — is not a closing act and gets no line. Framing and planning are spent before any task exists, and the ledger does not see them: a feature's price is the sum of its tasks' lines plus an overhead this record does not measure, and the forecast says so rather than pretending to a completeness it lacks.

```spec A ledger line states
Item — read from the branch name, so nothing is typed twice.
Date — the close moment every cost computation resolves prices against.
Outcome — the closing act, named: merged, refused, withdrawn, answered, or enacted. Five acts, five values, and no sixth. Only `merged` feeds the forecast's denominator.
Retries — failed attempts absorbed before the outcome was reached.
Runs — per model and effort, the token counts read from where the execution profile says they are read from — [Roles](02-roles.md) requires every profile to name that source — cached reads and writes recorded as their own quantities.
```

> [!WHY]
> A ledger maintained by discipline decays the way every maintained answer decays — silently. The close is an event that already happens, carried by an agent already acting, so the write has a forcing function instead of a memory.

## Abandoned work stays visible · *Rule*

A closed item that merged nothing still gets its line, and its `Outcome` says which act closed it. That distinction is not bookkeeping: `refused` is a station exercising the power the method gave it, `withdrawn` is the Owner cancelling work, and a ledger that wrote one value for both could not tell how often the verification has ever refused — which is the only record of whether the method's newest station has fired at all.

The forecasting unit is **cost per merged task**: every line feeds the numerator, only merged lines feed the denominator.

A task that took three attempts to land is visibly more expensive than one that landed first try. Averaging only the merged lines reports the cheaper, false number, and the variance a forecast exists to expose is smoothed away before anyone looks.

## A forecast is segmented and recency-weighted · *Rule*

A forecast is computed per model, never blended across them. Spend on two models averages into a figure with two price tables and two efficiency profiles behind it — a number describing no model that exists, offered about a next task that will run on one specific model.

Each line's contribution decays with its age. The task boundary is fixed — one task, one pull request — but what fits inside it grows with model capability, so an old average was measured against smaller tasks and understates today's. The error runs in one direction, toward optimism, and nothing in an unweighted average signals it.

The decay half-life is a stated knob, not a constant; the default is seven months, set against the pace at which models are replaced and measured against nothing yet. A forecast is reported as a property of the model and the half-life together, and it predicts the cost of one already-scoped task — how many tasks a goal needs is not its question.
