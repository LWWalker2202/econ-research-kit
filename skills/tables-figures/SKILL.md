---
name: tables-figures
description: Turn frozen estimation output into submission-ready tables and figures — booktabs-style tables, multi-column regression tables, descriptive statistics, event-study coefficient plots, table notes and figure captions. Use when exhibits are still pasted from the console, when a referee cannot find the standard errors, or when every table and figure must rebuild from one script. Triggers: 做表、三线表、回归表、事件研究图、图注、表注、表格排版、tables and figures, regression table, coefficient plot, table notes.
---

# Tables and figures

## When to use this

- The draft still carries a screenshot of the regression console and the journal requires an editable table.
- A referee reports that standard errors are missing, that the star legend is unexplained, or that the observation count does not match the text.
- You are converting a working paper from hand-typed tables to script-generated exhibits before submission.
- You need an event-study coefficient plot with confidence intervals and the omitted reference period drawn explicitly.
- You are assembling the appendix and need the robustness panels to share one column structure with the baseline regression.

## Inputs

| What you need | Where it comes from | If it is missing |
|---|---|---|
| Frozen estimation output | `estimation` skill, files under `output/estimates/` | rerun the estimation; never transcribe numbers from a log into a table |
| Exhibit-to-claim map | your outline or the draft's paragraph plan | write it before touching any script: one row per exhibit and the sentence it supports |
| Variable labels and units | `data-prep` codebook, `codebook/varlabels.csv` | fix the label file, not the table script; unlabelled variables ship with raw names |
| Journal rules on tables and figures | the journal's author guidelines | use the defaults in this skill and record each deviation in `[to fill]` |
| Software toolchain | Stata with `esttab` and `coefplot`, or Python with `pyfixest` and a `modelsummary`-style exporter | one toolchain per exhibit, stated in the table note |

## Procedure

The target form is fixed before the script is written: a booktabs-style table with three horizontal rules and no vertical rules, the coefficient on its own line with the standard error in parentheses on the line below, significance stars with their thresholds defined in the note, the note placed below the table, and no column running past the text block. For a submission to a Chinese journal the form is not this default but the one measured from published papers in `overrides/journal-cn.md`: table title above the table, note below it, no vertical rules in the body, and figure captions below the figure, which is the opposite of the convention in step 8. Where that file disagrees with the defaults here, the file wins.

1. Write `output/tables/table_index.csv` with one row per numbered exhibit: ID, the manuscript sentence it supports, the estimate file it reads, and the build status. Done when every exhibit mentioned in the draft has a row and no row lacks an estimate file.
2. Write one build script per exhibit under `code/tables/` and `code/figures/`. Each script reads only the frozen estimate files and never reruns a regression. Done when editing a coefficient in the estimate file changes that table and nothing else.
3. Fix the formatting once: three decimals for coefficients and standard errors, stars at 0.10, 0.05, and 0.01 with the thresholds typed into the note, and one shared definition of the sample. Done when a reader can recover the p-value band from the note alone.
4. Emit the table body on both toolchains with the same column order. In Stata, run `estimates store` for each specification, then let `esttab` write the LaTeX body with `b()` and `se()` so the standard error lands on the line under its coefficient, and let `coefplot` draw the figure from the same stored estimates. In Python, pass `pyfixest` model objects to a `modelsummary`-style exporter or `etable` with the same column order and the same star thresholds. Done when the Stata export and the Python export, run on the same estimate file, agree digit for digit. A worked reference lives in `templates/panel_ols.py` and `templates/make_table.do`, with the pinned output in `expected/table1.tex`: run `python templates/panel_ols.py --lang en` and diff the result against the golden file before adapting the script.
5. Add the four reporting panels to every column of the multi-column regression table: fixed effects, controls, observations, and fit statistic. Done when no column hides a control-set choice inside the note.
6. Place the table note below the table and make it self-sufficient: dependent variable and its unit, estimator, sample and sample period, fixed effects, level of the clustered standard errors, star legend, and data source. Done when a reader who never opens the text can read the table.
7. Build the figures: point estimates with confidence intervals, the reference period drawn at zero but not estimated, axes labelled with the unit of the estimand, one vector format for print and one raster copy for review. Stata uses `coefplot` on the stored estimates; Python plots the `pyfixest` coefficient frame directly. Done when the caption wording matches the axis labels.
8. Compile the manuscript once and run the width and reference check: nothing past the margin, captions above figures and notes below tables, and every exhibit cited by number at least once. Done when the rendered PDF shows no overflow and the reference check returns no orphan exhibit.

