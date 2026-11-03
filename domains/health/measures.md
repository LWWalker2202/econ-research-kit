# Health Economics: Constructing the Treatment Variable

## Constructing the treatment variable

Health treatments are rarely assigned by the researcher and rarely observed as a clean switch. A reform changes an insurance rule, a hospital's payment incentive, or a price, and the researcher must decide whether the treatment is the reform date, the eligibility rule it changed, the benefit it produced, or the exposure it implied. The choice determines the assumption, and the assumption determines what the paper can claim.

| Construction | What varies | Data source | Hidden assumption | When to use |
|---|---|---|---|---|
| Insurance coverage status | Whether a person is enrolled, and in which scheme, in each year | Survey insurance module, county enrollment rolls | Enrollment is not selected on health within the comparison group | Panel designs around an expansion that changed eligibility |
| Reimbursement rate and out-of-pocket share | The share of a bill paid by the patient, by county, year, and level of care | County policy documents, claims data | The rule in force is the rule actually applied to the sampled patient | Financial protection outcomes; designs that shift cost sharing |
| Medical expenditure | Total spending, out-of-pocket spending, or spending by category | Survey consumption modules, claims and hospital records | Reported spending is the price times the quantity actually consumed | Spending and financial burden outcomes |
| Health outcomes | Self-rated health, ADL and IADL limitations, chronic disease, BMI, depressive symptoms measured by CES-D | Survey health modules, physical measurements | The measure captures health status rather than reporting behavior | Any outcome in the health production function |
| Mortality and life expectancy | Death within a window, age at death, life expectancy at birth | Vital registration, disease surveillance points, census | Deaths are completely and consistently recorded across areas and years | Long-run and high-severity outcomes |
| Service utilization | Outpatient visits, admissions, length of stay, choice of facility level | Survey utilization modules, claims, hospital discharge records | A visit is the same object across facilities and years | Access designs and supply-side reforms |
| Exposure to pollution | Ambient concentration or facility proximity at the residence | Monitoring station data, satellite estimates, facility locations | Exposure measured at the monitor is exposure at the residence | Exposure-to-health designs; the regulation side is in `domains/energy-env` |

A coverage design needs the reform date to be a real eligibility change for a defined population, not merely an announcement. Report the enrollment rate before and after, and show that the take-up among the newly eligible was high enough for the reform to move coverage at the intensive margin.

A reimbursement design needs the actual schedule, not the nominal headline rate. Deductibles, ceilings, catalog restrictions, and reimbursement by level of care interact, and the effective rate faced by a patient with a given illness differs from the published rate. Where claims data exist, the realized reimbursement ratio is the better treatment.

A price design, including zero markup and centralized procurement, needs the exposure margin: which drugs and which facilities were affected, and how much of a patient's or hospital's revenue was exposed. National procurement prices are set by tender and apply to specific molecules, so the treatment is drug-specific exposure rather than a hospital-wide date.

A utilization design has to separate demand from supply. A visit is produced jointly by the patient and the provider, so a reform that changed hospital incentives changes utilization without changing need, which is exactly the identification in supply-side studies and a confounder in demand-side ones.

An exposure design needs the exposure variable to be measured where people live and to vary for reasons unrelated to health. Monitoring stations are not randomly placed, satellite estimates smooth over local variation, and facility proximity correlates with income and employment. State which of these problems the design addresses.

## Identification assumptions by definition

**Insurance coverage.** The identifying assumption is that enrollment is unrelated to unobserved health conditional on covariates, or that the reform changed eligibility for a group whose health trends would otherwise have been parallel to the comparison group. Voluntary enrollment violates this in a specific direction: sicker people enroll, so a cross-sectional comparison understates the protective effect and a before-after comparison can overstate it.

**Reimbursement and cost sharing.** Identification requires that the schedule change is not accompanied by a change in what is supplied. If a hospital responds to lower reimbursement by prescribing more or by shifting to uninsured services, the estimated effect on patient spending is a mixture of price and quantity, and the paper must report both margins or say which one it identifies.

**Expenditure.** The assumption is that reported spending reflects prices and quantities consumed rather than recall error that varies with insurance status. This is fragile when the recall window differs across survey waves and when insured patients have better records of their spending.

**Health outcomes.** Self-rated health involves a reference group: a person compares their health to those around them, so an improvement in the local environment or in the health of peers can shift the report without any change in true health. Objective measures reduce this but introduce their own problems, since ADL and chronic disease are also reported, and measured BMI requires a physical examination that some waves do not conduct.

**Mortality.** Vital registration coverage and cause-of-death coding quality differ by region and improved over time, so a decline in measured mortality can partly be a decline in under-registration. Where deaths are matched from administrative records, also report the match rate by treatment status.

**Utilization.** A visit or an admission is an equilibrium outcome of patient demand and provider response. Designs that change access identify a combined effect unless the paper can show the provider margin separately, for example with capacity or staffing data.

**Pollution exposure.** The assumption is that measured concentration is the exposure experienced and that the monitor's location is unrelated to unobserved determinants of health. Defend it with the monitor network's placement rule, with residential distance, and with a first stage on the health-relevant pollutant.

## Common construction errors

| Error | Consequence | What to do instead |
|---|---|---|
| Coding insurance as a single yes or no across a period when the scheme changed | Treated and control units change composition at the reform date and the estimate absorbs the reclassification | Build a scheme-by-year variable and show how each transition is coded |
| Using the headline reimbursement rate rather than the realized one | The treatment exaggerates generosity; effects on out-of-pocket spending are attenuated | Compute the realized ratio from claims or from the schedule including deductibles and ceilings |
| Treating a national procurement or price cut as a hospital-wide date | Exposure differs by drug mix and by facility, so the treatment is measured with error | Build drug-specific or department-specific exposure shares from pre-reform revenue |
| Comparing insured and uninsured people in a cross-section | Enrollment is selected on health and on income | Use the eligibility reform, or an instrument, or within-person change |
| Measuring health with self-rated health only, in a setting where reporting shifted | The estimate captures reporting rather than health | Report an objective measure alongside and discuss the divergence |
| Ignoring that death removes people from the panel | Survivors are selected and the panel composition changes with treatment | Report attrition and mortality by arm and estimate bounds |
