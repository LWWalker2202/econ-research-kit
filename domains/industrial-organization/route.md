# Industrial organization and regulation: how to walk the eight stages

## In one sentence
Industrial organization studies market structure and firm behaviour, and the hard parts are whether the shares you compute cover the whole market and whether a regulation moved entry and exit at the same time.

## Stage 0 feasibility: three questions to ask first
- Ask how shares are built. Read the passage on concentration as an outcome in "Constructing the treatment variable" of `measures.md`, and check that numerator and denominator cover the same firms.
- Ask about coverage. Read "Coverage" in `data.md` and confirm that the CIED size threshold does not contradict your market definition [verify].
- Ask about timing. Read "Timeline" in `institutional.md` and align the antitrust law, the merger notification thresholds, price liberalisation, and the creation of development zones.

## Stage 1 question and literature
- Read "Institutional background" in `institutional.md` for the four layers of regulation and pick the one you study.
- Read "Constructing the treatment variable" in `measures.md` and match one of the four definitions to your market definition.
- Check that the market boundary in the paper you follow (product, geography, firm) is the one in your data, otherwise the shares are not comparable.

## Stage 2 identification
- For merger-review exposure, read "Identification assumptions by definition" in `measures.md` and justify transactions below the notification threshold as a comparison group.
- For price liberalisation, establish that timing and scope were not set by firm performance.
- For development-zone exposure, show that site selection was unrelated to the outcome trend and cite the approval document under "Sources" in `institutional.md`.

## Stage 3 data
- Read "Data sources" in `data.md` and separate what CIED, customs records, business registrations, listed-firm accounts, and yearbooks each answer.
- Read "Variables and definitions": check whether firm identifiers match across years and which version of the industry classification is used.
- Read "Known issues" and register threshold changes, ownership restructuring, and revisions of the statistical scope.

## Stage 4 estimation
- Concentration is endogenous; read "Common construction errors" in `measures.md` and make sure you are not using the outcome as an exogenous regressor.
- Entry and exit change both shares and aggregates, so report a balanced panel and the full sample side by side.
- Markups and TFP estimates depend on functional form; report at least two specifications.

## Stage 5 tables and figures
- Build the balance table around the first referee question in `pitfalls.md`: what happens to concentration when only above-threshold firms are counted.
- State the market definition in the table note so the reader can judge HHI and CR4 on a comparable basis.
- The event-study figure must show pre-regulation trends and how the treated group was defined.

## Stage 6 report
- Report the market boundary and the firm coverage, following the first "How to respond" item in `pitfalls.md`.
- Report entry and exit of firms and the aggregation basis you used.
- Report the industry-classification version and the cross-year match rate.

## Stage 7 writing
- Start the institutional section from the "Ready-to-cite paragraphs" in `institutional.md`, and get the names of the law and the zone catalogue right.
- Cite laws, catalogues, and yearbooks only; leave page and document numbers for [verify].

## Stage 8 referee response
- Prepare the "What referees ask" items in `pitfalls.md`; the CIED threshold change and the classification revision are the two that come back most often.
- When the market definition is contested, answer with the alternative-definition results in "How to respond" and add a robustness table.

## The three things most often missed
- Using above-threshold firms to represent concentration in the whole market.
- Ignoring how entry and exit move the aggregate.
- Reading a classification-version change as a real change in specialisation.
