# Theory and mechanism design: how to walk the eight stages

## In one sentence

There is no regression treatment here, only the forcing variable of the model, and the paper is empirical to the extent that each assumption maps to an observable counterpart that could reject it.

## Stage 0 feasibility: three questions to ask first

- Does every parameter that drives the result have an observable counterpart, or is one of them a free dial? Read `measures.md` under constructing the treatment variable. Confirm the mapping before writing the calibration.
- Are there at least as many independent moments as parameters, and does each moment actually move with its parameter? Read `measures.md` under identification assumptions by definition. Confirm the sensitivity, not just the count.
- Does the policy instrument in the model exist in the institutional setting the paper describes? Read `institutional.md` under institutional background. Confirm the instrument and the commitment assumption before writing the welfare section.

## Stage 1 question and literature

- Locate the paper's mechanism relative to the nested standard model. Read `pitfalls.md` under what referees ask, which asks what a new friction changes. Confirm the new prediction is stated, not just the new assumption.
- Read `institutional.md` under institutional background for the institutional facts the model takes as given. Confirm each one is cited rather than asserted.

## Stage 2 identification

- `measures.md` under constructing the treatment variable lists six model objects: instrument intensity, information friction, commitment, bargaining weight, preferences, technology. Confirm which one carries the comparative static.
- Read `measures.md` under identification assumptions by definition for the calibration discipline. Confirm the calibration moments are disjoint from the moments used to test the model.
- Write the statement of what would falsify the mechanism. Confirm it names an observable, not a direction of the coefficient alone.

## Stage 3 data

- `data.md` under data sources covers national accounts, fiscal statistics, firm registries and household panels. Confirm the moment is computed on the same population the model describes.
- `data.md` under known issues states how prices, base years and deflators enter. Confirm nominal and constant-price quantities are not mixed in one moment.

## Stage 4 estimation

- Report convergence diagnostics, grid refinement and multiple starting points. Confirm each is in the replication record, not just in an email.
- Prove uniqueness, or state the selection rule and defend it with the institution. Confirm the comparative static names the equilibrium it refers to.
- Check the sign over the whole admissible parameter interval. Confirm the interval comes from several studies, not one.

## Stage 5 tables and figures

- Put the calibration table and the moment-to-parameter map next to each other. Confirm a reader can see which moment identifies which parameter.
- Report sensitivity of the main result to movement within the literature interval. Confirm the table shows the sign and not only the magnitude.

## Stage 6 report

- Record numerical inputs, tolerances and starting values in the replication record. Confirm the record is enough to rerun the solution from an empty folder.
- Report the welfare calculation relative to a feasible allocation. Confirm the resource and budget constraints are checked in the solution.

## Stage 7 writing

- State the sufficient conditions for each proposition in the text. Confirm the appendix does not carry the only statement of them.
- Use `institutional.md` under ready-to-cite paragraphs for the setting. Confirm the paragraph describes the institutions the model actually assumes.

## Stage 8 referee response

- `pitfalls.md` under what referees ask gives ten questions; treat them as the reading order for revision. Confirm each has a paragraph.
- For the calibration defence, report the range and the sensitivity rather than the plausibility. Confirm both appear.
- For the uniqueness objection, either prove it under stated conditions or write down the selection rule. Confirm it is one of these two, not a verbal reassurance.

## The three things most often missed

- An estimated reduced-form coefficient is presented as a structural parameter, so it cannot support a counterfactual.
- The moments used to calibrate are the same moments later presented as evidence the model fits.
- The comparative-static sign is reported only at the midpoint of the admissible range, where it may differ from the ends.
