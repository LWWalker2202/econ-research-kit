# Labor economics: referee pitfalls

Labor papers are refereed on two things above all: whether the treatment and the sample are defined in the same breath, and whether the wage variable measures what the paper says it measures. The questions below are the ones that come back in reports most often, phrased the way referees actually phrase them. Each is followed by the move that answers it rather than the paragraph that dodges it.

## What referees ask

1. Your wage sample is conditioned on employment. How do you know the estimated return to education is not driven by selection into work?
2. Employment is an outcome of the policy you study. Why is employment status in your conditioning set?
3. You enter years of schooling linearly, but a large part of your sample stopped at primary school. Isn't the specification misspecified?
4. Hukou status is chosen by the migrant. What identifies the hukou wage gap?
5. If you control for migration and for hukou, what variation is left to identify anything?
6. Your matched employer-employee panel covers only firms above a size threshold. What does that do to your conclusions?
7. Minimum wages vary by province and year, which is exactly what your province-year fixed effects absorb. What is left of your treatment?
8. Retirement eligibility is defined by age, but you observe only birth year. How do you handle measurement error at the cutoff?
9. Why should the 2008 Labor Contract Law be treated as exogenous to firm-level employment outcomes?

## How to respond

1. Report the effect on the probability of employment first, then bound the wage effect under explicit selection assumptions, for example by trimming the wage distribution on the side the selection direction implies. If the bounds include zero, say so in the abstract rather than only in an appendix.
2. Remove post-treatment employment from the controls. If the design needs employment variation, condition on employment measured before the treatment or in a pre-period, and present post-treatment employment as a mechanism outcome with its own effect estimate.
3. Present degree dummies alongside the linear years specification, show the non-parametric profile of log wages against education, and state which one the headline result uses. If the two disagree, the paper has to explain why the linear one is the one you keep.
4. Use hukou measured at a fixed pre-period, such as at age 16 or at origin, or exploit a rule that changed who could convert status. Acknowledge sorting on unobservables and show how large the gap would have to be to overturn the result.
5. Choose one margin. Either identify the migration effect conditional on origin hukou, or identify the hukou effect among people who do not move. Tabling both margins side by side with an explicit note on what each isolates is stronger than one equation that controls for both.
6. Reweight the matched panel to the firm-size distribution in the census or in an administrative universe, report which conclusions move, and restrict the claims to the covered firms if they do not. Also report whether the treatment intensity is correlated with firm size in the first place.
7. Show worker-level exposure: the distance of the worker's wage above the floor before the revision, or the share of the local wage distribution below the new floor. The province-year level alone has no variation left after fixed effects, but the individual-level bite does.
8. Use birth month when it exists. If only birth year is available, do not claim a sharp RDD on age; use a fuzzy design with the year-based eligibility as the instrument, report a donut around the cutoff, and show the first stage.
9. Show that the exposure measure was predetermined, test for anticipation with pre-2008 outcomes, run a placebo on firms with the lowest exposure, and present pre-trends by exposure quartile. The law itself is not exogenous, only the interaction with exposure is defensible.

## Where it goes wrong

| Failure | What the referee sees | What to do instead |
| Hukou entered as an exogenous control | The treatment variation is absorbed and the sign of the remaining coefficient is uninterpreted | Use hukou measured before the outcome, or a conversion rule as the source of variation |
| Sample restricted on current employment | Selection that runs through the treatment | Restrict on pre-period employment, or report the employment effect and bound the wage effect |
| Education converted to years and never compared with degree dummies | A linearity assumption doing the work of a result | Report both specifications and let the data choose |
| Matched panel used without reweighting | External validity limited to large covered firms, undisclosed | Reweight to a census distribution, or limit the claim explicitly |
| Wages not deflated by province-level prices | A spurious treatment effect from price levels | Deflate with provincial indices or use a wage index |
