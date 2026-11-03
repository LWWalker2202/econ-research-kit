# Development economics: common pitfalls

## What referees ask

1. "Why was this village selected for the program? What rule produced the list?"
2. "Your comparison group is the rest of the county. Are those villages plausibly a counterfactual?"
3. "Households are sampled from village rosters. What happens to the households that left?"
4. "The program ran alongside infrastructure, credit, and a work team. What exactly are you estimating?"
5. "Enumerators knew the hypothesis and respondents knew the program. How do you rule out reporting effects?"
6. "Treatment is assigned by village and you report household-clustered standard errors. Why?"
7. "The result holds in one province. What makes it general?"
8. "The outcome is measured income, and the same administration was evaluated on measured income. Why should we believe the increase?"
9. "Treated and control villages trade with each other. Can the control villages be contaminated?"
10. "Your effect is large relative to the literature. Is the sample representative or is the estimate a local one?"

## How to respond

1. Reproduce the allocation rule from the policy documents and show how far the realized list follows it. If the rule predicts selection, the paper can condition on the rule rather than claim selection is ignorable. If no rule is documented, say so and move the identification to a design that does not depend on selection being random.
2. Show pre-period balance on the outcome and on the covariates that determine eligibility, and report an event study around the selection date. Where possible narrow the comparison group to villages that were eligible but not selected, and report whether the estimate survives. A comparison group of ineligible villages is often the reason a referee is unconvinced.
3. Report attrition by treatment and control, test whether attrition predicts the baseline outcome, and estimate bounds for the extreme cases. If the program itself causes exit from the roster, that is part of the effect and should be discussed rather than treated as a nuisance.
4. Document the bundle: which components the treated villages received and which the control villages also received. If components cannot be separated, relabel the estimate as the effect of the package and interpret it as such. A decomposition on the subset of villages with component-level records is usually the most persuasive addition.
5. Use design features rather than assurances. Randomize or blind enumerator assignment where possible, keep the survey instrument neutral, do not mention the policy in the opening script, and add a module that asks respondents what they believed the study was about. Report the distribution of those beliefs and whether the effect differs by belief.
6. Cluster at the level at which treatment was assigned and report the number of clusters. With few clusters, use wild cluster bootstrap or randomization inference and report those standard errors next to the conventional ones.
7. Distinguish what the design identifies (a mechanism, a parameter for a defined population) from a national average. Report heterogeneity across the dimensions that theory says matter, and state the population the sample represents rather than implying a larger one.
8. Separate measured from real outcomes where the data allow: consumption, assets, and health measures that are not produced by the evaluated administration. If only administrative outcomes exist, discuss reporting incentives explicitly and show whether effects are larger where the incentive is stronger, which is a test rather than a disclaimer.
9. Compute treatment intensity in neighboring villages and show the estimate with and without spillover controls. Report the direction of the bias and, where feasible, estimate the spillover effect itself.
10. Compare the estimate with the closest published designs on comparable populations, and explain differences by design, population, or duration rather than asserting that the estimate is plausible. Report the sample's position in the national distribution of the key variables.

## Where it goes wrong

| Problem | What shows up in the output | How to fix it |
|---|---|---|
| Selection into the program is treated as ignorable | Covariate imbalance at baseline that the paper does not report | Report balance and the allocation rule; narrow the comparison group |
| Attrition concentrated in treated villages | Large differences in follow-up rates with no bounds or tests | Estimate Lee bounds and report attrition by arm |
| The package is described as one component | Effect sizes too large and mechanism claims that the components cannot support | Document each component and rename the treatment as the package |
| Clustering at household level with village assignment | Very small standard errors and implausibly precise estimates | Cluster at the village level; report wild bootstrap p-values |
| Administrative outcomes used without any non-administrative check | Effects that vanish when a survey outcome is used | Report both and treat the difference as informative |
