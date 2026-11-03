# Public economics: how to walk the eight stages

## In one sentence
Public economics asks where the money comes from and where it goes, and whether the fiscal rule you study was exogenous to the outcomes you measure.

## Stage 0 feasibility: three questions to ask first
- Ask where the variation comes from. Read "Institutional background" in `institutional.md` on tax sharing and intergovernmental transfers, and decide whether the usable part is formula-driven or locally discretionary.
- Ask whether the numbers line up. Read "Data sources" in `data.md` and check whether budget and extra-budget figures, city totals and districts, announced and executed amounts share a basis.
- Ask about endogeneity. Read the third "What referees ask" item in `pitfalls.md`; if transfers respond to outcomes, the design must change before the data work.

## Stage 1 question and literature
- Read "Timeline" in `institutional.md` and align the tax-sharing reform, the income-tax sharing change, and the transfer reforms; do not compare across regimes.
- Read "Constructing the treatment variable" in `measures.md` and decide which of its five constructions your question uses.
- Check that the fiscal concept in the paper you follow matches the budget line in your data, especially general versus earmarked transfers.

## Stage 2 identification
- For a transfer shock, read the first "Identification assumptions by definition" entry in `measures.md` and state which parts of the formula are unrelated to your outcome.
- For pilot status, show that selection does not coincide with an outcome trend, and cite the pilot document from "Sources".
- For a tax-sharing measure, establish whether the rate was changed centrally or decided locally.

## Stage 3 data
- Read "Data sources" in `data.md`: finance yearbooks, county yearbooks, published budgets, and survey data serve different purposes and should be described separately.
- Read "Variables and definitions": budget and final accounts are different series, and debt issuance is not the debt stock.
- Read "Known issues" and register the gap between the announced and executed year, plus changes in budget classification.

## Stage 4 estimation
- Per-capita fiscal variables are volatile in small counties; check "Common construction errors" in `measures.md` before scaling by population.
- When several policies land in one county, control for the others or use a non-overlapping subsample, and say so.
- Report the estimate with and without controls: a coefficient that moves a lot signals omitted variables.

## Stage 5 tables and figures
- Build the balance table around both referee questions in `pitfalls.md`: whether transfers respond to the tax base and whether pilots select in.
- State whether fiscal variables enter in logs or levels, and do not mix growth rates with levels.
- Report the fiscal concept and source year in the main table so the reader knows whether it is a budget or a final-accounts number.

## Stage 6 report
- Report the allocation formula and how far execution departed from it, following the first "How to respond" item.
- Report how the fiscal items move together and state which link you estimate.
- Report how you treated the announcement year versus the execution year.

## Stage 7 writing
- Start from the "Ready-to-cite paragraphs" in `institutional.md`, then check each year and document name.
- Cite documents and issuing bodies only; leave page and document numbers for [verify].

## Stage 8 referee response
- Work through the ten "What referees ask" items, preparing first for overlapping policies and coefficient attribution.
- When transfers are challenged as endogenous, use the "formula-driven versus discretionary" answer and add a placebo check.

## The three things most often missed
- Mixing budget and extra-budget spending in one variable.
- Using the announcement year as the year the policy took effect.
- Ignoring the other fiscal policies running in the same county.
