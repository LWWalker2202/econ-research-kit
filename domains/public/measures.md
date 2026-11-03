# Public economics: constructing the treatment variable

In this field the treatment variable is almost never read directly off a policy document. Transfers arrive in a budget line, taxes are shared by formula, and pilot status is a label that a locality may acquire for reasons correlated with its outcome. Constructing the variable means deciding which margin of the policy carries the variation, documenting the rule that maps the rule to the variable, and stating the assumption under which the resulting variation is exogenous. The tables below list the definitions that appear most often, the assumption each one buys, and the mistakes that get the definition rejected.

## Constructing the treatment variable

| Treatment definition | Data source | Implicit assumption | When to use |
|---|---|---|---|
| Per-capita transfer shock: the change in formula-allocated general transfers per capita between two budget years | Ministry of Finance transfer notices and provincial final accounts | The formula and the local characteristics that enter it did not change in response to the outcome | When the question is about the effect of extra fiscal resources on local public provision |
| Fiscal expenditure intensity: local government expenditure divided by local GDP, or the share of a spending category in total expenditure | China Finance Yearbook, county and city yearbooks | Higher intensity reflects policy choices rather than demand-driven spending | Cross-sectional work on public goods provision, where the variation is persistent rather than a reform |
| Tax sharing rate: the share of a given tax retained locally, or the ratio of local revenue to locally generated revenue | Provincial fiscal statistics and tax-sharing rules | The sharing rule is set from above and is not jointly determined with the local outcome | Studies of how revenue incentives shape local behavior, especially around the 1994 reform |
| Pilot program status: a dummy for a county or firm in a designated reform pilot, dated from the official launch | Reform notices, provincial implementation documents | Selection into the pilot is not driven by the outcome trend; or the propensity to be selected can be modeled | Event-study and staggered difference-in-differences designs around a documented pilot |
| Policy intensity score: a composite index built from the number of policy documents, the level of the issuing authority, or the stringency of requirements | Collected reform documents and implementing rules | The score orders places by exposure to the same policy in a way the outcome does not influence | When several instruments implement one policy and there is no single breakthrough date |

| Outcome variable | Definition to report | What the definition changes about the estimate |
|---|---|---|
| Local public expenditure | Budgetary expenditure by functional category, per capita, in real terms | Whether capital or current spending is included changes the sign in some settings |
| Transfer dependence | Transfers received divided by total local revenue or by expenditure | Using expenditure as the denominator introduces mechanical correlation with the outcome |
| Local debt | End-of-year balance of interest-bearing debt, including financing-vehicle debt where available | On-budget and off-budget definitions produce different levels and different trends |
| Firm tax burden | Taxes paid divided by sales or by value added | The sales denominator is sensitive to firm size and to transfer pricing [verify] |
| Policy adoption date | First year the locality appears in a reform document | Dating from the announcement rather than the implementation shifts the treatment timing |
| Reform exposure by sector | Share of local employment or output in the sectors named by the reform | Exposure shares can be endogenous to pre-reform growth [verify] |

## Identification assumptions by definition

| Definition | What must hold | What would break it |
|---|---|---|
| Per-capita transfer shock | The formula change is not a response to the outcome, and no other fiscal change coincides with it | A concurrent tax change or an anti-poverty campaign that moves the same money |
| Fiscal expenditure intensity | The variation in intensity is not driven by contemporaneous local demand | Reverse causality: a demand shock that raises both spending and the outcome |
| Tax sharing rate | The rule was set without anticipating the local outcome | A reform explicitly targeted at the outcome in the study |
| Pilot status | No selective selection, or selection on observables that the researcher can model | The upper-level government picks localities with the strongest pre-trend |
| Policy intensity score | The score measures exposure to the same policy, not the outcome itself | Documents are issued in response to local problems the outcome also reflects |
| Reform exposure by sector | The pre-reform sector composition is not itself a function of the outcome | Anticipatory adjustment before the reform date |

## Common construction errors

| Error | Consequence | Correct approach |
|---|---|---|
| Treating all transfers as one bucket | Mixing general and earmarked money, whose allocation rules differ | Split the transfer variable by channel and report each separately |
| Using the year the policy was announced as the treatment year | Attenuates the estimate when implementation lags | Report announcement and effective dates, and run both |
| Dividing by an endogenous denominator such as local GDP | Creates a mechanical correlation between treatment and outcome | Use the level in real per capita terms, or a denominator fixed at baseline |
| Ignoring overlapping reforms in the same window | The coefficient absorbs several policies at once | Map every active policy in the window and show the main result survives controlling for or excluding them |
| Scoring policy intensity by counting documents | Oversensitive to the volume of paperwork rather than the level of the instrument | Weight by the level of the issuing authority and by whether the document changes the rule |
