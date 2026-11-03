# Development economics: constructing the treatment variable

In this field a treatment variable almost never arrives as a clean indicator of whether a household was affected. It arrives as an administrative status, a project list, a rollout calendar, or a distance. The research task is to choose the version that matches the decision the data actually recorded, and then to state what that version assumes.

## Constructing the treatment variable

The four constructions below cover most applied designs. A paper can use more than one, but it should say which one carries the identifying argument and which are robustness.

| Construction | What varies | Data source | Hidden assumption | When to use |
|---|---|---|---|---|
| Administrative eligibility | Whether a household falls below a locally applied standard | County dibao standards, household rosters | The standard is applied consistently within a county and the household roster reflects it | You can observe both the standard and the household outcome near it |
| Project exposure | Whether the village, county, or school was selected for a program, or how many its share of the program was | Project lists, work reports, budget documents | Selection is either ignorable after covariates or predictable by a rule | Panel data exist before and after selection |
| Rollout timing | The date a program reached a unit, when timing differs across units | Provincial and county implementation notices | Timing is unrelated to the outcome trend within matched groups | Units are staggered and pre-periods are long enough |
| Distance and access | Continuous travel time or distance to a facility, market, or road | GIS layers, maps, road construction records | Distance affects outcomes only through the service or market of interest | A facility placement change provides a shift in access |

For eligibility designs, record jointly the standard in force, the year it changed, and the household's income measure as collected. If the survey income measure is not the administrative measure, draw the discontinuity on the variable that the administration used, or report both and show the estimate is insensitive.

For project designs the treatment is often a share rather than a dummy. Programs are allocated to counties or villages in proportion to population, poverty headcount, or area, and the intensity measure must be built from the pre-program allocation rule rather than from realized spending, which is endogenous to how the program worked.

For rollout designs, the calendar is the data. Implementation notices frequently give a month, not a year, and the assignment of units to early and late waves is the object of study. Collect the documents that assign units to waves and report any unit whose status is ambiguous rather than dropping it silently.

For access designs, distance is an equilibrium object: roads are built to places with economic activity. Use the component of access that changed because of an external placement decision, such as a facility opened by an administrative plan, and report what would invalidate that exclusion restriction.

## Identification assumptions by definition

**Administrative eligibility.** Identification rests on the running variable being measured the way the administration measured it and on no other discontinuity at the same threshold. Both assumptions fail routinely. Survey income is a recall measure, the administrative standard is updated by local documents, and the threshold year often coincides with a change in the survey instrument. Report the density of the running variable near the threshold, the covariate balance on either side, and the first stage if some eligible households were not actually enrolled.

**Project exposure.** The standard assumption is selection on observables: conditional on the covariates the paper includes, program placement is unrelated to the untreated outcome trend. That is strong when officials choose villages by the same poverty indicators the study uses as outcomes. The defensible alternatives are an explicit allocation rule, an instrument for selection, or a randomization lottery if the program used one. Write down which one applies, and report what happens to the estimate when the comparison group is narrowed to the villages ranked just around the eligibility cutoff.

**Rollout timing.** Staggered timing identifies effects under assumptions analogous to a difference-in-differences design, and with many periods and few treated units the standard two-way estimator can be biased. Use an estimator that is robust to heterogeneous treatment timing, report the event-study plot rather than a single coefficient, and state whether the early and late adopting units were comparable before their own rollout dates.

**Distance and access.** Exclusion requires that the access measure influences the outcome only through the facility or market it is meant to represent. Distance to a county seat also proxies for administrative capacity and for market integration, which is the standard objection. A credible version uses a placement change that moves access for some villages and not others and shows parallel trends in the pre-period.

**Whatever the construction, one further assumption is required: no simultaneous local shock.** Development programs are bundled. A village selected for a poverty project also received infrastructure, credit, and a work team. The estimate then captures the bundle unless the paper documents which components were delivered where. That documentation is usually what separates an accepted paper from a rejected one.

## Common construction errors

| Error | Consequence | What to do instead |
|---|---|---|
| Treating the program list as the treated sample and the rest of the county as control | Control villages were often ineligible or slated for a later round, so the comparison is not a counterfactual | Define the comparison group by an eligibility rule and show pre-period balance |
| Using realized program spending as exposure intensity | Spending responds to outcomes and to local capacity, so the measure is endogenous | Build intensity from the pre-program allocation formula |
| Measuring eligibility with survey income when the administration used a different measure | The discontinuity sits on the wrong variable and the estimate is attenuated | Use the administrative variable or report both discontinuities |
| Ignoring that a county-to-district change redraws the reporting unit | Panel observations are silently duplicated or dropped at the boundary date | Rebuild the panel on a stable geography and document the merge |
| Clustering at the household level when treatment is assigned by village | Standard errors are too small and significance is overstated | Cluster at the level of treatment assignment and report the number of clusters |
