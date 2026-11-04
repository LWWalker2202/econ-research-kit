---
name: feasibility
description: Assess whether an empirical research idea is feasible before any code is written: data availability and access, identification viability, time and compute cost, and written stop criteria for abandoning the topic. Use when a topic, dataset, or design must be judged go or no-go, and before starting any empirical pipeline. Triggers: 能不能做、数据有没有、值不值得做、可行性评估、要不要换题、止损判据, feasibility, is this feasible, can I do this, go no-go.
---

# Feasibility gate

The feasibility gate is the cheapest stage of a project and the only stage whose job is to say no. Its product is a verdict, not a plan: go, go with reduced scope, or stop. Everything it writes down exists so that the verdict can be audited later, when sunk costs start arguing in the other direction.

## When to use this

- A student proposes a topic in one sentence and no dataset has been named yet.
- A supervisor or referee asks whether the design can survive, and the answer has to be written rather than spoken.
- A pipeline has already consumed time, and the team cannot agree on whether to continue or switch topics.
- A batch of candidate topics must be ranked, and only one of them can receive a full pipeline.
- A pre-registration or a grant application requires the stop criteria to be stated in advance.

## Inputs

| What you need | Where it comes from | What if missing |
|---|---|---|
| Research question naming unit, treatment variable, outcome, and comparison | supervisor, reading list, policy documents | Run `scripts/preflight.py` first; ask the missing slots in at most three questions; if the question cannot be written in one sentence, the idea is not ready |
| Candidate datasets and their access routes | `data-dict/`, agency portals, coauthors | List at least two alternatives; a dataset with no access route counts as unavailable |
| Institutional detail on how treatment is assigned | `domains/*/institutional.md` | Read the primary policy documents and mark every claim `[to fill]` until verified |
| Budget in person-weeks and compute hours | your own project history and the deadline | Fix a number before the assessment starts, not after the idea has become attractive |
| A statement of what the paper would claim if it worked | field norms, prior papers | Write the claim as one sentence; the claim sets the minimum detectable effect that matters |

## Procedure

1. Run `python scripts/preflight.py "<the user's words>"` and copy the four-slot table into the memo, marking each slot's source (given by the user / inferred by me). **Do not enter step 2 with an open slot**: ask at most three questions at once, then stop and wait. Completion condition: all four slots filled, every slot carries a source, and every inferred slot has been confirmed by the user.
2. Screen data coverage. For each candidate dataset, mark each of the four fields present, proxy, or missing. Completion condition: a dataset-by-field matrix with no empty cell.
3. Screen access. For each dataset record the access route, the responsible person, and the lead time in weeks. Completion condition: every dataset has a week count and a named person who will file the application.
4. Name the source of exogenous variation in one sentence of the form "X varies across units because of Y, and Y is unrelated to Z". Completion condition: Y is an institution, a rule, or a mechanical formula, not a behavioral choice.
5. Cost the pipeline in three lines: cleaning and matching, estimation, and writing. Completion condition: a total in person-weeks and compute hours that can be compared directly with the time remaining [to fill].
6. Write the stop criteria before any further work. Each criterion needs a threshold and a decision rule, for example: two candidate datasets both lack the outcome; no credible counterfactual survives the threat list; the access lead time exceeds the time remaining; the minimum detectable effect exceeds the effect that would matter [to fill]. Completion condition: at least three criteria, each numeric or binary.
7. Return a verdict and name the binding constraint, the single risk that would kill the project if it materialised. Completion condition: exactly one of go, go with reduced scope, or stop, plus one sentence naming that constraint.

## Outputs (artifacts)

| File | Content | Used by |
|---|---|---|
| `feasibility-memo.md` | Verdict, four-slot question, dataset matrix, variation sentence, cost, binding constraint | Coauthors and supervisor; the record that the verdict was made on evidence |
| `feasibility-check.csv` | One row per candidate topic, with columns for data, variation, cost, and verdict | Ranking a batch of topics; reopening a rejected topic after a design change |
| `data-access-plan.md` | Dataset, access route, lead time, responsible person, fallback source | Whoever files the data application |
| `stop-criteria.md` | Pre-committed thresholds and decision rules, with the review date | Opened when a later stage stalls, to decide whether to abandon |

- `templates/check_memo.py` machine-checks a filled memo against the six gate items (slots, coverage classes, stop thresholds, verdict, binding constraint, access lead times) in English or Chinese; `expected/feasibility-memo.md` is a completed sample and `expected/check-report.txt` is the report it produced.

## Acceptance

- [ ] All four slots are filled, each carrying a stated source (given by the user / a confirmed inference); none is an unconfirmed guess.
- [ ] Every candidate dataset is marked present, proxy, or missing on each of the four fields.
- [ ] Each dataset has an access route, a responsible person, and a lead time in weeks.
- [ ] The variation sentence answers "variation from what" without referring to a regression.
- [ ] The cost is a number in person-weeks and compute hours, not a range described in words.
- [ ] At least three stop criteria carry a threshold and a decision rule.
- [ ] The memo ends with one of the three verdicts and names the binding constraint.
- [ ] No figure in the memo is presented as a finding; every unverified figure is marked `[to fill]`.

## Common failure modes

| Pattern | Symptom | Correction |
|---|---|---|
| Dataset wish list | The plan names datasets that nobody has checked for access | Record the access route and lead time for each dataset before any modelling work |
| Identification by assertion | "We use fixed effects to deal with endogeneity", with no variation source named | Write the variation sentence first; fixed effects remove variation, they do not create it |
| Cost written from the middle | The estimate covers estimation only, although cleaning and matching dominate the work | Cost cleaning and matching as separate lines and attach a person-week figure to each |
| No stop rule | The project runs for months because no criterion can trigger a stop | Pre-commit thresholds and put a review date at the gate |
| Sunk-cost reasoning | Every objection is answered with "we can handle that later" | Put the binding constraint on the first page and re-read it at the review date |

## Interfaces with other skills

- Upstream: the topic proposal, and the access facts recorded in `data-dict/`; a rejected topic returns here after the design changes.
- Downstream: `identification` inherits the variation sentence and the seed of the threat list; `data-prep` inherits the access plan and the coverage matrix.

## Where to look up domain details

- `domains/energy-env/institutional.md` for how environmental regulation assigns treatment across regions and years.
- `domains/labor/data.md` for which household or firm panels can carry the outcome together with the treatment variable.
- `domains/behavioral/pitfalls.md` for the standard objections raised against feasibility claims in lab and survey experiments.
- `data-dict/` for coverage years, level of aggregation, and access route of a named Chinese dataset.
