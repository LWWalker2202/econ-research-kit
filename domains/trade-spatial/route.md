# International trade and spatial economics: how to walk the eight stages

## In one sentence
Trade and spatial work both rest on exposure: how hard a place was hit by tariffs, import competition, market access, or a pilot policy, and how that exposure is measured decides the identification.

## Stage 0 feasibility: three questions to ask first
- Ask how exposure maps. Read "Constructing the treatment variable" in `measures.md` and check that industry-level tariffs or imports can be weighted down to regions in a defensible way.
- Ask whether the data join. Read "Data sources" in `data.md` and confirm that customs records, CIED, and city yearbooks can be linked on the same year and code.
- Ask about the spatial unit. Read the fourth and fifth "What referees ask" items in `pitfalls.md`; boundary changes and distance measures can break the panel.

## Stage 1 question and literature
- Read "Timeline" in `institutional.md` and align WTO accession, pilot free trade zones, cross-border e-commerce pilot zones, high-speed rail, and the Belt and Road; they are not one treatment.
- Read "Identification assumptions by definition" in `measures.md` and decide between tariff exposure, shift-share import competition, market access, and zone designation.
- Check that the exogeneity argument for the shares in the paper you follow matches yours, especially the choice of the base year.

## Stage 2 identification
- For tariff exposure, argue that the tariff cut was external and cite the tariff schedule and accession documents under "Sources" in `institutional.md`.
- For a shift-share design, show that the shares are measured before the shock and are not driven by contemporaneous outcomes.
- For market access, establish that transport-network changes were not a response to trade activity.

## Stage 3 data
- Read "Data sources" in `data.md` and state what customs records, CIED, yearbooks, night lights, CEPII-BACI, and timetables each contribute.
- Read "Variables and definitions": check whether trade values are in dollars or renminbi, FOB or CIF, and which version of the region code is used.
- Read "Known issues" and register the matching rate between customs and firm data, the mixing of processing and ordinary trade, and boundary changes.

## Stage 4 estimation
- Spatial autocorrelation makes standard errors too small; use "Common construction errors" in `measures.md` to check the clustering level and the spatial weights.
- Processing and ordinary trade carry different exposure; estimate them separately rather than pooling.
- Report results under alternative weights (industry share, employment share, base year) and say whether the sign holds.

## Stage 5 tables and figures
- Build the balance table around the high-speed-rail siting and free-trade-zone questions in `pitfalls.md`.
- Maps and scatter plots should state the spatial weights so the reader can judge spillovers and displacement.
- Report the exposure measure and the source of weights in the main table.

## Stage 6 report
- Report how exposure was mapped and why those weights were chosen, following the first "How to respond" item in `pitfalls.md`.
- Report the spillover and displacement checks, for example what happened in neighbouring places.
- Report how boundary changes were handled and which observations they affected.

## Stage 7 writing
- Start the institutional section from the "Ready-to-cite paragraphs" in `institutional.md`, and check the names and years of the accession and zone documents.
- Cite documents, yearbooks, and database names only; leave page and document numbers for [verify].

## Stage 8 referee response
- Prepare the "What referees ask" items in `pitfalls.md`; share exogeneity, spatial standard errors, and light saturation are the three that come back most often.
- When displacement is raised, answer with the neighbouring-place check in "How to respond" and report robustness over spatial scopes.

## The three things most often missed
- Pooling processing and ordinary trade in one exposure measure.
- Building a shift-share measure from contemporaneous shares without stating the base year.
- Ignoring how boundary changes break panel continuity.
