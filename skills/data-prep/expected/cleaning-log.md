# Cleaning log

This log is written by `templates/clean_panel.py`. The panel is synthetic and seeded, so every count below is exact and a rerun reproduces the file byte for byte; none of these numbers is an estimate from real data. The fixture carries the six failures this skill is about: duplicate records, missing key fields, an unbalanced panel, outliers, mixed units, and a definition that changes across years.

## 1. Fixture

The generator builds a firm-year panel and then injects each failure at a fixed row position, so the size of every anomaly is known before cleaning starts.

| Item | Value |
|---|---|
| Firms | 40 |
| Years | 2018-2023 |
| Balanced cells | 240 |
| Rows written by the generator | 245 |
| Seed | 20261103 |

## 2. Step 1: duplicates

A duplicate is removed on the full row: two rows that agree on every column are the same record, and the second copy carries no information. The count is logged instead of inspecting records one by one.

| Item | Value |
|---|---|
| Rows before | 245 |
| Exact duplicate rows removed | 5 |
| Rows after | 240 |

## 3. Step 2: missing values in key fields

The missing rate is computed before any row is dropped. `revenue` and `roa` are key fields: a row missing either one is dropped and the count is logged. `leverage` is not a key field, so its gaps stay in the file and only the specification that uses it loses those rows.

| Variable | Missing | Rate | Key field | Rule |
|---|---|---|---|---|
| revenue | 4 | 1.67% | yes | drop the row |
| roa | 3 | 1.25% | yes | drop the row |
| leverage | 3 | 1.25% | no | keep the row |

7 rows are dropped because the key-field gaps sit on disjoint rows: 4 + 3 = 7. Rows remaining: 233.

## 4. Step 3: panel balance

233 of the 240 firm-year cells are present, so the panel is unbalanced. The response is not to interpolate the gaps and not to drop firms until the table looks rectangular: keep the gaps visible, report them in the sample-flow table, and let the estimator declare the imbalance.

| Year | Cells present | Cells missing |
|---|---|---|
| 2018 | 39 | 1 |
| 2019 | 40 | 0 |
| 2020 | 39 | 1 |
| 2021 | 38 | 2 |
| 2022 | 39 | 1 |
| 2023 | 38 | 2 |
| Total | 233 | 7 |

## 5. Step 4: winsorize

Winsorizing uses the 1st and 99th percentiles of each ratio variable. `revenue` is a level variable whose unit is still mixed at this step, so it is deliberately kept out of the pooled limits. Missing values are ignored when the percentiles are computed, and they are not filled with a winsor limit.

| Variable | Min before | Max before | Clipped low | Clipped high | Min after | Max after |
|---|---|---|---|---|---|---|
| roa | -1.1000 | 2.4000 | 3 | 3 | -0.0848 | 0.1872 |
| leverage | 0.0000 | 12.4000 | 3 | 3 | 0.0004 | 1.3048 |

## 6. Step 5: unit harmonization

`revenue` is recorded in yuan for 2018-2019 and in ten-thousand yuan for 2020-2023. The conversion runs in the script, never in a spreadsheet cell, and the harmonized column is renamed `revenue_wan` so that the unit travels with the variable name.

| Item | Value |
|---|---|
| Years reported in yuan | 2018-2019 |
| Rows converted | 79 |
| Conversion factor | 10000 |
| Mean revenue before conversion | 261,505,528.31 |
| Mean revenue after conversion | 76,283.02 |

A pooled mean computed before the conversion mixes two units and is not a quantity; that is why the conversion cannot be deferred to the estimation step.

## 7. Step 6: definition drift

The codebook records what each variable meant in each period, and the script compares those records instead of assuming the variable is stable. The check finds 2 changes:

> WARNING: `revenue` is recorded differently across the period: yuan in 2018-2019, ten-thousand yuan in 2020-2023. Unit drift only: harmonized to ten-thousand yuan in step 5; the meaning of the variable itself does not change.

> WARNING: `roa` is recorded differently across the period: net profit / total assets in 2018-2019, operating profit / total assets in 2020-2023. The two periods are not directly comparable; rows are tagged and the template does not pool them.

| Variable | Period | Definition | Status in the cleaned file |
|---|---|---|---|
| revenue | 2018-2019 | yuan | harmonized to ten-thousand yuan in step 5 |
| revenue | 2020-2023 | ten-thousand yuan | reference unit |
| roa | 2018-2019 | net profit / total assets | tagged vintage 1 |
| roa | 2020-2023 | operating profit / total assets | tagged vintage 2 |

The cleaned file keeps all 233 rows and tags each one with `roa_vintage`. The template does not choose a pooling rule: either split the sample at 2020 or add a vintage dummy, and record the choice in the paper's cleaning log.

The break shows up in the tagged data before any regression:

| Vintage | Years | Observations | Mean roa |
|---|---|---|---|
| 1 | 2018-2019 | 79 | 0.0302 |
| 2 | 2020-2023 | 154 | 0.0615 |

## 8. Outputs

| File | Rows | Columns |
|---|---|---|
| clean_panel.csv | 233 | 6 |
| clean_panel_summary.csv | 24 | 2 |

Columns of `clean_panel.csv`:

| Column | Unit | Note |
|---|---|---|
| firm | identifier | firm identifier, 1 to 40 |
| year | calendar year | 2018-2023 |
| revenue_wan | ten-thousand yuan | harmonized in step 5 |
| roa | ratio | two definitions, tagged in `roa_vintage` |
| leverage | ratio | winsorized at the 1st and 99th percentiles |
| roa_vintage | code | 1 = net profit definition, 2 = operating profit definition |

Rows are sorted by firm and year and floats are written with six decimals, so the file does not depend on row order or on the platform's default rounding. The three `leverage` gaps that step 2 keeps stay empty in the file; the column is not imputed.

## 9. Reproducibility

- No timestamp, no absolute path, and no unseeded draw enters the output, so two runs produce the same bytes.
- The checksums are written into this log: `clean_panel.csv` sha256 `89dee1364eb26fbdfe6b5334ba846d84e4594c2ff9b4638e5f6e125c2ec9df21`, `clean_panel_summary.csv` sha256 `f51af7148d7aed16f94d8c5f465e2f0137b057285c2d1bf8e713bfd224e87b6e`.
- The golden copy in `skills/data-prep/expected/` holds the output of the same command; a diff against it is the regression test for the pipeline: run `python skills/data-prep/templates/clean_panel.py --lang en` from the repository root and compare `output/cleaning-log.md` with the golden file.
