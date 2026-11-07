# Labor economics: constructing the treatment variable

In labor economics the treatment is rarely a program dummy. It is an exposure measure built from a statutory floor, an eligibility threshold, a reform cohort, or a status whose return you want to estimate. The definition is the identification, so write it down before running anything and make the sample restriction that follows from it explicit.

## Constructing the treatment variable

Four definitions cover most designs in this field.

| Treatment definition | How it is built | Data source | Implicit assumption | When to use |
| Statutory minimum-wage exposure | Assign the provincial or municipal monthly minimum wage to the worker's province-year-month; alternatively use the ratio to the local average wage or a Kaitz-type index | Provincial government announcements; China Labor Statistical Yearbook | Covered workers are in the sample and the floor is enforced; the bite is comparable across provinces after normalizing by local wages | Wage-floor, employment, and spillover designs |
| Statutory retirement eligibility | Eligibility indicator from age times gender times occupation thresholds; the running variable is age in months | Statutory rules; survey birth year and month | No manipulation of reported birth date near the cutoff; no other policy discontinuity at the same age | Regression discontinuity design (RDD) on retirement, consumption, health |
| Reform cohort exposure | Treatment intensity by birth cohort times province, for example exposure to the college expansion or to a compulsory schooling reform | Cohort and province of residence at school age | Reform timing is unrelated to cohort outcomes conditional on covariates | Returns to education, schooling attainment |
| Hukou status | Binary local non-agricultural hukou at the survey date, or a three-way rural, urban non-local, urban local classification | Survey hukou module | Status is not adjustable within the window studied, or a policy rule shifts who can convert | Hukou wage gap, discrimination, labor mobility |

A second table fixes the outcome-side concepts, which carry as much identification risk as the treatment itself.

| Construct | Option | Definition | Implicit assumption | When to use |
| Education years | Years-of-schooling conversion | Map highest degree to years, primary 6, junior 9, senior 12, college 16 (to confirm against the official codebook) | Schooling duration is stable across cohorts and provinces | Descriptive work; linear wage equation when the linearity is tested |
| Education years | Highest-degree dummies | One dummy per degree, no cardinalization | Degree completion carries the return, not years | When returns are non-linear or a reform changed completion only |
| Wage | Monthly earnings including bonuses and allowances | Self-reported or payroll total labor income for the reference month | Bonus timing does not shift the measured month | Employment and wage-level designs |
| Wage | Hourly wage excluding overtime and bonuses | Base pay divided by usual hours | Hours are measured consistently and overtime is not part of the return | Labor supply elasticity and hours-wage designs |
| Employment status | International Labour Organization style employed | Worked at least one hour in the reference week or had a job but was absent | The reference period is short enough to be unaffected by the treatment | Participation and employment-rate outcomes |
| Employment status | Formal employment | Has a written contract or employer social insurance | Formality is measured the same way across waves | Job-quality and social-insurance designs |
| Industry and occupation | Single classification vintage | Recode all waves to one national industry or occupation classification | Crosswalks preserve the underlying category | Descriptive comparisons and industry-level exposure |
| Matching | Unique firm identifier | Link worker and firm records on a firm ID within the same year, or on administrative records | The identifier is stable and matching is not selective by firm size | Matched employer-employee panel designs |

## Identification assumptions by definition

| Definition | What must hold | What would break it |
| Minimum-wage exposure | The sample contains covered workers; the floor binds; the province-year panel of statutory levels is measured at the right date | Most workers earn far above the floor, or the revision date is assigned to the wrong year |
| Retirement eligibility | Age is measured precisely enough for the bandwidth; no manipulation of birth dates; no co-occurring policy at the same age | Only birth year is observed, so the running variable is coarse; pension rules change at the threshold |
| Reform cohort exposure | Reform timing is not correlated with unobserved cohort quality; treatment is not partially anticipated | Reform targeted the same cohorts that were already changing |
| Hukou status | Status is predetermined relative to the outcome, or a conversion rule provides the variation | Status is measured after migration, so it is an outcome of the treatment |
| Matched panel | Firms are sampled independently of the treatment, and worker mobility is not driven by the outcome | Covered firms are above a size threshold that correlates with the treatment |

## Common construction errors

| Error | Consequence | Correct approach |
| Deflating wages with the national consumer price index when treatment varies by province | Provincial price-level differences are absorbed into the treatment variable | Deflate with provincial price indices or use a wage index |
| Changing the income concept across waves, for example including bonuses in one wave only | A measured wage change is actually a survey-design change | Document the income concept per wave and restrict to a consistently asked concept (to confirm against the official codebook) |
| Conditioning on employment when estimating a wage equation | Selection bias if employment responds to the treatment | Model employment explicitly, report the employment effect, or bound the wage effect |
| Converting education to years, entering it linearly, and also controlling for birth cohort | Cohort trends absorb the variation that identifies returns to education | Use degree dummies or a reform-based instrument for schooling |
| Linking individuals and firms on name or address without a unique identifier | False matches concentrated in large firms | Match on a unique firm ID, report the match rate, and validate against administrative totals |
