# Health Economics: how to walk the eight stages

## In one sentence

The treatment is a rule written by an insurer or a hospital regulator, not a choice made by the respondent, so fix the insurance-by-year definition before anything else.

## Stage 0 feasibility: three questions to ask first

- Can the county-level reimbursement rules and their revision dates be collected? Read `data.md` under data sources. Confirm the county documents exist for the study window before the design is fixed.
- Does the panel contain the age group the reform targets? Read `data.md` under coverage. Confirm the age and residence filters match the policy's eligible population.
- What happens to people who die or drop out between waves? Read `pitfalls.md` under where it goes wrong. Confirm the attrition and death plan before estimating anything.

## Stage 1 question and literature

- Choose the reform from `institutional.md` under institutional background, and confirm the paper's claim is about that one reform.
- Read the timeline in `institutional.md`. Confirm the reform dates in the paper match the timeline, and that no second reform lands inside the window.

## Stage 2 identification

- `measures.md` under constructing the treatment variable lists seven definitions, from insurance status through reimbursement rates to health outcomes. Confirm which one the identification claim rests on.
- Read `measures.md` under identification assumptions by definition for the chosen one. Confirm the voluntary-enrolment objection is answered in the design, not in the discussion.
- Decide whether health is measured subjectively or objectively, and read `measures.md` under variables and definitions for the consequences of each. Confirm both measures are reported.

## Stage 3 data

- `data.md` under data sources separates household panels, insurance settlement records, vital statistics and exposure data. Confirm at least one source gives the outcome and one gives the treatment, and say which is which.
- `data.md` under variables and definitions: confirm the insurance category is coded by scheme and year, not by a single indicator.
- `data.md` under known issues covers death and attrition. Confirm the paper states how these cases are handled.

## Stage 4 estimation

- Cluster at the county or the insurer, that is, the level at which the premium and benefit rules are set. Confirm the clustering level matches `pitfalls.md` under where it goes wrong.
- Report the subjective and the objective outcome side by side. Confirm the sign agrees, or explain why it does not.
- Check the reform overlap list from the timeline before interpreting any coefficient. Confirm the estimation window excludes a second reform.

## Stage 5 tables and figures

- Put the outcome definition in the table notes, naming the survey and the wave. Confirm a reader can rebuild the variable from the note.
- Report the sample flow: baseline, attrition, death, final. Confirm the numbers add up.
- Plot the outcome by cohort and wave around the reform. Confirm the pre-trend figure uses the same definition as the main table.

## Stage 6 report

- `data.md` under known issues: state the wave, the survey and the variable construction for each outcome. Confirm no version numbers appear.
- Report how the reimbursement rate was computed, since the nominal and the effective rate differ. Confirm both are reported.

## Stage 7 writing

- Use the two paragraphs in `institutional.md` under ready-to-cite paragraphs for the background section. Confirm the placeholders are replaced and the paragraph names only this reform.
- Answer the objections in `pitfalls.md` under how to respond in the limitations paragraph. Confirm each limitation is stated once.

## Stage 8 referee response

- `pitfalls.md` under what referees ask gives ten questions; treat them as the response checklist. Confirm every objection has a paragraph.
- For self-rated health, add an objective measure instead of arguing. Confirm the measure exists in the data before promising it.
- For insurance endogeneity, present the design-based variation explicitly. Confirm the first-stage argument is in the paper.

## The three things most often missed

- Deaths are treated as missing values, so the estimated effect is conditional on surviving.
- The reimbursement rate is measured as the nominal rule rather than the amount actually reimbursed.
- Variables with the same name in different waves are concatenated without checking the question text.
