---
name: estimation
description: Estimate a frozen specification and defend it: justify the fixed effects and the clustering level, keep only robustness checks that answer a named threat, define heterogeneity subgroups before the split, and report the diagnostics for weak instruments, pre-trends, and multiple testing. Use when running the baseline regression or answering a referee on robustness. Triggers: 估计、固定效应、聚类标准误、稳健性检验、异质性分析、多重检验, estimation, fixed effects, clustered standard errors, robustness checks.
---

# Estimation and robustness

Estimation looks like a technical step and is really an interpretive one. Every choice in the specification decides which comparison the coefficient is allowed to make, and every robustness check decides which objection the paper has answered. The stage is finished when the author can say, in one paragraph, what the estimate is and what it is not.

## When to use this

- The analysis sample is built, and the main specification from the identification memo must be estimated.
- A clustering level has to be chosen and justified in writing rather than by convention.
- A referee asks which robustness checks belong in the main text and which belong in an appendix.
- A heterogeneity analysis is planned, and the subgroup definitions have to be fixed before the split is run.
- The diagnostics of the main model are ambiguous, and a decision rule is needed instead of one more specification.

## Inputs

| What you need | Where it comes from | What if missing |
|---|---|---|
| Analysis sample with documented construction | `data-prep`, `sample-flow.csv` | Do not estimate on a sample with no flow table; return to `data-prep` first |
| Frozen main specification | `identification-memo.md` | If the specification is not frozen, fix it before looking at any estimate |
| Threat list with tests already mapped | `threat-list.csv` | A robustness check with no mapped threat does not belong in the main text |
| Thresholds fixed at the design stage: instrument strength, pre-trend window, minimum detectable effect | design memo, funder, field norms | State the threshold before estimating; never choose it after seeing the result |
| Software and package choices for the run | project convention | Write one command file so a rerun reproduces the same numbers |

## Procedure

1. Rebuild the baseline regression from the frozen specification and report the coefficient with clustered standard errors at the pre-specified level. Completion condition: the table matches the specification in the memo variable by variable. A worked reference is in `templates/estimate_main.py`, with the Stata counterpart in `templates/estimate_main.do` and the pinned report in `expected/estimation-results.md`: run `python skills/estimation/templates/estimate_main.py --lang en For the stepwise mode, add `--ladder` to write `output/spec-ladder.md`, one rung per line, or run `--step 1` through `--step 5` to stop after a chosen rung and look before going on. `templates/spec-ladder.md` is the form to copy into a project and fix the reported rung before the run.` from the repository root and diff `output/estimation-results.md` and `output/estimation-results.json` against the golden files before adapting the script.
2. Justify the fixed effects. For each set, write the variation it absorbs and the variation it leaves. Completion condition: no fixed effect is included only because it is conventional.
3. Justify the clustering level. State the level at which the treatment variable is assigned and the level at which errors are correlated, then report one alternative clustering as a check. Completion condition: the clustering sentence in the memo and the command file use the same level.
4. Run only the robustness checks that answer a threat on the list, and place every other check in an appendix with a one-line reason. Completion condition: each main-text check names the threat it addresses in its table note.
5. Run diagnostics before interpretation: first-stage strength for an instrumental variable (IV), parallel trends and event study leads for difference-in-differences (DiD), density and covariate balance at the cutoff for regression discontinuity design (RDD), donor fit for the synthetic control method (SCM). Completion condition: each diagnostic has a pass rule that was written before the diagnostic was run.
6. Fix heterogeneity subgroups from theory or pre-registration, not from the data, and count the tests. Completion condition: each subgroup cut is defined before the split, and the multiple-testing adjustment is named.
7. Apply the multiple-testing correction to the family of confirmatory tests and name the family. Completion condition: every p-value that enters a claim is either inside the family or explicitly labelled exploratory.
8. Write the results memo that separates what the estimate is from what it is not. Completion condition: the memo names at least one claim that the design cannot support.

## Outputs (artifacts)

| File | Content | Used by |
|---|---|---|
| `results-memo.md` | Baseline estimate, diagnostics, verdict per robustness check, claims the design cannot support | Coauthors and the writing stage |
| `main-table.tex` | Baseline and the main-text robustness columns, in booktabs-style table format | The results section of the paper |
| `diagnostics.csv` | Diagnostic, threshold, value, pass or fail, ruling | The appendix and the referee response |
| `robustness-index.csv` | One row per check: check, threat addressed, result, verdict | Keeping the appendix consistent with the threat list |
| `run_estimation.py` | The command file that produces every number, with a fixed seed where relevant | The replication package |

## Acceptance

- [ ] Every estimate is produced by a command file whose rerun gives the same number.
- [ ] Each set of fixed effects has a stated reason and a stated variation it absorbs.
- [ ] The clustering level is justified by the level of treatment assignment, and one alternative is reported.
- [ ] Every main-text robustness check names the threat it addresses.
- [ ] Every diagnostic has a pass rule written before the diagnostic was run.
- [ ] Heterogeneity subgroups are defined before the split, and the number of tests is stated.
- [ ] A multiple-testing family is named and the correction applied to every confirmatory p-value.
- [ ] The results memo names at least one claim the design cannot support.

- `python scripts/../../crosscheck.py` (from a project root: `python scripts/crosscheck.py`) agrees with the golden coefficients; a coefficient that moves more than 1e-6 is a change of specification, not a rounding difference.

## Common failure modes

| Pattern | Symptom | Correction |
|---|---|---|
| Kitchen-sink robustness | Dozens of checks, none mapped to a threat, so referees cannot tell which one carries weight | Keep only checks tied to the threat list and move the rest to an appendix with a one-line reason |
| Clustering by habit | Errors are clustered at the unit level although the treatment varies at the region level | Cluster at the level of treatment assignment and report the alternative as a check |
| Diagnosing after the result | The pre-trend window is the one that happens to pass | Fix the window in the identification memo and report the result as fixed |
| Star-chasing | The main specification is chosen from a grid by significance | Pre-commit the main specification and present the grid as a specification curve with the committed one marked |
| Heterogeneity fishing | Subgroups appear after the split because one of them was significant | Define subgroups from theory or pre-registration, then state the number tested and the correction |

## Interfaces with other skills

- Upstream: `identification` supplies the frozen specification, the threat list, and the clustering level; `data-prep` supplies the analysis sample and the sample-flow table.
- Downstream: `tables-figures` renders these results; `report` turns the results memo and the diagnostics into the reproducible report; `writing` uses the boundary stated here to avoid over-claiming.

## Where to look up domain details

- `domains/energy-env/pitfalls.md` for the diagnostics referees request in regulation and carbon pricing designs.
- `domains/labor/pitfalls.md` for the objections that follow wage and labor mobility estimates.
- `domains/behavioral/pitfalls.md` for what a manipulation check and a balance check must show before results are interpreted.
- `data-dict/` for measurement cautions that change how a coefficient should be read.
- `overrides/identification-reporting-cn.md` for how Chinese journals expect causal estimates to be reported: which rows the table must carry, which base period the event study uses, whether pre-trends appear as a figure or a table, and where robustness checks are placed.
