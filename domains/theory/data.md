# Theory and mechanism design: data for calibration and computation

A theory paper uses data twice: to fix the moments that identify the parameters, and to test the model on moments it was not calibrated to. Both uses have to be documented at the level of the exact table and the exact variable definition, because a referee cannot check a calibration that is described only as "standard values from the literature". This file records what to collect, how to define it, what counts as coverage, and what typically goes wrong.

## Data sources

| Object to calibrate | Moment to target | Source and table | Frequency and level | What to record |
|---|---|---|---|---|
| Factor income shares | Labour and capital share of value added | National accounts; provincial statistical yearbooks | Annual, province and sector | The exact industry classification and the treatment of self-employment income |
| Policy instrument intensity | Statutory or effective rate, and its reform dates | Policy documents; fiscal and tax yearbooks | Annual, province or prefecture | The document that establishes the date and the effective base |
| Information environment | Price dispersion or contract-term dispersion | Price micro-data; administrative contract or audit records | Monthly or annual, product or firm | Whether dispersion is within product or across products |
| Commitment and rule stability | Frequency and size of rule reversals | Policy event histories; announced targets versus outcomes | Event-based, province or national | Coding rules for what counts as a reversal |
| Preferences | Consumption growth moments by cohort; insurance uptake | Household panels; administrative insurance records | Annual, household | Whether the panel is balanced and how attrition is treated |
| Technology and entry | Entry rates; size distribution of entrants | Firm registries; industrial surveys | Annual, firm | The threshold that defines entry and the treatment of re-registration |
| Wage and price stickiness | Duration of unchanged prices or wages | Micro price data; personnel records | Monthly, item or worker | Whether durations are censored and how they are modelled |

Moments that matter for identification but are not directly observed should be listed as `[to fill]` with the source that would be needed, not replaced by a plausible-looking number.

## Variables and definitions

- Calibration moments must be defined on the same population and the same time window as the model's steady state. If the model is annual and the data are monthly, say how the aggregation was done.
- Treatment of prices: specify the base year, the deflator, and whether nominal or real quantities enter the moment. A capital share computed from nominal flows is not the same object as one computed from constant-price flows.
- Self-employment and household production: state explicitly whether they are inside or outside the measured capital share; the choice moves the calibrated value by several percentage points and is not innocuous.
- Administrative reform dates: use the date the rule took effect, not the date it was announced, and record both if the gap is informative.
- For moments taken from published research, record the paper, the table, the sample, and the exact number, and mark it `[verify]` until the table has been read. A number quoted from memory is not a source.
- Numerical inputs that are not moments at all (grid sizes, tolerances, iteration caps, starting values) belong in the replication record, not in the calibration table, but they must be recorded with equal care.

## Coverage

| Dimension | What to report | Acceptable shorthand |
|---|---|---|
| Time span | First and last year actually used after cleaning, not the span of the raw file | Report both if they differ |
| Geographic level | National, province, prefecture, county, or firm, and how many units | Report the count of units per year |
| Sample size | Order of magnitude of observations after cleaning | "About one hundred thousand household-years" is acceptable; an invented precise count is not |
| Sector coverage | Which sectors are in, which are out, and why | List the excluded sectors explicitly |
| Missing data | Share missing by key variable, and the imputation rule if any | Report the share, not a qualitative statement |
| Weighting | Whether moments are weighted and by what | State the weight variable |

If a moment has to be taken from a different level than the model's unit of analysis, say how the two are linked and what that linkage assumes about aggregation.

## Known issues

| Issue | Why it matters | How to handle it |
|---|---|---|
| Mixed vintages of the same series | Rebasing and methodology changes create artificial jumps that can be mistaken for a regime change | Note the vintage, or splice with an explicit method |
| Moments computed on a different population than the model | The calibrated parameter absorbs the mismatch and the counterfactual is misdirected | Align populations or report the sensitivity to the mismatch |
| Borrowed parameter values from other economies | The institutional setting that generated those values may not hold here | Report sensitivity and discuss the direction of the bias |
| Numerical solution not checked | The fit can be to a grid artefact rather than to the model | Report tolerance, grid refinement, and multiple starting points; check Euler-equation residuals |
| Equilibrium multiplicity ignored | Comparative statics are undefined without a selection rule | Prove uniqueness or state and defend the selection rule |
| Replication package incomplete | A referee cannot see which run produced which table | Ship the data-construction script, the estimation or solution script, and the table-generating script, in that order |

For the computational side, state the algorithm (value function iteration, shooting, or projection), the approximation used for any continuous state, and the convergence criterion. The choice is defensible in several ways, but the reporting is not optional: a paper that reports one run of one algorithm on one grid gives the reader no way to tell a converged solution from a failed one.
