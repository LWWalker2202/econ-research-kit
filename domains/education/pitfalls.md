# Education economics: referee pitfalls

Referees in education economics are skeptical of two things at once: that the reform is the only thing that changed for the cohort being studied, and that the schooling variable measures what it claims to measure. The questions below are the ones that recur in reports on Chinese education papers, phrased as a referee phrases them.

## What referees ask

1. Your treatment varies by cohort and province. How do you separate the expansion from other changes that hit the same cohorts in the same provinces?
2. The return to education is confounded by unobserved ability and family background. What in your design addresses that, beyond controlling for a few covariates?
3. Class size is chosen by schools and parents. Why would the variation in class size be unrelated to the students in the class?
4. Are your test scores comparable across survey waves or across counties? What equating procedure did you use?
5. As college enrollment expands, the composition of students changes. What population does your estimate describe?
6. Years of schooling is self-reported and heaped. How large is the measurement error, and which way does it bias your estimate?
7. You assign treatment by the county where the respondent was surveyed. What if the respondent moved before or during the reform?
8. Fee exemptions were introduced together with other measures for the same grades. How do you know the coefficient is the fee exemption?
9. Is the vocational track effect you estimate the return to vocational schooling, or the return to the students who select into it?
10. The compulsory schooling law was enforced unevenly across counties. Why does your cohort comparison identify the law rather than the enforcement?

## How to respond

1. Document everything else that hit the cohort. Build a cohort-by-province panel of concurrent reforms, show which cells are exposed to which, and re-estimate on cells exposed only to your reform. Also report a placebo cohort that was already past the relevant grade.
2. Use a sibling or twin comparison if the survey allows it, or an ability measure collected before the schooling decision, and report how much of the raw return survives. Say plainly what remains unobserved and how large a bias that could produce. Do not claim to have solved ability.
3. Exploit a rule-based source of class size variation, such as a maximum class size regulation or a discontinuously assigned teacher cohort, and test whether student characteristics are smooth around the rule. If no such rule exists, report the result as an association.
4. Describe the assessment and its scaling, report within-wave standardization, and use only within-wave comparisons. If two waves must be compared, present the equating exercise and the range of estimates it supports.
5. Define the marginal student. Show how the composition of enrollees changed across cohorts using observable characteristics, and discuss whether the estimate is a policy-relevant average or an average over a selected group.
6. Quantify the heaping and its direction. Compare self-reported years with a categorical measure of completed level, report the implied attenuation, and, if the survey has a school-leaving age or a school-start variable, use it to bound the error.
7. Construct treatment from the county where the respondent attended school at the relevant age, not the survey county, and check how many respondents moved. For movers, report the result excluding them and the result assigning them by origin.
8. List the concurrent measures and test whether the fee exemption is the binding one: if the exemption was announced and funded at a different date from the other measures, use the funding date; if they coincide, say so and bound the effect of the package.
9. Model selection into the track. Use the admission threshold as an instrument or a regression discontinuity, report the compliers' characteristics, and interpret the estimate for the marginal student at the threshold rather than for all vocational students.
10. Measure enforcement. Reconstruct county-level enforcement from school construction, teacher hiring, or enrollment jumps at the law date, and interact the mandate with enforcement intensity. If enforcement is unobservable, describe the comparison as intent to treat.

## Where it goes wrong

| Frequent failure | What it looks like in the draft | What it costs |
|---|---|---|
| Ignoring ability and family background | A Mincer coefficient with a handful of controls, read as a causal return | The estimate is read as an upper bound and the contribution collapses to description |
| Treating class size as random | Cross-sectional class size coefficient presented as a resource effect | Sorting and remediation reverse the sign; referees demand a rule-based design |
| Confusing shadow education with schooling | Tutoring participation entered as a control in a schooling regression | The control absorbs the mechanism the paper claims to study |
| Comparing scores across waves without equating | A test-score trend spanning two survey instruments | Measurement change is read as learning change |
| Mixing expansion cohorts with other cohort shocks | A single post indicator for everyone born after a given year | The estimate is attributed to the expansion alone without support |
| Reporting self-reported years without validation | A continuous years variable with no heaping check | Attenuation is unmentioned and the magnitude of the return is not credible |
