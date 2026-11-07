---
name: identification
description: Turn a research question into an executable identification design: define treatment and control, name the source of exogenous variation, write a threat list with a test for each threat, and fix the pre-registration and robustness plans before estimation. Use when the variation behind an estimate cannot be stated, or when a referee disputes it. Triggers: 识别策略、外生变异、内生性、威胁清单、预注册、怎么识别, identification strategy, source of variation, threat list, is this identified.
---

# Identification strategy and design

An identification design answers one question: compared to what. The treatment variable, the control group, the source of exogenous variation, and the threat list all exist to pin that comparison down, so that another researcher using the same data would arrive at the same comparison rather than a defensible-sounding one.

## When to use this

- The feasibility gate returned go, and the question must now be converted into a design that can be estimated.
- A treatment variable exists, but no one can say which part of its variation identifies the effect.
- A referee writes that the design "may be endogenous", and the answer has to be a threat list with tests rather than a paragraph of assurance.
- A pre-registration is due, so the main specification, the sample rules, and the robustness plan must be fixed before outcome results are seen.
- A coauthor proposes another control or another fixed effect, and someone has to state what that term is identifying.

## Inputs

| What you need | Where it comes from | What if missing |
|---|---|---|
| Research question with unit, treatment variable, outcome, and comparison | `feasibility-memo.md` | Return to `feasibility`; do not design on a question that names no comparison |
| Source of exogenous variation: a policy, a cutoff, a lottery, an unexpected shock | policy texts, `domains/*/institutional.md` | Name the assignment mechanism; if none exists, label the design as descriptive |
| Data structure: cross-section, panel, repeated cross-section, and the level at which treatment varies | `data-dict/`, codebooks | Decide this before writing the specification; the estimator and the fixed effects follow from it |
| What prior papers used and what referees attacked | reading list | Record the design they used and the objection each one faced; mark page-level claims ` (to be read off the project's own sample)` until verified |
| Pre-registration requirements from the outlet or funder | journal, funder, or registry | Copy the required fields into `pre-registration-draft.md` before estimation starts |

## Procedure

1. Define treatment and control in measurable terms. The treatment variable needs a definition, a source, and a time of measurement; the control group is the set of untreated units that is otherwise comparable. Completion condition: a reader with only the codebook could reconstruct both groups.
2. Write the source of exogenous variation as one sentence: "X varies across units because of Y, and Y is unrelated to Z". Completion condition: Y is an institution, a rule, or a mechanical formula rather than a behavioral choice.
3. Draw the comparison. Name the counterfactual, the time window, and the unit of analysis. Completion condition: the sentence survives the question "compared to what, over what period, at what level?".
4. Build the threat list. Write three to five specific threats, and for each one give the direction of bias, the test or robustness check that addresses it, and the outcome that would falsify the design. Completion condition: every threat has all three parts, and at least one test can be run on data already in hand.
5. Match sample to level. Align the level of the treatment variable with the level of the outcome and the level of the clustered standard errors, and state what happens to units that switch treatment status. Completion condition: one sentence in the memo names the unit of analysis and the clustering level together.
6. Fix the main specification. Write the estimating equation and list every fixed effect and every control with the variation it uses. Completion condition: each control has a one-line reason, and any control that absorbs the identifying variation is either dropped or reported as a separate specification.
7. Write the robustness plan before estimation. For each planned check, state which threat it addresses and what result would count as a failure. Completion condition: no entry in the plan lacks a named threat.
8. Freeze the design in `identification-memo.md` and, where required, copy the main specification into `pre-registration-draft.md`. Completion condition: the memo carries a version date, and each pre-registration field is filled or marked ` (to be read off the project's own sample)`.

## Outputs (artifacts)

| File | Content | Used by |
|---|---|---|
| `identification-memo.md` | Variation sentence, comparison, threat table with tests, unit of analysis and clustering level | Coauthors and referees; the reference document for the later stages |
| `threat-list.csv` | One row per threat: threat, direction of bias, test, falsifying outcome, status | Tracking which threats are closed before the paper is written |
| `pre-registration-draft.md` | Main specification, sample rules, robustness plan, analysis start date | Registry, journal, or funder |
| `specification-table.tex` | Main equation plus the list of fixed effects and controls with the variation each uses | The empirical strategy section of the paper |

- Worked example and check: `templates/check_design.py` grades a design memo on the six items above, `expected/identification-memo.md` is a filled example, and `expected/check-report.txt` is the pinned output; run `python skills/identification/templates/check_design.py skills/identification/expected/identification-memo.md` from the repository root and compare the report with the pinned one.

## Acceptance

- [ ] Treatment and control are defined from the codebook, not from the sample left after matching.
- [ ] The variation sentence names an institutional or mechanical mechanism, not a behavioral choice.
- [ ] The comparison sentence answers "compared to what, over what period, at what level?".
- [ ] The threat list holds three to five threats, and each gives direction of bias, a test, and a falsifying outcome.
- [ ] The unit of analysis, the level of the treatment variable, and the clustering level appear in one place.
- [ ] Every fixed effect and control in the main specification has a one-line reason stating the variation it uses.
- [ ] Every robustness check in the plan names the threat it addresses.
- [ ] The memo is dated, and every pre-registration field is filled or marked ` (to be read off the project's own sample)`.
- [ ] Every threat in the memo has a row in `threat-table.md`, and every row carries a verdict of `cleared`, `weakened`, `binding` or `open`.

- `gate.py pass` refuses to advance while the threat table or the memo is missing; `--force` makes you name the gap.
- `python scripts/coverage.py` shows whether the identification memo and the ledger entry exist.

## Common failure modes

| Pattern | Symptom | Correction |
|---|---|---|
| Fixed effects treated as identification | The memo says "we control for unit and year fixed effects" and names no source of variation | Write the variation sentence first; fixed effects remove variation rather than create it |
| Decorative threat list | Threats are generic, with no test attached to any of them | Require direction of bias, a test, and a falsifying outcome for each row |
| Sample defined by what merged | Treatment and control are defined after dropping the records that failed to match | Define the groups from the codebook, then apply sample rules in a fixed order |
| Control pile-up | Controls are added in the name of robustness although they absorb the identifying variation | State what each control uses; if it uses the identifying variation, drop it or report it separately |
| Robustness without purpose | Twenty checks, none mapped to a threat, and referees cannot tell which one matters | Keep only checks tied to the threat list and move the rest to an appendix with a one-line reason |

## Interfaces with other skills

- Upstream: `feasibility` supplies the variation sentence and the binding constraint; `domains/*/institutional.md` supplies the assignment mechanism.
- Downstream: `data-prep` builds treatment and control to the definitions fixed here; `estimation` runs the main specification and the checks mapped to the threat list.

## Where to look up domain details

- `domains/energy-env/institutional.md` for the assignment rule behind environmental regulation and pilot programs.
- `domains/energy-env/measures.md` for competing definitions of the treatment variable and the assumption each one carries.
- `domains/labor/measures.md` for treatment definitions in wage and labor mobility settings.
- `domains/behavioral/institutional.md` for what randomization can and cannot deliver in lab and survey experiments.
