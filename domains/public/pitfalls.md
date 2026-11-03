# Public economics: referee pitfalls

Referees in this field are less worried about the direction of the coefficient than about whether the money moved for a reason connected to the outcome. The questions below are the ones that come back most often in reports on central-local fiscal papers. They are phrased as a referee would phrase them, because that is how they arrive.

## What referees ask

1. Several reforms overlapped in your sample window. How do you know the coefficient is not picking up the other ones?
2. Transfers are allocated to places that need them. What makes you confident that the allocation is not simply a response to the outcome you are studying?
3. Your treatment is measured at the county level by merging two yearbooks. How large is the measurement error, and in which direction does it bias the estimate?
4. The pilot was chosen by the provincial government, not randomly assigned. Can you rule out selection on pre-existing trends?
5. National macroeconomic conditions changed at the same time. How do you separate the policy shock from the business cycle?
6. What is the counterfactual for a county that never received the transfer? Is the comparison group actually comparable?
7. Your spending measure aggregates categories with very different functions. Why should a percentage point of education spending and a percentage point of infrastructure spending be treated as the same treatment?
8. Does your result survive a different but equally defensible definition of the treatment, and of the outcome?
9. Is this new money or relabeled money? If the transfer is fungible, the effect you estimate may be a composition effect rather than a resource effect.
10. Your panel is unbalanced because some counties report in some years only. Does that create the result, or does the result create the sample?

## How to respond

1. Build the overlap map first: list every policy active in the window, show which localities are exposed to which, and re-run the main specification on the subsample exposed to your policy only. If the coefficient survives the exclusion, the overlap objection loses its force.
2. Show the allocation rule. Reconstruct the formula from the published notices, demonstrate that the rule does not contain the outcome variable, and report a test of whether past outcomes predict the allocation conditional on the formula inputs. If the allocation is discretionary, say so and switch to a design that exploits the rule rather than the amount.
3. Quantify it rather than argue about it. Compare the merged measure against a second source for the years where both exist, report the correlation and the implied attenuation bias, and if the bias is severe, present the bounds rather than the point estimate.
4. Examine the pre-trend directly, using the years before selection was announced, and report the event study. If the pre-trend is flat, say what test would have caught a violation and show that it passes. If it is not flat, do not claim parallel trends; change the comparison group or the design.
5. Use a comparison group that shares the cyclical exposure but not the policy, or absorb the cycle with year fixed effects interacted with baseline characteristics. Explain why the interaction you chose captures the cyclical channel rather than another policy.
6. Define the comparison group in terms of the allocation rule, not in terms of who received money. Counties just below and just above a formula threshold, or counties whose formula amount barely changed, are more credible comparisons than all non-recipients.
7. Defend the aggregation or disaggregate. If the theory is about total resources, show the result holds for total spending and is not driven by one category; if the theory is about a specific service, run the categories separately.
8. Report the alternative definitions in the appendix with the same table structure. A result that survives two defensible definitions of treatment and outcome is much harder to dismiss than one that survives only the preferred definition.
9. Test fungibility directly: if the transfer is earmarked for a program, check whether spending on that program rises by more than the transfer, and whether other spending falls. The flypaper question is answered with the composition of spending, not with the total.
10. Report the selection process for the sample. If reporting is correlated with local fiscal capacity, model the reporting decision, report bounds under the worst case, and show that the main result does not depend on the counties that enter and leave.

## Where it goes wrong

| Frequent failure | What it looks like in the draft | What it costs |
|---|---|---|
| Treating a bundle of policies as one treatment | A single post indicator that turns on when several reforms start | The coefficient is not attributable to any policy; referees reject the interpretation |
| Using the announced date as the treatment date | Event study shows effects before the reform | Pre-trend test fails and the design is read as endogenous |
| Measuring transfers as a total | General and earmarked money in one variable | Allocation rule cannot be reconstructed, so exogeneity cannot be argued |
| Ignoring off-budget flows | Debt measured only from budget documents | The outcome series misses the larger part of the variation |
| Reporting only the preferred specification | One table, no alternative definitions | The result reads as a specification search and invites a replication demand |
