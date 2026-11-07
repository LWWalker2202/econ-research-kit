# China Family Panel Studies (CFPS)

> Where this sits: stage 3 (data). A dictionary entry is usable only when five fields are filled: unit of observation, coverage (years and regions), the key variables with their exact definitions, the access route, and the known defects. Anything still marked `[待核实]` / `[verify]` is a question for the person who owns the data, not a fact you may quote.

## Basic information

| Item | Detail |
|---|---|
| Full name (Chinese) | 中国家庭追踪调查 |
| Full name (English) | China Family Panel Studies |
| Abbreviation | CFPS |
| Maintainer | Institute of Social Science Survey (ISSS), Peking University |
| First wave | 2010 baseline |
| Frequency | Biennial follow-up |
| Unit of observation | Individual, household, community |

## Variables

| Variable name | Chinese name | Meaning and definition | Typical values |
|---|---|---|---|
| `pid` | 个人标识 | Permanent individual identifier; the key for following the same person across waves | Unique numeric code, stable across waves |
| `fid` | 家庭标识 | Household identifier; each household record in a wave has one | Unique numeric code, wave-specific |
| `cid` | 社区标识 | Community or village identifier; the sampling unit below county | Unique numeric code |
| `wave` | 调查轮次 | Survey wave, usually stored as the survey year | 2010, 2012, 2014, 2016, 2018, 2020, 2022 |
| `provcd` | 省份代码 | Province in which the household is located | GB/T 2260 code; 2-digit or 6-digit depending on the file [verify] |
| `urban` | 城乡标识 | Urban or rural classification of the community, based on the NBS urban-rural division | 1 = urban, 0 = rural (confirm in the codebook) |
| `cfps_gender` | 性别 | Sex of the respondent; some wave files store the same concept as `gender` | Male / Female |
| `age` | 年龄 | Age in the survey year; can be recomputed from birth year | Integer years |
| `eduy` | 受教育年限 | Completed years of schooling, constructed from the education module | Integer years, roughly 0 to 22 [verify] |
| `fincome` | 家庭收入 | Household income in the survey year; total or net depending on the wave | Continuous, in RMB; deflate with a provincial CPI |

The names above follow the harmonised cross-wave files. Raw wave files also carry questionnaire construct names, so confirm the exact name against the codebook of the wave you use. Do not merge waves by variable name alone.

## Known issues

- Attrition is non-random. Households that move, the oldest respondents and some urban households drop out at higher rates, so the unbalanced panel is not missing at random. Report wave-specific response rates [to fill] and show that results survive reweighting or a balanced subsample.
- Household identifiers are wave-specific and household composition changes through splits, mergers, deaths and new members. Using `fid` as a panel identifier without the family relationship file silently assigns a new household to the old one.
- The same concept can carry a different construct name or recoded categories across waves. A cross-wave variable has to be built wave by wave, not merged by name; education and income are the usual casualties.
- Several modules are fielded only in selected waves, for example the detailed mental health and subjective wellbeing scales. These outcomes cannot be used in a balanced multi-wave panel.
- Income and consumption are collected at the household level, and their components differ by wave. Individual-level income requires an allocation rule that should be stated in the paper.
- The sample design was revised after the baseline, and supplementary samples were added in later waves [verify]. Weights from a single wave cannot be applied to a pooled multi-wave sample.
- Geographic detail is limited in the public release: province is available, while county and village identifiers need an additional application for some waves [verify]. Designs that need county-level treatment therefore need a separate access step.

## Access

| Item | Detail |
|---|---|
| Entry type | Application for academic use; free of charge |
| Channel | Data platform of the Institute of Social Science Survey (ISSS), Peking University |
| Institutional account | Not required, but registration and a stated research purpose are required [verify] |
| Cost | Free for academic use |
| Ethics review | The survey itself holds ethics approval; whether users need their own IRB review depends on their institution |
| Usage agreement | No redistribution to third parties, no commercial use, and publications must cite the data source and acknowledge the survey |
