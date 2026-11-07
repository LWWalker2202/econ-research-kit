# Education economics: data sources

Education data in China come in two layers. Surveys describe individuals and families but rely on self-reported schooling, while administrative statistics describe schools and counties but cannot be linked to individual outcomes without a matching key. Most credible work uses one layer to build the treatment and the other to check it. This file lists the sources, the variables with their original names, the coverage each source offers, and the problems that recur.

## Data sources

**China Family Panel Studies (CFPS).** A nationally representative longitudinal survey of individuals and households, with detailed education histories, school type, and cognitive and non-cognitive assessments. Its panel structure makes it the main source for tracking cohorts through schooling transitions.

**China Household Income Project (CHIP).** Repeated cross-sections with detailed income, education, and employment modules, widely used for returns to education and inequality because the income measurement is unusually careful.

**Chinese General Social Survey (CGSS).** Repeated cross-sections on social attitudes with a standard education and occupation module. Better for attitudes and status attainment than for schooling histories.

**China Health and Nutrition Survey (CHNS).** Panel survey with individual education, health, and nutrition, covering a fixed set of provinces. Useful where education and health outcomes must be observed together, but the geographic coverage limits national claims.

**Population census and the one percent sample.** Decennial censuses and the inter-census one percent surveys provide large samples with education, occupation, and migration, at the cost of coarse schooling categories and no test or school information.

**China Education Statistics Yearbook.** Annual school, enrollment, teacher, and finance statistics by province and county. This is the standard source for constructing county-level treatment intensity and for school-resource measures.

**County education finance data.** Per-student expenditure and budget documents published by county finance and education bureaus. Coverage is uneven, but it is the only source that separates recurrent from capital spending.

**School records and assessment data.** Student registers and standardized test scores held by education bureaus or by survey projects; access is restricted and the sampling frame must be documented. (to confirm against the official codebook)

## Variables and definitions

| Variable (original name) | Chinese name | Definition | Typical values |
|---|---|---|---|
| highest education completed | 最高学历 | Highest level of schooling completed, categorical | Primary to tertiary |
| years of schooling | 受教育年限 | Years-equivalent of schooling completed | 0 to about 19 |
| school type | 学校类型 | Academic, vocational, or other track of the current or last school | Categorical |
| enrollment status | 在学状态 | Whether currently enrolled in school | Binary |
| grade | 年级 | Current grade, used to time a reform | 1 to 12 plus tertiary |
| school location | 学校所在地 | County or township of the school, and whether boarding | Categorical |
| class size | 班级人数 | Students in the respondent's class | Count, heaped at multiples of five |
| pupil-teacher ratio | 生师比 | Students divided by teachers, school or county level | Continuous |
| per-student expenditure | 生均教育经费 | Recurrent education spending per enrolled student | Yuan, real |
| test score | 考试成绩 | Standardized score on a survey or administrative assessment | Standardized |
| college entrance examination participation | 是否参加高考 | Whether the respondent sat the national examination | Binary |
| birth year and county | 出生年份与县 | Cohort and location identifiers for treatment assignment | Year, county code |

## Coverage

| Data | Years | Level | Sample size order |
|---|---|---|---|
| China Family Panel Studies | Multi-wave panel | Individual and household | About the ten-thousand-household level (to confirm against the official codebook) |
| China Household Income Project | Repeated rounds | Individual and household | About the ten-thousand-household level (to confirm against the official codebook) |
| Chinese General Social Survey | Repeated rounds | Individual | About the ten-thousand level per round (to confirm against the official codebook) |
| China Health and Nutrition Survey | Multi-wave panel, fixed provinces | Individual and household | About the thousand-household level per province (to confirm against the official codebook) |
| Population census and one percent sample | Decennial and inter-census | Individual, full or sampled population | Millions in the census, about the one-percent sample |
| China Education Statistics Yearbook | Annual | Province, county, and school | Universe of schools |
| County education finance data | Annual, coverage uneven | County | Varies by province (to be read off the project's own sample) |

## Known issues

1. Self-reported years of schooling are heaped on multiples of three and six, and respondents often report the nominal rather than the actual years completed.
2. Education categories changed across census and survey waves, so a variable built from one wave may not be comparable with the next without a crosswalk.
3. Vocational and academic degrees at the same nominal level are reported inconsistently, and surveys rarely record the track of the completed degree.
4. County-level school statistics are reported by the education bureau and are revised after publication; the same series can differ across yearbook volumes.
5. Per-student expenditure figures mix budgets and final accounts, and teacher salary arrears are not visible in the published totals.
6. Survey weights and sampling frames differ across the major surveys, so levels of enrollment and attainment are not comparable across sources without adjustment.
7. Test scores from different assessments, and from different years of the same assessment, are not comparable without equating, and the equating is often undocumented.
8. Administrative school records are available for selected counties only, so any study using them must argue that the selection of counties is unrelated to the treatment.
