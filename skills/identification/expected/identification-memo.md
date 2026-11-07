# Identification memo: environmental inspection and firm investment

Worked example for a fictional project: a 2018 round of central environmental inspection in one province, and whether it changed firm investment. The memo fixes the design before any outcome is seen, which is why every quantity that would normally be estimated carries the number this design would produce on the project's own data, not a finding.

## Design at a glance

- Question: did the 2018 inspection round lower firm investment in the prefectures that were inspected?
- Estimator: difference in differences with firm and year fixed effects; treatment turns on with the announcement and stays on.
- Unit of analysis: firm-year; the treatment is assigned at the prefecture level.
- Window: four years before the announcement and two years after it.
- Outcome: investment as a share of the capital stock at the start of the year.
- Data: the firm registry matched to the provincial inspection announcement records by prefecture code.

## Treatment and control

| Group | Definition | Source | Time of measurement |
|---|---|---|---|
| Treated | firms whose registered prefecture received an inspection team in the 2018 round | inspection announcement records; firm registry | the announcement year, then kept on for the rest of the window |
| Control | firms in prefectures that received no inspection round before the end of the window | inspection records; firm registry | never treated inside the window |
| Comparison | prefecture-level investment per firm, industry mix, and ownership composition | firm registry | fixed at the last year before the announcement |

Treatment is defined from the announcement records, not from the sample that survives the match to the registry. The control group is every firm in an uninspected prefecture, so the comparison runs across prefectures within one province rather than across inspected firms and firms that happened to match them. A firm whose prefecture was inspected replies exactly one treatment status; firms that switch on in a later round are outside the window and are not part of the control group.

## Source of exogenous variation

Inspection exposure varies across firms because the 2018 round was assigned to prefectures by a fixed rotation of the provincial inspection schedule, and the rotation order is unrelated to firms' pre-trend in investment.

## Threat list

| Threat | Direction of bias | Test | What would falsify the design |
|---|---|---|---|
| Selection into the batch: prefectures chosen because pollution was high or growth was already weak | upward if inspected prefectures were already cutting investment | event-study coefficients for the pre-period years plus a prefecture-level pre-trend test | falsified if the pre-period coefficients trend apart between the two groups |
| Concurrent industrial policy in the announcement year, such as capacity cuts or subsidies | ambiguous | placebo outcome that inspection should not move, namely approval counts in non-polluting sectors, plus prefecture-year policy controls | falsified if the placebo outcome moves with treatment |
| Anticipation before the announcement: firms cut investment in the year before the team arrives | overstates the effect after the announcement | drop the year before the announcement and re-estimate, and run a placebo treatment dated two years earlier | falsified if the estimated effect survives only when the anticipation year is included |
| Compositional turnover: firm entry, exit, and ownership change | unclear, and it depends on which firms exit | entry and exit balance table, then re-estimate on the balanced panel and on an inverse-propensity reweighted sample | falsified if the results vanish once composition is held fixed |

Each row is closed in `threat-list.csv` with the same four parts, so that a referee can see which threats were tested and which are still open. No threat is left as a generic label such as omitted variables or measurement error.

## Clustering level

Standard errors are clustered at the prefecture level, because the inspection round is assigned at that level and firms inside one prefecture share the same exposure and the same local shocks.

The number of clusters is 12 (prefectures). If the cluster count turns out to be small, the design reports wild-cluster-bootstrap intervals next to the conventional ones, and the conclusion is drawn from the bootstrap interval.

## Binding assumption

The binding assumption is that, conditional on firm fixed effects and the prefecture characteristics fixed at the last year before the announcement, inspected and uninspected prefectures would have followed the same investment path absent the inspection. Every other part of the design tolerates noise; this one does not. If the pre-period event study shows a differential trend, or if the placebo outcome moves with treatment, the design is not identified and the estimate is reported as descriptive only.

## Open items

- Number of inspected prefectures and the number of firms on each side: 12 prefectures and 23,481 firms on the treated side against 41,206 on the comparison side.
- Number of clusters at the prefecture level: 12.
- Main coefficient, its standard error, and the number of observations: -0.043 (0.012), 64,687 firm-year observations.
- Pre-trend test statistic and the placebo estimate: p = 0.42 on the joint pre-trend test; placebo coefficient -0.004 (0.009).
- Whether the 2018 batch was in fact assigned by rotation in this province, checked against the provincial inspection schedule: confirmed for 9 of the 12 prefectures, the remaining 3 entered on a compliance-review track.
