# Project state

## Where we stopped
v0.3.9 is pushed to both repositories. On 2026-11-05 we ran the ten-point repository audit
(0 problems) and verified every journal name in `skills/literature/journals.json` against
Crossref (135 exact title matches, 7 confirmed by ISSN, 0 mismatches; see
`decisions/ADR-0002-journal-tiers.md`).

## Next
Nothing is blocking. Two things, in order of value:
1. The lab-meeting demo (2026-11-11, 40 minutes, title fixed as "AI-assisted data work: from a
   raw dataset to the tables and figures in a paper") — **waits for the user to pick the dataset**;
   do not choose it for them.
2. Check the Codex plugin in the plugins page (open Codex and look for econ-research-kit).

## Waiting on the user
- The demo dataset (synthetic panel, a public CFPS/CHARLS subset, or their own de-identified slice).
- Whether the demo needs slides (recommend slides plus a pre-recorded backup).

## Known gaps
- The Codex plugin is registered in `config.toml` but has never been looked at in the UI (G2).
- About 250 `[to fill]` markers sit in illustrative positions on purpose; nobody has triaged
  which belong to the author and which the scripts should fill (G4).
- Table and report checks are structural only; the semantic layer needs a human gate (G5).
- The 142 journal names in `journals.json` are verified, but the A/B tiers are still a first-pass
  human judgement and need a field expert (G6).
- Chinese journal table rules cover two journals only; the user confirmed that is enough (G3 closed).
