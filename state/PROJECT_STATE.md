# Project state

## Where it stopped
D1 release done. v0.3.9 is out on both repositories, four badges green, six assets per release.
The nine scripts now form one chain: preflight -> spec -> gate -> stage templates -> review -> recall,
with `workflows/main.yaml` declaring the hand-off contract between stages.

## Next
No hard todo. Three worthwhile things, in order:
1. The 40-minute group meeting on 2026-11-11. Title is fixed: "AI-assisted data work: from one raw file to
   the tables and figures in a paper". **The user has not picked the demo data yet; do not choose for him.**
2. Verify the Codex plugin in the Codex plugins page.
3. Extend the Chinese-journal table rules from two journals to four.

## Waiting on the user
- Demo data for the meeting (synthetic panel / public CFPS-CHARLS subset / own de-identified slice).
- Whether slides are wanted (recommendation: slides plus a recorded fallback).

## Known gaps
- Chinese-journal rules cover only two journals.
- About 250 `[to fill]` markers remain on purpose.
- Table and report checks are formal, not numerical.
- `journals.json` is a first pass; the A/B lists need a field expert's review.
