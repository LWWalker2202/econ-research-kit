# Energy and Environmental Economics: Constructing the Treatment Variable

## Constructing the treatment variable

Environmental economics in China rarely has a single clean treatment. The workable approach is to state the definition explicitly and then state what the definition assumes about who is exposed. Four definitions cover most of the papers in this area.

| Definition | Data source | Implied assumption | When to use |
|---|---|---|---|
| Inspection exposure: indicator equal to one after the CEPI team enters province p | Ministry of Ecology and Environment entry announcements | Conditional on province and year fixed effects, batch order is unrelated to province-specific pollution trends | Province-year panels with staggered entry and several pre-period years |
| Key pollutant discharging unit: firm-level dummy for appearing on the provincial list | Provincial lists of key pollutant discharging units | Selection into the list is driven by size and sector rather than by unobserved emission behaviour | Firm panels where the list is refreshed before the outcome window |
| Pilot ETS coverage: firm, plant, or sector dummy for being covered by a pilot scheme | Pilot scheme coverage rules, including the sector list and the emission threshold | Coverage is determined by pre-policy emissions and does not respond to expected future regulation | Firm or plant panels around the 2013-2014 pilot launch |
| Energy intensity target: city or province target, either continuous or as an above-median indicator | Five-year plan targets reproduced in provincial government work reports | Targets are set using information available before the plan period begins | City panels where a continuous dose is more credible than a binary switch |

Three practical notes. First, inspection exposure can be coded at the day, month, quarter, or year level, and the choice changes the estimated effect size because most of the short-run effect is concentrated in the stationing month and the quarter after it. Second, pilot ETS coverage is often coded as province times sector times post even though the actual coverage line is an emission threshold, which is a different treatment and a different estimand. Third, the carbon price is a price and not a treatment indicator; using it as a regressor requires a separate argument about what identifies its variation.

## Identification assumptions by definition

**Inspection exposure.** The identifying assumption is that, within province and year fixed effects, the batch in which a province was inspected is unrelated to its pollution trend. This fails if the centre inspected the dirtiest or the most politically responsive provinces first. Falsification tests: inspect pre-trends province by province, re-estimate with batch fixed effects, and check whether batch order correlates with pre-period pollution levels or with the 2013 action plan exposure ranking. Report the event-study figure with the pre-period coefficients visible, not only the post-period ones.

**Key pollutant discharging unit status.** The assumption is that list membership is not itself a response to the inspection. Because the lists are compiled annually and are strongly predicted by firm size, industry, and prior emissions, the relevant specification includes industry times year fixed effects and firm fixed effects. The useful check is whether firms enter or leave the list around the inspection date; if they do, list membership is an outcome and not a treatment.

**Pilot ETS coverage.** The cleanest version exploits the emission threshold that defines coverage, comparing firms just above and just below the cutoff at the time of the pilot launch. That requires plant-level emissions for the pre-period and a credible running variable. The weaker version, province times sector times post, assumes no differential trend between covered and uncovered sectors within the same province, which is hard to defend when the pilot provinces are also richer and more industrialized.

**Energy intensity target.** Targets are politically negotiated and are set with knowledge of past energy use, so a target level is not exogenous. The workable version uses the gap between the target and the pre-period trend as the dose, and controls for the pre-period growth rate. If the target is used as a binary above-median indicator, the assumption is that the median split is unrelated to other determinants of energy use, which should be shown rather than asserted.

## Common construction errors

| Error | Consequence | Correct approach |
|---|---|---|
| Coding inspection at the province level but running firm-level outcomes without province times industry fixed effects | The coefficient absorbs any concurrent province-level shock, and standard errors are too small | Add province times industry times year fixed effects, or aggregate the outcome to the treatment level |
| Treating pilot ETS coverage as a firm characteristic without using the emission threshold | Covered and uncovered firms differ in size and energy intensity, so the estimate mixes coverage with firm type | Use a threshold-based design, or match covered firms to uncovered firms on pre-period emissions |
| Using realized energy intensity as both the outcome and the dose | Mechanical negative correlation between the target and the outcome | Use the target and the pre-period trend, never the realized value, to build the dose |
| Ignoring that the environmental protection tax changed the price of emissions in 2018 | Inspection and tax effects are attributed to whichever variable is coded first | Include tax rates as a control, or restrict the window to before 2018 |
| Assuming treated status is absorbing when later inspection rounds revisit earlier provinces | Post indicators stay on after the treatment has ended, so the estimate averages over on and off periods | Build a separate indicator per round, or use a stacked design with clean not-yet-treated controls |
