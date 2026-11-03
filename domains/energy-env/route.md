# Energy and environmental economics: how to walk the eight stages

## In one sentence

Identification in this field rests on regulation that lands unevenly across space and time, so fix the spatial unit of exposure before choosing a model.

## Stage 0 feasibility: three questions to ask first

- Can the regulated units be identified at the level the design needs, firm or county or station? Read `data.md` under data sources. Confirm the permit registry or the emission reporting system covers the years in question.
- Which other policies hit the same units in the same window? Read `institutional.md` under institutional background. Confirm the overlap list exists before the design is fixed.
- Is the spatial unit of exposure the same as the spatial unit of the outcome? Read `measures.md` under common construction errors. Confirm both units in one sentence in the design memo.

## Stage 1 question and literature

- Choose the policy the paper is about from `institutional.md`, not the policy with the best data. Confirm the paper's claim concerns that single policy.
- Read `pitfalls.md` under what referees ask and locate the concurrent-policy question. Confirm the answer is drafted before the introduction is written.

## Stage 2 identification

- `measures.md` under constructing the treatment variable lists four definitions. Confirm which one the identification claim rests on, and state it before any estimate appears.
- Read `measures.md` under identification assumptions by definition for the chosen definition. Confirm the assumption is written in the text rather than the appendix.
- `data.md` under known issues covers station siting and satellite estimates. Confirm the exposure measure is defended against the siting objection.

## Stage 3 data

- `data.md` under data sources names monitoring, firm self-reporting, permit records and carbon market transactions. Confirm which of these exist for the study window.
- `data.md` under coverage: confirm the panel spans years on both sides of the policy, and say how many.
- `data.md` under known issues: confirm which listed problems apply here, and say so in the data section rather than in a footnote.

## Stage 4 estimation

- `pitfalls.md` under where it goes wrong discusses clustering. Confirm the clustering level equals the level at which the policy is assigned.
- `measures.md` under common construction errors shows intensity measures. Confirm the estimate survives a change of definition.
- Read the timeline in `institutional.md`. Confirm the event window does not straddle two reforms at once.

## Stage 5 tables and figures

- Put the treatment definition in the table notes, naming the measure from `measures.md`. Confirm a reader can rebuild the variable from the note plus the data appendix.
- Report alternative definitions in one robustness table. Confirm the sign survives every row.
- Plot the event study against the timeline dates. Confirm the x-axis uses the same dates as `institutional.md`.

## Stage 6 report

- `data.md` under known issues: state the measurement year and the source for each variable. Confirm no version numbers and no file names appear.
- Report the exposure construction in a replication appendix. Confirm a coauthor can rebuild it from the appendix alone.

## Stage 7 writing

- Lift the background paragraphs from `institutional.md` under ready-to-cite paragraphs. Confirm the placeholders are replaced and the paragraph names only the policy the paper studies.
- Use the answers in `pitfalls.md` under how to respond as the skeleton of the discussion. Confirm each limitation is stated once, not twice.

## Stage 8 referee response

- `pitfalls.md` under what referees ask is a checklist for the response letter. Confirm every objection has one paragraph of reply.
- For clustering and for concurrent policy, point to the specific table. Confirm the table exists before the letter is sent.
- If a referee proposes a different exposure definition, rerun it as `measures.md` describes and report both. Confirm both definitions are shown side by side.

## The three things most often missed

- The unit of exposure and the unit of the outcome differ, and the paper never says so.
- The concurrent-policy list is asserted rather than written down with dates.
- The clustering level is finer than the level at which the policy is assigned.