Why the form matters: a table that does not rebuild from the estimate file will eventually contradict the text, and that contradiction usually surfaces during revision, when it is expensive. The script cost is paid once.

## Outputs (artifacts)

| File | Contents | Consumer |
|---|---|---|
| `output/tables/table_index.csv` | exhibit ID, supported claim, estimate file, build status | authors, `report` build |
| `output/tables/Table1_summary.tex` | descriptive statistics with mean, standard deviation, and counts by group | manuscript build |
| `output/tables/Table2_main.tex` | booktabs-style baseline regression table with the four reporting panels | manuscript build |
| `output/tables/TableA1_robust.tex` | robustness checks in the same column order as the baseline regression | appendix |
| `output/figures/Figure3_event_study.pdf` | event-study coefficient plot with confidence intervals and the reference period at zero | manuscript build, slides |
| `code/tables/build_tables.py` | one command that rebuilds every table from the frozen estimates | replication package |
| `code/figures/build_figures.py` | one command that rebuilds every figure from the frozen estimates | replication package |
| `output/tables/notes.md` | table notes keyed by exhibit ID, plain text | `writing` skill |

## Acceptance

- [ ] Every numbered exhibit in the draft has a file under `output/tables/` or `output/figures/` and a row in `table_index.csv`.
- [ ] Rebuilding from an empty `output/` with one command reproduces every exhibit without a manual edit.
- [ ] Coefficients sit above their standard errors, and no table prints a standard error in a separate right-hand column.
- [ ] Each table note is below the table and defines the star thresholds, the estimator, the sample, the fixed effects, and the clustering level.
- [ ] No table or figure extends past the text margin in the rendered PDF.
- [ ] Every exhibit is cited by number at least once, and no citation points to an exhibit that does not exist.
- [ ] The Stata export and the Python export on the same estimate file agree digit for digit.

## Common failure modes

| Pattern | Symptom | Correction |
|---|---|---|
| Numbers typed by hand from the console log | the table does not move when the model changes | read the frozen estimate file; never type into a table |
| Star legend buried in the caption | a referee asks what one star means | thresholds written into the note below the table |
| Standard errors in a separate column at the far right | the reader has to match rows across the page | standard error on the line under its coefficient |
| Table wider than the text block | the last control column is cut off in the PDF | drop a reporting panel, reduce decimals, or split the table into panels |
| Figure exported as a screen capture | blurry at print size and not editable | export vector PDF from the plotting script, plus a raster copy for review |

## Interfaces with other skills

- Upstream: `estimation` hands over frozen estimates and the specification table; `data-prep` hands over variable labels and units.
- Downstream: `report` consumes the generated `.tex` and `.pdf` files; `writing` consumes the table notes and the claim map; `review` cites exhibit IDs when answering a referee.

## Where to look up domain details

- Energy and environment: `domains/energy-env/measures.md` for the treatment variable definition the baseline table must display, and `domains/energy-env/pitfalls.md` for the robustness panels a referee will ask for.
- Labor: `domains/labor/measures.md` for the treatment variable definitions a wage equation needs, and `domains/labor/data.md` for the sample restrictions that belong in the note.
- Behavioral: `domains/behavioral/pitfalls.md` for the balance check and manipulation check that belong in an appendix table.
