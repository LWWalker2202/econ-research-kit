# Behavioral and experimental economics: how to walk the eight stages

## In one sentence

The institution here is the research infrastructure, which subject pool, which platform, which ethics process, and the treatment is assigned by the designer rather than observed in the world.

## Stage 0 feasibility: three questions to ask first

- Can the chosen pool support the design, group interaction in a lab or a wide panel online? Read `institutional.md` under institutional background on the three pools. Confirm the pool supports the task before the design is written.
- Can the ethics committee review the design in time for the field or lab schedule? Read `institutional.md` under ready-to-cite paragraphs. Confirm the committee and the submission window.
- Is the budget large enough for the sample the power calculation needs? Read `pitfalls.md` under what referees ask, which opens with the minimum detectable effect. Confirm the budget covers a pilot and a main sample.

## Stage 1 question and literature

- Choose the paradigm from `institutional.md`: public goods, auctions, time preference, risk, or labor supply. Confirm the implementation follows the convention referees compare it to.
- Confirm the question is about a mechanism, not an average effect that a survey could estimate more cheaply.

## Stage 2 identification

- `measures.md` under constructing the treatment variable lists four ways to build a manipulation. Confirm the manipulation is between subjects wherever the treatment can contaminate later decisions.
- Read `measures.md` under identification assumptions by definition for the design chosen. Confirm the identification claim names the assumption, not just the estimator.
- Plan the manipulation check in `measures.md`. Confirm the check comes after the outcome variable, and that the order is in the preregistration rather than only in the code.

## Stage 3 data

- `data.md` under data sources covers the lab, the domestic platforms and the international platforms. Confirm the platform's screening, attention and quality features are recorded in the paper.
- `data.md` under known issues discusses panel composition and translation. Confirm the recruitment window, the filters and the translation procedure are documented.

## Stage 4 estimation

- `pitfalls.md` question 1 asks for the minimum detectable effect. Confirm the design is powered for the effect size in the literature, or say plainly that it is not.
- Cluster at the session or matching group. Confirm the clustering unit equals the unit of assignment, and report the number of clusters.
- Report the intention-to-treat estimate on the full sample first. Confirm the secondary analysis of subjects who passed the check is labeled as secondary.

## Stage 5 tables and figures

- Put the manipulation check and the balance table in the first two tables. Confirm both are in the main text rather than the appendix.
- `pitfalls.md` under where it goes wrong mentions outcome families. Confirm every outcome measured appears in at least one appendix table.
- Report payout distributions. Confirm the amounts and the exchange rate are in the note, not only in the instructions.

## Stage 6 report

- Archive instructions, stimuli, code and preregistration. `data.md` under data sources names the repository to use.
- Confirm the archive is deposited before submission, not after acceptance.

## Stage 7 writing

- Use `institutional.md` under ready-to-cite paragraphs for the design section. Confirm the placeholders are replaced and the paragraph describes this study, not a generic one.
- Write the deviation-from-preregistration paragraph early. Confirm it names the dates and says whether the change came before or after the data were seen.

## Stage 8 referee response

- `pitfalls.md` under what referees ask has ten questions. Confirm the response letter answers each in one paragraph with a table or appendix reference.
- For demand effects, add a condition rather than an argument. Confirm the condition is feasible within the schedule.
- For external validity, report the sample description and a replication on a wider panel. Confirm the replication exists before it is promised.

## The three things most often missed

- The manipulation check runs before the outcome, so part of the treatment effect is priming.
- Power is computed for an effect larger than the design can detect, and the confidence interval still contains the claimed size.
- Deviations from the preregistration are disclosed only when a referee finds them.
