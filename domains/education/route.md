# Education economics: how to walk the eight stages

## In one sentence

Most designs here are cohorts crossed with places, so the whole paper turns on dating a reform to the grade a respondent was in, in the county where that respondent went to school.

## Stage 0 feasibility: three questions to ask first

- Can the reform's local start year be recovered county by county? Read `measures.md` under constructing the treatment variable. Confirm the county-level documents exist before the design is fixed.
- Did the respondents migrate for school or for work? Read `measures.md` under identification assumptions by definition. Confirm the exposure is assigned where schooling happened, not where the survey took place.
- Are test scores or attainment measured the same way across the waves used? Read `measures.md` under common construction errors. Confirm the comparability problem before proposing a test-score outcome.

## Stage 1 question and literature

- Choose the reform from `institutional.md` under institutional background, and confirm the paper's claim is about that reform rather than about education in general.
- Read the timeline in `institutional.md`. Confirm the reform dates used in the analysis match it, and that no second reform hits the same cohort.

## Stage 2 identification

- `measures.md` under constructing the treatment variable lists five exposures: college expansion, consolidation, fee removal, years of schooling, and class size. Confirm which one the paper uses, and why the others are less suited to the question.
- Read `measures.md` under identification assumptions by definition for that one. Confirm the assumption is written before the estimate.
- Decide how schooling is measured: years, stage-specific years or degree dummies. Read `measures.md` for what each changes about the estimate. Confirm the choice is stated and defended.

## Stage 3 data

- `data.md` under data sources names the censuses, the household panels and the education statistics. Confirm which source gives the cohort and which gives the county exposure.
- `data.md` under coverage: confirm the survey covers the cohorts born on both sides of the reform.
- `data.md` under known issues: confirm what is known about migration and about self-reported schooling.

## Stage 4 estimation

- Cluster at the province or the county, that is, where the reform varied. Confirm the level matches `pitfalls.md` under where it goes wrong.
- If class size is the treatment, do not control for school fixed effects and claim the effect is causal. Confirm the variation used is within school or across cohorts, and say which.
- Report results with stage-specific returns and with a vocational indicator. Confirm the split is shown rather than described.

## Stage 5 tables and figures

- Put the reform year and the cohort window in the table notes. Confirm a reader can rebuild the treated cohort from the note.
- Plot attainment by cohort and province around the reform. Confirm the pre-trend figure uses the same definitions as the main table.
- Show the class-size or teacher-ratio distribution before using it as a treatment. Confirm the measure is not heaped and that the heaping is discussed.

## Stage 6 report

- `data.md` under known issues: state the schooling mapping and the cohort definition per table. Confirm no version numbers appear.
- Report the exposure construction in an appendix, county by county. Confirm a coauthor can rebuild it.

## Stage 7 writing

- Use the paragraphs in `institutional.md` under ready-to-cite paragraphs for the background section. Confirm the placeholders are replaced.

## Stage 8 referee response

- `pitfalls.md` under what referees ask gives the checklist. Confirm each question has a reply, especially the ability and family-background one.
- If a referee asks for a different schooling measure, report the years, the stage-specific years and the degree dummies together. Confirm the sign is stable.
- For class-size endogeneity, show the sorting test. Confirm the test is in the paper rather than promised.

## The three things most often missed

- The reform is dated to the survey year rather than to the grade the respondent was in when it happened.
- Consolidation exposure is built from the resident population of the county, which mixes consolidation with migration.
- Test scores from different waves are compared without equating, so measurement change is read as learning change.
