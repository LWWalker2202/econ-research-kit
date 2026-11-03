# Theory and mechanism design: from assumptions to testable implications

A theory paper has no treatment variable in the regression sense. What it has is a set of objects that the model says drive the equilibrium, and the discipline that makes the paper empirical: each object must be pinned down by an observable counterpart, and each assumption must imply a sign or pattern that data could reject. This file turns that discipline into a table a referee can check line by line.

## Constructing the treatment variable

Read "treatment" as the forcing variable of the model: the instrument, the informational friction, the commitment technology, or the preference parameter whose movement generates the comparative static. For each one, write down the observable counterpart and the moment that identifies it before touching the data.

| Model object | How it enters the model | Observable counterpart | Where the number comes from | Implicit assumption | When to use |
|---|---|---|---|---|---|
| Policy instrument intensity | Multiplies the price or cost faced by agents, shifting first-order conditions | Statutory or effective rate by region and year, from policy documents and fiscal statistics | Policy documents; fiscal and tax yearbooks | The instrument is exogenous to agents in the sample and not offset by unobserved policy | Comparative statics on subsidies, taxes, or quotas |
| Information friction | Restricts the signal available to a principal or agent | Price dispersion, contract terms, audit and inspection frequency | Administrative records; surveys with matched buyer and seller information | The measured dispersion reflects information rather than unobserved heterogeneity in preferences | Screening, moral hazard, delegation models |
| Commitment capacity | Probability weight on honoured promises, or a move-order restriction | Rule changes around leadership transitions, announced targets versus outcomes | Policy documents; event histories of rule reversals | The event identifies the commitment parameter and not a shock to the environment | Credibility, time inconsistency, policy games |
| Bargaining weight | Sets the split of a surplus between parties | Pass-through of input prices to output prices, or margin responses to cost shocks | Price and cost micro-data; customs and firm data | Bargaining structure is stable over the window studied | Vertical relations, supply chains, factor markets |
| Preference and discount parameters | Appear in Euler equations or insurance conditions | Consumption growth moments, portfolio and insurance choices | Household panels; administrative banking or insurance records | Preference heterogeneity is second order, or is modelled explicitly | Consumption, saving, insurance, risk-sharing |
| Technology and entry costs | Determine capital intensity and firm selection | Factor income shares; entry rates and the size distribution of entrants | National accounts; firm registries; industrial surveys | Factor markets clear at observed prices, which is itself an institutional claim | Production, investment, entry and exit models |

A second table states what must hold for a parameter to be identified at all. #moments at least #parameters is necessary but not sufficient; the moments must also be sensitive to the parameter.

## Identification assumptions by definition

| Definition or parameter | What must hold to pin it down | What breaks it |
|---|---|---|
| Target moments | At least as many independent moments as parameters, and each moment responds to the parameter being calibrated | Calibrating a parameter on the same moment later used to test the model, which makes the test circular |
| Local sensitivity | The Jacobian of moments with respect to parameters is well conditioned over the literature range | A parameter that barely moves any moment drifts across the admissible range without changing fit |
| Literature range | The admissible interval comes from several studies and is stated as an interval, not a point | Taking one study as the truth and reporting no sensitivity band |
| Institutional consistency | Parameters describing technology or preferences are not transplanted from economies with different factor-market institutions without comment | Using competitive-market capital shares in an economy with administered prices and ownership-biased credit |
| Numerical solution | Convergence is reported with a tolerance, the grid is refined, and multiple starting points are tried | Reporting one run of one algorithm on one grid |
| Equilibrium selection | Existence and uniqueness are proved, or a selection rule is stated when multiple equilibria exist | Comparative statics asserted without saying which equilibrium they refer to |

The practical implication is that a theory paper should be able to answer four questions in one page: what is the sufficient statistic, what moment pins it down, what sign does the model predict, and what would the data have to look like for the sign to reverse.

## Common construction errors

| Error | Consequence | Correct approach |
|---|---|---|
| Treating an estimated reduced-form coefficient as a structural parameter | The parameter absorbs equilibrium effects and cannot be used for counterfactuals | State the mapping from reduced form to structure, and test invariance across policy regimes |
| Calibrating on the moments that are later used for validation | The model passes by construction and the test has no power | Separate calibration moments from over-identifying test moments, and report both fits |
| Reporting the comparative-static sign only at the midpoint of the parameter range | The sign may reverse at the ends of the range, and the paper's claim is not robust | Derive the analytic sign, or report the sign over the admissible interval |
| Reporting one numerical run without convergence diagnostics | The conclusion can be a grid artefact or a failed iteration | Report tolerance, grid refinement, and multiple starting points, and check Euler-equation residuals |
| Ignoring the model's own resource and budget constraints when computing welfare | The welfare ranking is not attainable and the policy conclusion is empty | Write the constraints out, verify they hold in the solution, and compute welfare relative to a feasible allocation |
| Importing parameters wholesale from a different institutional setting | The calibrated model misdescribes the economy it claims to explain | Report sensitivity to the imported values and discuss the direction of the bias |
| Letting the story do the work the model cannot do | The mechanism is verbal, the model is decorative, and neither is refutable | State which model restriction generates the mechanism and which observation could reject it |

**What to check before submitting.** The order is stable across fields. First, does the model have assumptions that do any work, or could the main proposition survive with the assumption removed? Second, is each comparative-static sign derived rather than assumed? Third, is the mapping from parameters to moments one-to-one in the relevant range? Fourth, are the numerical choices documented well enough to reproduce? A paper that answers these in the model section pre-empts most of the report.
