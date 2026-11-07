# China Health and Retirement Longitudinal Study (CHARLS)

> Where this sits: stage 3 (data). A dictionary entry is usable only when five fields are filled: unit of observation, coverage (years and regions), the key variables with their exact definitions, the access route, and the known defects. Anything still marked `[待核实]` / `[verify]` is a question for the person who owns the data, not a fact you may quote.

## Basic information

| Item | Detail |
|---|---|
| Full name (Chinese) | 中国健康与养老追踪调查 |
| Full name (English) | China Health and Retirement Longitudinal Study |
| Abbreviation | CHARLS |
| Maintainer | National School of Development (NSD), Peking University; fieldwork by the Institute of Social Science Survey (ISSS) |
| First wave | 2011 national baseline; a pilot was run in 2008 in two provinces |
| Frequency | Every two to three years |
| Unit of observation | Individual, household, community |

## Variables

| Variable name | Chinese name | Meaning and definition | Typical values |
|---|---|---|---|
| `ID` | 个人标识 | Permanent individual identifier; the key for following the same person across waves | Unique alphanumeric code, stable across waves |
| `householdID` | 家庭标识 | Household identifier; links members to the household record in the same wave | Unique code, wave-specific |
| `communityID` | 社区标识 | Village or urban community identifier; the primary sampling unit | Unique code |
| `wave` | 调查轮次 | Survey wave, often stored as the survey year | 2011, 2013, 2015, 2018, 2020 |
| `province` | 省份 | Province of residence | GB/T 2260 province code [verify] |
| `urban_nbs` | 城乡标识 | Urban or rural classification based on the NBS urban-rural division | 1 = urban, 0 = rural [verify] |
| `gender` | 性别 | Sex of the respondent | Male / Female, coded 1/2 in most waves [verify] |
| `birthyear` | 出生年 | Year of birth, used to compute age and to define the 45+ eligibility | Four-digit year |
| `education` | 受教育程度 | Highest level of education completed | Categorical, roughly 1 to 11 depending on the wave [verify] |
| `hukou` | 户口类型 | Agricultural versus non-agricultural household registration | Categorical (agricultural / non-agricultural / unified residence) [verify] |
| `adl` | 日常生活活动能力 | Number of activity-of-daily-living limitations reported | Count, typically 0 to 6 [verify] |
| `cesd` | 抑郁量表得分 | CES-D 10 score constructed from the mental health module | Ordinal score; check the wave-specific range [verify] |

Names above follow the harmonised files distributed with the survey. Raw module files carry item numbers from the questionnaire, so confirm the construct against the wave codebook. Health, cognition and biomarker variables are the most sensitive to wave-specific naming.

## Known issues

- Age eligibility. The sample targets residents aged 45 and over (spouses are included regardless of age) [verify], so it is not representative of younger adults. Results on education or early-career outcomes cannot be generalised to the whole adult population.
- Attrition and death. Loss to follow-up is highest among the oldest-old and the least healthy. Deaths are recorded in a separate exit file; treating the deceased as attrited biases health and income outcomes, so merge the exit file before building the panel.
- Biomarker modules. Blood samples, anthropometry and physical measurements are collected in a subsample and not in every wave; response rates for the blood module are below the main survey rate, which reintroduces selection.
- Proxy interviews. For respondents unable to answer, a proxy reports on their behalf. Proxy shares rise with age and correlate with the very health outcomes being studied.
- Questionnaire changes. The 2018 wave restructured several modules and introduced new scales, so variable names and category codes shift across waves; a cross-wave variable has to be checked item by item.
- Household aggregation. Income and consumption are measured at the household level; individual-level analysis needs an allocation rule, commonly per-capita or an equivalence scale.
- Geographic identifiers. Province and county are released, while village identifiers require an additional application [verify]. The 2008 pilot covered only two provinces and is not comparable with the national baseline.
- Measurement error in self-reports. Self-reported chronic disease and healthcare use are known to under-report conditions that have not been diagnosed, which attenuates effects estimated from these outcomes.

## Access

| Item | Detail |
|---|---|
| Entry type | Online application for academic use; free of charge |
| Channel | CHARLS project team at the National School of Development (NSD), Peking University, through the ISSS data platform |
| Institutional account | Registration required; applications from institutional email addresses are processed faster [verify] |
| Cost | Free for academic use |
| Ethics review | The survey holds ethics approval; whether users need their own IRB review depends on their institution |
| Usage agreement | No redistribution to third parties, no commercial use, cite the data source and acknowledge the survey; some modules require a separate application and agreement |
