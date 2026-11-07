---
name: data-prep
description: Build an analysis sample from raw data by scripts rather than by hand-editing spreadsheets: audit variable definitions across years, screen missing values and outliers, merge sources on identifiers, harmonize units, and keep a cleaning log. Use when merging datasets, when a definition changes across waves, or when a replication package must rebuild the sample. Triggers: 数据清洗、变量口径、合并数据、缺失值、样本构造、清洗日志, data cleaning, merge, harmonizing definitions, sample construction.
---

# Data acquisition and preparation

Data preparation is where a reproducible paper is won or lost. The rule that governs the whole stage is one sentence: every number in the analysis sample is produced by a script that starts from raw files, and no number is produced by a hand edit. A cleaned spreadsheet is not a result; it is an unrecoverable decision.

## When to use this

- The identification memo is frozen and the analysis sample must be built to its definitions.
- Two sources have to be merged on an identifier, and the matched share is expected to be a problem.
- A variable needed for the analysis changed its wording, its unit, or its reference period across survey waves or yearbooks.
- Someone has already hand-edited a table, and the sample must be rebuilt from raw files before anything is estimated.
- A replication package or a data availability statement must document every cleaning step.

## Inputs

| What you need | Where it comes from | What if missing |
|---|---|---|
| Raw files, unchanged, with file name and checksum | agency, survey, vendor, or the project attachment folder | Copy raw files to a read-only directory and record the checksum; never clean in place |
| Codebook or variable list for each wave or year | data provider, or `data-dict/` if the source is already covered | If the source has no entry, build one from the official documentation and add it back to `data-dict/` (its README says which sources get an entry); mark every unverified name `[to fill]` |
| Identifier crosswalk between sources | `data-dict/`, official concordance | Without a crosswalk, report the unmatched share and never force a match on names |
| Sample rules from the design | `identification-memo.md` | Write the sample rules before cleaning starts; do not derive them from what survives the merge |
| Unit and price conventions for the analysis | project convention, prior papers | Fix one unit and one price base per variable and write the choice in the data dictionary |

## Procedure

1. Freeze the raw layer. Copy raw files into a read-only directory and record file name, size, and checksum. Completion condition: every raw file has a checksum entry and no script writes into the raw directory.
2. Audit variable definitions before any merge. For each analysis variable, record the exact wording, the unit, and the reference period for each year. Completion condition: a table lists, per variable, the years in which the definition changed and the harmonization rule applied to each change.
3. Write one cleaning script per source, each reading raw files and writing a clean intermediate file. Completion condition: the intermediate file is rebuilt from raw by running one command, and a rerun reproduces the same checksum. A worked reference is in `templates/clean_panel.py`, with the Stata counterpart in `templates/clean_panel.do` and the pinned log in `expected/cleaning-log.md`. From the repository root run `python skills/data-prep/templates/clean_panel.py --lang en` and diff `output/cleaning-log.md` against the golden file before adapting the script. For the stepwise mode run `--decisions` first: it writes `output/cleaning-decisions.md`, one row per action, and touches no data; then run `--step 1` through `--step 6`, reading the file each step leaves before starting the next. `templates/cleaning-decisions.md` is the form to copy into a project and sign off before the run.
4. Screen missing values and outliers. Compute the missing rate by variable, year, and group; flag values outside the documented range; never drop silently. Completion condition: every drop is one line in the log with the count before and after.
5. Merge on identifiers and report the match. Keep unmatched records from both sides in a separate file and report the match rate by year. Completion condition: the merge report gives unmatched counts and a reason bucket for each one.
6. Harmonize units and scale. Convert each variable to one unit and one price base inside the script, never in a spreadsheet cell. Completion condition: no downstream script contains a unit conversion factor.
7. Build the analysis sample. Apply the sample rules in a fixed order and record the sample size at every step. Completion condition: a sample-flow table gives N before and after each rule.
8. Write the cleaning log and the data dictionary. Completion condition: a reader who has only the log, the scripts, and the raw files can rebuild every variable in the analysis sample.

## Outputs (artifacts)

| File | Content | Used by |
|---|---|---|
| `cleaning-log.md` | Step, script, files in and out, row counts, decisions and reasons | Coauthors and replicators; the audit trail for every drop |
| `sample-flow.csv` | Sample size before and after each sample rule | The data section of the paper |
| `data-dictionary.csv` | Variable name, label, unit, source file, years covered, harmonization note | Coauthors writing code against the sample |
| `merge-report.csv` | Match rate by year and by source side, with unmatched buckets | The appendix table that defends the merge |
| `run_all.py` | One entry point that rebuilds the analysis sample from raw files | The replication package |

## Acceptance

- [ ] Every raw file has a checksum, and no script writes into the raw directory.
- [ ] Every variable whose definition changed over time has a stated harmonization rule.
- [ ] Running the entry point from raw files rebuilds the analysis sample and reproduces the same checksum.
- [ ] No analysis variable was created by hand-editing a table; every one comes from a script.
- [ ] The sample-flow table gives N before and after every sample rule.
- [ ] The merge report gives match rates by year and keeps unmatched records from both sides.
- [ ] All unit conversions sit in the code, not in spreadsheet cells.
- [ ] The cleaning log contains no step that lacks a stated reason.

- `python scripts/verify_chain.py --project .` checks that rows in minus duplicates minus incomplete records equals the analysis sample.
- `python scripts/to_fill.py` lists every placeholder in the project and who should fill it (author / script / tutor / doc / golden / unknown).

## Common failure modes

| Pattern | Symptom | Correction |
|---|---|---|
| Hand-edited spreadsheet | A corrected value exists only in one cell of one workbook | Move the correction into a script together with the condition that triggers it, then re-derive the file |
| Silent drops | Rows vanish between raw and analysis with no record of where | Log every drop with the count before and after, grouped by the rule that caused it |
| Definition drift ignored | A variable is pooled across waves although its wording changed | Build the harmonization table first; if no common definition exists, split the sample by period |
| Merge by name | Firm or region names are matched with fuzzy rules and no report | Match on identifiers when they exist; report name-match rates and never overwrite matched values silently |
| Unit chaos | One column mixes yuan and ten-thousand yuan across years | Convert inside the script and write the resulting unit into the data dictionary |

## Interfaces with other skills

- Upstream: `identification` fixes the treatment and control definitions and the sample rules; `feasibility` supplies the access plan and the coverage matrix.
- Downstream: `estimation` reads the analysis sample and the sample-flow table; `report` consumes the cleaning log and the entry point as the replication package.

## Where to look up domain details

- `data-dict/` for coverage years, level of aggregation, and known issues of a named Chinese dataset.
- `data-dict/README.md` when the source is not covered there: it says which sources get an entry, which deliberately do not, and how to build one — so that no variable name is invented.
- `domains/labor/data.md` for merge keys and panel structure of household and firm panels.
- `domains/energy-env/data.md` for the geographic identifiers needed to attach regulation to units.
- `domains/behavioral/data.md` for exclusions and attention checks that must be applied before analysis.
