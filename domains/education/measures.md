# Education economics: constructing the treatment variable

Education research in China is mostly about cohorts and places. A reform reaches the children in a particular grade in a particular county, and the researcher's job is to turn that rule into a variable that identifies who was treated, when, and how intensively. The complication is that the same variable, years of schooling, can be built in several defensible ways that differ in what they assume about vocational degrees, grade repetition, and the returns to each stage. The tables below give the definitions that recur in the literature, the assumption each one requires, and the constructions that referees reject.

## Constructing the treatment variable

| Treatment definition | Data source | Implicit assumption | When to use |
|---|---|---|---|
| College expansion exposure: interaction of birth cohort with the province-specific increase in enrollment quotas | Enrollment quota announcements and provincial education statistics; cohort from census or survey birth year | The expansion was not targeted at the cohorts or provinces whose outcomes it changed, and no other policy moved the same cohorts | Studies of returns to education, inequality, and the quality-quantity trade-off |
| Consolidation exposure: number of village schools closed or merged in the county in the years the respondent was of primary-school age | County education statistics, yearbooks, provincial layout-adjustment documents | The timing of closures within a county is not driven by the schooling outcomes of the children affected | Effects of school accessibility and school resources on attainment |
| Free compulsory education exposure: birth cohort that was in the treated grade when fees were removed in that province | Provincial fee-exemption documents and grade-by-grade phase-in schedules | Fee removal was not accompanied by other changes specific to the same cohort | Effects of schooling cost on enrollment and completion |
| Years of schooling: years-equivalent mapping from the highest level completed | Household surveys or census education variables | Each year of schooling maps to a constant increment of human capital | Returns to education when only the level is observed |
| Class size and pupil-teacher ratio at the school or county level | School-level education statistics, county yearbooks | Class size varies for reasons unrelated to the achievement of the students in the class | Resource effects on achievement, when within-school variation is available |

| Outcome variable | Definition to report | What the definition changes about the estimate |
|---|---|---|
| Years of schooling, standard mapping | 6 years primary, 3 junior secondary, 3 senior secondary, 4 college | Treats vocational and academic upper secondary as equivalent and ignores repetition |
| Years of schooling, stage-specific | Separate years for each level, with a separate indicator for vocational track | Allows the return to differ by stage; requires a larger sample per cell |
| Highest degree completed | Categorical dummies for primary, junior, senior, tertiary | Robust to mapping errors but discards within-level variation |
| Enrollment or transition rate | Share of an age cohort enrolled, or share of junior graduates entering senior secondary | Cohort denominator choice changes the level and the trend |
| Class size | Students per class, self-reported or from school records | Self-reported class size is heaped and measured with error |
| Pupil-teacher ratio | Students divided by teachers, county or school level | Includes non-teaching staff differently across sources |
| Per-student expenditure | Recurrent expenditure per enrolled student, real terms | Capital spending and teacher salary arrears are excluded and differ across counties |
| Test score | Standardized score from a survey or administrative assessment | Scores from different tests or years are not comparable without equating |

## Identification assumptions by definition

| Definition | What must hold | What would break it |
|---|---|---|
| College expansion exposure | Quota growth is not a response to cohort size or to province-level labor demand for graduates | Expansion targeted at provinces with rising returns, or simultaneous migration of young workers |
| Consolidation exposure | Closure timing is not correlated with unobserved determinants of the children's schooling | Counties consolidate in response to falling enrollment that itself reflects out-migration |
| Free education exposure | Fee removal is the only change affecting that cohort in that province | Concurrent curriculum reform or teacher hiring that moves the same cohort |
| Years of schooling | The mapping is constant across cohorts and regions, and schooling is measured without systematic error | Grade repetition or vocational degrees counted as fewer years, differently across provinces |
| Class size | Variation in class size is not driven by student sorting | Parents move children into smaller classes, or schools assign weaker students to larger ones |
| Test scores | The assessment is comparable across the units being compared | Different tests, different years, different grading standards, or selective participation |

## Common construction errors

| Error | Consequence | Correct approach |
|---|---|---|
| Mapping all post-compulsory schooling to the same years | Understates the return to vocational and overstates the return to academic tracks | Report stage-specific returns and a separate vocational indicator |
| Treating "senior secondary" as one category | Mixes academic and vocational students, whose returns differ | Split by track, and check whether the split is available before starting |
| Assigning the reform year to the survey year | Misplaces treatment for cohorts surveyed years later | Date treatment by the respondent's grade at the time of the reform |
| Using county averages without checking the school-age population | County exposure conflates consolidation with migration | Reconstruct exposure from school cohorts, not from resident population |
| Comparing test scores across waves without equating | Reads measurement change as learning change | Use within-wave standardized scores and report the equating procedure |
| Ignoring self-reported education years in the census | Rounding and heaping create attenuation | Use completed-level dummies as a robustness check, and report the heaping pattern |
