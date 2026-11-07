# Macroeconomics and finance: how to walk the eight stages

## In one sentence
Macro and finance causal work is blocked by the reaction problem: the central bank and the regulator watch exactly the variables you want to explain, so the first job is to find variation they could not see.

## Stage 0 feasibility: three questions to ask first
- Ask what the policy rule is. Read "Institutional background" in `institutional.md` and write down the reaction function, the regulatory indicators, and the operating target, then decide which variation is exogenous.
- Ask about event timing. Read the second "What referees ask" item in `pitfalls.md` and confirm that policy announcements and data releases do not fall on the same day.
- Ask about exposure shares. Read "Constructing the treatment variable" in `measures.md` and check that shares are measured before the shock (to confirm against the official codebook).

## Stage 1 question and literature
- Read "Timeline" in `institutional.md` and align interest-rate liberalisation, the LPR reform, reserve-requirement changes, and revisions of the regulatory indicators.
- Read "Constructing the treatment variable" in `measures.md` and choose among high-frequency surprises, narrative or episode coding, differential exposure to an aggregate shock, and reform dummies.
- Check that the paper you follow defines the policy surprise over the same window as you do; a different window makes the estimates incomparable.

## Stage 2 identification
- For a high-frequency surprise, read the first "Identification assumptions by definition" entry in `measures.md` and argue that no other information enters the window.
- For differential exposure, show that shares are unrelated to outcome levels and only shift sensitivity to the shock.
- For a reform dummy, show that the reform date is unrelated to pre-existing trends of firms or regions.

## Stage 3 data
- Read "Data sources" in `data.md` and separate central-bank and statistical series, aggregated database series, and local debt and house-price data.
- Read "Variables and definitions": fix the definitions of rates, spreads, and leverage, and settle percentage points versus basis points.
- Read "Known issues" and register data revisions, breaks in series, and splicing across regimes.

## Stage 4 estimation
- Use "Common construction errors" in `measures.md`: check whether a market rate has been used as a proxy for the policy rate.
- When the estimate vanishes after controls are added, check whether the control is itself an outcome before calling the result robust.
- Report results under alternative windows and alternative proxies.

## Stage 5 tables and figures
- Build the balance table around the first referee question in `pitfalls.md`: whether policy exogeneity and the exposure shares hold up.
- The event-study figure must mark the announcement date, the window, and the base period.
- State the units of every rate in the main table and their conversion.

## Stage 6 report
- Report the policy rule and how the surprise was identified, following the first "How to respond" item in `pitfalls.md`.
- Report the timing relation between policy announcements and data releases.
- Report how exposure shares were built and which base period they use.

## Stage 7 writing
- Start the institutional section from the "Ready-to-cite paragraphs" in `institutional.md`, and check the names and years of the reform documents.
- Cite institutions, reports, and statistical definitions only; leave page and document numbers for (to confirm against the official codebook).

## Stage 8 referee response
- Prepare the "What referees ask" items in `pitfalls.md`; policy endogeneity, window contamination, and endogenous exposure are the most common.
- When an instrument is challenged as splicing two regimes, use the "compare only within one regime" answer in "How to respond" and add a placebo check.

## The three things most often missed
- Mixing the policy rate and the market rate into one variable.
- Defining a surprise with data released on the same day as the announcement.
- Failing to state the unit conversion, which makes the result unreproducible.
