# Health Economics: Data

## Data sources

Health data in China comes from four layers: population-based panel surveys, administrative insurance records, facility and vital statistics, and environmental exposure data. A credible paper usually combines at least two, because the survey measures the person while the administrative records measure the treatment.

The panel surveys are the main source of individual outcomes. The China Health and Retirement Longitudinal Study (CHARLS) covers people aged 45 and older and collects health, cognition, insurance, and expenditure along with physical measurements. The China Family Panel Studies (CFPS) covers all ages, is biennial, and has a detailed health and insurance module. The China Health and Nutrition Survey (CHNS) is a long provincial panel with detailed nutrition, anthropometry, and biomarkers. The Chinese Longitudinal Healthy Longevity Survey (CLHLS) focuses on the oldest old and is the standard source for mortality and longevity outcomes at advanced ages.

Administrative data carry the treatment and sometimes the outcome. County medical insurance bureaus hold enrollment records and reimbursement schedules; claims data record what was spent and reimbursed; hospital discharge records and case-based payment records describe admissions. The China Health Statistical Yearbook provides province-level beds, personnel, outpatient and inpatient volumes, and average medical costs per visit and per admission, which are enough to control for supply-side capacity but not to construct patient-level treatments.

Vital statistics and censuses provide mortality context. Disease surveillance point data report deaths by cause for selected counties, the census gives age structure and crude death rates, and the national mortality registration system became more complete over the period. For exposure, monitor-based and satellite-based pollution estimates can be matched to residence at the county or gridded level; the construction and identification issues on the regulation side are in `domains/energy-env`, and this file covers only the exposure-to-health path.

## Variables and definitions

| Variable | Definition | Source |
|---|---|---|
| insurance scheme | The scheme covering the respondent in the reference year, coded by scheme type | CFPS, CHARLS, county enrollment records |
| enrollment status | Whether the respondent was covered by any scheme in the reference year | Survey insurance module |
| reimbursement rate | The share of covered medical spending reimbursed, realized rather than nominal | Claims data, county schedule |
| out-of-pocket spending | Medical spending paid by the household, total and by service type | Survey consumption module, claims |
| total medical spending | Household medical spending including reimbursed components | Survey and claims combined |
| self-rated health | Five-point self-assessment of general health | CFPS, CHARLS, CLHLS |
| ADL and IADL | Number of activities of daily living and instrumental activities with limitations | CHARLS, CLHLS |
| chronic disease | Whether a doctor diagnosed a chronic condition, by condition | CFPS, CHARLS, CHNS |
| BMI | Weight in kilograms divided by squared height in meters, from measured anthropometry | CHNS, CHARLS |
| CES-D score | Depressive symptom score from the CES-D instrument | CHARLS, CFPS [verify module] |
| outpatient visits | Number of outpatient visits in the reference period | Survey utilization module, claims |
| hospitalization | Whether the respondent was admitted and the number of admissions | Survey, hospital records |
| death | Whether the respondent died in the interval, with date of death | Follow-up waves, vital registration |
| pollution exposure | Annual mean concentration of the relevant pollutant at the residence | Monitoring stations, satellite estimates |

## Coverage

| Data | Period | Level | Notes |
|---|---|---|---|
| CHARLS | National panel from the 2010s | Individual, household, community | Age 45 and older; physical measurements [verify waves] |
| CFPS | Biennial national panel | Individual, household, community | All ages; health and insurance modules [verify waves] |
| CHNS | Long provincial panel | Individual, household | Anthropometry and biomarkers [verify waves] |
| CLHLS | Repeated waves of oldest old | Individual | Focus on ages 65 and above; mortality follow-up [verify waves] |
| China Health Statistical Yearbook | Annual | Province | Beds, personnel, volumes, average costs |
| Claims and discharge data | Event-specific | Individual, facility | Access usually requires local agreement |
| Disease surveillance points | Annual | County | Cause-specific mortality; coverage improved over time [verify] |
| Census and intercensal surveys | Every ten years plus samples | Province, county | Age structure and mortality denominators |

## Known issues

- Death is not a missing value. Respondents who die leave the panel, and because death is correlated with the treatment in exactly the designs that matter, the survivor sample is selected. Report mortality and attrition by treatment arm and estimate bounds.
- Attrition in the health modules is larger than in the income modules, and it is larger for the sick and the old. Compare the baseline characteristics of attriters with those who remain, and report the balance by treatment status.
- Insurance coding changes with each survey wave because the schemes themselves merged. A variable named as the same thing across waves may not be, so construct the scheme variable from the raw question wording in each wave.
- Reported expenditure is subject to recall error, and the recall window differs across surveys. Reimbursed spending may be recalled better than out-of-pocket spending, or the reverse, so the direction of the bias must be argued rather than assumed.
- Self-reported chronic disease reflects diagnosis as well as disease. Where insurance expanded access, diagnosis rates rise for reasons that have nothing to do with incidence, which is a real effect on a different margin and should not be called a health improvement.
- Physical measurements are available only in some waves and for some subsamples. Analyses that condition on measured BMI or blood pressure silently drop the respondents who were not examined.
- Facility-level data cover hospitals that report, and reporting thresholds change. Time-series comparisons of admission volumes must check the reporting panel.
- Pollution monitors are unevenly distributed and are placed in urban areas. Satellite estimates fill the grid but are noisy, and neither is measured at the household.
- Linking surveys to administrative insurance records requires identifiers that are usually removed from public releases. Where the study has a linked file, describe the match rate and the loss by treatment status.
