# Labor economics: data sources

The Chinese labor literature draws on a small set of surveys plus the census. Each was designed for a different purpose, and most refereeing problems in this field start with using a dataset outside the margin it was built for: a household income survey to measure hourly wages, a retirement survey to study prime-age employment, or a repeated cross-section to make a panel claim. This file maps each source to what it measures well and what it does not measure at all.

## Data sources

**China Household Income Project (CHIP, 中国住户收入调查).** Repeated cross-sections with waves in 1988, 1995, 2002, 2007, 2013, and 2018 (to confirm against the official codebook), covering urban households, rural households, and migrants as separate samples. It has the most detailed income components of any public Chinese survey and a long span, which makes it the standard source for wage structure and inequality over time. It is not a panel, and the wave spacing is irregular.

**China Family Panel Studies (CFPS, 中国家庭追踪调查).** A longitudinal survey starting in 2010 with biennial follow-ups (to confirm against the official codebook), covering individuals, households, and communities. It carries the hukou and migration modules and a full employment and wage block, so it supports panel designs on labor mobility and on the returns to education. Wage questions have changed across waves, and province-by-year cells are thin.

**China Health and Retirement Longitudinal Study (CHARLS, 中国健康与养老追踪调查).** A biennial survey starting in 2011 that samples people aged 45 and above (to confirm against the official codebook), with rich retirement, pension, health, and consumption modules. It is the workhorse for retirement designs and for health-labor interactions. It is not representative of prime-age workers, so employment and wage levels estimated on CHARLS cannot be read as national labor-market statistics.

**Chinese General Social Survey (CGSS, 中国综合社会调查).** A repeated cross-section run annually to 2008 and irregularly afterwards (to confirm against the official codebook). It covers occupation, industry, income, hukou, and attitudes. It is useful for cross-sectional wage gaps and for validating the distribution of occupation and industry codes, but it has no panel structure and its income variable is a broad category rather than a wage.

**China Labor-force Dynamics Survey (CLDS, 中国劳动力动态调查).** A labor-force oriented survey starting in 2012 (to confirm against the official codebook), with household rosters, job characteristics, employment status, and migration histories. It is the best public source on informal employment and job quality, at the cost of a shorter time span than CHIP or CFPS.

**Population Census and 1% population sample surveys (全国人口普查与 1% 人口抽样调查).** Census rounds and the 1% sample surveys between them. Coverage is national and near-universal, with occupation, industry, education, hukou, and migration for every person enumerated work, but there is no wage information. Their role in labor research is to supply denominators, migration flows, and reweighting targets, not outcome variables.

**Urban Household Survey (UHS, 城镇住户调查).** An annual survey of urban registered households with detailed income and expenditure, organised by the National Bureau of Statistics. It excludes most migrants and covers registered urban residents, so it is a good source for urban wage structure before the 2010s and a misleading source for anything involving migration. It was integrated into the national household survey after 2013 (to confirm against the official codebook).

## Variables and definitions

The table gives the variable name as it appears in most public codebooks; confirm the exact name in the wave you use, because naming conventions change between waves.

| Concept | Typical public variable name | What to confirm |
| Person identifier | pid or ID | Whether the identifier is stable across waves (to confirm against the official codebook) |
| Household identifier | fid or householdID | Whether household composition is measured at the same time as income |
| Province | provcd or province | Whether codes are harmonised across waves |
| Hukou | hukou or hukou status | Agricultural versus non-agricultural, and local versus non-local |
| Education | edu or highest degree | Degree categories versus years of schooling |
| Wage | wage or income | Reference period and whether bonuses are included |
| Employment | employ or work status | Reference week versus reference year |
| Industry | industry code | Classification vintage and digit level |

## Coverage

| Dataset | Years | Level | Sample magnitude |
| CHIP | 1988 to 2018, six waves (to confirm against the official codebook) | Household and individual | Tens of thousands of households per wave |
| CFPS | 2010 onward, biennial (to confirm against the official codebook) | Individual, household, community | About ten thousand households (to confirm against the official codebook) |
| CHARLS | 2011 onward, biennial (to confirm against the official codebook) | Individual, household, community | About ten thousand households, age 45 and above (to confirm against the official codebook) |
| CGSS | 2003 onward, irregular (to confirm against the official codebook) | Individual | About ten thousand individuals per wave (to confirm against the official codebook) |
| CLDS | 2012 onward (to confirm against the official codebook) | Individual, household | About ten thousand households (to confirm against the official codebook) |
| Census and 1% sample surveys | Census rounds and the years between (to confirm against the official codebook) | Person and household | National; the 1% samples contain millions of records (to confirm against the official codebook) |
| UHS | Annual (to confirm against the official codebook) | Household and individual | Tens of thousands of urban households (to confirm against the official codebook) |

## Known issues

1. Earnings are top-coded and rounded. Heaping at round monthly figures distorts the upper tail and makes quantile estimates fragile.
2. The income concept changes between waves: the reference period, whether bonuses and in-kind payments are included, and whether net or gross income is asked all move. Compare questionnaires wave by wave before pooling.
3. Self-employment income and farm income are not wages, but they enter total income. Mixing them into the dependent variable changes the estimated returns to education.
4. Hukou status and migration status are measured at the survey date, so both are outcomes of the migration decision. Any design that uses them as a control has to explain why they are predetermined.
5. Recall periods differ across waves and across income components, which can create apparent wage changes that are survey artefacts.
6. Longitudinal surveys suffer attrition and refreshment. Attrition is correlated with migration and with job loss, exactly the outcomes labor papers study, so report inverse-probability weights and a bounding exercise.
7. The 1% population sample surveys carry no earnings variable, and occupation and industry are self-reported at a coarse level. Use them to construct denominators and reweighting targets, not to estimate wage equations.
8. The UHS covers registered urban households and excludes most migrants. A migration paper that uses the UHS without acknowledging this is estimating the wage gap only among those already registered in the city.
