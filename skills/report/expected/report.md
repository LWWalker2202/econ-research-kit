# Reproducible report

Built by `skills/report/templates/build_report.py` from the two frozen files listed under `## How to reproduce`. Every number below is copied or rounded from those files; a field they do not contain is printed as a placeholder rather than typed by hand.

## One-line conclusion

The coefficient on `D` is 0.352, with a standard error of 0.143 (standard errors clustered at the id level); it is estimated on 600 observations under the specification `y ~ D + x1 + x2 | id + year`.

## Main results

Baseline specification selected from `skills\estimation\expected\estimation-results.json`: `y ~ D + x1 + x2 | id + year` with fixed effects `id, year`; point estimate 0.352, standard error 0.143, p-value 0.017, R-squared 0.529, observations 600.

Table 1 is embedded verbatim from `skills\tables-figures\expected\table1.tex`. A converter should pass the fenced block through unchanged so that the booktabs-style layout, the label and the table note survive. This demo deliberately embeds a table from a different project: read the closing checklist and watch the guard fire.

```latex
\begin{table}[htbp]
\centering
\caption{Baseline results}
\label{tab:main}
\begin{tabular}{lccc}
\toprule
\multicolumn{4}{c}{y} \\
\midrule
 & (1) & (2) & (3) \\
\midrule
Treatment & 0.503*** & 0.500*** & 0.487*** \\
 & (0.097) & (0.102) & (0.101) \\
\addlinespace[0.3ex]
Control x &  &  & 0.268*** \\
 &  &  & (0.044) \\
\addlinespace[0.3ex]
\midrule
Firm FE & --- & Yes & Yes \\
Year FE & --- & Yes & Yes \\
\addlinespace[0.3ex]
\midrule
Observations & 480 & 480 & 480 \\
$R^2$ & 0.053 & 0.188 & 0.236 \\
\bottomrule
\end{tabular}
\par\smallskip\footnotesize Note: ***, ** and * denote significance at the 1%, 5% and 10% levels; standard errors are in parentheses. Standard errors are clustered at the firm level.
\end{table}
```

## Robustness

Each item below applies one variance estimator to the robustness specification `y ~ D + x1 + x2 | id + year`; the point estimate is held fixed, so the comparison isolates the standard errors.

- iid standard errors: coefficient 0.352, standard error 0.152, p-value 0.021.
- standard errors clustered at the id level: coefficient 0.352, standard error 0.143, p-value 0.017, 60 clusters.
- standard errors clustered at the block level: coefficient 0.352, standard error 0.156, p-value 0.041, 15 clusters.
- standard errors clustered at the year level: coefficient 0.352, standard error 0.100, p-value 0.007, 10 clusters.

## Data and definitions

This section is written by the researcher. The builder leaves it open on purpose: the two input files record estimates and exhibits, not sample construction, so any sentence a machine typed here would be invention.

- Sample frame and period: `—`
- Unit of observation: `—`
- Variable definitions and data sources: `—`
- Sample restrictions and winsorizing rules: `—`

## How to reproduce

- Estimation script: `—`
- Random seed: `20260315` (read from the results file)
- Input files: `skills\tables-figures\expected\table1.tex` and `skills\estimation\expected\estimation-results.json`
- Command: `python skills/report/templates/build_report.py --tables skills/tables-figures/expected/table1.tex --results skills/estimation/expected/estimation-results.json --lang en --out skills/report/expected/report.md`

## What is still missing

- The estimation script is not recorded; pass `--script` so a reader can rerun the estimates.
- The data and definitions section is still open; only the researcher can close it.
- The embedded table does not contain the baseline coefficient 0.352 from the results file. Check that both inputs come from the same project before the report leaves the folder.
- Event-study coefficients are present in the results file but are not summarised in this report.
- No figure is embedded; figures are produced in the tables-figures stage and included separately.
