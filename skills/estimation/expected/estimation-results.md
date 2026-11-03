# Estimation results

This report is written by `templates/estimate_main.py` from a synthetic panel generated inside the script with a fixed seed. Every number below is recomputed on each run, so the file is meant to be diffed against `expected/estimation-results.md`: when the specification or the estimation library moves, the diff says where. The estimates are exact outputs of the seeded sample, not evidence about any real market.

## 1. Fixture

The panel is balanced: 60 individuals observed from 2010 to 2019. Twenty individuals are treated from 2014 and twenty from 2016; the remaining twenty are never treated. Treatment is absorbing, so D is one from the cohort year onward and zero before it. The spread of cohort years is deliberate: it keeps the design away from the single-period case, where the two-way fixed effects coefficient and the event study answer the same question.

| Item | Value |
|---|---|
| Individuals | 60 |
| Years | 2010-2019 |
| Observations | 600 |
| Treated individuals, cohort 2014 | 20 |
| Treated individuals, cohort 2016 | 20 |
| Never treated individuals | 20 |
| Treated individual-years | 200 |
| Share of treated individual-years | 0.3333 |
| Generator seed | 20260315 |

## 2. Main chain

Column (1) is the workhorse: the outcome on the treatment indicator with individual and year fixed effects, which is the two-way fixed effects estimator. Column (2) adds two time-varying controls. Column (3) keeps the column (2) coefficients and changes only the standard errors, clustering them at the individual level, because treatment turns on for all remaining years of an individual and residuals are serially correlated within an individual. The coefficient on D moves from 0.4153 in column (1) to 0.3518 in column (2), less than half of its own standard error of 0.1585: the controls are not driving the comparison, and the standard error in column (3) is the one to quote.

| Term | (1) Individual and year fixed effects | (2) Plus controls | (3) Clustered by individual |
|---|---|---|---|
| D | 0.4153 (0.1585) | 0.3518 (0.1516) | 0.3518 (0.1431) |
| x1 | — | 0.2044 (0.0446) | 0.2044 (0.0493) |
| x2 | — | -0.2347 (0.0420) | -0.2347 (0.0433) |
| Observations | 600 | 600 | 600 |
| R-squared | 0.4818 | 0.5292 | 0.5292 |
| Individual fixed effects | yes | yes | yes |
| Year fixed effects | yes | yes | yes |
| Standard errors | iid | iid | clustered by individual |

## 3. Event study

The single coefficient on D averages every post-treatment year and hides timing. The event study replaces it with relative-time terms: the leads test whether the treatment timing is anticipated, the lags trace the dynamic path, and the period just before treatment is the base period and is omitted. Cells further than two periods from the cohort year are binned into the two endpoint terms instead of silently joining the base period. Controls and both sets of fixed effects are kept.

| Relative period | Coefficient (standard error) |
|---|---|
| -3 or earlier | 0.0666 (0.1964) |
| -2 | 0.0613 (0.2566) |
| -1 (base period) | omitted |
| 0 | 0.4908 (0.2706) |
| +1 | 0.3634 (0.2715) |
| +2 | 0.3402 (0.2601) |
| +3 or later | 0.3439 (0.2581) |
| Observations | 600 |
| R-squared | 0.5297 |
| Fixed effects | individual, year |
| Controls | x1, x2 |
| Standard errors | clustered by individual |

## 4. Robustness

The specification stays at column (2) and only the cluster level changes. The coefficient on D is identical by construction, because a cluster level changes the variance estimator and not the point estimate; the standard error moves with the level of aggregation. The last row clusters on year with ten clusters, where the asymptotic cluster-robust standard error is optimistic: report that row next to a wild cluster bootstrap instead of treating it as a verdict.

| Cluster level | Clusters | Coefficient on D | Standard error | t | p |
|---|---|---|---|---|---|
| none (iid) | — | 0.3518 | 0.1516 | 2.32 | 0.021 |
| individual | 60 | 0.3518 | 0.1431 | 2.46 | 0.017 |
| block, four individuals each | 15 | 0.3518 | 0.1561 | 2.25 | 0.041 |
| year | 10 | 0.3518 | 0.1004 | 3.50 | 0.007 |

## 5. Reproducibility

Run `python skills/estimation/templates/estimate_main.py --lang en` from the repository root, then diff `output/estimation-results.md` against this file and compare `output/estimation-results.json` with `expected/estimation-results.json`. The JSON is language-neutral, so `--lang en` and `--lang zh` write the same bytes; its checksum is `f2668095ad68f5aebe682834dc78d20f0c8114407d3ac3586b8c22bea0e4454a`. Two consecutive runs give the same checksum, which is what turns the seed into a regression test. The Stata counterpart `templates/estimate_main.do` repeats the five steps with `reghdfe`, clustering the same way; its random draws differ from the ones here, so it matches on structure and step order, not on values.
