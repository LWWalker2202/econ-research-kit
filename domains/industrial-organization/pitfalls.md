# Industrial organization and regulation: referee pitfalls

Papers in this field are refereed above all on measurement: whether the concentration or markup variable measures what the paper says, and whether the policy that supplies the variation is separable from the market cycle that supplies the rest of it. The questions below are phrased the way referees phrase them in reports. Each is followed by the move that answers it, not by the paragraph that dodges it.

## What referees ask

1. Your HHI is computed on firms above a survey threshold. How much of the measured concentration is an artefact of that threshold, and what happens to your conclusion when the threshold moves?
2. Markup is a ratio of price to marginal cost that you never observe. Which production-function assumption is doing the identifying work here, and do you get the same answer under gross output and under value added?
3. The merger cases you observe are the ones that were notified. What does selection into notification do to the price effects you estimate?
4. Your treatment is a capacity-reduction target issued in the same year that steel prices collapsed. How do you separate the policy from the commodity cycle?
5. Zone designation is not random. Which growth trends were already under way in the places that received a zone?
6. You match the industrial survey to customs records. What is the match rate, and is it correlated with firm size or with trade regime?
7. Your industry is a four-digit code, but the merging parties compete in a narrower product market. Why is your HHI the relevant measure of concentration?
8. Exit in your data means that a firm disappears from a size-thresholded database. How do you distinguish death from falling below the threshold?
9. Entry liberalization was national, and your identifying variation is differential exposure across industries. What makes that exposure predetermined?

## How to respond

1. State the coverage rule for every year, show the HHI computed on the constant-coverage subsample, and report the bound implied by the firms you cannot observe. If the conclusion flips when the sample is held at constant coverage, that is the result to report.
2. Report the markup under at least two specifications that differ in what is assumed: gross output versus value added, and a cost-share elasticity versus an estimated elasticity. If the two disagree, say which assumption the headline number relies on and why it is defensible for these firms.
3. Model the notification decision: estimate whether notification probability is related to observable market characteristics, and either reweight to the population of concentrations or restrict the claim to reviewed cases. Also report the share of cases that were cleared unconditionally, because they carry no treatment variation.
4. Add industry-by-year fixed effects so that the comparison is within the same product market, control for output prices at the product level, and show a placebo on industries that were not assigned targets. The capacity target has to be shown to bind on capacity rather than on demand.
5. Show pre-designation trends by cohort of designation year for entry, output, and land prices. If zones were placed on already-growing counties, use the boundary discontinuity: compare firms just inside and just outside the zone boundary.
6. Report the match rate by firm-size decile and by trade regime, and reweight or restrict. Match on a unique identifier where one exists, and validate the matched sample against aggregate trade and output totals.
7. Justify the market definition with a substitutability argument or with price co-movement across products, and show that the results survive a narrower market definition. The industry code is a fallback, not a definition.
8. Use registry deregistration and revocation dates to identify genuine death, report the share of disappearances that are threshold crossings, and show the exit results under both definitions.
9. Show that exposure is a function of pre-period industry characteristics, not of contemporaneous performance, and run the event study with leads. If exposure was revised in the light of industry performance, the design has to use the earliest version of the list.

## Where it goes wrong

| Failure | What the referee sees | What to do instead |
|---|---|---|
| HHI series compared across a sample-threshold change | A break in concentration at the threshold date that looks like a competition effect | Hold coverage constant or reweight to the registry universe, and report the break explicitly |
| Markup estimated as output value divided by cost, with no production function | A rent measure that moves with the price deflator | Estimate the elasticity, report the assumptions, and show the accounting markup as a robustness check |
| Only notified merger cases used, treated as a random sample | Price effects estimated on the transactions that were expected to raise prices | Model notification, reweight, or restrict the claim to reviewed cases |
| Exit measured as disappearance from the firm panel | A survivorship story in which policy is credited with reallocation | Use deregistration records and report the share of threshold crossings |
| Capacity reduction used as a competition-policy treatment | A market-structure effect that is really an environmental or industrial-policy effect | Control for the environmental layer or move the policy to the treatment and hold structure as the outcome |
