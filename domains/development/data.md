# Development economics: data

## Data sources

Development data comes from three layers, and papers usually need at least two of them. The household survey gives outcomes and eligibility variables. The administrative record gives program participation and local policy parameters. The county or village yearbook gives the covariates and the geography that define the comparison group.

National household panels are the backbone. The China Family Panel Studies (CFPS) is a biennial national panel with income, consumption, health, education, and migration modules, and it includes community questionnaires that can be matched to the household file. The China Health and Nutrition Survey (CHNS) provides a longer provincial panel with detailed nutrition and health measures. The China Household Income Project (CHIP) and the China Household Finance Survey (CHFS) are widely used for income distribution, wealth, and borrowing, and each has its own wave structure and geographic coverage that must be checked before use. The Chinese General Social Survey (CGSS) is repeated cross-section rather than a panel.

Administrative and program records decide the treatment. County civil affairs records hold the minimum living standard guarantee roll and the local standard in force. Poverty registration records identify households and villages in the campaign. Provincial and county implementation notices, work reports, and budget documents date the rollout and state the allocation rule. School, clinic, and road placement can be reconstructed from education and transport yearbooks and from map layers.

Village-level surveys are the field component. Research teams collect village rosters, village finances, distance to the county seat, and lists of programs received. These data are rarely published, so the paper must document the instrument, the sampling of villages, and the field dates. A replication package should include the questionnaire, the codebook, and the anonymized village file; if it cannot, say so and describe what is available.

## Variables and definitions

| Variable | Definition | Source |
|---|---|---|
| household income per capita | Survey-reported annual household income divided by resident household size | CFPS, CHIP, CHFS |
| poverty status | Indicator that household income falls below the applicable official poverty line | Survey income plus the official line in force |
| dibao receipt | Whether the household received the minimum living standard guarantee in the reference year | Survey module and county civil affairs roll |
| local dibao standard | The monthly income standard set by the county for the reference year | County civil affairs documents |
| program participation | Whether the village or household appears on the program list for the reference year | County and provincial program records |
| village treatment status | Whether the village was selected, and in which wave | Implementation notices and work reports |
| land contract rights | Whether the household holds a registered contract certificate for its contracted plots | Land confirmation records and survey |
| land rented out | Whether any contracted land was transferred to another operator in the reference year | Survey land module |
| migration | Whether a household member worked outside the county for at least one month | CFPS, CHIP |
| children's schooling | Enrollment and grade of school-age children, plus travel time to school | Survey education module and village questionnaire |
| health insurance | Whether each member is covered by the rural cooperative or resident scheme | Survey health module |
| distance to county seat | Road distance or travel time from the village to the county government seat | Village questionnaire and GIS |
| digital financial inclusion index | County-year index of digital financial service penetration | Published index, county and year level |

## Coverage

| Data | Period | Level | Notes |
|---|---|---|---|
| CFPS | 2010 baseline, biennial | Individual and household | Community questionnaire allows village matching [verify wave list] |
| CHNS | Long provincial panel | Individual and household | Detailed nutrition and health [verify waves] |
| CHIP | Multiple waves | Household | Income-focused; verify province coverage per wave [verify] |
| CHFS | Multiple waves | Household | Wealth and finance; verify sampling frame [verify] |
| CGSS | Annual or biennial cross-sections | Individual | Repeated cross-section, not a panel [verify] |
| County statistical yearbooks | Annual | County | Fiscal, population, and agricultural variables |
| Program records | Event-specific | County, village, household | Coverage and variable names differ by program |
| Village field surveys | Study-specific | Village | Sampling and field dates must be documented |

## Known issues

- Survey income and administrative income are different constructs. The recall period, the treatment of transfers, and the treatment of agricultural self-consumption differ, so a threshold measured on one is not a threshold on the other.
- Panel attrition is not random. Migration and death remove exactly the households most affected by land and poverty policies, so report attrition by wave and by treatment status and estimate bounds.
- Village lists are revised by administrative mergers. The village that appears in one wave may not exist in the next, and merging by name is unreliable; match on codes and document every manual merge.
- Program lists are incomplete. A village may have received a program without appearing in the county list, especially for small infrastructure, so cross-check against village reports.
- The geographic identifier is often coarser than the treatment. County codes change with boundary reforms, and prefecture codes are sometimes all that is available.
- Weights and sampling frames are survey-specific. Pooling two surveys without harmonizing weights produces levels that no survey supports.
- Field data collection has its own demand effects: enumerators know the hypothesis, and respondents learn what answers are rewarded. Use blind allocation of enumerators to treatment status where the design allows.
- Ethics and data protection apply to fieldwork. Report consent procedures, the ethics approval, and how household identifiers are stored, because 《个人信息保护法》 requirements are now commonly checked at submission.
