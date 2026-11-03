# Health Economics: Common Pitfalls

## What referees ask

1. "Who is in your control group, and were they eligible for the same reform?"
2. "Enrollment is voluntary. What makes you think the insured and uninsured are comparable?"
3. "Self-rated health is relative. How do you know the report changed and not the person?"
4. "You measure spending in the survey. Does it include reimbursed amounts, and does the recall period match the reform?"
5. "Sicker people die during the study. Who is left in your sample and how does that bias the estimate?"
6. "Reimbursement rises and utilization rises. Which is the treatment and which is the result?"
7. "The reform was accompanied by a supply-side change in the same hospitals. Can you separate them?"
8. "Your health variable is only available in some waves. What happened to the people who were not examined?"
9. "Diagnosis rates rose after insurance expanded. Is that incidence or access to diagnosis?"
10. "The pollution monitor is far from the household. What is your exposure measure actually measuring?"

## How to respond

1. Define the control group by eligibility, not by geography. Show the eligibility rule before the reform and demonstrate that the comparison group was not eligible for that reform, or was eligible at a different date. If everyone was eligible at once, the design is a before-after and needs a second comparison dimension such as pre-reform insurance status or county generosity.
2. Report the selection directly: baseline health, income, and utilization of enrollees versus non-enrollees, and the change in those gaps at the reform date. Where the reform changed eligibility for a defined group, use that as the design. Where enrollment remains voluntary, an instrument based on local enrollment drives or on policy rules is the usual fix. A cross-sectional insured-uninsured comparison should not be the main specification.
3. Use an objective or anchoring measure alongside the self-report. Within-person changes, vignette-style anchoring, and physical measurements are the standard responses. If only self-rated health is available, report the result as a measure of perceived health and interpret it accordingly rather than as a change in true health.
4. Report the exact expenditure concept in each wave: whether reimbursed amounts are included, what the recall window is, and whether the survey changed the question. Where claims data exist, compare the survey measure with the claims total for the same households, which also quantifies the recall error.
5. Report death and attrition rates by treatment arm, estimate the effect on the survivor sample with bounds, and where possible use the death outcome itself as an additional endpoint rather than a nuisance. A health reform that reduces mortality but increases measured morbidity among survivors is a coherent and reportable finding, not a contradiction.
6. Separate price from quantity with the data: report spending, utilization, and out-of-pocket spending per visit together. The reform's effect is the combination, and the paper should say which margin it identifies explicitly, ideally with a decomposition.
7. Document the supply-side changes that coincided with the insurance reform in the study areas. Where they cannot be separated, relabel the estimated effect as the effect of the package, and use variation in the exposure to the supply-side date to test whether the result is driven by it.
8. Restrict attention to waves with consistent measurement or report the specification that uses only those waves. Report the baseline characteristics of respondents who were examined and those who were not, and show that the treatment effect does not depend on the measurement subsample.
9. Treat diagnosis as an outcome of its own. Report the measured prevalence as a separate result and state that the rise in diagnosed disease is consistent with better access, not worse health. Use objective biomarkers or measured conditions where the survey provides them.
10. Describe the exposure construction precisely: which monitor or which grid cell, how the assignment from monitor to residence is done, how distance is controlled, and what the monitor's placement rule is. Where possible use a monitoring network change or facility placement as the source of variation rather than cross-sectional distance.

## Where it goes wrong

| Problem | What shows up in the output | How to fix it |
|---|---|---|
| Voluntary enrollment treated as random | Treated and control differ on health at baseline; large and implausible effects | Use the eligibility reform or an instrument; report baseline balance |
| Self-rated health used as the only outcome | Effects that appear in reports but not in objective measures, or the reverse | Report both and interpret the divergence |
| Survey spending mixed with claims spending | Levels that no single dataset can support and effects that flip depending on the source | Keep sources separate and reconcile on the overlapping sample |
| Death ignored in the panel | Survivors are healthier; effects on morbidity are biased toward zero or upward | Estimate bounds; report mortality by arm |
| Reform bundled with hospital payment changes | Effect attributed to insurance that belongs to the payment system | Document the bundle and use exposure variation to separate them |
| Diagnosis-based morbidity used as the health outcome | Rising diagnosis after insurance expansion read as worsening health | Report measured conditions; label diagnosis effects separately |
