# Economic history: what referees ask, and where it goes wrong

Referees in this field are usually not asking whether the identification strategy is clever. They are asking whether the document you turned into a variable says what you think it says, and whether the units you compare are the same thing over time. The questions below are the ones that recur, in roughly the order they arrive.

## What referees ask

1. How was your sample of ports, counties, or firms selected, and what does the selection do to the estimate?
2. Where is the coding manual for the text-derived variable, and what is the agreement between the two coders?
3. How did you convert nineteenth-century silver into a comparable unit, and what happens to the result under another conversion?
4. How do you know the quota or entitlement you use as treatment was not revised in response to the outcome?
5. Did the county boundaries change over your window, and how did you match historical counties to the units in your panel?
6. How much of your variable comes from OCR, and what did you do about errors in the numbers?
7. Is the opening date of a port a diplomatic event or an economic one?
8. Which version of the gazetteer did you use, and was it a revised edition?
9. What does the plan-era record measure: entitlement, issuance, or actual consumption?
10. If the referee re-coded a random sample of your documents, would they get the same variable?

## How to respond

1. Report the construction rule for the sample, count what was excluded and why, and show the main result on the narrower sample that the rule can be defended for. If the sample is defined by survival of a document, say so and show whether the surviving units differ from the others on observables that are available for both.
2. Attach the coding manual as an appendix, code a random subsample twice, report the agreement measure, and state how disagreements were adjudicated. If only one coder did the work, say so and show the sensitivity of the result to the ambiguous cases.
3. State the conversion in a table note, cite the exchange or price series used, and report the main coefficient under at least one alternative numeraire. A conversion that changes the sign or the significance has to be discussed, not hidden in a footnote.
4. Show the editions of the quota source that span your window and demonstrate that the quota was unchanged over the relevant interval; if it was revised, restrict to the interval after the last revision or use the revision as the event.
5. Provide the correspondence table between historical and modern units, name the historical geography source, and show that the result is not driven by the units whose boundaries changed.
6. Describe the transcription and checking protocol, report the estimated error rate on a verified subsample, and show the main result after correcting the cases that were checked. Where the source itself is ambiguous, report the alternative coding.
7. Show that opening dates are dated by treaty or by the establishment of the customs house, not by trade volume, and test whether the opening date predicts pre-opening trade growth. If early openings were already the fastest-growing ports, restrict to openings that are plausibly unrelated to trade conditions.
8. Name the edition and the year it was compiled, and check whether its figures are copied from an earlier edition. When two editions disagree, report both and treat the disagreement as measurement error rather than choosing the convenient one.
9. State which margin the record captures, triangulate with a second source where one exists, and restrict claims about consumption to the periods and places where the two sources can be reconciled.
10. Make the reproduction path explicit: the raw transcription, the cleaning script, and the variable definition should let an independent reader rebuild the variable. Report the number of records checked and the disagreements resolved, with the unresolved ones listed.

## Where it goes wrong

| Error | Consequence | Correct approach |
|---|---|---|
| Building the panel from whatever documents survived, then treating it as the population | Survivors are larger, more commercial, and better connected, so the coefficient describes the documented units rather than the institution | State the selection rule, compare survivors with available non-survivors, and bound the result |
| Comparing prices or wages across centuries with a single modern index | The index has no pre-modern base, so the comparison imports a modern basket | Use a silver or grain numeraire for the early period and report more than one conversion |
| Treating the text-derived variable as objective because it is coded from a document | The variable measures the coder's reading as much as the event, and the estimate is not replicable | Code a subsample twice, report agreement, and publish the manual and the adjudication rule |
| Using a county-level source without checking boundary changes | The wrong territory is assigned and the coefficient mixes real effects with place effects | Match through historical administrative geography and show the correspondence |
| Reading plan-era quantities as consumption | Entitlement, issuance, and consumption differ, and informal exchange is missing from the record | State which margin is measured and reconcile the record with a second source |
