# Labor economics: how to walk the eight stages

## In one sentence

The treatment is a statutory floor, an eligibility threshold or a reform cohort rather than a program dummy, so the definition of the exposure is the identification.

## Stage 0 feasibility: three questions to ask first

- Can the statutory levels be matched to the sample at the right date and place? Read `measures.md` under constructing the treatment variable. Confirm the province-year-month panel of floors exists for the whole window.
- Does the survey measure age or birth date finely enough for the design? Read `measures.md` under identification assumptions by definition. Confirm the running variable is precise enough for the bandwidth before proposing a discontinuity design.
- Can workers be linked to firms on a unique identifier? Read `measures.md` under common construction errors. Confirm the identifier exists, since matching on names fails in a way that biases the sample.

## Stage 1 question and literature

- Choose the institution from `institutional.md` under institutional background, and confirm the paper is about that rule rather than the survey wave.
- Read the timeline in `institutional.md`. Confirm no second labor regulation takes effect inside the window.

## Stage 2 identification

- `measures.md` under constructing the treatment variable lists four definitions: minimum-wage exposure, retirement eligibility, reform cohorts and hukou status. Confirm which one carries the paper.
- Read `measures.md` under identification assumptions by definition for that one. Confirm the assumption is stated in the design section.
- Check the measure against the outcome concept. Confirm the wage concept and the exposure concept refer to the same population.

## Stage 3 data

- `data.md` under data sources lists the yearbooks and the household and census sources. Confirm which one supplies the statutory levels and which supplies the outcomes.
- `data.md` under coverage: confirm the panel spans the reform and covers the provinces with variation.
- `data.md` under known issues: confirm the income concept is consistent across waves, and say which waves change it.

## Stage 4 estimation

- Cluster at the level where the rule varies, usually the province. Confirm this matches `pitfalls.md` under where it goes wrong.
- If the outcome is wages and employment also responds, report the employment effect and bound the wage effect. Confirm both appear.
- Deflate with the price index at the level of the treatment variation. Confirm the deflator is not national while the treatment is provincial.

## Stage 5 tables and figures

- Report the exposure definition and the income concept in the table notes. Confirm a reader can rebuild both from the note plus the appendix.
- Show the first stage or the discontinuity plot before the main table. Confirm the plot uses the same bandwidth as the estimate.
- Report results by degree or by cohort group. Confirm the heterogeneous table does not silently restrict the sample.

## Stage 6 report

- `data.md` under known issues: state the survey wave, the income concept and the deflator used for each table. Confirm no version numbers appear.
- Report the sample restriction that follows from the treatment definition. Confirm it is stated in one sentence, not implied.

## Stage 7 writing

- Use the paragraphs in `institutional.md` under ready-to-cite paragraphs for the background. Confirm the placeholders are replaced.
- Use `pitfalls.md` under how to respond to write the threats paragraph. Confirm each threat appears with its test.

## Stage 8 referee response

- `pitfalls.md` under what referees ask is the checklist. Confirm every question has a reply, including the composition-of-the-sample one.
- For selection into employment, present a bound or a model rather than a robustness table with a different sample. Confirm the bound is reported.
- For measurement of statutory levels, cite the revision date used for each province-year. Confirm the dates are in an appendix table.

## The three things most often missed

- Wages are deflated with a national price index while the treatment varies by province.
- The wage equation conditions on employment, so the estimate is a selection-contaminated return.
- Only birth year is observed, so the running variable is too coarse for the discontinuity design that the paper claims.
