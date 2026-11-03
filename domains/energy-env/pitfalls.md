# Energy and Environmental Economics: Pitfalls

## What referees ask

1. "The inspection timing is not random. What determined which province was inspected first, and how do you rule out that early-inspected provinces were already on a different pollution trajectory?"
2. "Your treatment varies at the province level but your outcome is measured at the firm level. Why are the standard errors clustered at the firm level, and what happens if you cluster at the province level?"
3. "Carbon prices in the pilot schemes were administratively bounded. Can the coefficient really be read as a response to the marginal cost of abatement?"
4. "CEPI, the permit system, the environmental protection tax, and dual control of energy consumption all bind in your sample period. How do you separate the effect of the inspection from the effect of the other instruments?"
5. "Monitoring stations are not randomly located, and several were relocated during your sample period. Does your pollution variable measure emissions or monitoring effort?"
6. "Is the key pollutant discharging unit list a treatment, or is it a proxy for firm size and industry?"
7. "Your event-study figure shows a coefficient in the periods before the inspection. Is that anticipation, a pre-trend, or a coding error in the treatment date?"
8. "What happens to the estimate when you use plant-level CEMS emissions instead of the county aggregate?"
9. "Would the result survive if you restricted the sample to provinces inspected in the last batch, using the earlier provinces as controls?"
10. "The 2021 national carbon market covers one sector only. What does your estimate identify about carbon pricing in general?"

## How to respond

1. Show what predicts batch order. Regress batch assignment on pre-period pollution, industrial structure, and fiscal capacity, and report the result whether or not it is null. Then add batch fixed effects and re-estimate; if the coefficient moves, say so and explain which design you prefer. Do not argue that the timing is random when it is not.
2. State the level at which treatment is assigned and cluster there, then report the alternative as a robustness check. With few treated provinces, add wild cluster bootstrap p-values or a randomization-inference p-value based on reassigning batch order. The honest statement is that province-level treatment with few provinces limits inference, not that clustering fixes it.
3. Separate the price from the policy. If the price is bounded, the estimand is the effect of the scheme, not the elasticity of emissions with respect to price. Say which one the paper delivers. If a price elasticity is the goal, use the within-pilot variation in the allowance allocation or the compliance-cycle variation, and show that the price variation is not driven by a single administrative adjustment.
4. Build a policy inventory table with the exact dates at which each instrument binds in each province, and show which are collinear with the inspection. Where collinearity is exact, restrict the window; where it is partial, include the other instruments as controls and report the bound.
5. Report the station count by year, the relocation log, and results with a fixed station set. If the monitor sample changes with treatment, that is a finding about monitoring, not about emissions, and the paper should say which of the two it estimates.
6. Test list entry and exit around the policy date. If firms do not move on and off the list around the inspection, membership is predetermined and the treatment is defensible. If they do, use the list as an outcome and find another treatment definition.
7. Look at the pre-period coefficients province by province rather than in the pooled event study, and check the source date of the announcement against the date in the treatment variable. Anticipation of a few months is plausible and should be modeled as a separate lead term rather than interpreted as a failed design.
8. Report both. If the plant-level effect is larger than the aggregate effect, the difference is informative: it can reflect reallocation across firms within the county, which is a mechanism the aggregate cannot see.
9. Do this, and also use the not-yet-inspected provinces as the control group in a stacked design with cohort-specific event time. If the estimate changes, the paper has to choose and defend one.
10. Be explicit about the estimand. A one-sector national market identifies the effect of coverage for power generators, not a general carbon price elasticity. Offer the pilot evidence, which has more sector coverage, as a complement with its own caveats.

## Where it goes wrong

| Problem | What you see in the output | Fix |
|---|---|---|
| Treatment date taken from the first news report rather than the official announcement | Event-study coefficients are shifted by weeks and the pre-period looks contaminated | Use the announcement date, and build a separate lead term for the announcement window |
| Province-level treatment with province and year fixed effects only | The coefficient is large and the standard error is small because any province shock loads onto the treatment | Add province times industry or province times year controls, or aggregate to the treatment level |
| Using the emission threshold as a running variable without checking manipulation | A density plot shows bunching just below the cutoff, or firms' reported emissions change discontinuously at the cutoff | Test for bunching, report the McCrary-style density check, and use pre-policy emissions to define the running variable |
| Mixing pilot ETS and national ETS in one treatment indicator | The post period is long and the estimate averages two schemes with different coverage and prices | Estimate them separately, with separate boundary dates and separate control groups |
| Reporting only the post-period event-study coefficients | Referees see a clean result but cannot judge the pre-trend | Show the full event-study window from at least three pre-period years to three post-period years, and report the joint test on pre-period leads |
