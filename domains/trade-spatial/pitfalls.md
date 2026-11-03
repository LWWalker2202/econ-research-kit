# International Trade and Spatial Economics: Pitfalls

## What referees ask

1. "Your shift-share measure uses industry shares from the first year of your panel. Why are those shares exogenous to the trade shock that arrives afterwards, and what happens to the estimate if you move the base year back by five years?"
2. "The shock in your design is import growth by industry. Is that shock as-if randomly assigned across industries, or is the identifying variation really coming from the shares? Which of the two claims is the paper making?"
3. "You cluster at the city level, but tariff shocks are correlated across neighbouring cities in the same province. What do Conley standard errors with a distance cutoff give you, and how did you choose the cutoff?"
4. "High-speed rail stations are not placed at random. Your treatment is the travel-time change. What ensures that the places whose travel time fell were not already growing faster before the line opened?"
5. "Nighttime light is saturated in the centre of large cities and spills over into rural counties. Does your light measure capture economic activity, electrification, or the reclassification of land?"
6. "Several of your cities absorbed neighbouring counties during the sample period. Are your city boundaries constant, and are your population and output series built on the same boundary in every year?"
7. "Your customs data mix processing trade and ordinary trade. Since processing imports entered duty-free, how is the tariff exposure of a processing firm defined in your measure?"
8. "The treatment is at the product level and the outcome is at the city level. What is the exposure mapping, and was it fixed before you looked at the outcome?"
9. "Pilot free trade zones were given to the largest coastal cities. What is the counterfactual for those cities, and how do you rule out that the coefficient captures the pre-existing growth of a port?"
10. "If the rail line moves activity from one city to its neighbour, your control group is contaminated. What does your coefficient identify, creation or displacement?"

## How to respond

1. Report the base-year sensitivity table rather than argue one base year is right. Move the base year to the earliest census, to the year before accession, and to the year before the domestic liberalization wave, and show whether the sign and magnitude survive. If the estimate collapses when the base year moves back, the measure is detecting pre-existing trends and the paper should say so.
2. State the claim explicitly and test the one you made. In the shares route, test for pre-trends across share deciles and show the shares are balanced on pre-period observables. In the shocks route, show that the industry shocks are not driven by one industry or one partner, and run the leave-one-industry-out exercise. A paper that does both is more convincing than a paper that asserts either.
3. Report both clustering schemes, and add a spatial correction. Conley standard errors with a cutoff chosen from the distance at which residuals stop being correlated is the defensible version; report the autocorrelation function so the cutoff is visible. With few treated cities, add randomization inference that reassigns exposure across cities.
4. Show the pre-trend by distance to the corridor line, and use a design that compares places near the line with places farther from it rather than cities on the line with cities off it. Route plans that were fixed before the outcome window, and terrain and corridor-engineering cost, are useful conditioning variables. If the pre-trend is present, say whether it is anticipation of the line or a separate trend in the region.
5. Cross-calibrate the two sensors and report results with light as a control rather than as the outcome, or restrict the outcome window to one sensor. Report the estimates at several saturation thresholds, and check whether the result survives when the largest city centres are dropped, because that is where saturation is worst.
6. Rebuild the panel on constant boundaries: use the earliest boundary for the whole period, or aggregate boundary-changed counties to the larger unit consistently in every year, and report the number of units affected. Publish the code history file as part of the replication package, because boundary changes are the one adjustment a reader cannot verify from the paper.
7. Split the sample by trade mode, or rebuild the exposure measure on ordinary trade only, and report the processing share by city and year. If the result holds only when processing trade is included, the mechanism cannot be the tariff, because processing imports were not paying it.
8. State the mapping before the estimates: employment shares, output shares, or input-output linkages each define a different treatment. Report the results under more than one mapping, and say which one the text adopts. A mapping chosen after looking at the results will not survive review.
9. Use the shortlisted-and-losing cities or a matched control group built on pre-period port throughput, foreign investment, and growth, and report coefficient stability across matching specifications. Also report the event study with a long enough pre-period that the port trend would be visible if it were there.
10. Report the estimate with and without neighbouring cities in the control group, and with a distance gradient. If the coefficient shrinks when neighbours are excluded and grows in the ring, the design is capturing displacement, and the paper should estimate the net effect over a wider market rather than a city-level effect.

## Where it goes wrong

| Problem | What you see in the output | Fix |
|---|---|---|
| Weights taken from the year the shock starts | A large, precisely estimated effect that disappears when the base year is moved back | Fix weights in a pre-period year and show the sensitivity table |
| Tariff exposure built on all imports, including processing | The estimated response is too large for the aggregate and too small for processing firms | Split by trade mode and report the exposure measure separately |
| Binary treatment of a rail or zone without a spillover ring | The coefficient flips sign when neighbouring cities are added to the control group | Include a distance gradient and estimate the effect over a market that contains the spillover |
| Travel time measured from straight-line distance | Attenuated estimates with implausibly large standard errors at the edges of the network | Use timetable travel time, and keep straight-line distance as a robustness check |
| Light used as the only outcome across the sensor change | A level jump at the year the sensor changes, read as a policy effect | Cross-calibrate, or restrict the window to one sensor, and use light as a control elsewhere |
| City panel built on current administrative codes | Population and output jump in the year of a merger and the jump is attributed to the policy | Rebuild on constant boundaries and publish the code history |
