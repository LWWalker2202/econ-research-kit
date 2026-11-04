---
name: report
description: Build a reproducible report pipeline from raw data to intermediate files to tables and figures to a rendered document, with a fixed directory contract, a Quarto skeleton, and English and Chinese versions sharing one numeric source. Use when a draft report is edited by hand, when coauthors need a one-command rebuild, or when the same results must appear in two languages. Triggers: 可复现报告、流水线、目录结构、双语报告、一键重建、数据溯源、reproducible report, build pipeline, Quarto, one-command rebuild.
---

# Reproducible report

## When to use this

- A coauthor edits a number in the document and the tables no longer match the regressions.
- You must hand an editor a report that a new machine can rebuild from the raw data with one command.
- The same results go out in an English report and a Chinese report, and the numbers have to agree.
- A referee asks which data snapshot and which code commit produced Table 3.
- You are converting a folder of loose scripts into a layout a new research assistant can run on the first day.

## Inputs

| What you need | Where it comes from | If it is missing |
|---|---|---|
| Read-only raw data | the data provider, stored under `data/raw/` and never edited in place | stop and fix the source before writing any pipeline code |
| Cleaned intermediate files | `data-prep` output under `data/interim/` | run `data-prep`; the report never reads `data/raw/` directly |
| Generated tables and figures | `tables-figures` output under `output/tables/` and `output/figures/` | build them first; a report that plots from scratch duplicates the exhibit code |
| Numeric values for the prose | `output/estimates/` JSON or CSV files | extract them into `report/values.json` before writing a sentence that quotes a number |
| Journal or template requirements | the outlet's guidelines | default to the skeleton in this skill and flag deviations in `[to fill]` |

## Procedure

The directory contract comes first: `data/raw/` is read-only, `data/interim/` holds cleaned data, `output/tables/` and `output/figures/` hold generated exhibits, `report/` holds the document source, `code/` holds scripts, and `manifests/` holds provenance.

1. Write `manifests/directory_contract.md` naming every directory, its owner, and whether the build writes it. Done when every path the build touches appears in the contract and the build creates no directory outside it.
2. Write the entry point `Makefile` with the targets `data`, `tables`, `figures`, `numbers`, `report`, and `all`, each target depending on its inputs rather than on an assumed order. Done when `make -n all` prints the whole chain with no manual step left out.
3. Extract every number the prose will cite into `report/values.json`, one stable key per number, read from the frozen estimate files. Done when searching the report source for a literal three-decimal number returns nothing.
4. Configure `report/_quarto.yml` with the project type, the output formats, `execute: freeze`, the bibliography path, and the filters the template needs. Done when a render from an empty `output/` directory succeeds with zero warnings.
5. Write the English source `report/report_en.qmd` with the section skeleton only, pulling tables through include statements and numbers through inline references to `values.json`. Done when the source contains no pasted table and no typed number.
6. Add `report/report_zh.qmd` sharing `values.json`, the same includes, and the same figure paths, with the language-dependent strings in `report/i18n/en.yaml` and `report/i18n/zh.yaml`. Done when both renders print identical values for every shared number.
7. Add `manifests/provenance.json` recording the data snapshot date, the code commit, and the software environment as resolved by a lockfile. Done when the file regenerates on every build with no manual edit.
8. Run the clean rebuild: delete `output/`, run one command, compare against the reviewed artefacts. Done when the rebuild reproduces the tables, the figures, and both reports, and the diff shows no content change.

Why the report must be generated and never hand-edited: a hand-edited report is a second, invisible copy of the results. Every later change to a model then produces two versions of the truth, and the version that reaches the editor is the one nobody can rebuild.

## Outputs (artifacts)

| File | Contents | Consumer |
|---|---|---|
| `Makefile` | build entry point with one target per stage | authors, replication package |
| `manifests/directory_contract.md` | directory map with owner and write policy | new research assistant, referee |
| `report/_quarto.yml` | Quarto project configuration with frozen execution | report build |
| `report/report_en.qmd` | English report source: skeleton, includes, inline numbers | English report |
| `report/report_zh.qmd` | Chinese report source sharing the same values and exhibits | Chinese report |
| `report/values.json` | every number cited in prose, keyed by name | both report sources |
| `manifests/provenance.json` | data snapshot, code commit, software environment | editor, referee |
| `build/build.log` | timestamped log of the last full build | troubleshooting |

- Runnable template and gold sample: `skills/report/templates/build_report.py` builds the report from one frozen table file and one frozen estimate file, `skills/report/templates/README.md` states the input and output contract, and `skills/report/expected/report.md` is the builder's own output on the gold sample inputs.

## Acceptance

- [ ] From a clean checkout, one command rebuilds the intermediate data, the tables, the figures, and both reports with no manual step.
- [ ] No number in the report prose is typed literally; every cited value resolves from `report/values.json`.
- [ ] Files under `data/raw/` hash the same before and after the build.
- [ ] The English and the Chinese report show identical values for every shared exhibit.
- [ ] A render from an empty `output/` directory completes without warnings.
- [ ] `manifests/provenance.json` names the data snapshot date, the code commit, and the software environment.
- [ ] The rebuilt tables and figures are identical to the reviewed versions, or every difference is explained in `build/build.log`.
- [ ] `python skills/report/templates/check_report.py output/report.md` prints seven out of seven.

## Common failure modes

| Pattern | Symptom | Correction |
|---|---|---|
| Number typed into the report source | the report and the table disagree after the next rerun | move the value to `values.json` and reference its key |
| A script writes into `data/raw/` | the raw snapshot cannot be re-downloaded and is destroyed | raw stays read-only; every edit lands in `data/interim/` |
| Two exhibit code paths, one for the report and one for the paper | the two outputs drift apart silently | the report includes the table file and never rebuilds the exhibit |
| Bilingual sources maintained as two independent documents | one language is updated and the other is forgotten | shared values and includes, language strings in `i18n/` |
| The build depends on an interactive session | a new machine cannot reproduce it | the entry point is one command with no prompts |

## Interfaces with other skills

- Upstream: `data-prep` supplies `data/interim/`; `estimation` supplies `output/estimates/`; `tables-figures` supplies `output/tables/` and `output/figures/`.
- Downstream: `writing` pulls the numbers and exhibits into the manuscript; `review` uses the provenance file to answer reproducibility questions.

## Where to look up domain details

- Energy and environment: `domains/energy-env/data.md` for the coverage years the report must state and the known breaks that need a footnote.
- Labor: `domains/labor/data.md` for the survey waves and the sample restrictions the report has to document.
- Behavioral: `domains/behavioral/measures.md` for the treatment definitions the report's design section must state.
