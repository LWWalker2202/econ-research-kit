# Specification ladder

A regression result is not one number but a path: each rung adds one decision, and what matters is how far the coefficient moves between rungs. This file is the ladder written down before the results are read, so that a coefficient that only survives under one clustering choice cannot quietly become "the result".

## How to use this file

- Copy it into the project as `spec-ladder.md`.
- One rung per row, in the order you will actually run them: baseline first, then one change at a time.
- Every rung states what changed relative to the rung above. "Add controls" is not enough; name them.
- `python skills/estimation/templates/estimate_main.py --ladder` writes the filled table for the synthetic panel, one rung at a time.
- Decide in advance which rung is the reported one. Writing it down first is what stops the reported rung from being chosen after the fact.

## The ladder

| # | What changes | Fixed effects | Clustering | N | R2 | Coefficient (SE) | Change vs previous |
|---|---|---|---|---|---|---|---|
| 1 | Baseline, treatment dummy only | | | | | | |
| 2 | Add control variables | | | | | | |
| 3 | Cluster at the treatment level | | | | | | |
| 4 | Event study around the treatment date | | | | | | |
| 5 | Alternative clustering levels | | | | | | |

## Which rung is the result

Write this down before running anything:

- **Reported rung**: the number that goes into the abstract.
- **Why this one**: one sentence, referring to the identification stage.
- **What would change my mind**: the change in coefficient or standard error that would make you stop and rethink.

## How to read a rung that moves

- Coefficient moves, standard error stays: the added control is absorbing part of the treatment variation. Say which control and why it belongs.
- Coefficient stays, standard error moves: usually a clustering choice, not a story about the effect. If the significance changes, the honest sentence is "significant only under clustering at X", not "significant".
- Both move together: something is wrong upstream. Go back to the identification stage before adding more rungs.

## What this file is not

- It is not a robustness section. Ruggedness checks defend against named threats; the ladder shows what each decision does.
- It is not a fishing licence. Rungs are written before the run, and a rung added afterwards is labelled as such.
- It is not a substitute for the event study. The ladder says whether the average effect is stable; it says nothing about pre-trends.
