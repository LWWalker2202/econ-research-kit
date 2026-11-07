# Development economics: how to walk the eight stages

## In one sentence
In development work the paper is judged by how the intervention reached households, whether the comparison group is credible, and whether the data survive scrutiny.

## Stage 0 feasibility: three questions to ask first
- Find how the list was made. Read "Institutional background" in `institutional.md` and ask which rule and which office produced the eligibility list; that decides whether a threshold design exists.
- Check the data first. Read "Coverage" in `data.md` and confirm the surveys cover your counties and years, and whether village questionnaires or programme records fill the gaps (to confirm against the official codebook).
- Settle the counterfactual. If the only comparison is programme villages versus the rest of the county, read the second "What referees ask" item in `pitfalls.md`.

## Stage 1 question and literature
- Read "Timeline" in `institutional.md`; make sure the policy you name is not two programmes with different rules and start years.
- Read "Constructing the treatment variable" in `measures.md` and pick the construction your question uses: administrative eligibility, project exposure, rollout timing, or distance and access.
- Check that the strategy in the paper you follow can be rebuilt with your data: a threshold design needs the threshold measured as the administration measured it.

## Stage 2 identification
- For administrative eligibility, read "Identification assumptions by definition" in `measures.md` and confirm the same rule was applied in the counties you compare.
- For rollout timing, justify that batch assignment is unrelated to outcome trends and cite the document that set the batches in "Sources".
- For distance and access, confirm distance acts only through the service or the market, not through terrain and infrastructure.

## Stage 3 data
- Read "Data sources" in `data.md`: surveys, county yearbooks, and programme records answer different questions; a usable paper combines at least two.
- Read "Variables and definitions": survey income and the administrative poverty line are different constructs and cannot be spliced inside one exposure measure.
- Read "Known issues" and map each entry to a variable in your table, particularly attrition and the income construct.

## Stage 4 estimation
- When treatment is assigned by village and the outcome is at household level, cluster at the assignment level; "Common construction errors" in `measures.md` shows why.
- Before using realized programme spending as exposure, check that spending is not allocated on the outcome.
- Report the main estimate under two treatment definitions and show whether the sign survives.

## Stage 5 tables and figures
- Build the balance table around `pitfalls.md`'s two questions: how the list was made and whether the comparison group is credible.
- The event-study figure must show the pre-period; state the base period and treatment date in the note.
- Report the number of clusters and treated units so the reader can judge statistical power.

## Stage 6 report
- Report how the list was produced and how far implementation departed from it, following the first "How to respond" item.
- Report attrition and replacement, and whether leaving the sample is related to treatment.
- Report the other interventions active in the window, such as infrastructure, credit, and work teams.

## Stage 7 writing
- Start from the "Ready-to-cite paragraphs" in `institutional.md`, then check every date.
- Cite documents and issuing bodies only; leave page and document numbers for (to confirm against the official codebook).

## Stage 8 referee response
- Work through the ten "What referees ask" items before submission; clustering, external validity, and spillovers come back most often.
- When asked whether the result generalises, answer with "Coverage" in `data.md` rather than with an assertion.

## The three things most often missed
- Treating a programme list as random assignment.
- Replacing the administrative eligibility line with survey income.
- Ignoring the other interventions that ran alongside the programme.
